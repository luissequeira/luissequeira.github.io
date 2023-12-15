---
layout: post
title:  Comandos útiles para obtener información del sistema y gestionar sesión
date:   2013-12-12 06:00:00
description: En este caso, se presentan una serie de comandos que nos permiten obtener cierta información del sistema y gestionar la sesión.
tags: GNU consola terminal linux
categories: Tutorials
---
<p>
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;">En un artículo anterior se mostraba el uso de algunos <a href="index.php/es/zona-linux/tutoriales/item/41-como-gestionar-archivos-y-directorios-gnu-linux.html">comandos útiles para la manipulación de ficheros y directorios</a>, en este caso, se presentan una serie de comandos que nos permiten obtener cierta <strong>información del sistema</strong>, o bien, como la visualización del <strong>contenido de ciertos ficheros también puede dar información</strong> útil. Además, se describirá el uso de comandos para gestionar la sesión.</span></span></p>

<p>
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;">Empezaremos con algunos comandos para obtener información del sistema como: características del kernel y arquitectura.</span></span></p>
<pre>arch              # arquitectura de la máquina
uname -m          # arquitectura de la máquina
uname -r          # versión del kernel
uname -a          # información completa
cat /etc/issue    # nombre de la distribución</pre>
<p>
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;">Recordemos que en Linux todo se guarda en archivos, así que si queremos ver una <strong>información detallada del sistema</strong> el directorio <em>"/proc"</em> nos será de mucha ayuda, ya que&nbsp;<strong>contiene la jerarquía de archivos que representan el estado actual del kernel</strong>. Dentro que en este directorio se puede encontrar una gran cantidad de información sobre el hardware y cualquier proceso que se esté ejecutando. Si al entrar en dicho directorio te das cuenta que los ficheros tienen 0 bytes, no te preocupes es normal, ya que el directorio <em>"/proc"</em> contiene otro tipo de archivos llamados&nbsp;<strong>archivos virtuales</strong>, a diferencia de los conocidos archivos de texto y binarios con los que estarás más familiarizado. A continuación algunos ejemplos:</span></span></p>
<pre>cat /proc/cpuinfo         # mostrar información de la CPU
cat /proc/interrupts      # mostrar las interrupciones
cat /proc/meminfo         # verificar el uso de memoria
cat /proc/mounts          # mostrar el sistema de ficheros montado
cat /proc/swaps           # mostrar ficheros swap
cat /proc/version         # mostrar versión del kernel
cat /proc/net/dev         # mostrar adaptadores de red y estadísticas
lspci -tv                 # mostrar dispositivos PCI
lsusb -tv                 # mostrar dispositivos USB</pre>
<p>
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;">Por otro lado, si lo que quieres es <strong>monitorizar el sistema en tiempo real</strong>, el siguiente comando es el indicado. Cuando se está utilizando se pueden digitar algunas opciones: <em>h – ayuda, u – usuario, p – PID, q – salir</em>.</span></span></p>
<pre>top      # mostrar tareas de Linux</pre>
<p>
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;">Para fechas, calendarios y hora también tenemos dos comandos útiles:</span></span></p>
<pre>date                     # mostrar la fecha del sistema
date 041217002011.00     # ajustar fecha y hora
cal 2011                 # mostrar calendario del 2011
cal 02 2009              # mostrar calendario para el mes febrero de 2009
clock -w                 # guardar los cambios de fecha en la BIOS</pre>
<p>
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;">Para ver el <strong>espacio que consumen discos</strong>, directorios o ficheros podemos utilizar diferentes comandos como <em>"ls"</em>, <em>"df"</em> y <em>"du"</em>. A continuación se combinan con otros comandos para optimizar la visualización:</span></span></p>
<pre>ls -lSr | more                    # mostrar tamaño de ficheros y directorios ordenados por tamaño
df -h                             # mostrar lista de particiones montadas
du -sh dir1                       # Estimar el espacio usado por el directorio dir1
du -h --max-depth=1 | sort -nr    # mostrar tamaño de subdirectorios en orden descendente
du -sk * | sort -rn               # mostrar el tamaño de los ficheros y directorios ordenados por tamaño</pre>
<p>
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;">Para finalizar, apagar, reiniciar o cerrar sesión:</span></span></p>
<pre>shutdown -h 23:17         # apagado planificado a las 23:17
shutdown -c               # cancelar un apagado planificado
shutdown -h now           # apagar el sistema
shutdown -r now           # reiniciar
halt                      # apagar el sistema
poweroff                  # apagar sistema
reboot                    # reiniciar
logout                    # cerrar sesión</pre>
<p>
&nbsp;</p>
<h1>
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;">Referecias</span></span></h1>
<ol>
<li>
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;">Red Hat Enterprise Linux: Manual de referencia</span></span></li>
</ol>