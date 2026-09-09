# Hardware y entorno de laboratorio

Este apartado registra la plataforma utilizada para la práctica. La información
sirve para reproducir el entorno, pero no constituye una autorización para
examinar redes externas.

## Equipo anfitrión

| Campo | Valor |
| --- | --- |
| Modelo | MacBook Pro |
| Identificador del modelo | `MacBookPro15,1` |
| Procesador | Intel Core i9 de seis núcleos, 2,9 GHz |
| Procesadores / núcleos | 1 / 6 |
| Hyper-Threading | Activado |
| Memoria | 32 GB |
| Caché L2 | 256 KB por núcleo |
| Caché L3 | 12 MB |
| Firmware del sistema | `2103.160.2.0.0` |
| iBridge | `23.16.16068.0.0,0` |
| Cargador del sistema operativo | `583~2317` |
| Bloqueo de activación | Desactivado |

Los números de serie, UUID del equipo y UDID del perfil se omiten del repositorio
porque identifican de forma única al equipo anfitrión. Deben conservarse solo en
la documentación privada de la práctica si fueran necesarios para una auditoría
interna.

## Máquina virtual Kali Linux

| Campo | Valor |
| --- | --- |
| Nombre | `Kali Linux Lab` |
| Sistema invitado | Debian (64-bit) / Linux26_64 |
| Arquitectura | x86 |
| Memoria asignada | 16.384 MB |
| CPU virtuales | 4 |
| Chipset | PIIX3 |
| Firmware | BIOS |
| VRAM | 128 MB |
| Controlador gráfico | VMSVGA |
| Aceleración 3D | Activada |
| Virtualización de hardware | Activada |
| Nested Paging | Activado |
| Long Mode | Activado |
| PAE | Desactivado |
| HPET | Desactivado |
| IOAPIC / APIC | Activado / Activado |
| VT-x VPID | Activado |
| VT-x unrestricted execution | Activado |
| Adaptador de red virtual | Intel 82540EM, puente sobre `en0: Wi-Fi`, cable conectado |
| MAC del adaptador virtual | `08:00:27:5C:ED:2F` |
| Audio | AC97, activado |
| Portapapeles | Bidireccional |
| Carpetas compartidas | `win_compartida` y `Laboratorio`, según configuración local |
| Estado registrado | En ejecución el 07/09/2026 |

Las rutas locales de VirtualBox, UUID de la VM, UUID del hardware, UUID del disco
virtual y archivos NVRAM se omiten porque contienen identificadores y rutas del
usuario. La VM utiliza un disco VDI conectado a un controlador SATA.

## Adaptadores USB

| Adaptador | Fabricante / producto | Identificadores técnicos | Estado |
| --- | --- | --- | --- |
| Red cableada | Realtek USB 10/100 LAN | VID `0x0BDA`, PID `0x8152`, revisión `0x3200` | Conectado a la VM |
| WiFi para auditoría | Ralink 11n Adapter | VID `0x07D1`, PID `0x3C16`, revisión `0x0101` | Filtro USB configurado, no conectado en el registro aportado |
| WiFi para auditoría | Realtek 802.11ac NIC | VID `0x2357`, PID `0x0138`, revisión `0x0300` | Filtro USB activo |

No se publican números de serie de los periféricos USB. Para reproducir la
práctica, comprobar el modelo y chipset reales dentro de Kali antes de iniciar
la captura.

## Interfaz inalámbrica `wlan1`

La interfaz documentada para Aircrack-ng es la asociada al adaptador Ralink:

| Campo | Valor |
| --- | --- |
| PHY | `phy2` |
| Interfaz | `wlan1` |
| Driver | `mt7601u` |
| Chipset | Ralink Technology, Corp. MT7601U |
| Modo monitor inicial | Desactivado |

Comprobación recomendada dentro de Kali:

```text
lsusb
iw dev
ip link
sudo airmon-ng check kill
sudo airmon-ng start wlan1
iw dev
```

Después de activar el modo monitor, usar el nombre que devuelva `iw dev`,
habitualmente `wlan1mon`. Si el sistema renombra la interfaz, sustituir
`wlan1mon` en todos los comandos por el nombre real. No asumir que el adaptador
Realtek 802.11ac es `wlan1` sin comprobarlo.

## Condiciones de reproducibilidad

- Ejecutar Kali dentro de VirtualBox con el adaptador WiFi USB pasado a la VM.
- Confirmar que el filtro USB activo corresponde al adaptador que se utilizará.
- Registrar versión de Kali, Aircrack-ng, kernel, driver y salida de `iw dev`.
- Usar únicamente el AP, cliente y capturas ficticios definidos en el proyecto.
- Mantener capturas, diccionarios y resultados de validación fuera de Git.
