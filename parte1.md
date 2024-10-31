# Archivos Principales de Bind.

Los archivos de DNS una vez instalado se encuentran en la carpeta /etc/bind
Aquí en esta carpeta están todos los archivos importantes que queremos editar, entre ellos nos interesa:

named.conf.local (estado base)
```bash
//
// Do any local configuration here
//

// Consider adding the 1918 zones here, if they are not used in your
// organization
//include "/etc/bind/zones.rfc1918";
```
db.127 (estado base)
```bash
;
; BIND reverse data file for local loopback interface
;
$TTL    604800
@       IN      SOA     localhost. root.localhost. (
                              1         ; Serial
                         604800         ; Refresh
                          86400         ; Retry
                        2419200         ; Expire
                         604800 )       ; Negative Cache TTL
;
@       IN      NS      localhost.
1.0.0   IN      PTR     localhost.
```

db.local (estado base)
```bash
;
; BIND data file for local loopback interface
;
$TTL    604800
@       IN      SOA     localhost. root.localhost. (
                              2         ; Serial
                         604800         ; Refresh
                          86400         ; Retry
                        2419200         ; Expire
                         604800 )       ; Negative Cache TTL
;
@       IN      NS      localhost.
@       IN      A       127.0.0.1
@       IN      AAAA    ::1
```

Estos tres archivos van a ser los más importantes en nuestra quest de hacer un servicio de DNS, por el momento lo importante es realizar
una copia de los dos segundos archivos a saber hacer un ```bash cp /etc/bind/db.local /etc/bind/db.dominio.com bash cp /etc/bind/db.127 /etc/bind/db.192.168.13```
(la IP de la copia de ```db.127`` puede ser cualquier IP pero es recomendable que coincida con la de tu servidor de DHCP
