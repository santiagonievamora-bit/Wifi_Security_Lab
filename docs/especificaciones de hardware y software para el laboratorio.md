# Hardware y software del laboratorio

Esta ficha publica solo los datos necesarios para reproducir la práctica. El
ejercicio debe realizarse exclusivamente con el AP, el cliente y las capturas
ficticias del proyecto.

## Plataforma de ejecución

| Componente | Especificación relevante |
| --- | --- |
| Equipo anfitrión | macOS sobre un MacBook Pro Intel |
| Memoria del anfitrión | 32 GB |
| Virtualización | VirtualBox |
| Sistema invitado | Kali Linux de 64 bits |
| Recursos de la VM | 4 CPU virtuales y 16 GB de RAM |

La versión exacta de Kali, del kernel, de VirtualBox y de Aircrack-ng debe
registrarse en la evidencia de cada ejecución, porque puede afectar a los
drivers y a los resultados. No es necesario publicar firmware, UUID, MAC,
rutas locales, configuración de audio, portapapeles o carpetas compartidas.

## Adaptador inalámbrico

| Campo | Valor de referencia |
| --- | --- |
| Fabricante y chipset | Ralink MT7601U |
| Driver | `mt7601u` |
| Interfaz inicial | `wlan1` |
| Modo de captura | Monitor, habilitado durante la práctica |
| Conexión | Adaptador USB pasado directamente a la VM |

El nombre de la interfaz puede cambiar. Comprobar el dispositivo dentro de Kali
antes de iniciar la captura y usar el nombre devuelto por `iw dev`.

```text
lsusb
iw dev
ip link
```

## Distribución de herramientas

- Kali prepara la interfaz inalámbrica y ejecuta las pruebas autorizadas.
- El anfitrión puede ejecutar la validación de capturas y diccionarios si se
	necesita.
- Registrar las versiones de las herramientas junto con la evidencia, sin
	publicar credenciales, capturas ni diccionarios.
