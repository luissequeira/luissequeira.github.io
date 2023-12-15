---
layout: post
title:  Las 2 mejores herramientas para la captura y la interpretación de datos de red
date:   2013-12-05 06:00:00
description: Las aplicaciones para capturar paquetes en la red como tcpdump y wireshark son bien conocidas por sus características, además de la captura de datos, estas aplicaciones son útiles para realizar ciertos análisis con los datos obtenidos.
tags: captura tcpdump wireshark medidas-de-red telemática
categories: Tools
---
<p>
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;">Les presento mis <strong>aplicaciones favoritas para la captura</strong> de paquetes en la red, si bien es cierto son muy conocidas por sus características, he decidido dar un pequeño espacio para comentar algunas de sus funcionalidades. Además de la captura de datos, estas aplicaciones son útiles para realizar ciertos <strong>análisis con los paquetes obtenidos</strong>, por otro lado, cuando el análisis que necesitamos realizar es un poco complejo o muy específico, siempre es recomendable construir nuestros propios scripts; pero no cabe duda que sin importar para que las utilicemos, nos <strong>será de gran ayuda para obtener información</strong> de la red.&nbsp;Estas applicaciones también se pueden combinar con <a href="index.php/es/investigacion/herramientas/item/29-generadores-de-trafico.html">generadores de tráfico</a> con el fin de analizar algunos problemas de la red.</span></span></p>
<h2>
&nbsp;</h2>
<h2>
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;">TCPDUM</span></span></h2>
<p>
<span style="font-family: arial, helvetica, sans-serif; font-size: 14px;">TCPDUMP </span><span style="font-family: arial, helvetica, sans-serif; font-size: 14px; color: rgb(255, 140, 0);"><strong>[1]</strong></span><span style="font-family: arial, helvetica, sans-serif; font-size: 14px;"> es una herramienta para </span><strong style="font-family: arial, helvetica, sans-serif; font-size: 14px;">captura del tráfico que circula por la red en tiempo real</strong><span style="font-family: arial, helvetica, sans-serif; font-size: 14px;">, esto incluye los paquetes </span><strong style="font-family: arial, helvetica, sans-serif; font-size: 14px;">transmitidos y recibidos</strong><span style="font-family: arial, helvetica, sans-serif; font-size: 14px;"> en una determinada interfaz de red determinada. Dicha herramienta carece de interfaz gráfica, esto lo convierte en una de las aplicaciones preferidas cuando se quiere usar los </span><strong style="font-family: arial, helvetica, sans-serif; font-size: 14px;">mínimos recursos posibles</strong><span style="font-family: arial, helvetica, sans-serif; font-size: 14px;">, además, de ser idónea para la captura de paquetes en forma </span><strong style="font-family: arial, helvetica, sans-serif; font-size: 14px;">desatendida</strong><span style="font-family: arial, helvetica, sans-serif; font-size: 14px;">, ya que se puede gestionar </span><strong style="font-family: arial, helvetica, sans-serif; font-size: 14px;">por línea de comandos</strong><span style="font-family: arial, helvetica, sans-serif; font-size: 14px;">&nbsp;como se puede apreciar en la <span style="color:#0000ff;"><strong>Figura # 1</strong></span>.</span></p>
<p>
&nbsp;</p>
<p style="text-align: center;">
<img alt="" class="caption" src="images/Research/las-dos-mejores-herramientas-para-la-captura-de-trafico/1.jpg" title="Vista del contenido de varios paquetes por línea de comando utilizando TCPDUMP." /></p>
<p style="text-align: center;">
<strong style="font-family: arial, helvetica, sans-serif; font-size: 14px;"><span style="color:#0000ff;">Figura # 1</span></strong><span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;">:&nbsp;Vista del contenido de varios paquetes por línea de comando utilizando TCPDUMP.</span></span></p>

