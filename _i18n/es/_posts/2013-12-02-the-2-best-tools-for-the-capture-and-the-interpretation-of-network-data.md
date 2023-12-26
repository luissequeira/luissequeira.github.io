---
layout: post
title:  Las 2 mejores herramientas para la captura y la interpretación de datos de red
date:   2013-12-05 06:00:00
description: Las aplicaciones para capturar paquetes en la red como tcpdump y wireshark son bien conocidas por sus características, además de la captura de datos, estas aplicaciones son útiles para realizar ciertos análisis con los datos obtenidos.
tags: tcpdump wireshark telemática tráfico
categories: Networks
thumbnail: assets/img/Research/las-dos-mejores-herramientas-para-la-captura-de-trafico/2.jpg
---
Les presento mis **aplicaciones favoritas para la captura** de paquetes en la red, si bien es cierto son muy conocidas por sus características, he decidido dar un pequeño espacio para comentar algunas de sus funcionalidades. Además de la captura de datos, estas aplicaciones son útiles para realizar ciertos **análisis con los paquetes obtenidos**, por otro lado, cuando el análisis que necesitamos realizar es un poco complejo o muy específico, siempre es recomendable construir nuestros propios scripts; pero no cabe duda que sin importar para que las utilicemos, nos **será de gran ayuda para obtener información** de la red. Estas applicaciones también se pueden combinar con [generadores de tráfico]({% post_url 2013-11-11-traffic-generators %}) con el fin de analizar algunos problemas de la red.

## TCPDUM

**TCPDUMP** [1] es una herramienta para **captura del tráfico que circula por la red en tiempo real**, esto incluye los paquetes **transmitidos y recibidos** en una determinada interfaz de red determinada. Dicha herramienta carece de interfaz gráfica, esto lo convierte en una de las aplicaciones preferidas cuando se quiere usar los **mínimos recursos posibles**, además, de ser idónea para la captura de paquetes en forma **desatendida**, ya que se puede gestionar **por línea de comandos** como se puede apreciar en la Figura #1.

<div class="row mt-3" style="text-align: center">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="assets/img/Research/las-dos-mejores-herramientas-para-la-captura-de-trafico/1.jpg" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Figure #1: Vista del contenido de varios paquetes por línea de comando utilizando **TCPDUMP**.
</div>

Esta aplicaciónción se encuentra disponible para casi todos los sistemas operativos (en Windows se llama WinDUMP), hace uso de la librería `libpcap` en el casos se sistemas UNIX y `winpcap` para Windows, además, es la encargada de las capturas de paquetes. Esta herramienta **permite la depuración de la salida** obtenida por medio de filtros, permitiendo **filtrar capturas** de puerto específico, o filtrando **por tipo de protocolo**, dirección origen o destino, en una **interfaz** en específico y otros.

La instalación de `tcpdump` en sistemas operativos Linux usualmente no es necesaria, ya que viene instalado por defecto en la mayoría de las distribuciones, pero si fuera necesario, basta con instalar mediante el gestor de paquetes de nuestra distribución, de fijo estará en los repositorios, pero si quieres compilarlo tu mismo puedes descargarlo [aquí](http://www.tcpdump.org/#latest-release). Para sistemas Windows puedes descargar [aquí](http://www.winpcap.org/windump/install/default.htm).

## Wireshark

Wireshark [2] es un **programa de análisis**, mantenido bajo licencia GNU GPL (GNU General Public License), también hace uso de las mismas librerías de captura de paquete de las que se utilizan en TCPDUMP, dependiendo del sistema operativo. A diferencia de TCPDUMP, Wireshark permite su gestión mediante una **interfaz gráfica amigable** (ver Figura #2) con el usuario sin la posibilidad de una gestión desatendida, además, posee **funciones de filtrado y análisis** de tráfico como **estadísticas, gráficos** y otras utilidades. Es compatible con el formato de archivo que utiliza TCPDUMP y reconoce una gran cantidad de protocolos.

<div class="row mt-3" style="text-align: center">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="assets/img/Research/las-dos-mejores-herramientas-para-la-captura-de-trafico/2.jpg" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Figura #2: Vista del contenido de un paquete UDP utilizando Wireshark.
</div>

Otra característica interesante para los investigadores es que **permite la exportación de los archivos** de capturas a diferentes formatos de aplicaciones orientadas al análisis matemático o de bases de datos, algo que puede resultar útil para realizar un análisis más detallado, como por ejemplo, cálculos de retardos, MOS, estadísticas y otras magnitudes que se puedan extraer de la captura de paquetes en la red.

Para la instalación en sistemas Linux, esta aplicación usualmente se encuentra en los repositorios, así que se utiliza el gestor de paquetes según la distribución, si no lo encuentras o usas Windows lo puedes descargar [aquí](http://www.wireshark.org/download).

## References

1. [http://www.tcpdump.org/](http://www.tcpdump.org/)
2. [http://www.wireshark.org/](http://www.wireshark.org/)