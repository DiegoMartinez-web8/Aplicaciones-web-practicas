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
