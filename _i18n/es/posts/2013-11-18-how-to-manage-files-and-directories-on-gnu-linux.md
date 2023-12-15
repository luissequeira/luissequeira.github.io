---
layout: post
title:  ¿Cómo gestionar archivos y directorios GNU/Linux?
date:   2013-11-21 06:00:00
description: Una vez dentro de un directorio, tal vez quieras ver el contenido, los ficheros ocultos, permisos o detalles de cada uno de los ficheros o subdirectorios, incluso mover, encontrar ficheros y directorios.
tags: linux consola terminal comandos GNU
categories: Tutorials
---
<p>
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;">Antes de empezar con el uso de <strong>algunos comando Linux</strong>, quiero recordarles la importancia de revisar el <strong>manual de referencia</strong> de cada comando, ya que es ahí donde se especifican todas las posibles opciones. El manual de referencia se puede visualizar en un terminal mediante el comando "<em>man"</em> (man comando), por ejemplo, si queremos ver el manual del comando "<em>man"</em>, en un terminal digitamos "<em>man man"</em> veríamos algo así:</span></span></p>
<p style="text-align: center;">
<img alt="" src="images/Linux/como-gestionar-archivos-y-directorios-en-gnu-linux/snapshot18.png" style="font-family: arial, helvetica, sans-serif; font-size: 14px; text-align: center; height: 368px; width: 600px;" /></p>
<p style="text-align: center;">
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;"><strong><span style="color:#0000ff;">Figura # 1</span></strong>: Terminal Linux mostrando el maual del comando "<em>man"</em>.</span></span></p>

<p>
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;">Uno de los comando más utilizados es "<em>cd"</em>, se utiliza para acceder a un directorio, aquí les muestro algunos ejemplos:</span></span></p>
<pre>cd                        # ir al directorio personal
cd ..                     # retroceder un nivel
cd ../..                  # retroceder 2 niveles
cd -                      # ir al directorio anterior
cd /home                  # ir al directorio /home
cd ~user1                 # ir al directorio user1
</pre>
<p>
<span style="font-family: arial, helvetica, sans-serif; font-size: 14px;">Si quieres saber la ruta actual:</span></p>
<pre>pwd                       # mostrar la ruta del directorio actual</pre>
<p>
<span style="font-family: arial, helvetica, sans-serif; font-size: 14px;">Una vez dentro de un directorio, tal vez quieras ver el contenido, los ficheros ocultos, permisos o detalles de cada uno de los ficheros o subdirectorios, en este caso "</span><em style="font-family: arial, helvetica, sans-serif; font-size: 14px;">ls"</em><span style="font-family: arial, helvetica, sans-serif; font-size: 14px;"> la solución:</span></p>
<pre>ls                        # listar el contenido de un directorio
ls -F                     # distinguiendo los directorios con una barra
ls -l                     # mostrando los detalles
ls -lh                    # mostrando los detalles (y el tamaño en un formato K, M)
ls -a                     # incluyendo los ficheros ocultos
ls *[0-9]                 # listar los ficheros y carpetas que contienen números
tree                      # mostrar los ficheros y carpetas en forma de árbol comenzando por la raíz</pre>
<p>
<span style="font-family: arial, helvetica, sans-serif; font-size: 14px;">Para crear directorios utilizamos "</span><em style="font-family: arial, helvetica, sans-serif; font-size: 14px;">mkdir"</em><span style="font-family: arial, helvetica, sans-serif; font-size: 14px;"> así:</span></p>
<pre>mkdir dir1                # crear un directorio llamado dir1
mkdir dir1 dir2           # crear dos directorios a la vez
mkdir -p /dir1/dir2/dir3  # crear una estructura de directorios, si no existe.</pre>
<p>
<span style="font-family: arial, helvetica, sans-serif; font-size: 14px;">Para eliminar ficheros y directorios:</span></p>
<pre>rm file1                  # eliminar el archivo file1
rm -f file1               # eliminar el archivo file1 en modo forzado
rm -r dir1                # eliminar recursivamente el directorio dir1 con todo lo que contenga
rm -rf dir1 dir2          # borrar dos directorios con su contenido de forma recursiva y forzado</pre>
<p>
<span style="font-family: arial, helvetica, sans-serif; font-size: 14px;">Para mover (renombrar) y copiar ficheros y carpetas necesitaremos dos comandos diferentes:</span></p>
<pre>mv old_dir new_dir            # renombrar o mover un fichero o directorio
cp file1 /ruta/a/destino/     # copiar un fichero al destino
cp file1 file2 destino/       # copiar a la vez dos ficheros
cp file1 file2                # copiar file1 en file2
cp -r dir1 destino/           # copiar un directorio.</pre>
<p>
<span style="font-family: arial, helvetica, sans-serif; font-size: 14px;">Para crear enlaces simbólicos (accesos directos):</span></p>
<pre>ln -s file link               # crear un enlace simbólico al fichero o directorio</pre>
<p>
<span style="font-family: arial, helvetica, sans-serif; font-size: 14px;">Para encontrar archivos existen varias opciones una de las más comunes es "</span><em style="font-family: arial, helvetica, sans-serif; font-size: 14px;">find"</em><span style="font-family: arial, helvetica, sans-serif; font-size: 14px;">, sin embargo para algunos usuarios les es molesto ya que puede llegar a tardar mucho en sistemas muy grandes, por lo que prefieren "</span><em style="font-family: arial, helvetica, sans-serif; font-size: 14px;">locate"</em><span style="font-family: arial, helvetica, sans-serif; font-size: 14px;">, para que este comando funcione bien, la base de datos de ficheros debe estar actualizada mediante el comando "</span><em style="font-family: arial, helvetica, sans-serif; font-size: 14px;">updatedb"</em><span style="font-family: arial, helvetica, sans-serif; font-size: 14px;">.</span></p>
<pre>find / -name file1                       # buscar fichero y directorio a partir de la raíz del sistema
find / -user user1                       # pertenecientes al usuario user1
find /home/user1 -name \*.bin            # con extensión .bin dentro del directorio / home/user1
find /usr/bin -type f -atime +100        # ficheros binarios no usados en los últimos 100 días
find /usr/bin -type f -mtime -10         # ficheros creados o cambiados dentro de los últimos 10 días
locate \*.ps                             # encuentra ficheros con extensión .ps
whereis file                             # mostrar la ubicación de un fichero binario, de ayuda o fuente
which comando                            # mostrar la ruta completa a un comando</pre>
<p>
&nbsp;</p>
<h1>
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;">Referencias</span></span></h1>
<ol>
<li>
<span style="font-size: 14px;"><span style="font-family: arial, helvetica, sans-serif;">Red Hat Enterprise Linux: Manual de referencia</span></span></li>
</ol>