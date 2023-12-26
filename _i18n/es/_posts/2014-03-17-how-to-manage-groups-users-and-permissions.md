---
layout: post
title:  ¿Cómo administrar grupos, usuarios y permisos?
date:   2014-03-20 06:00:00
description: Los sistemas basados en Unix organizan todo esto por usuarios y grupos, donde cada usuario debe identificarse con un nombre de usuario y una contraseña. Durante el proceso de login, la contraseña introducida por cada usuario, es encriptada y comparada con las contraseñas encriptadas que han sido previamente almacenadas en el sistema.
tags: linux administrar-grupos consola terminal comandos
categories: Linux
thumbnail: assets/img/Linux/como-administrar-grupos-usuarios-permisos/1.png
---

<div class="row mt-3" style="text-align: center">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="assets/img/Linux/como-administrar-grupos-usuarios-permisos/1.png" class="img-fluid rounded z-depth-1" %}
    </div>
</div>

Linux es un sistema operativo multiusuario y multitarea, es decir, que múltiples usuario pueden trabajar en el sistema de forma simultánea, ejecutando diversas tareas a al vez. **Por este motivo es muy importante que el sistema operativo permita la gestión y control de los usuarios**.

**Los sistemas basados en Unix organizan todo esto por usuarios y grupos, donde cada usuario debe identificarse con un nombre de usuario y una contraseña**. Durante el proceso de login, la contraseña introducida por cada usuario, es encriptada y comparada con las contraseñas encriptadas que han sido previamente almacenadas en el sistema.

**Los grupos son útiles para agrupar una serie de permisos especiales en el sistema a un grupo de usuarios determinado**, todo usuario debe pertenecer, al menos, a un grupo. En todo sistema debe haber un superusuario (`root`), que tendrá todos los permisos y privilegios máximos que le permitirán hacer cualquier operación sobre el sistema.

A continuación, se describen algunos ejemplos de los comandos más comunes para la gestión de grupos, usuarios y sus respectivos permisos.

## Usuarios y grupos

```sh
groupadd nombre_del_grupo         # crear un nuevo grupo
groupdel nombre_del_grupo         # borrar un grupo
groupmod -n nuevo_nombre_del_grupo viejo_nombre_del_grupo      # cambiar nombre de un grupo
useradd user1                     # crear un nuevo usuario
useradd -c Nombre_completo -g admin -d /home/user1 -s /bin/bash user1        # Crear un usuario user1 perteneciente al grupo admin
userdel -r user1                  # borrar un usuario y eliminar el directorio home
usermod -c “User FTP” -g system -d /ftp/user1 -s /bin/nologin user1         # cambiar atributos de usuario
usermod -aG grupo1,grupo2 user1   # agregar el usuario user1 a otros grupos existentes
passwd                            # cambiar contraseña
passwd user1                      # cambiar la contraseña de un usuario
chage -E 2011-12-31 user1         # cambiar la fecha en que una clave expira para el usuario
pwck                              # revisar la sintaxis correcta el formato de fichero de /etc/passwd y la existencia de usuarios
grpck                             # revisar la sintaxis correcta y el formato del fichero /etc/group y la existencia de grupos
```
## Permisos en ficheros

```sh
ls -lh                        # mostrar permisos
ls /tmp | pr -T5 -W$COLUMNS   # dividir la terminal en 5 columnas
chmod ugo+rwx dir1            # colocar permisos de lectura (r), escritura (w) y ejecución (x) al propietario (u), al grupo (g) y a otros (o) sobre el directorio dir1
chmod go-rwx dir1             # quitar permiso de lectura (r), escritura (w) y ejecución (x) al grupo (g) y otros (o) sobre el directorio dir1
chown user1 file1             # cambiar el dueño de un fichero
chown -R user1 dir1           # cambiar el propietario de un directorio y de todos los ficheros y directorios contenidos dentro
chgrp grupo1 file1            # cambiar grupo de fichero
chown user1:grupo1 file1      # cambiar usuario y el grupo propietario de un fichero
find / -perm -u+s             # visualizar todos los ficheros del sistema con SUID configurado
chmod u+s /bin/file1          # colocar el bit SUID en un fichero binario. El usuario que corriendo ese fichero adquiere los mismos privilegios como dueño
chmod u-s /bin/file1          # deshabilitar el bit SUID en un fichero binario
chmod g+s /home/public        # colocar un bit SGID en un directorio, similar al SUID pero por directorio
chmod g-s /home/public        # desabilitar un bit SGID en un directorio
chmod o+t /home/public        # colocar un bit STIKY en un directorio. Permite el borrado de ficheros solamente a los dueños legítimos
chmod o-t /home/public        # desabilitar un bit STIKY en un directorio
```
