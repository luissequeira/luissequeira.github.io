---
layout: post
title:  Generadores de tráfico
date:   2013-11-14 07:00:00
description: Los generadores de tráfico son útiles para emular el tráfico de ciertas aplicaciones o servicios de red y no tener la necesidad de tener operando dichas aplicaciones, en mi caso particular los he utilizado para emular tráfico de VoIP, video streaming, video vigilancia y hasta para hacer un poco de ingeniería inversa a ciertos equipos comerciales.
tags: generadores-de-tráfico telemática tráfico aplicaciones medidas-de-red etg ditg jtg
categories: Tools
---
<p>
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;">Desde hace ya algún tiempo he estado utilizando diversos generadores de tráfico y hoy me ha surgido la inquietud de compartir 3 de los que más utilizo por sus interesantes funcionalidades. Los generadores de tráfico son útiles para <strong>emular el tráfico</strong> de ciertas aplicaciones o servicios de red y no tener la necesidad de tener operando dichas aplicaciones, en mi caso particular los he utilizado para emular tráfico de<strong> VoIP, video streaming, video vigilancia</strong> y hasta para hacer un poco de ingeniería inversa a ciertos equipos comerciales. A continuación les dejo una pequeña reseña de cada uno de ellos:</span></span></p>
<p>
&nbsp;</p>

<h2>
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;">JTG</span></span></h2>
<p>
<span style="font-family: arial, helvetica, sans-serif; font-size: 14px;">El JTG (“Jugi's Traffic Generator”) es un generador de tráfico IP gestionado por <strong>línea de comandos</strong>, desarrollado por la Universidad de Helsinki <span style="color:#ff8c00;"><strong>[1]</strong></span>, permite generar tráfico paramétrico y reproducir tráfico a partir de archivos con intervalos de tiempo y tamaños de paquetes a enviar en cada intervalo de tiempo. Por otro lado, provee un receptor para recoger el tráfico, a partir del cual se <strong>pueden calcular estadísticas</strong>. El JTG incluye un programa llamado jtg_calc que a partir del log de paquetes recibidos realiza un análisis estadístico de<strong> pérdidas, retardos y jitter</strong>. Para el caso de IPv6 también se encuentra una versión del generador llamada JTG6.</span></p>
<p>
&nbsp;</p>
<p>
<span style="font-family: arial, helvetica, sans-serif; font-size: 14px; color: rgb(68, 68, 68);">D-ITG</span></p>
<p>
<span style="font-family: arial, helvetica, sans-serif; font-size: 14px;">Otro generador de tráfico IP multiprotocolo (IPv4 y IPv6), desarrollado por la Universidad de Nápoles, es el D-ITG <span style="color:#ff8c00;"><strong>[2]</strong></span>. Este generador también <strong>permite el análisis de los datos enviados o recibidos</strong>, así <a href="http://www.telecomsharing.com/es/laboratorio/herramientas/item/30-las-2-mejores-herramientas-para-la-captura-y-la-interpretacion-de-datos-de-red">como realizar capturas en ambos extremos de la comunicación</a>, además, permite realizar medidas en un solo sentido OWD (one-way-delay) y de ida y vuelta RTT (round-trip-time), además <strong>soporta protocolos como</strong>: TCP (“Transmission Control Protocol”), UDP (“User Datagram Protocol”), SCTP(“Stream Control Transmission Protocol”) y DCCP (“Datagram Congestion Control Protocol”). Puede ser gestionado mediante<strong> línea de comandos o por medio de GUI</strong> (“Graphical User Interface”) que puede ser obtenida en la misma página web del proyecto.</span></p>
<h2>
&nbsp;</h2>
<h2>
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;">ETG</span></span></h2>
<p>
<span style="font-family: arial, helvetica, sans-serif; font-size: 14px;">Recientemente, en el GTC (Grupo de Tecnologías de la Comunicación) de la Universidad de Zaragoza <span style="color:#ff8c00;"><strong>[3]</strong></span>, ha implementado una herramienta denominada ETG (“E2E Trafic Generator”) <strong><span style="color:#ff8c00;">[4]</span></strong>, inicialmente implementada para el análisis de enlaces en el <strong>transporte de voz sobre IP</strong> y que actualmente se ha generalizado para generar diversos tipos de flujos IP.</span></p>
<p>
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;">Esta herramienta permite calcular parámetros objetivos de calidad como: <strong>retardo, jitter, y tasa de pérdidas</strong>, y otros subjetivos de QoS como: <strong>factor R y MOS</strong>. Se trata de una herramienta capaz de realizar comunicaciones E2E entre usuarios mediante el envío y recepción de varias secuencias de ráfagas de tráfico UDP. Permite generar tráfico OWD y RTT, así como capturas en ambos puntos de la comunicación, además, mediante el análisis del tráfico recibido se obtienen los parámetros de retardo, pérdidas y jitter, con los cuales podemos calcular el factor R que determina el MOS para cada comunicación.</span></span></p>
<p>
<span style="font-family: arial, helvetica, sans-serif; font-size: 14px;">Una ventaja de esta aplicación:</span></p>
<ul>
<li>
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;">La facilidad que presenta para la <strong>repetibilidad</strong> de la pruebas ya que contempla mecanismos que permiten la automatización de ciertas funciones facilitando el trabajo a los investigadores, como por ejemplo: cada flujo se podrá reiterar cada cierto tiempo entre una fecha y hora inicial y final.</span></span></li>
<li>
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;"><strong>Generar tráfico equivalente</strong> al de diferentes servicios.</span></span></li>
<li>
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;">Permite el envío de paquetes <strong>a partir de un fichero</strong> con los intervalos de transmisión de paquetes y el tamaño.</span></span></li>
<li>
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;">Además, emular comunicaciones cuando los tiempos y tamaños de paquete no son constantes y nos <strong>garantiza poder repetir las pruebas</strong> en las mismas condiciones.</span></span></li>
</ul>
<h2>
&nbsp;</h2>
<h2>
<span style="font-family: arial, helvetica, sans-serif; font-size: 14px;">Referencias</span></h2>
<ol>
<li>
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;"><a href="http://www.cs.helsinki.fi/u/jmanner/software/">http://www.cs.helsinki.fi/u/jmanner/software/</a></span></span></li>
<li>
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;"><a href="http://traffic.comics.unina.it/software/ITG/">http://traffic.comics.unina.it/software/ITG/</a></span></span></li>
<li>
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;"><a href="http://www.gtc.cps.unizar.es/">http://www.gtc.cps.unizar.es/</a></span></span></li>
<li>
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;">L. A. Casadesus Pazos, J. Fernández Navajas, J. Ruiz Mas, J. M. Saldana Medina, J. I. Aznar Baranda, E. Viruete Navarro. Herramienta para Automatización de Medidas de Tiempo Real Extremo a Extremo. Actas del XXVI Simposium Nacional de la Unión Científica Internacional de Radio (URSI 2011). Leganés (España). ISBN 9788493393458. Sept. 2011.</span></span></li>
</ol>