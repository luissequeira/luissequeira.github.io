---
layout: post
title:  ¿Cómo gestionar archivos y directorios GNU/Linux?
date:   2013-11-21 06:00:00
description: Una vez dentro de un directorio, tal vez quieras ver el contenido, los ficheros ocultos, permisos o detalles de cada uno de los ficheros o subdirectorios, incluso mover, encontrar ficheros y directorios.
tags: consola terminal comandos 
categories: Linux
thumbnail: assets/img/Linux/como-gestionar-archivos-y-directorios-en-gnu-linux/snapshot18.png
---
Antes de empezar con el uso de **algunos comando Linux**, quiero recordarles la importancia de revisar el **manual de referencia** de cada comando, ya que es ahí donde se especifican todas las posibles opciones. El manual de referencia se puede visualizar en un terminal mediante el comando `man`, por ejemplo, si queremos ver el manual del comando `man`, en un terminal digitamos `man man` veríamos algo así:

<div class="row mt-3" style="text-align: center">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="assets/img/Linux/como-gestionar-archivos-y-directorios-en-gnu-linux/snapshot18.png" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Figura #1: Linux terminal displaying the manual of the `man` command.
</div>

Uno de los comando más utilizados es `cd`, se utiliza para acceder a un directorio, aquí les muestro algunos ejemplos:

```sh
cd                        # ir al directorio personal
cd ..                     # retroceder un nivel
cd ../..                  # retroceder 2 niveles
cd -                      # ir al directorio anterior
cd /home                  # ir al directorio /home
cd ~user1                 # ir al directorio user1
```

Si quieres saber la ruta actual:

```sh
pwd                       # mostrar la ruta del directorio actual</pre>
```

Una vez dentro de un directorio, tal vez quieras ver el contenido, los ficheros ocultos, permisos o detalles de cada uno de los ficheros o subdirectorios, en este caso `ls` la solución:

```sh
ls                        # listar el contenido de un directorio
ls -F                     # distinguiendo los directorios con una barra
ls -l                     # mostrando los detalles
ls -lh                    # mostrando los detalles (y el tamaño en un formato K, M)
ls -a                     # incluyendo los ficheros ocultos
ls *[0-9]                 # listar los ficheros y carpetas que contienen números
tree                      # mostrar los ficheros y carpetas en forma de árbol comenzando por la raíz
```

Para crear directorios utilizamos `mkdir` así:

```sh
mkdir dir1                # crear un directorio llamado dir1
mkdir dir1 dir2           # crear dos directorios a la vez
mkdir -p /dir1/dir2/dir3  # crear una estructura de directorios, si no existe.
```

Para eliminar ficheros y directorios:

```sh
rm file1                  # eliminar el archivo file1
rm -f file1               # eliminar el archivo file1 en modo forzado
rm -r dir1                # eliminar recursivamente el directorio dir1 con todo lo que contenga
rm -rf dir1 dir2          # borrar dos directorios con su contenido de forma recursiva y forzado
```

Para mover (renombrar) y copiar ficheros y carpetas necesitaremos dos comandos diferentes:

```sh
mv old_dir new_dir            # renombrar o mover un fichero o directorio
cp file1 /ruta/a/destino/     # copiar un fichero al destino
cp file1 file2 destino/       # copiar a la vez dos ficheros
cp file1 file2                # copiar file1 en file2
cp -r dir1 destino/           # copiar un directorio.
```

Para crear enlaces simbólicos (accesos directos):

```sh
ln -s file link               # crear un enlace simbólico al fichero o directorio
```

Para encontrar archivos existen varias opciones una de las más comunes es `find`, sin embargo para algunos usuarios les es molesto ya que puede llegar a tardar mucho en sistemas muy grandes, por lo que prefieren `locate`, para que este comando funcione bien, la base de datos de ficheros debe estar actualizada mediante el comando `updatedb`.

```sh
find / -name file1                       # buscar fichero y directorio a partir de la raíz del sistema
find / -user user1                       # pertenecientes al usuario user1
find /home/user1 -name \*.bin            # con extensión .bin dentro del directorio / home/user1
find /usr/bin -type f -atime +100        # ficheros binarios no usados en los últimos 100 días
find /usr/bin -type f -mtime -10         # ficheros creados o cambiados dentro de los últimos 10 días
locate \*.ps                             # encuentra ficheros con extensión .ps
whereis file                             # mostrar la ubicación de un fichero binario, de ayuda o fuente
which comando                            # mostrar la ruta completa a un comando
```

## References

1. Red Hat Enterprise Linux: Reference Manual