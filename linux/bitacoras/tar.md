```
erickmain@erickmain:~/Documentos$ ls -la
total 12
drwxrwxr-x 2 erickmain erickmain 4096 jun 14 18:37 .
drwxr-xr-x 9 erickmain erickmain 4096 jun 14 18:37 ..
-rwxrwxrwx 1 erickmain erickmain    0 jun 13 22:06 pruebaSuperUsuario.txt
-rwxrwxrwx 1 erickmain erickmain   41 jun 13 22:13 pruebaUsuario.txt

erickmain@erickmain:~/Documentos$ tar -cvf comprimido.tar pruebaUsuario.txt 
pruebaUsuario.txt

erickmain@erickmain:~/Documentos$ ls -la
total 24
drwxrwxr-x 2 erickmain erickmain  4096 jun 14 18:39 .
drwxr-xr-x 9 erickmain erickmain  4096 jun 14 18:37 ..
-rw-rw-r-- 1 erickmain erickmain 10240 jun 14 18:39 comprimido.tar
-rwxrwxrwx 1 erickmain erickmain     0 jun 13 22:06 pruebaSuperUsuario.txt
-rwxrwxrwx 1 erickmain erickmain    41 jun 13 22:13 pruebaUsuario.txt

erickmain@erickmain:~/Documentos$ rm prueba*
erickmain@erickmain:~/Documentos$ ls -la
total 32
drwxrwxr-x 2 erickmain erickmain  4096 jun 14 18:49 .
drwxr-xr-x 9 erickmain erickmain  4096 jun 14 18:37 ..
-rw-r--r-- 1 root      root      10240 jun 14 18:40 comprimido2.tar
-rw-rw-r-- 1 erickmain erickmain 10240 jun 14 18:39 comprimido.tar

erickmain@erickmain:~/Documentos$ tar -xf comprimido.tar
erickmain@erickmain:~/Documentos$ ls -la
total 36
drwxrwxr-x 2 erickmain erickmain  4096 jun 14 18:49 .
drwxr-xr-x 9 erickmain erickmain  4096 jun 14 18:37 ..
-rw-r--r-- 1 root      root      10240 jun 14 18:40 comprimido2.tar
-rw-rw-r-- 1 erickmain erickmain 10240 jun 14 18:39 comprimido.tar
-rwxrwxr-x 1 erickmain erickmain    41 jun 13 22:13 pruebaUsuario.txt
```