# Guía del laboratorio

## 1. Empresa ficticia

El proyecto incluye perfiles de referencia en [fichas empresariales](fichas-empresariales%28tabla%29.md).
Se puede elegir Best Games, EcoNova o DigitalSoft para comenzar el ejercicio.
Las tres fichas empresariales sin procesar están disponibles en el catálogo.

Hay un informe individual en PDF para cada empresa en la carpeta
[`reports/`](../reports/).
La correspondencia de los archivos de captura recibidos está documentada en el [registro de capturas](registro-capturas%20de%20red.md); los binarios deben permanecer fuera
del repositorio.
Los parámetros de AP y cliente desautenticado están en [parametros de las redes](parametros%20de%20las%20redes.md).
Las especificaciones de equipo anfitrión, la máquina virtual Kali y la interfaz `wlan1` están
documentados en [especificaciones de hardware y software para el laboratorio](especificaciones%20de%20hardware%20y%20software%20para%20el%20laboratorio.md).

Crear una ficha sin nombres, fechas, teléfonos ni datos personales reales. Debe
contener información suficiente para que el ejercicio sea reproducible, pero la
contraseña no debe aparecer publicada de forma directa. Puede contener:

| Campo | Ejemplo |
| --- | --- |
| Empresa | TucumanTech |
| Rubro | Desarrollo de software |
| Fundación | 2021 |
| Fundador ficticio | Marcos Diaz |
| Ciudad ficticia | Tucuman |
| Producto | Sentinel |
| Mascota | Tuki |
| Eslogan | Tecnologia que protege |

## 2. Contraseña de prueba

La contraseña debe tener exactamente ocho caracteres, incluir letras y números, no
contener espacios y estar relacionada con la empresa.

No se aceptan contraseñas completamente aleatorias, demasiado obvias, iguales al
SSID o basadas en información real. Ejemplos didácticos correctos: `Tuki2021`, `TucuTech`,
`Sent2021` y `MarDia21`.

## 3. Punto de acceso

Configurar un hotspot dedicado al laboratorio con estos criterios:

- WPA2-Personal, cuando el dispositivo lo permita.
- WPA3 o modo mixto desactivado durante la práctica, si es posible.
- Banda de 2,4 GHz por compatibilidad con el hardware del laboratorio.
- SSID basado en la empresa ficticia.
- Al menos un dispositivo de prueba conectado.

Ejemplo: SSID `TucumanTech`, WPA2-Personal, banda de 2,4 GHz.

## 4. Metodología

### Reconocimiento

Registrar SSID, BSSID, canal, cifrado y clientes conectados usando la herramienta
de monitorización autorizada.

### Captura

Capturar tráfico únicamente del BSSID y canal definidos para la práctica. Obtener el handshake o PMKID mediante una reconexión manual siempre que sea posible. Si se
usa desautenticación controlada, debe ser breve y dirigida a un dispositivo propio.

### Diccionario

Partir de las palabras del perfil ficticio y documentar las reglas usadas para
generar combinaciones de ocho caracteres. Filtrar duplicados y conservar el
diccionario exacto utilizado en la evidencia. Consultar la [documentación de
diccionarios](Diccionarios.md) y la sección de validación del reporte HTML
correspondiente.

### Validación

Probar la captura con Aircrack-ng o convertirla al formato compatible con Hashcat.
Registrar el comando, la herramienta, el tiempo y el resultado sin publicar
credenciales fuera del entorno de evaluación. La distribución de tareas de la suite Aircrack-ng entre
la máquina anfitriona y la VM está descrita en las [especificaciones de
hardware y software](especificaciones%20de%20hardware%20y%20software%20para%20el%20laboratorio.md).

## 5. Evidencias

Completar [la plantilla de evidencias](../templates/evidencia.md) para cada red.
Las capturas, archivos `.cap`, `.pcapng`, `.22000` y diccionarios deben permanecer
fuera del repositorio o en un almacenamiento privado.

## 6. Cierre técnico

El análisis mostró que la información asociada a la empresa ficticia permitió
construir un diccionario contextualizado y reducir el espacio de búsqueda de la
credencial. La captura del handshake y su validación con el diccionario de
prueba demostraron que una contraseña corta, predecible o relacionada con datos
del perfil empresarial ofrece una resistencia insuficiente frente a un ataque
offline. El resultado no implica acceso a redes reales ni permite extrapolarlo a
otras redes sin evaluar su configuración y sus credenciales.

La mitigación recomendada es utilizar contraseñas largas, aleatorias y únicas,
evitar datos del nombre o actividad de la organización, activar WPA3 cuando sea
compatible, rotar las credenciales con una política definida y separar la red
de invitados de los sistemas internos. La evidencia debe conservar el comando,
la herramienta, el tiempo y el resultado de forma reproducible, pero no debe
publicar la credencial recuperada, los diccionarios completos ni las capturas de
red.