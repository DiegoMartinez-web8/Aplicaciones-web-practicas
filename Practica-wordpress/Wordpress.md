# Información Personal
## Nombre: Diego Alejandro Martínez Rojas
## Curso: 2 Smx
## Fecha: 16/10/2026

# Apartado 1. Conexión por SSH y comprobación del servidor
Apartado 1. Conexión por SSH y comprobación del servidor
1.1. Averigua la IP del servidor. Con la consola de la máquina virtual (o ya conectado por SSH), ejecuta:
```bash
hostname -I
```
Apunta la IP que aparezca (por ejemplo, 192.168.56.10).

1.2. Conéctate por SSH desde tu ordenador. Abre una terminal en tu ordenador (en Windows, PowerShell) y escribe:
ssh TU_USUARIO@IP_DEL_SERVIDOR
La primera vez te preguntará si confías en el servidor: escribe yes. Después te pedirá la contraseña de tu usuario. A partir de aquí, todos los comandos de la práctica se escriben en esta terminal.

1.3. Comprueba que todo lo anterior sigue funcionando:
```bash
systemctl is-active apache2 mariadb
php -v
```
Debe aparecer active dos veces y PHP 8.3.x.
📸 Captura de la conexión SSH y del resultado de los dos comandos.
!()[]
❓ ¿Qué dos "puertas" (programas y puertos) usas para trabajar con el servidor en esta práctica y para qué sirve cada una?
