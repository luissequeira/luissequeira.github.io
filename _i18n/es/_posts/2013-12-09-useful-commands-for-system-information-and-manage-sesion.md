---
layout: post
title:  Comandos útiles para obtener información del sistema y gestionar sesión
date:   2013-12-12 06:00:00
description: En este caso, se presentan una serie de comandos que nos permiten obtener cierta información del sistema y gestionar la sesión.
tags: consola terminal linux comandos
categories: Linux
thumbnail: assets/img/Linux/como-obtener-informacion-sistema-gestionar-apagado-GNULinux/1.png
---

<div class="row mt-3" style="text-align: center">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="assets/img/Linux/como-obtener-informacion-sistema-gestionar-apagado-GNULinux/1.png" class="img-fluid rounded z-depth-1" %}
    </div>
</div>

En un artículo anterior se mostraba el uso de algunos [comandos útiles para la manipulación de ficheros y directorios]({% post_url 2013-11-18-how-to-manage-files-and-directories-on-gnu-linux %}), en este caso, se presentan una serie de comandos que nos permiten obtener cierta **información del sistema**, o bien, como la visualización del **contenido de ciertos ficheros también puede dar información** útil. Además, se describirá el uso de comandos para gestionar la sesión.

Empezaremos con algunos comandos para obtener información del sistema como: características del kernel y arquitectura.

```sh
arch              # arquitectura de la máquina
uname -m          # arquitectura de la máquina
uname -r          # versión del kernel
uname -a          # información completa
cat /etc/issue    # nombre de la distribución
```

Recordemos que en Linux todo se guarda en archivos, así que si queremos ver una **información detallada del sistema** el directorio `/proc` nos será de mucha ayuda, ya que **contiene la jerarquía de archivos que representan el estado actual del kernel**. Dentro que en este directorio se puede encontrar una gran cantidad de información sobre el hardware y cualquier proceso que se esté ejecutando. Si al entrar en dicho directorio te das cuenta que los ficheros tienen 0 bytes, no te preocupes es normal, ya que el directorio `/proc` contiene otro tipo de archivos llamados **archivos virtuales**, a diferencia de los conocidos archivos de texto y binarios con los que estarás más familiarizado. A continuación algunos ejemplos:

```sh
cat /proc/cpuinfo         # mostrar información de la CPU
cat /proc/interrupts      # mostrar las interrupciones
cat /proc/meminfo         # verificar el uso de memoria
cat /proc/mounts          # mostrar el sistema de ficheros montado
cat /proc/swaps           # mostrar ficheros swap
cat /proc/version         # mostrar versión del kernel
cat /proc/net/dev         # mostrar adaptadores de red y estadísticas
lspci -tv                 # mostrar dispositivos PCI
lsusb -tv                 # mostrar dispositivos USB
```

Por otro lado, si lo que quieres es **monitorizar el sistema en tiempo real**, el siguiente comando es el indicado. Cuando se está utilizando se pueden digitar algunas opciones: `h – ayuda`, `u – usuario`, `p – PID`, `q – salir`.

```sh
top      # mostrar tareas de Linux
```

Para fechas, calendarios y hora también tenemos dos comandos útiles:

```sh
date                     # mostrar la fecha del sistema
date 041217002011.00     # ajustar fecha y hora
cal 2011                 # mostrar calendario del 2011
cal 02 2009              # mostrar calendario para el mes febrero de 2009
clock -w                 # guardar los cambios de fecha en la BIOS
```

Para ver el **espacio que consumen discos**, directorios o ficheros podemos utilizar diferentes comandos como `ls`, `df` y `du`. A continuación se combinan con otros comandos para optimizar la visualización:

```sh
ls -lSr | more                    # mostrar tamaño de ficheros y directorios ordenados por tamaño
df -h                             # mostrar lista de particiones montadas
du -sh dir1                       # Estimar el espacio usado por el directorio dir1
du -h --max-depth=1 | sort -nr    # mostrar tamaño de subdirectorios en orden descendente
du -sk * | sort -rn               # mostrar el tamaño de los ficheros y directorios ordenados por tamaño
```

Para finalizar, apagar, reiniciar o cerrar sesión:

```sh
shutdown -h 23:17         # apagado planificado a las 23:17
shutdown -c               # cancelar un apagado planificado
shutdown -h now           # apagar el sistema
shutdown -r now           # reiniciar
halt                      # apagar el sistema
poweroff                  # apagar sistema
reboot                    # reiniciar
logout                    # cerrar sesión
```

## Refereces

1. Red Hat Enterprise Linux: Reference Manual