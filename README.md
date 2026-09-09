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
│   ├── laboratorio.md                                      # Consigna, fases y metodología
│   ├── fichas-empresariales(tabla).md                     # Perfiles ficticios para el ejercicio
│   ├── registro-capturas de red.md                        # Asociación y estado de los handshakes
│   ├── parametros de las redes.md                         # AP, BSSID y cliente propios ficticios
│   └── especificaciones de hardware y software para el laboratorio.md # Equipo anfitrión, VM y wlan1
├── reports/
│   ├── informe-best-games.pdf       # Informe individual en PDF
│   ├── informe-econova.pdf          # Informe individual en PDF
│   └── informe-digitalsoftware.pdf  # Informe individual de DigitalSoft
├── templates/
│   └── evidencia.md         # Plantilla para registrar cada objetivo
├── .gitignore
└── README.md
```

## Inicio rápido

1. Leer la [guía del laboratorio](docs/laboratorio.md).
2. Elegir una ficha de [empresas ficticias](docs/fichas-empresariales%28tabla%29.md) y crear una red completamente ficticia.
3. Registrar el trabajo en una copia de [la plantilla de evidencias](templates/evidencia.md).
4. Guardar capturas y artefactos locales fuera del repositorio.
5. Revisar que no haya datos reales antes de compartir cambios.

El hardware y el entorno de ejecución están documentados en
[especificaciones de hardware y software para el laboratorio.md](docs/especificaciones%20de%20hardware%20y%20software%20para%20el%20laboratorio.md), incluida la interfaz
`wlan1`, su chipset y la configuración de Kali en VirtualBox.

## Informes

Los informes individuales están disponibles en [Best Games](reports/informe-best-games.pdf),
[EcoNova](reports/informe-econova.pdf) y [DigitalSoft](reports/informe-digitalsoftware.pdf).
Sus fuentes HTML editables están en la misma carpeta. Los PDFs contienen el
procedimiento, comandos corregidos, campos de evidencia y análisis de riesgos.

## Alcance

Se permiten el reconocimiento de la red del laboratorio, la captura de tráfico
802.11, la captura de handshake o PMKID, la creación de diccionarios y las
pruebas de diccionario controladas con herramientas como Aircrack-ng, Hashcat y
Wireshark.

No se permiten ataques contra redes o dispositivos ajenos, cambios de contraseña durante la actividad, listas masivas como estrategia inicial ni desautenticaciones
continuas o indiscriminadas.

## Resultado esperado

Cada entrega debe incluir una descripción reproducible del procedimiento, evidencias
técnicas sin información sensible, la relación entre la contraseña y la empresa
ficticia, el tiempo aproximado y una recomendación de seguridad.


