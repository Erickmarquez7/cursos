```
erickmain@erickmain:~$ chmod 777 prueba*
chmod: changing permissions of 'pruebaSuperUsuario.txt': Operation not permitted

erickmain@erickmain:~$ ls -la prueba*
-rw-r--r-- 1 root      root       0 jun 13 22:06 pruebaSuperUsuario.txt
-rwxrwxrwx 1 erickmain erickmain 41 jun 13 22:13 pruebaUsuario.txt

erickmain@erickmain:~$ sudo -i

root@erickmain:~# cd /home/erickmain/

root@erickmain:/home/erickmain# ls -la prueba*
-rw-r--r-- 1 root      root       0 jun 13 22:06 pruebaSuperUsuario.txt
-rwxrwxrwx 1 erickmain erickmain 41 jun 13 22:13 pruebaUsuario.txt

root@erickmain:/home/erickmain# chmod 777 prueba*

root@erickmain:/home/erickmain# ls -la prueba*
-rwxrwxrwx 1 root      root       0 jun 13 22:06 pruebaSuperUsuario.txt
-rwxrwxrwx 1 erickmain erickmain 41 jun 13 22:13 pruebaUsuario.txt
```