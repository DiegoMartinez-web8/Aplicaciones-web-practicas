### Apartado 1: Comprobar el estado de ubuntu.server

Comprobamos el sistema.

**Comando ejecutado:**

Actualiza la lista de paquetes y el sistema:
```bash
sudo apt update
sudo apt upgrade -y
```
Comprueba la versión del sistema:

```bash
lsb_release -a

```
![captura 1](./imagenes/Captura1.appweb.png)

### Apartado 2: Instalación apache
```bash
sudo apt install apache2 -y
```
Comprueba la versión instalada:

```bash
apache2 -v

```


### ¿Qué paquetes adicionales se han instalado como dependencias? (pista: revisa la salida de apt).
Los paquetes adicionales instalados como dependencias son: 
```bash
ssl-cert, libaprutil1t64, libaprutil1-dbd-sqlite3, liblua5.4-0, apache2-data, apache2-bin, apache2-utils, libaprutil1-ldap y libapr1t64

```
### Apartado 3. Comprobación del funcionamiento
3.1. Estado del servicio
sudo systemctl status apache2
3.2. Puertos en escucha
sudo ss -tulpn | grep apache2
3.3. Prueba desde el terminal y desde el navegador
curl -I http://localhost
salida: 
HTTP/1.1 200 OK
Date: Mon, 05 Oct 2026 08:19:12 GMT
Server: Apache/2.4.58 (Ubuntu)
Last-Modified: Mon, 05 Oct 2026 07:24:29 GMT
ETag: "29af-65d12c5cb16ac"
Accept-Ranges: bytes
Content-Length: 10671
Vary: Accept-Encoding
Content-Type: text/html

Desde el navegador (idealmente de otro equipo de la red) accede a http://IP_DE_TU_SERVIDOR. Debe aparecer la página "Apache2 Ubuntu Default Page".
Correcto
