# Diccionarios personalizados

Para cada empresa se generó un diccionario contextualizado a partir de las
palabras y fechas de su ficha ficticia. El procedimiento no es fuerza bruta
exhaustiva: genera candidatos de ocho caracteres mediante patrones de letras y
números, lo que reduce el espacio de búsqueda frente a todas las combinaciones
posibles.

El objetivo documentado es producir **10 millones de candidatos por empresa**. Los diccionarios y las capturas se conservan fuera del repositorio;
aquí solo se documentan el método y la evidencia.

## Criterios

- Longitud exacta de ocho caracteres.
- Al menos una letra minúscula, una mayúscula y un dígito.
- Palabras y números derivados exclusivamente de la ficha ficticia.
- Un archivo independiente para DigitalSoft, EcoNova y Best Games.
- La salida debe revisarse antes de una prueba formal.

## Generador

El siguiente código corrige la configuración del objetivo, la normalización de
acentos y el cierre de la cadena final. También deja explícito que el contador
representa líneas candidatas generadas.

```python
import unicodedata

EMPRESA_ACTUAL = "digitalsoft"
TARGET_CANDIDATOS = 10_000_000

DATOS_EMPRESAS = {
    "digitalsoft": {
        "palabras": ["Digi", "Soft", "Enzo", "Gomez", "Salta", "Landing", "Page", "Doki", "Solucion", "Cliente"],
        "numeros": ["2020", "2022", "0211", "2026", "02", "11", "20", "22", "07"],
        "archivo": "diccionario_digitalsoft_10m.txt",
    },
    "econova": {
        "palabras": ["Eco", "Nova", "Tech", "Bottle", "Sustentable", "Martin", "Gonzalez", "Buenos", "Aires", "Nubi"],
        "numeros": ["2022", "0506", "506", "2026", "123", "20", "22", "05", "06", "01"],
        "archivo": "diccionario_econova_10m.txt",
    },
    "bestgames": {
        "palabras": ["Best", "Game", "Juan", "Perez", "Tucuman", "Cyber", "Punk", "Night", "City", "Tuki", "Beta", "Jam"],
        "numeros": ["2010", "1970", "2077", "2026", "0907", "1209", "2208", "1111", "2207", "1982"],
        "archivo": "diccionario_bestgames_10m.txt",
    },
}


def quitar_acentos(texto):
    normalizado = unicodedata.normalize("NFD", texto)
    return "".join(
        caracter
        for caracter in normalizado
        if unicodedata.category(caracter) != "Mn"
    )


config = DATOS_EMPRESAS[EMPRESA_ACTUAL]
tokens = []
for palabra in config["palabras"]:
    limpia = quitar_acentos(palabra)
    tokens.extend((limpia.lower(), limpia.capitalize(), limpia.upper()))

contador = 0
print(
    f"[+] Generando {TARGET_CANDIDATOS:,} candidatos para "
    f"'{EMPRESA_ACTUAL}'...",
    flush=True,
)

with open(
    config["archivo"],
    "w",
    encoding="ascii",
    buffering=1024 * 1024 * 5,
) as archivo:
    while contador < TARGET_CANDIDATOS:
        for t1 in tokens:
            for t2 in tokens:
                for numero in config["numeros"]:
                    patrones = (
                        t1[:2] + numero[:2] + t2[:4],
                        t1[:4] + numero[:2] + t2[:2],
                        t1[:3] + numero[:3] + t2[:2],
                        numero[:2] + t1[:6],
                    )
                    for candidato in patrones:
                        candidato = candidato[:8]
                        if (
                            len(candidato) == 8
                            and any(caracter.islower() for caracter in candidato)
                            and any(caracter.isupper() for caracter in candidato)
                            and any(caracter.isdigit() for caracter in candidato)
                        ):
                            archivo.write(candidato + "\n")
                            contador += 1
                            if contador % 1_000_000 == 0:
                                print(
                                    f"[+] Progreso: {contador:,} líneas",
                                    flush=True,
                                )
                            if contador >= TARGET_CANDIDATOS:
                                break
                    if contador >= TARGET_CANDIDATOS:
                        break
                if contador >= TARGET_CANDIDATOS:
                    break
            if contador >= TARGET_CANDIDATOS:
                break

print(
    f"[!] Archivo '{config['archivo']}' creado "
    f"({contador:,} líneas)."
)
```

## Ejecución

```text
python3 generador10m.py
[+] Generando 10,000,000 candidatos para 'digitalsoft'...
[+] Progreso: 1,000,000 líneas
...
[!] Archivo 'diccionario_digitalsoft_10m.txt' creado (10,000,000 líneas).
```
