# Archivo: named.conf.local

Este archivo es el core del DNS, este archivo no lo copiamos porque lo que vamos a añadir es principalmente líneas por debajo de el útimo comentario.
En este archivo definimos las zonas y los archivos en donde vamos a indicar la información sobre nuestro nombre de dominio, para ello definimos un
```zone``` y ojo cuidado, a excepción de la primera línea, todas y cada una de las líneas terminan con ";" no poner uno podría producir un error.
Para nuestro dominio principal, se debería de dejar más o menos así:

```bash
//
// Do any local configuration here
//

// Consider adding the 1918 zones here, if they are not used in your
// organization
//include "/etc/bind/zones.rfc1918";

zone "www.tudominio.com" in {
    type master;
    file "/etc/bind/db.tudominio.com";
};
```
El archiv llamado db.tudominio.com es el nombre que debería tener el archivo donde vamos a configurar los nombres para la
llamada direct al DNS.
