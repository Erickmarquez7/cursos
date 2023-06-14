```
erickmain@erickmain:~$ apt-get update
Leyendo lista de paquetes... Hecho
E: No se pudo abrir el fichero de bloqueo «/var/lib/apt/lists/lock» - open (13: Permission denied)
E: No se pudo bloquear el directorio /var/lib/apt/lists/
W: Se produjo un problema al desligar el fichero /var/cache/apt/pkgcache.bin - RemoveCaches (13: Permission denied)
W: Se produjo un problema al desligar el fichero /var/cache/apt/srcpkgcache.bin - RemoveCaches (13: Permission denied)

erickmain@erickmain:~$ sudo apt-get update
Ign:1 http://packages.linuxmint.com vera InRelease
Obj:2 http://packages.linuxmint.com vera Release                                                     
Obj:3 http://archive.ubuntu.com/ubuntu jammy InRelease                                                                                
Des:4 http://packages.microsoft.com/repos/code stable InRelease [3 569 B]                                                             
Des:6 http://archive.ubuntu.com/ubuntu jammy-updates InRelease [119 kB]                                                   
Des:7 http://security.ubuntu.com/ubuntu jammy-security InRelease [110 kB]           
Des:8 http://packages.microsoft.com/repos/code stable/main armhf Packages [71.1 kB]            
Des:9 http://packages.microsoft.com/repos/code stable/main arm64 Packages [70.8 kB]                   
Des:10 http://packages.microsoft.com/repos/code stable/main amd64 Packages [70.5 kB]                
Des:11 http://archive.ubuntu.com/ubuntu jammy-backports InRelease [108 kB]                                            
Des:12 http://archive.ubuntu.com/ubuntu jammy-updates/main i386 Packages [419 kB]                        
Des:13 http://archive.ubuntu.com/ubuntu jammy-updates/main amd64 Packages [676 kB]
Des:14 http://security.ubuntu.com/ubuntu jammy-security/main amd64 DEP-11 Metadata [41.5 kB]
Des:15 http://archive.ubuntu.com/ubuntu jammy-updates/main amd64 DEP-11 Metadata [99.8 kB]
Des:16 http://archive.ubuntu.com/ubuntu jammy-updates/universe amd64 Packages [921 kB]                           
Des:17 http://archive.ubuntu.com/ubuntu jammy-updates/universe i386 Packages [623 kB]                        
Des:18 http://archive.ubuntu.com/ubuntu jammy-updates/universe amd64 DEP-11 Metadata [274 kB]
Des:19 http://security.ubuntu.com/ubuntu jammy-security/universe amd64 DEP-11 Metadata [21.9 kB]
Des:20 http://archive.ubuntu.com/ubuntu jammy-updates/multiverse amd64 DEP-11 Metadata [940 B]                 
Des:21 http://archive.ubuntu.com/ubuntu jammy-backports/main amd64 DEP-11 Metadata [7 976 B]
Des:22 http://archive.ubuntu.com/ubuntu jammy-backports/universe amd64 DEP-11 Metadata [16.9 kB]
Descargados 3 655 kB en 3s (1 255 kB/s)                                       
Leyendo lista de paquetes... Hecho
```