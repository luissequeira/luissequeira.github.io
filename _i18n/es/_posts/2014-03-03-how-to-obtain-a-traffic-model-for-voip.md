---
layout: post
title:  ¿Cómo obtener un modelo de tráfico para VoIP?
date:   2014-03-06 06:00:00
description: En este artículo se describe como obtener un modelo de tráfico para voip, el cual es bastante sencillo de interpretar y facilitará algunas de las cosas que se deben hacer.
tags: tráfico voip multimedia
categories: Networks Innovation 
thumbnail: assets/img/Research/como-obtener-modelo-trafico-voip/1.png
---
Para realizar las estimaciones del modelo de tráfico para flujos multimedia, es necesario que el investigador tenga un control preciso del entorno de pruebas, minimizando los posibles errores e interferencia que puedan presentarse, dejando un escenario de pruebas que permita un desarrollo fluido a la aplicación que se dese modelar. **A modo de ejemplo se ha seleccionado un tráfico de [VoIP]({% post_url 2014-02-24-what-is-voip %})**, el cual es bastante sencillo de interpretar y facilitará algunas de las cosas que se deben hacer.

## Escenario para las pruebas

**En la Figura #1 se muestra el diagrama utilizado para realizar las pruebas con la finalidad de obtener el modelo del tráfico en la transmisión de voz sobre IP**. En este caso, utilizaremos un *gateway* de voz sobre IP *Linksys SPA 3102*, con el fin de conectar un sistema telefónico convencional con una red IP y viceversa. Un sniffer permite la captura del tráfico que circula por la red para su posterior análisis.

<div class="row mt-3" style="text-align: center">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="assets/img/Research/como-obtener-modelo-trafico-voip/1.png" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Figura #1: Escenario utilizado para determinar el tráfico de voz.
</div>

## Procedimiento

**En primer lugar, se debe configurar el *gateway***, esto se hace con relativa facilidad por medio de un menú IVR (*Interative Voice Response*) o mediante cualquier navegador de Internet. Los aspectos más relevantes de la configuración son: la utilización de SIP (Session Initiation Protocol) como protocolo de señalización, asignación de direcciones IP a cada pasarela y la desactivación de NAT (Network Address Translation). Para la configuración de audio: uso del codec G.729, una paquetización de dos muestras por paquete y no se realiza supresión de silencio.

**Después de la configuración de los equipos se lanza el sniffer** para poder realizar la captura del tráfico, **posteriormente, se realiza una llamada entre los terminales**. Mediante el sniffer se realiza la captura de paquetes mientras la llamada está en curso y se almacenan los datos para su posterior análisis.

## Modelo de VoIP

Analizando la captura realizada, con alguna de las herramientas recomendadas [para la captura e interpretación de datos de red]({% post_url 2013-12-02-the-2-best-tools-for-the-capture-and-the-interpretation-of-network-data %}), **se puede reconstruir la distribución de los encabezados de cada uno de los paquetes capturados** y de esta manera deducir la Figura #2.

<div class="row mt-3" style="text-align: center">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="assets/img/Research/como-obtener-modelo-trafico-voip/2_en.png" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Figura #2: Descripción de los encabezados de cada paquete para el tráfico de voz.
</div>

Como se puede observar, **VoIP utiliza el protocolo RTP (Real-Time TRansport Protocol) para la transmisión de datos en tiempo real y este se transporta por medio de UDP**, la Figura #2 permite comprobar la utilización de los protocolos mencionados. **Se destaca en el análisis de la captura de paquetes realizada, que la transmisión de cada uno de los paquetes tiene una distribución constante (no se presentan ráfagas de paquetes)**. Además, se confirma que cada terminal realiza el envío de paquetes cada $$20 ms$$ y que el contenido de datos de dichos paquetes corresponde con el tipo de codec utilizado (G.729) y la cantidad de muestras que se definieron en la configuración de cada gateway (dos muestras por paquete).

Un aspecto importante de tener en cuenta para un modelo de tráfico es el tiempo, o la variación de éste, en el cual cada paquete es enviado. Para ello es necesario extraer del fichero de traza, el tiempo entre los inicios (o llegadas) de cada paquete. En la Figura #3 se puede observar la variación de la duración de cada paquete, para el tráfico enviado y recibido de voz en función del tiempo de transmisión. **Para las muestras tomadas en este caso, se obtiene un tiempo medio de envío de paquetes de $$20 ms$$ con una desviación estándar de $$0.62 ms$$. Cada conexión de este flujo tiene un consumo de ancho de banda a nivel IP $$BW = (60x8) / 20X10^{-3}$$, lo que equivale a $$24 Kbps$$**.

<div class="row mt-3" style="text-align: center">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="assets/img/Research/como-obtener-modelo-trafico-voip/3_en.png" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Figura #3: Detalle del tiempo entre los inicios de cada paquete para el tráfico de voz.
</div>

## Conclusión

El modelo de la transmisión de voz es relativamente sencillo y estable en cuanto a tiempos y tamaños ya que **no presenta un comportamiento de ráfagas, o bien, puede verse como una sola. Generar un flujo IP de este tipo consiste en el envío de paquetes de $$60$$ bytes (incluyendo las cabeceras) cada $$20 ms$$ con una desviación estándar de $$0.62 ms$$, esto si, se utiliza el codec G.729 y una paquetización de dos muestras por paquete**. En el caso de que sea necesario cambiar el codec o la cantidad de muestras por paquete, los cambios son sencillos de hacer. Para este caso, se debe tener en cuenta la frecuencia de muestreo definida por el nuevo codec utilizado y la cantidad de muestras que se quieren empaquetar, las cuales se incluirían después del encabezado RTP.