<p>
<span style="font-family: arial, helvetica, sans-serif; font-size: 14px;">Esta aplicaciónción se encuentra disponible para casi todos los sistemas operativos (en Windows se llama WinDUMP), hace uso de la librería libpcap en el casos se sistemas UNIX y winpcap para Windows, además, es la encargada de las capturas de paquetes. Esta herramienta </span><strong style="font-family: arial, helvetica, sans-serif; font-size: 14px;">permite la depuración de la salida</strong><span style="font-family: arial, helvetica, sans-serif; font-size: 14px;"> obtenida por medio de filtros, permitiendo </span><strong style="font-family: arial, helvetica, sans-serif; font-size: 14px;">filtrar capturas</strong><span style="font-family: arial, helvetica, sans-serif; font-size: 14px;"> de puerto específico, o filtrando </span><strong style="font-family: arial, helvetica, sans-serif; font-size: 14px;">por tipo de protocolo</strong><span style="font-family: arial, helvetica, sans-serif; font-size: 14px;">, dirección origen o destino, en una </span><strong style="font-family: arial, helvetica, sans-serif; font-size: 14px;">interfaz</strong><span style="font-family: arial, helvetica, sans-serif; font-size: 14px;"> en específico y otros.</span></p>
<p>
<span style="font-family: arial, helvetica, sans-serif; font-size: 14px;">La instalación de tcpdump en sistemas operativos Linux usualmente no es necesaria, ya que viene instalado por defecto en la mayoría de las distribuciones, pero si fuera necesario, basta con instalar mediante el gestor de paquetes de nuestra distribución, de fijo estará en los repositorios, pero si quieres compilarlo tu mismo puedes descargarlo </span><a href="http://www.tcpdump.org/#latest-release" style="font-family: arial, helvetica, sans-serif; font-size: 14px;" target="_blank">aquí</a><span style="font-family: arial, helvetica, sans-serif; font-size: 14px;">. Para sistemas Windows puedes descargar </span><a href="http://www.winpcap.org/windump/install/default.htm" style="font-family: arial, helvetica, sans-serif; font-size: 14px;" target="_blank">aquí</a><span style="font-family: arial, helvetica, sans-serif; font-size: 14px;">.</span></p>
<h2>
&nbsp;</h2>
<h2>
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;">Wireshark</span></span></h2>
<p>
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;">Wireshark <span style="color:#ff8c00;"><strong>[2]</strong></span> es un <strong>programa de análisis</strong>, mantenido bajo licencia GNU GPL (GNU General Public License), también hace uso de las mismas librerías de captura de paquete de las que se utilizan en TCPDUMP, dependiendo del sistema operativo. A diferencia de TCPDUMP, Wireshark permite su gestión mediante una <strong>interfaz gráfica amigable</strong>&nbsp;(ver&nbsp;</span></span><strong style="text-align: center; font-family: arial, helvetica, sans-serif; font-size: 14px;"><span style="color: rgb(0, 0, 255);">Figura # 2</span></strong><span style="font-family: arial, helvetica, sans-serif; font-size: 14px;">) con el usuario sin la posibilidad de una gestión desatendida, además, posee </span><strong style="font-family: arial, helvetica, sans-serif; font-size: 14px;">funciones de filtrado y análisis</strong><span style="font-family: arial, helvetica, sans-serif; font-size: 14px;"> de tráfico como </span><strong style="font-family: arial, helvetica, sans-serif; font-size: 14px;">estadísticas, gráficos</strong><span style="font-family: arial, helvetica, sans-serif; font-size: 14px;"> y otras utilidades. Es compatible con el formato de archivo que utiliza TCPDUMP y reconoce una gran cantidad de protocolos.</span></p>
<p>
&nbsp;</p>
<p style="text-align: center;">
<img alt="" src="images/Research/las-dos-mejores-herramientas-para-la-captura-de-trafico/2.jpg" /></p>
<p style="text-align: center;">
<strong style="font-family: arial, helvetica, sans-serif; font-size: 14px;"><span style="color: rgb(0, 0, 255);">Figura # 2</span></strong><span style="font-size: 14px;"><span style="font-family: arial, helvetica, sans-serif;">:&nbsp;Vista del contenido de un paquete UDP utilizando Wireshark.</span></span></p>
<p style="text-align: center;">
&nbsp;</p>
<p>
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;">Otra característica interesante para los investigadores es que <strong>permite la exportación de los archivos</strong> de capturas a diferentes formatos de aplicaciones orientadas al análisis matemático o de bases de datos, algo que puede resultar útil para realizar un análisis más detallado, como por ejemplo, cálculos de retardos, MOS, estadísticas y otras magnitudes que se puedan extraer de la captura de paquetes en la red.</span></span></p>
<p>
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;">Para la instalación en sistemas Linux, esta aplicación usualmente se encuentra en los repositorios, así que se utiliza el gestor de paquetes según la distribución, si no lo encuentras o usas Windows lo puedes descargar <a href="http://www.wireshark.org/download.html" target="_blank">aquí</a>.</span></span></p>
<h2>
&nbsp;</h2>
<h2>
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;">Referencias</span></span></h2>
<ol>
<li>
<a href="http://www.tcpdump.org/" target="_blank"><span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;">http://www.tcpdump.org/</span></span></a></li>
<li>
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;"><a href="http://www.wireshark.org/" target="_blank">http://www.wireshark.org/</a></span></span></li>
</ol>
<div id="ckimgrsz" style="left: 8px; top: 322.34375px;">
<div class="preview" style="background-image: url(http://localhost/telecomsharing/images/Research/las-dos-mejores-herramientas-para-la-captura-de-trafico/1.jpg); display: none; top: 0px; left: 0px; width: 875px; height: 407.453125px;">
&nbsp;</div>
</div>