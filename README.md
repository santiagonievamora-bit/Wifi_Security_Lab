# WiFi Security Lab

Laboratorio educativo para analizar la seguridad de redes WiFi ficticias mediante OSINT, generación de diccionarios y verificación controlada de credenciales.

> **Aviso de autorización**
> Todo el trabajo debe realizarse únicamente sobre redes, dispositivos y datos
> creados para esta actividad. No se permite probar redes cercanas ni información
> personal real.

## Objetivos

- Identificar SSID, BSSID, canal y tipo de cifrado.
- Construir un perfil OSINT de una empresa ficticia.
- Generar un diccionario personalizado de ocho caracteres.
- Capturar un handshake o PMKID dentro del entorno autorizado.
- Validar la contraseña y documentar el resultado técnico.
- Proponer una mejora de seguridad basada en los hallazgos.

## Estructura

```text
.
├── docs/
│   ├── laboratorio.md       # Consigna, fases y metodología
│   └── fichas-empresariales.md # Perfiles ficticios para el ejercicio
├── templates/
│   └── evidencia.md         # Plantilla para registrar cada objetivo
├── .gitignore
└── README.md
```

## Inicio rápido

1. Leer la [guía del laboratorio](docs/laboratorio.md).
2. Elegir una ficha de [empresas ficticias](docs/fichas-empresariales.md) y crear una red completamente ficticia.
3. Registrar el trabajo en una copia de [la plantilla de evidencias](templates/evidencia.md).
4. Guardar capturas y artefactos locales fuera del repositorio.
5. Revisar que no haya datos reales antes de compartir cambios.

## Alcance

Se permiten el reconocimiento de la red del laboratorio, la captura de tráfico
802.11, la captura de handshake o PMKID, la creación de diccionarios y las
pruebas de diccionario controladas con herramientas como Aircrack-ng, Hashcat y
Wireshark.

No se permiten ataques contra redes o dispositivos ajenos, cambios de contraseña
durante la actividad, listas masivas como estrategia inicial ni desautenticaciones
continuas o indiscriminadas.

## Resultado esperado

Cada entrega debe incluir una descripción reproducible del procedimiento, evidencias
técnicas sin información sensible, la relación entre la contraseña y la empresa
ficticia, el tiempo aproximado y una recomendación de seguridad.

## Licencia

Este repositorio está destinado a fines educativos. Añade una licencia antes de
publicarlo si el proyecto se distribuirá fuera del entorno de clase.

