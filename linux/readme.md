# Linux y su terminal

[Entorno](bitacoras/entorno.md)

## Nivel de usuario

Si en la terminal tenemos el signo de dolar ($) significa que estamos en modo usuario normal

Si tenemos un gatito (#) entonces estamos en modo super usuario, generalmente este se activa con la instrucción [_**sudo -i**_](bitacoras/usuario.md)

```
usuario@dominio:~$ sudo -i
root@dominio:~#
```

## Conexión de red

### ping

Una buena practica es comprobar si tenemos internet para actualizar paquetes, esto se hace con [_**ping**_](bitacoras/ping.md)

```
usuario@dominio:~$ ping 8.8.8.8
```

Donde 
- -c es para la cantidad de paquetes
- -a lo hace audible
- -i establece intervalos en segundos entre paquetes
- -q muestra solo un resumen

Y ponemos un dirección ipv4

### actualizar

Para actualizar (en el entorno de mint, derivado de debian) es con el manejador _apt-get_ y [_**update**_](bitacoras/update.md)

```
usuario@dominio:~$ apt-get update
```

Nos dirá que permiso denegado por lo cual es necesario hacerlo con _sudo_

```
usuario@dominio:~$ sudo apt-get update
```

Para aplicar las actualizaciones con [_**upgrade**_](bitacoras/upgrade.md)

```
usuario@dominio:~$ sudo apt-get upgrade
```

En el caso de distrbuiciones redHat lo hacemos con _**yum**_ o _**dnf**_

Estas actualizaciones las obtiene de algún servidor o pagina web 
el cual viene en algún archivo de nuestro SO dependiendo de la distribuición,
suele ser en _etc/apt/source.list_ en el caso de debian

## Directorios y permisos

### Directorios

Todo en linux nace desde "/" que es la carpeta raíz, para saber en qué carpeta nos encontramos escribimos [_**pwd**_](bitacoras/pwd.md)

```
usuario@dominio:~$ pwd
```

Notemos que cambiamos de dirección si alternamos entre usuario normal y root

Como usario normal estamos en _/home/usuario_ y NO podremos ir a la carpeta _/root_

Como usuario _root_ estamos en la carpeta _/root_ y tenemos la posibilidad de ir a la carpeta _/home/usuario_
 
Para cambiar de directorio _**cd**_

Y saber el contenido de la carpeta _**ls**_, para ver detalles con la bandera [_**-la**_](bitacoras/ls-la.md), donde

- d--------- indica que es directorio
- l--------- indica que es enlace o acceso directo
- ---------- indica que ya es el archivo

Además 
- r es permiso de lectura
- w permiso de escritura
- x para ejecutar

Los tres primeros (sin contar el primer caracter) indican los permisos del superusuario, los siguientes 3 los permisos que tiene un cierto grupo y los ultimos 3 los permisos de todos los usuarios

Un ejemplo al momento de crear documentos con _**touch**_ y los usuarios

```
erickmain@erickmain:~$ ls -la pruebaUsuario.txt 
-rw-rw-r-- 1 erickmain erickmain 0 jun 13 22:05 pruebaUsuario.txt
erickmain@erickmain:~$ sudo -i

[sudo] password for erickmain:    
root@erickmain:~# cd /home/erickmain/
root@erickmain:/home/erickmain# touch pruebaSuperUsuario.txt
root@erickmain:/home/erickmain# ls -la prueba*
-rw-r--r-- 1 root      root      0 jun 13 22:06 pruebaSuperUsuario.txt
-rw-rw-r-- 1 erickmain erickmain 0 jun 13 22:05 pruebaUsuario.txt
root@erickmain:/home/erickmain# 
```

El primer archivo fue creado por un superusuario y el segundo por usuario normal.
Notemos que el segundo archivo tiene el permiso de escritura para ciertos grupos

Algunos comandos que pueden servir

- rm \<archivo\> elimina el archivo
- rm -r \<carpeta\> elimina la carpeta de manera recursiva
- rm -ri \<carpeta\> elimina la carpeta de manera recursiva con pregunta de seguridad
- cp \<origen\> \<destino\> copia el archivo
- mv \<origen\> \<destino\> mueve el archivo
- touch \<archivo\> crea un archivo
- mkdir \<carpeta\> crea una carpeta
- cat \<archivo\> muestra el contenido del archivo

Además con touch podemos modificar tiempos de acceso, de escritura, fecha, hora, etc.

### Carpetas en linux

Todo en linux es un archivo o carpeta, en ese sentido cada una tiene un propósito y va por niveles

- /bin/ Archivos binarios del usuario
- /sbin/ Binarios del sistema
- /boot/ Donde se aloja el kernel junto con otros archivos de arranque (uname -r)
- /etc/ Archivos de configuración de los servicios o sistemas 
- /home/ Directorio personal
- /lib/ Bibliotecas necesarias para la ejecución de los binarios
- /opt/ Aplicaciones externas que no se integran en /usr/
- /proc/ Archivos virtuales, información de procesos, el contenido no está en el disco sino en la memoria
- /root/ Directorio del superusuario
- /srv/ Archivos relacionados a servidores
- /tmp/ Temporales
- /usr/ Archivos de programas y apps instaladas
- /var/ Variables

### Permisos

Para cambiar los **permisos** lo hacemos con el comando [_**chmod**_](bitacoras/chmod.md)

```
usuario@dominio:~$ chmod 777 archivo
```

También podemos cambiar la **propiedad** con el comando [_**chown**_](bitacoras/chown.md)

```
usuario@dominio:~$ chown <usuario:grupo> <archivo>
```

Aquí cambió la propiedad de root a mi usuario, para ello se debe estar en modo _root_

*en este punto hubo cambio de carpetas

### Comprimir archivos

Para comprimir archivos lo hacemos con el comando [_**tar**_](bitacoras/tar.md), donde

- -c Crea el archivo .tar
- -v Muestra el proceso de comprensión
- -f Le pone nombre al archivo
- -z Comprime en gzip
- -x Descomprime el archivo

Notemos que al descomprimir se quedan guardadas la última hora de modificación y no la de descomprensión. 

También tenemos la posibilidad de comprimir con _**gzip**_ pero solo archivos, con _**tar**_ pueden ser también carpetas

## Procesos en Linux

Para ver los procesos en la maquina escribimos [_**top**_](bitacoras/top.md)

```
usuario@dominio:~$ top
```

Para matar alguno de estos procesos lo hacemos con _**kill**_

```
usuario@dominio:~$ kill <PID>
```

Estado de los procesos que se están ejecutando con [_**ps**_](bitacoras/ps.md)

Las registros de los procesos suelen guardarse en archivos _.log_

```
usuario@dominio:~$ ps -f
```
## Script básico

El archivo necesita tener extensión .sh y empezar con _!/bin/bash_, esto le indica que será interpretado por la shell de linux

Aquí un [script](bitacoras/script.sh) de prueba

Podemos declarar variables con var=ejemplo, y para utilizarlas tenemos que acceder a ellas con el signo de dolar ($), ya que si lo dejamos como _var_ entonces lo identifica como palabra.

Además, este archivo debe ser propiedad de _root_ y tener permisos de ejecución. Para ejecutarlo escribirmos _./script.sh_

De esta manera podemos automatizar tareas como respaldos _.tar_, limpieza, actualizaciones, etc.

Esto se puede configurar con el demonio _cron_, el cual se ejecuta desde que se inicia la maquina y comprueba si hay alguna tarea a ejecutar, por lo cual la configuración de la fecha y hora debe ser la correcta

_crontrab_ es un archivo de texto que contiene las tareas a ejecutar

Podemos editar este archivo con

```
usuario@dominio:~$ crontab -e
```

Para una mejor [documentación](https://www.redeszone.net/tutoriales/servidores/cron-crontab-linux-programar-tareas/)

Este lenguaje bash y los scripts requieren de un curso completo, esta es solamente una breve introducción

## Hardware

Algunos comandos para obtener información del hardware

```
usuario@dominio:~$ free
```

Muestra la información de la memoria RAM y SWAP, donde las banderas

- -m Lo muestra en megabytes
- -h Lo hace mas legible

Para mostrar información acerca de la cpu

```
usuario@dominio:~$ lscpu
```
o bien con 

```
usuario@dominio:~$ cat /proc/cpuinfo 
```

Para mostrar información acerca de las particiones

```
usuario@dominio:~$ lslbk
```

Para obtener información acerca de los perifericos

```
usuario@dominio:~$ lsusb
```