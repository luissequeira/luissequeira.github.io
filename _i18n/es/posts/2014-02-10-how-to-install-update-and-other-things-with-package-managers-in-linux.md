---
layout: post
title:  ¿Cómo instalar, actualizar y otras cosas con gestores de paquetes en Linux?
date:   2014-02-13 06:00:00
description: Los gestores de paquetes son herramientas que automatizan el proceso de instalación, actualización, desintalación o configuración del software en Linux. 
tags: linux consola terminal GNU
categories: Tutorials
---
<p>
<span style="font-family: arial, helvetica, sans-serif; font-size: 14px;"><strong>Los gestores de paquetes son herramientas que automatizan el proceso de instalación, actualización, desintalación o configuración del software</strong> en Linux. Los gestores de paquetes <strong>forman parte del sistema operativo</strong> y utilizan una única base de datos para la instalación y un único formato de paquetes, por ejemplo: rpm o deb. También se encargan de la comprobación de la firma digital, resolución de dependencias y búsqueda de actualizaciones.</span></p>

<p>
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;">Actualmente, la gran mayoría de los sistemas operativos Linux poseen interfaces gráficas para sus gestores de paquetes que son muy intuitivas y fáciles de usar. Por este motivo, comentaremos algunas funciones básicas de los gestores más conocidos, pero por línea de comandos ya que son los que comúnmente nos generan más inquietudes.</span></span></p>
<p>
&nbsp;</p>
<h1>
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;">Gestor de paquetes YUM (Yellow dog Updater, Modified)</span></span></h1>
<p>
<span style="font-family: arial, helvetica, sans-serif; font-size: 14px;">Es el <strong>gestor de paquetes para sistemas Linux basados en RPM</strong> como lo es Fedora, Redhat, CentOS y sus derivados como BlueCat. Algunos de los usos más comunes son:</span></p>
<pre>yum install paquete                     # descargar e instalar un paquete y sus dependencias
yum localinstall paquete.rpm            # instalar un paquete previamente descargado y sus dependencias
yum update                              # actualizar todos los paquetes instalados
yum update paquete                      # actualizar un paquete
yum remove paquete                      # eliminar un paquete
yum list                                # listar todos los paquetes instalados
yum search paquete                      # buscar un paquete en repositorio
yum clean all                           # eliminar caché de paquetes, encabezados y otros</pre>
<p>
&nbsp;</p>
<h1>
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;">Gestor de paquetes DPKG </span></span></h1>
<p>
<span style="font-family: arial, helvetica, sans-serif; font-size: 14px;">Este es la base del <strong>sistema de gestión de paquetes de Debian, y por lo tanto, también es utilizado por distribuciones como Ubuntu y sus derivados</strong>. Algunos ejemplos son:</span></p>
<pre>dpkg -i paquete.deb          # instalar un paquete
dpkg -r paquete              # eliminar un paquete
dpkg -l                      # mostrar todos los paquetes instalados
dpkg -l | grep httpd         # mostrar todos los paquetes con el nombre “httpd”
dpkg -s paquete              # obtener información en un paquete específico instalado en el sistema.
dpkg -L paquete              # mostar lista de ficheros de un paquete instalado
dpkg -S /bin/ping            # verificar a cuál paquete pertenece a un fichero</pre>
<p>
&nbsp;</p>
<h1>
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;">Gestor de paquetes APT y APTITUDE (Debian, Ubuntu y otros)</span></span></h1>
<p>
<span style="font-family: arial, helvetica, sans-serif; font-size: 14px;">APT (Advanced Packaging Tool) no es realmente un programa, sino, una biblioteca de C++ que es utilizada por varios programas, por ejemplo, apt-get o apt-cache. Por otro lado, aptitude es una interfaz para apt que facilita al usuario los sistemas de búsqueda y las resoluciones de dependencias entre otras cosas. <strong>Ambos gestores de paquetes tienen comandos y opciones similares a las que ya hemos descrito</strong>, como se puede ver a continuación:</span></p>
<pre>apt-get install paquete                # instalar un paquete
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
aptitude clean                         # limpia la cache de paquetes.</pre>
<p>
<span style="font-family: arial, helvetica, sans-serif; font-size: 14px;">PD: Te gustan las vacas? escribe en un terminal: apt-get moo</span></p>
<p>
&nbsp;</p>
<h1>
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;">Referencias</span></span></h1>
<ol>
<li>
<a href="http://yum.baseurl.org/" style="font-family: arial, helvetica, sans-serif; font-size: 14px;">http://yum.baseurl.org/</a></li>
<li>
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;">http://www.debian.org/doc/manuals/debian-faq/ch-pkgtools.en.html</span></span></li>
<li>
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;"><a href="http://www.debian.org/doc/manuals/apt-howto/index.es.html">http://www.debian.org/doc/manuals/apt-howto/index.es.html</a></span></span></li>
<li>
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;"><a href="http://algebraicthunk.net/~dburrows/projects/aptitude/">http://algebraicthunk.net/~dburrows/projects/aptitude/</a></span></span></li>
</ol>