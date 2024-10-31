# DNS
Creación de un DNS server en Debian12

Cosas que vamos a necesitar:
- Máquina Virtual Debian (última versión) con servicio DNS
- Máquina Virtual (Debian o no, recomendable que sea similar) con otro servicio DNS
- Servicio DHCP en la máquina servidor (ya montado)

## Primeros Pasos
Para comenzar es bueno empezar desactivar el DHCP para evitar dar IP a quienes no necesitamos.

``` bash
systemctl stop isc-dhcp-service
```
Si no quieres que esté iniciándose cada vez que inicies, en vez de ```stop``` puedes poner ```disable```.
A esto le sigue un paso esencial (si usas ```su -``` puedes ignorar el sudo).
``` bash
sudo apt update
sudo apt upgrade
sudo apt install bind9
```
Esta es la parte principal, a partir de aquí toodo irá cambiando.

[parte1.md](Archivos Principales)
