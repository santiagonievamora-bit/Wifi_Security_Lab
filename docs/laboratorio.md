# Guía del laboratorio

## 1. Empresa ficticia

El proyecto incluye perfiles de referencia en [fichas empresariales](fichas-empresariales.md).
Se puede elegir Best Games o EcoNova para comenzar el ejercicio. La ficha de
DigitalSoftware está pendiente de transcripción porque el adjunto recibido no
incluye texto legible suficiente.

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

La información puede compartirse en un documento, tablero o perfil ficticio creado
exclusivamente para el ejercicio.

## 2. Contraseña de prueba

La contraseña debe tener exactamente ocho caracteres, incluir letras y números, no
contener espacios y estar relacionada con la empresa. No debe publicarse antes de
la evaluación.

No se aceptan contraseñas completamente aleatorias, demasiado obvias, iguales al
SSID o basadas en información real. Ejemplos didácticos: `Tuki2021`, `TucuTech`,
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

Capturar tráfico únicamente del BSSID y canal definidos para la práctica. Obtener
el handshake o PMKID mediante una reconexión manual siempre que sea posible. Si se
usa desautenticación controlada, debe ser breve y dirigida a un dispositivo propio.

### Diccionario

Partir de las palabras del perfil ficticio y documentar las reglas usadas para
generar combinaciones de ocho caracteres. Filtrar duplicados y conservar el
diccionario exacto utilizado en la evidencia.

### Validación

Probar la captura con Aircrack-ng o convertirla al formato compatible con Hashcat.
Registrar el comando, la herramienta, el tiempo y el resultado sin publicar
credenciales fuera del entorno de evaluación.

## 5. Evidencias

Completar [la plantilla de evidencias](../templates/evidencia.md) para cada red.
Las capturas, archivos `.cap`, `.pcapng`, `.22000` y diccionarios deben permanecer
fuera del repositorio o en un almacenamiento privado.

## 6. Cierre técnico

Explicar qué información permitió construir la hipótesis, qué debilidad fue
demostrada y cómo se mitigaría: mayor longitud, aleatoriedad, WPA3 cuando esté
disponible, rotación de credenciales y separación de la red de invitados.