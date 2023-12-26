---
layout: post
title:  Generadores de tráfico
date:   2013-11-14 07:00:00
description: Los generadores de tráfico son útiles para emular el tráfico de ciertas aplicaciones o servicios de red y no tener la necesidad de tener operando dichas aplicaciones, en mi caso particular los he utilizado para emular tráfico de VoIP, video streaming, video vigilancia y hasta para hacer un poco de ingeniería inversa a ciertos equipos comerciales.
tags: generadores-de-tráfico telemática tráfico
categories: Networks Innovation
thumbnail: assets/img/Research/generadores-de-trafico/topology.jpg
---

<div class="row mt-3" style="text-align: center">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="assets/img/Research/generadores-de-trafico/topology.jpg" class="img-fluid rounded z-depth-1" %}
    </div>
</div>

Desde hace ya algún tiempo he estado utilizando diversos generadores de tráfico y hoy me ha surgido la inquietud de compartir 3 de los que más utilizo por sus interesantes funcionalidades. Los generadores de tráfico son útiles para **emular el tráfico** de ciertas aplicaciones o servicios de red y no tener la necesidad de tener operando dichas aplicaciones, en mi caso particular los he utilizado para emular tráfico de **VoIP, video streaming, video vigilancia** y hasta para hacer un poco de ingeniería inversa a ciertos equipos comerciales. A continuación les dejo una pequeña reseña de cada uno de ellos:

## JTG

El JTG (“Jugi's Traffic Generator”) es un generador de tráfico IP gestionado por **línea de comandos**, desarrollado por la Universidad de Helsinki [1], permite generar tráfico paramétrico y reproducir tráfico a partir de archivos con intervalos de tiempo y tamaños de paquetes a enviar en cada intervalo de tiempo. Por otro lado, provee un receptor para recoger el tráfico, a partir del cual se **pueden calcular estadísticas**. El JTG incluye un programa llamado `jtg_calc` que a partir del log de paquetes recibidos realiza un análisis estadístico de **pérdidas, retardos y jitter**. Para el caso de IPv6 también se encuentra una versión del generador llamada JTG6.

## D-ITG

Otro generador de tráfico IP multiprotocolo (IPv4 y IPv6), desarrollado por la Universidad de Nápoles, es el D-ITG [2]. Este generador también **permite el análisis de los datos enviados o recibidos**, así [como realizar capturas en ambos extremos de la comunicación]({% post_url 2013-12-02-the-2-best-tools-for-the-capture-and-the-interpretation-of-network-data %}), además, permite realizar medidas en un solo sentido OWD (one-way-delay) y de ida y vuelta RTT (round-trip-time), además **soporta protocolos como**: TCP (“Transmission Control Protocol”), UDP (“User Datagram Protocol”), SCTP(“Stream Control Transmission Protocol”) y DCCP (“Datagram Congestion Control Protocol”). Puede ser gestionado mediante **línea de comandos o por medio de GUI** (“Graphical User Interface”) que puede ser obtenida en la misma página web del proyecto.

## ETG

Recientemente, en el GTC (Grupo de Tecnologías de la Comunicación) de la Universidad de Zaragoza [3], ha implementado una herramienta denominada ETG (“E2E Trafic Generator”) [4], inicialmente implementada para el análisis de enlaces en el **transporte de voz sobre IP** y que actualmente se ha generalizado para generar diversos tipos de flujos IP.

Esta herramienta permite calcular parámetros objetivos de calidad como: **retardo, jitter, y tasa de pérdidas**, y otros subjetivos de QoS como: **factor R y MOS**. Se trata de una herramienta capaz de realizar comunicaciones E2E entre usuarios mediante el envío y recepción de varias secuencias de ráfagas de tráfico UDP. Permite generar tráfico OWD y RTT, así como capturas en ambos puntos de la comunicación, además, mediante el análisis del tráfico recibido se obtienen los parámetros de retardo, pérdidas y jitter, con los cuales podemos calcular el factor R que determina el MOS para cada comunicación.

Una ventaja de esta aplicación:

- La facilidad que presenta para la **repetibilidad** de la pruebas ya que contempla mecanismos que permiten la automatización de ciertas funciones facilitando el trabajo a los investigadores, como por ejemplo: cada flujo se podrá reiterar cada cierto tiempo entre una fecha y hora inicial y final.
- **Generar tráfico equivalente** al de diferentes servicios.
- Permite el envío de paquetes **a partir de un fichero** con los intervalos de transmisión de paquetes y el tamaño.
- Además, emular comunicaciones cuando los tiempos y tamaños de paquete no son constantes y nos **garantiza poder repetir las pruebas** en las mismas condiciones.

## Referencias

1. [http://www.cs.helsinki.fi/u/jmanner/software/](http://www.cs.helsinki.fi/u/jmanner/software/)
2. [http://traffic.comics.unina.it/software/ITG/](http://traffic.comics.unina.it/software/ITG/)
3. [http://www.gtc.cps.unizar.es/](http://www.gtc.cps.unizar.es/)
4. L. A. Casadesus Pazos, J. Fernández Navajas, J. Ruiz Mas, J. M. Saldana Medina, J. I. Aznar Baranda, E. Viruete Navarro. Herramienta para Automatización de Medidas de Tiempo Real Extremo a Extremo. Actas del XXVI Simposium Nacional de la Unión Científica Internacional de Radio (URSI 2011). Leganés (España). ISBN 9788493393458. Sept. 2011.
