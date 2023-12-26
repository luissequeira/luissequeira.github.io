---
layout: post
title:  ¿Cómo instalar, actualizar y otras cosas con gestores de paquetes en Linux?
date:   2014-02-13 06:00:00
description: Los gestores de paquetes son herramientas que automatizan el proceso de instalación, actualización, desintalación o configuración del software en Linux. 
tags: consola terminal comandos
categories: Linux
thumbnail: assets/img/Linux/como-instalar-actualizar-gestores-paquetes-linux/1.jpg
---

<div class="row mt-3" style="text-align: center">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="assets/img/Linux/como-instalar-actualizar-gestores-paquetes-linux/1.jpg" class="img-fluid rounded z-depth-1" %}
    </div>
</div>

**Los gestores de paquetes son herramientas que automatizan el proceso de instalación, actualización, desintalación o configuración del software** en Linux. Los gestores de paquetes **forman parte del sistema operativo** y utilizan una única base de datos para la instalación y un único formato de paquetes, por ejemplo: `rpm` o `deb`. También se encargan de la comprobación de la firma digital, resolución de dependencias y búsqueda de actualizaciones.

Actualmente, la gran mayoría de los sistemas operativos Linux poseen interfaces gráficas para sus gestores de paquetes que son muy intuitivas y fáciles de usar. Por este motivo, comentaremos algunas funciones básicas de los gestores más conocidos, pero por línea de comandos ya que son los que comúnmente nos generan más inquietudes.

## Gestor de paquetes YUM (Yellow dog Updater, Modified)

Es el **gestor de paquetes para sistemas Linux basados en RPM** como lo es Fedora, Redhat, CentOS y sus derivados como BlueCat. Algunos de los usos más comunes son:

```sh
yum install paquete                     # descargar e instalar un paquete y sus dependencias
yum localinstall paquete.rpm            # instalar un paquete previamente descargado y sus dependencias
yum update                              # actualizar todos los paquetes instalados
yum update paquete                      # actualizar un paquete
yum remove paquete                      # eliminar un paquete
yum list                                # listar todos los paquetes instalados
yum search paquete                      # buscar un paquete en repositorio
yum clean all                           # eliminar caché de paquetes, encabezados y otros
```

## Gestor de paquetes DPKG 

Este es la base del **sistema de gestión de paquetes de Debian, y por lo tanto, también es utilizado por distribuciones como Ubuntu y sus derivados**. Algunos ejemplos son:

```sh
dpkg -i paquete.deb          # instalar un paquete
dpkg -r paquete              # eliminar un paquete
dpkg -l                      # mostrar todos los paquetes instalados
dpkg -l | grep httpd         # mostrar todos los paquetes con el nombre “httpd”
dpkg -s paquete              # obtener información en un paquete específico instalado en el sistema.
dpkg -L paquete              # mostar lista de ficheros de un paquete instalado
dpkg -S /bin/ping            # verificar a cuál paquete pertenece a un fichero
```

## Gestor de paquetes APT y APTITUDE (Debian, Ubuntu y otros)

APT (Advanced Packaging Tool) no es realmente un programa, sino, una biblioteca de C++ que es utilizada por varios programas, por ejemplo, apt-get o apt-cache. Por otro lado, aptitude es una interfaz para apt que facilita al usuario los sistemas de búsqueda y las resoluciones de dependencias entre otras cosas. *Ambos gestores de paquetes tienen comandos y opciones similares a las que ya hemos descrito**, como se puede ver a continuación:

```sh
apt-get install paquete                # instalar un paquete
apt-cdrom install paquete              # instalar un paquete desde un cdrom
apt-get update                         # actualizar la lista de paquetes
apt-get upgrade                        # actualizar todos los paquetes instalados
apt-get remove paquete                 # eliminar un paquete
apt-get check                          # verificar las dependencias.
apt-get clean                          # limpiar cache
apt-cache search paquete               # lista los paquetes que corresponde a “paquete”
aptitude search paquete                # busca un paquete por el nombre
aptitude show paquete | less           # muestra información sobre un paquete
aptitude install paquete1 paquete2 …   # instala varios paquetes con sus dependencias
aptitude remove paquete                # desinstala un paquete.
aptitude purge paquete                 # desinstala un paquete y lo limpia de la cache
aptitude clean                         # limpia la cache de paquetes.
```

> PD: Do you like cows? writes in a terminal: `apt-get moo`

## References

1. [http://yum.baseurl.org/](http://yum.baseurl.org/)
2. [http://www.debian.org/doc/manuals/debian-faq/ch-pkgtools.en.html](http://www.debian.org/doc/manuals/debian-faq/ch-pkgtools.en.html)
3. [http://www.debian.org/doc/manuals/apt-howto/index.es.html](http://www.debian.org/doc/manuals/apt-howto/index.es.html)
4. [http://algebraicthunk.net/~dburrows/projects/aptitude/](http://algebraicthunk.net/~dburrows/projects/aptitude/)
