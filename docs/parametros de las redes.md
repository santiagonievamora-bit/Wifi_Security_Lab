# Parámetros de las redes

Los BSSID del AP se obtienen de airodump-ng. También están contenidas en el archivo `.cap`. Se debe verificar esto antes de ejecutar
Aircrack-ng. Las MAC de cliente son identificadores privados asignados a los tres dispositivos propios del laboratorio.

| Empresa | SSID documentado | BSSID/AP observado | Cliente propio asignado | Canal | Cifrado |
| --- | --- | --- | ---: | ---: | --- |
| Best Games | `Best Games` | `82:18:48:75:E3:76` | `7A:4C:91:2E:B7:08` | 11 | WPA2-Personal / CCMP |

| EcoNova | `Novacorp.srl` | `8E:7F:6E:F3:B2:B8` | `6E:39:A4:71:C2:0D` | 6 | WPA2-Personal / CCMP |

| DigitalSoftware | `DigitalSoft` | `8E:75:F8:BA:9F:9E` | `B2:58:73:0C:D6:41` | 1 | WPA2-Personal / CCMP |

Los valores anteriores deben reemplazar los marcadores `<BSSID_DEL_AP>` y
`<MAC_DEL_CLIENTE_PROPIO>` al ejecutar comandos dentro del laboratorio. Las MAC
de cliente usan direcciones localmente administradas para evitar suplantar hardware real; su apariencia es la de una MAC normal, pero son valores generados para esta documentación.
