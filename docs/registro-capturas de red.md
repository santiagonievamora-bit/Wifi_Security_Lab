# Registro de capturas de handshake

Este registro documenta los archivos `.cap` encontrados a apartir de el procedimiento mostrado en mostrado en [`../reports/Ejemplo%20completo.pdf 
`](../reports/Ejemplo%20completo.pdf)
 
## Resumen

| Archivo de captura | Tamaño indicado | SSID visible | Asociación | BSSID/AP observado | Cliente propio asignado | Estado |
| --- | ---: | --- | --- | --- | --- | --- |
| `handshake-82-18-48-75-E3-76.cap` | 273.581 bytes | `Best Games` | Best Games | `82:18:48:75:E3:76` | `7A:4C:91:2E:B7:08` | Válida (1 handshake)|

| `handshake-jorge.cap` | 281.894 bytes | `DigitalSoft` | DigitalSoft | `8E:75:F8:BA:9F:9E` | `B2:58:73:0C:D6:41` | Válida (1 handshake)|

| `handshake-01.cap` | 367.330 bytes | `Novacorp.srl` | EcoNova | `8E:7F:6E:F3:B2:B8` | `6E:39:A4:71:C2:0D` | Válida (1 handshake)|

## Verificación local

Con cada archivo almacenado:

aircrack-ng <BSSID> /ruta/privada/handshake.cap

## Resultado por empresa

- **Best Games:** 

santiago.nm@MacBook-Pro-de-Santiago Wifi Security Lab % aircrack-ng handshake-82-18-48-75-E3-76.cap
Reading packets, please wait...
Opening handshake-82-18-48-75-E3-76.cap
Resetting EAPOL Handshake decoder state.
Read 6201 packets.

   #  BSSID              ESSID                     Encryption

   1  82:18:48:75:E3:76  Best Games                WPA (1 handshake)

Choosing first network as target.

Reading packets, please wait...
Opening handshake-82-18-48-75-E3-76.cap
Resetting EAPOL Handshake decoder state.
Read 6201 packets.

1 potential targets

Please specify a dictionary (option -w).

- **EcoNova:** 

santiago.nm@MacBook-Pro-de-Santiago Wifi Security Lab % aircrack-ng handshakes/handshake-01.cap
Reading packets, please wait...
Opening handshake-01.cap
Read 9654 packets.

   #  BSSID              ESSID                     Encryption

   1  8E:7F:6E:F3:B2:B8  Novacorp.srl              WPA (1 handshake)

Choosing first network as target.

Reading packets, please wait...
Opening handshake-01.cap
Read 9654 packets.

1 potential targets

Please specify a dictionary (option -w).

la captura asignada es `handshake-01.cap`; su SSID visible es
  `Novacorp.srl`.

- **DigitalSoft:** 

santiago.nm@MacBook-Pro-de-Santiago Wifi Security Lab % aircrack-ng handshake-jorge.cap
Reading packets, please wait...
Opening handshake-jorge.cap
Read 6248 packets.

   #  BSSID              ESSID                     Encryption

   1  8E:75:F8:BA:9F:9E  DigitalSoft               WPA (1 handshake)

Choosing first network as target.

Reading packets, please wait...
Opening /ruta/privada/handshake-jorge.cap
Read 6248 packets.

1 potential targets

Please specify a dictionary (option -w).

la captura asignada es `handshake-jorge.cap`; su SSID
  visible es `DigitalSoft`, según la correspondencia indicada para el laboratorio.

## Siguiente paso:

como podemos ver, en cada captura nos pide uasr el comando -w para especificar diccionario o "wordlist" para ejecutar el ataque, que veremos en el siguiente reporte
->  [`./Diccionarios.md `](./Diccionarios.md)
 