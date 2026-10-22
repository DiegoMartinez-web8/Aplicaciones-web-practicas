# Información Personal
## Nombre: Diego Alejandro Martínez Rojas
## Curso: 2 SMX
## Fecha: 16/10/2026

# Desarrollo de la práctica

Lo primero que vamos a hacer es deshabilitar los dos sitios virtuales que hicimos en la práctica anterior y
dejaremos de nuevo solo uno.

```bash
sudo a2ensite 000-default.conf
sudo systemctl reload apache2
```

Actualiza la lista de paquetes y comprueba que Apache sigue funcionando


```bash

sudo apt update
sudo apt upgrade -y
systemctl is-active apache2

```
![Captura-active](/Practica-02-MariaDB-PHP/Imagenes-02/Captura-01-active.png)

# Apartado 2. Instalación de MariaDB
Para instalar 
```bash
sudo apt install mariadb-server -y
```

Comprueba la versión instalada:
```bash
mariadb --version
```
![Captura-version-02](/Practica-02-MariaDB-PHP/Imagenes-02/Captura-02-version.png)
# Apartado 3. Comprobación del funcionamiento
3.1. Estado del servicio
```bash
sudo systemctl status mariadb
systemctl is-enabled mariadb
```
# Apartado 3. Comprobación del funcionamiento
3.1. Estado del servicio

```bash
sudo systemctl status mariadb
``` 
![Captura-03-running](/Practica-02-MariaDB-PHP/Imagenes-02/Captura-03-running.png)
```bash
systemctl is-enabled mariadb
```
 ![Captura-03-running](/Practica-02-MariaDB-PHP/Imagenes-02/Captura-3.1-enabled.png)

# 3.2. Entrar en la base de datos
```bash
sudo mariadb
```
![Captura-version-02](/Practica-02-MariaDB-PHP/Imagenes-02/Captura-3.2-salida.png)
# Apartado 4. Comandos principales
| Comando | Función |
| :--- | :--- |
| `sudo systemctl start mariadb` | Arranca el servicio |
| `sudo systemctl stop mariadb` | Detiene el servicio |
| `sudo systemctl restart mariadb` | Reinicia el servicio |
| `sudo systemctl status mariadb` | Muestra su estado |
| `sudo systemctl enable mariadb` | Lo arranca automáticamente al encender el equipo |

# Apartado 5
Más adelante, cuando WordPress muestre el error "Error al establecer una conexión con la base de
datos", lo primero que tendrás que mirar es si MariaDB está funcionando. Vamos a ver cómo se nota.

Detén el servicio a propósito
```bash
sudo systemctl stop mariadb
systemctl is-active mariadb
sudo mariadb
```

![Captura-version-02](/Practica-02-MariaDB-PHP/Imagenes-02/Captura-5-error.png)


 Vuelve a arrancarlo y comprueba
que todo vuelve a la normalidad:

```bash
sudo systemctl start mariadb
systemctl is-active mariadb
```
![Captura-version-02](/Practica-02-MariaDB-PHP/Imagenes-02/Captura-5.1-solucion.png)

Para comprobar si el problema es que MariaDB está parado, usarías estos dos comandos: 
```bash
systemctl is-active mariadb 
```
(para comprobar si el servicio está activo o inactive).
```bash 
sudo mariadb
```
(para verificar si da el error de conexión por socket al intentar entrar).   

# Apartado 6. Instalación de PHP
WordPress está hecho en PHP. Instalamos PHP y las piezas que WordPress necesita:
sudo apt install php libapache2-mod-php php-mysql php-curl php-gd php-mbstring php-xml php-zip
```bash
php-intl -y
php -v
```
debe mostrar PHP 8.3.x. 
Para qué sirve cada paquete:

| Paquete | Función |
| :--- | :--- |
| **php** | El lenguaje PHP |
| **libapache2-mod-php** | Permite a Apache ejecutar PHP |
| **php-mysql** | Permite a PHP hablar con MariaDB (imprescindible) |
| **php-curl** | Conexiones a otros servidores (actualizaciones, plugins) |
| **php-gd** | Tratamiento de imágenes |
| **php-mbstring** | Manejo de textos con tildes y caracteres especiales |
| **php-xml** | Lectura y escritura de ficheros XML |
| **php-zip** | Instalación y actualización de plugins y temas |
| **php-intl** | Idiomas y formatos regionales |

Reinicia Apache y comprueba que ha cargado PHP:
```bash
sudo systemctl restart apache2
sudo apache2ctl -M | grep -E "mpm|php"
```
Debes ver mpm_prefork_module y php_module.
Comprueba que PHP puede hablar con MariaDB:
Práctica MariaDB y PHP 
```bash
php -m | grep -i mysql
```
Debe aparecer mysqli, mysqlnd y pdo_mysql. Son las piezas que usa WordPress para conectarse a la base
de datos.
Comprueba que Apache ejecuta PHP:
```bash
echo '<?php phpinfo();' | sudo tee /var/www/html/info.php
```
Abre http://IP_DE_TU_SERVIDOR/info.php en el navegador. Debe aparecer una página morada con la
versión de PHP.
















