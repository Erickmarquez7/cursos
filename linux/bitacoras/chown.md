```
erickmain@erickmain:~$ ls -la prueba*
-rwxrwxrwx 1 root      root       0 jun 13 22:06 pruebaSuperUsuario.txt
-rwxrwxrwx 1 erickmain erickmain 41 jun 13 22:13 pruebaUsuario.txt

erickmain@erickmain:~$ chown erickmain:erickmain pruebaSuperUsuario.txt 
chown: changing ownership of 'pruebaSuperUsuario.txt': Operation not permitted

erickmain@erickmain:~$ sudo -i
root@erickmain:~# cd /home/erickmain/

root@erickmain:/home/erickmain# ls -la prueba*
-rwxrwxrwx 1 root      root       0 jun 13 22:06 pruebaSuperUsuario.txt
-rwxrwxrwx 1 erickmain erickmain 41 jun 13 22:13 pruebaUsuario.txt

root@erickmain:/home/erickmain# chown erickmain:erickmain pruebaSuperUsuario.txt

root@erickmain:/home/erickmain# ls -la prueba*
-rwxrwxrwx 1 erickmain erickmain  0 jun 13 22:06 pruebaSuperUsuario.txt
-rwxrwxrwx 1 erickmain erickmain 41 jun 13 22:13 pruebaUsuario.txt
root@erickmain:/home/erickmain# 
```