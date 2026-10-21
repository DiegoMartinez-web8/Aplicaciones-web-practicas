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




















