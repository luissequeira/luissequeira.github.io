---
layout: post
title:  Técnicas para la transmisión de datos en LTE
date:   2014-01-23 06:00:00
description: FDD (Frecuency Division Duplex) es un esquema de transmisión y recepción de señales, este sistema permite una comunicación full duplex utilizando dos frecuencias diferentes, una para el enlace descendente y otra para el ascendente, manteniendo una banda de separación entre dichas frecuencias con la finalidad de no traslapar los canales. La técnica de modulación y codificación del canal es uno de los puntos importantes en cuanto a las velocidades que permite LTE. Este nuevo modelo de red móvil utiliza AMC (Modulación y Codificación Adaptativa), esta técnica consiste en valorar las condiciones del canal de radio.
tags: LTE 4G FDD TDD transmisión propagación modulación codificación wireless
categories: Networks Innovation
thumbnail: assets/img/TICs/tecnicas-para-la-transmision-de-datos-en-LTE/1.jpg
---
## Sistemas Duplex para transmisión: LTE-FDD y LTE-TDD

FDD (Frecuency Division Duplex) es un **esquema de transmisión y recepción de señales**, este sistema permite una comunicación **full duplex** utilizando dos frecuencias diferentes, una para el enlace descendente y otra para el ascendente, manteniendo una [banda de separación entre dichas frecuencias]({% post_url 2014-01-06-the-spectrum-and-multiplexing-in-lte %}) con la finalidad de **no traslapar los canales**, esto hace que la eficiencia espectral de FDD no sea muy buena. Sin embargo, una de las ventajas de este esquema de multiplexación es que **no introduce retardos ni latencia adicional**.

Por otro lado, TDD (Time Division Duplex) es otra **técnica de multiplexado** para comunicaciones que utiliza **un solo canal, o frecuencia**, para la transmisión de información, en este caso la transmisión y la recepción se realiza por la misma frecuencia pero con diferencias de tiempo y una **separación temporal entre los dos sentidos de la comunicación**, haciendo más eficiente el uso del espectro. La multiplexación TDD realiza una asignación temporal para los sentidos de comunicación, además del tiempo de guarda, esto hace que sea **más sensible a los retardos y la latencia**.

Algunas comparaciones:

- **En cuanto a la distancia** FDD presenta mejores características a más largas distancias que TDD, de tal manera que TDD tiene más aceptación en escenarios donde las distancias son más cortas.
- **La propagación de las señales también presenta características diferentes**, ya que TDD utiliza una sola frecuencia, esto hace que el canal como tal, presente las mismas características en las transmisión y en la recepción.
- En FDD cada uno de **los canales presenta diferentes características de propagación** en función de la frecuencia utilizada.
- La diferencia de frecuencias de los canales FDD, produce que **la capacidad de cada canal dependa de la frecuencia** asignada por las autoridades reguladoras.
- En TDD es **más sencillo hacer una distribución dinámica** de la capacidad del downlink y el uplink con la finalidad de satisfacer las características de la demanda de recursos.

Las asignaciones de frecuencias que ha establecido el 3GPP para el uso de TDD y FDD se muestran la siguiente figura:

<div class="row mt-3" style="text-align: center">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="assets/img/TICs/tecnicas-para-la-transmision-de-datos-en-LTE/1.jpg" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Figura #1: Bandas de frecuencias para LTE FDD y TDD [1].
</div>

## Modulación y codificación

La técnica de modulación y codificación del canal es uno de los **puntos importantes en cuanto a las velocidades** que permite [LTE]({% post_url 2013-11-04-what-is-4g-and-what-are-the-most-important-technical-characteristics %}). Este nuevo modelo de red móvil utiliza AMC (Modulación y Codificación Adaptativa) [9], esta técnica **consiste en valorar las condiciones del canal de radio**, se usan distintos esquemas de codificación de canal y de modulación. El proceso para seleccionar la **modulación óptima y el esquema de codificación** se lleva a cabo muy en coordinación con el de “fast scheduling”. Los esquemas de modulación son: $$QPSK$$, $$16QAM$$ y $$64QAM$$.

<div class="row mt-3" style="text-align: center">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="assets/img/TICs/tecnicas-para-la-transmision-de-datos-en-LTE/2.jpg" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Figura #2: Diagramas de constelación de 16QAM y 64QAM.
</div>

La codificación de canal en [LTE]({% post_url 2013-11-04-what-is-4g-and-what-are-the-most-important-technical-characteristics %}) se denomina HARQ (“Fast Hybrid ARQ, Fast Hybrid Automatic Repeat Request”) es una combinación de FEC+ARQ, si una trama no puede ser corregida, entonces, se solicita una retransmisión. Para este caso las tramas dañadas que han podido ser corregidas mediante el FEC **no se descartan**, sino, que se guardan para combinarse con otras tramas sucesivas dañadas y producir una correcta, esto se basa en el principio que para dos tramas sucesivas, que contengan la misma información, **la probabilidad de que tengan los mismos bit erróneos es muy baja**, por lo que **la probabilidad de reconstruir un paquete sin errores de los dos anteriores es muy alta**. Los mecanismos de corrección de errores se implementan en el eNodoB.

## References

1. Ericsson , Gerhard, Fritze, SAE - The Core Network for LTE , 2008
2. Nortel, Long-Term Evolution (LTE): The vision beyond 3G, 2008
3. Motorola, long Term Evolution (LTE): A Technical Overview, 2010
4. 3GPP 25.913, Requirements for Evolved UTRA (E-UTRA) and Evolved UTRAN (E-UTRAN) (Release 8), 2008
5. Santosh KD, LTE Whitepaper, 2009
6. 3GPP 36.300, EUTRA and EUTRAN overall description, Stage 2, 2009
7. 3GPP 25.892, Multiplexing (OFDM) for UTRAN enhancement (Release 6), 2004
8. Rohde & Schwarz, UMTS Long Term Evolution (LTE) Tecnologi Introduccion, 2007
9. Telefónica I+D, ¿Qué podemos esperar de LTE? Ventajas y prestaciones, 2010
10. [http://www.3gpp.org/LTE](http://www.3gpp.org/LTE)
11. [http://sociedadinformacion.fundacion.telefonica.com/DYC/SHI/seccion=1188&amp;idioma=es_ES&amp;id=2009100116310140&amp;activo=4.do?elem=7096](http://sociedadinformacion.fundacion.telefonica.com/DYC/SHI/seccion=1188&amp;idioma=es_ES&amp;id=2009100116310140&amp;activo=4.do?elem=7096)
12. [http://www.gradiant.org/index.php?option=com_content&amp;view=article&amp;id=289:mimo-en-wimax-y-lte&amp;catid=1:noticias&amp;Itemid=7&amp;lang=es](http://www.gradiant.org/index.php?option=com_content&amp;view=article&amp;id=289:mimo-en-wimax-y-lte&amp;catid=1:noticias&amp;Itemid=7&amp;lang=es)
