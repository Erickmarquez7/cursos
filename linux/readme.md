# Linux y su terminal

## Nivel de usuario

Si en la terminal tenemos el signo de dolar ($) significa que estamos en modo usuario normal

Si tenemos un gatito (#) entonces estamos en modo super usuario, generalmente este se activa con la instrucción [_sudo -i_](bitacoras/usuario)

```
usuario@dominio:~$ sudo -i
root@dominio:~#
```

## Conexión de red

### ping

Una buena practica es comprobar si tenemos internet para actualizar paquetes, esto se hace con [ping](bitacoras/ping)

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

Para actualizar (en el entorno de mint, derivado de debian) es con el manejador _apt-get_ y [_update_](bitacoras/update.md)

```
usuario@dominio:~$ apt-get update
```

Nos dirá que permiso denegado por lo cual es necesario hacerlo con _sudo_

```
usuario@dominio:~$ sudo apt-get update
```

Para aplicar las actualizaciones con [_upgrade_](bitacoras/upgrade.md)

```
usuario@dominio:~$ sudo apt-get upgrade
```

En el caso de distrbuiciones redHat lo hacemos con _yum_ o _dnf_

Estas actualizaciones las obtiene de algún servidor o pagina web 
el cual viene en algún archivo de nuestro SO dependiendo de la distribuición,
suele ser en _etc/apt/source.list_ en el caso de debian

## Directorios y permisos

Todo en linux nace desde "/" que es la carpeta raíz, para saber en qué carpeta nos encontramos escribimos [_pwd_](bitacoras/pwd.md)

```
usuario@dominio:~$ pwd
```

Notemos que cambiamos de dirección si alternamos entre usuario normal y root

Como usario normal estamos en _/home/usuario_ y NO podremos ir a la carpeta _/root_

Como usuario _root_ estamos en la carpeta _/root_ y tenemos la posibilidad de ir a la carpeta _/home/usuario_
 
Para cambiar de directorio _cd_

Y saber el contenido de la carpeta _ls_, para ver detalles con la bandera [_-la_](bitacoras/ls-la.md), donde

- d--------- indica que es directorio
- l--------- indica que es enlace o acceso directo
- ---------- indica que ya es el archivo

Además 
- r es permiso de lectura
- w permiso de escritura
- x para ejecutar

Los tres primeros (sin contar el primer caracter) indican los permisos del superusuario, los siguientes 3 los permisos que tiene un cierto grupo y los ultimos 3 los permisos de todos los usuarios

Un ejemplo al momento de crear documentos con _touch_ y los usuarios

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