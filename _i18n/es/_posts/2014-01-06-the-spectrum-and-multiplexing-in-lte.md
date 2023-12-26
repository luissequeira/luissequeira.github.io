---
layout: post
title:  El espectro y la multiplexión en LTE
date:   2014-01-09 06:00:00
description: En relación al espectro, LTE se torna bastante flexible permitiendo anchos de banda de 1.25MHz, 1.6MHz, 2.5MHz, 5MHz, 10MHz, 15MHz and 20MHz en el enlace descendente así como en el ascendente. La Multiplexación por División de Frecuencias Ortogonales (OFDM) es un esquema de multiplexación de frecuencia que se caracteriza por enviar una cantidad determinada de frecuencias portadoras dentro de un ancho de banda específico.
tags: LTE 4G wireless espectro multiplexión QAM PSK OFDM
categories: Networks
thumbnail: assets/img/TICs/el-espectro-y-la-multiplexion-en-LTE/2.jpg
---
## El espectro

En relación al espectro, LTE se torna bastante flexible permitiendo **anchos de banda** de $$1.25MHz$$, $$1.6MHz$$, $$2.5MHz$$, $$5MHz$$, $$10MHz$$, $$15MHz$$ y $$20MHz$$ en el enlace descendente así como en el ascendente [4]. Además, soporta transmisión broadcast en modos solamente descendente y descendente-ascendente, por otro lado, **los recursos de radio pueden modificarse** para transmisiones broadcast según las necesidades del operador.

Los diversos escenarios que se presentan entre la interacción de diferentes proveedores de servicios y las otras redes de las que disponen, no se ven afectados en gran medida ya que los fabricantes han previsto la **coexistencia** dentro de la misma área geográfica de la [EUTRAN con otro tipo de redes como 3G y la coexistencia entre operadores adyacentes]({% post_url 2013-12-16-architecture-features-lte-sae %}), así también, es el caso del solapamiento en los **límites de los países** [4].

La eficiencia espectral que presenta LTE supera en buena medida a HSPA+, estos son los resultados de Telefónica [9], el estudio contempla un escenario de centros urbanos con **alta densidad de edificios**, configuración de antenas MIMO $$2x2$$ para los dos casos y utilizando $$64QAM$$ como esquema de modulación, con esto, el estudio asegura que **LTE supera en eficiencia espectral a HSPA+** por un $$20%$$ a plena carga. De la Figura #1 se deduce que para centros rurales o suburbanos las prestaciones de LTE serán mayores, además, a lo largo de la gráfica se denota la superioridad de LTE.

<div class="row mt-3" style="text-align: center">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="assets/img/TICs/el-espectro-y-la-multiplexion-en-LTE/1.jpg" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Figura #1: Eficiencia espectral en función del uso de recursos [9].
</div>

## Multiplexación por División de Frecuencia Ortogonal (OFDM)

La Multiplexación por División de Frecuencias Ortogonales (OFDM) es un **esquema de multiplexación de frecuencia** que se caracteriza por enviar una cantidad determinada de frecuencias portadoras dentro de un ancho de banda específico [7, 8], cada una de estas portadoras transporta información utilizando esquemas de **modulación como $$QAM$$ o $$PSK$$ ($$QPSK$$, $$16QAM$$ y $$64QAM$$)** [10]. Una de las **principales ventajas** que presenta este tipo de multiplexación es en cuanto al **desvanecimiento de las señales, retados y en general ante las interferencias**, además [presenta características óptimas frente al multitrayecto]({% post_url 2013-11-25-general-aspects-of-propagation-on-lte %}), por otro lado, con modulaciones $$QAM$$ y $$PSK$$ es posible transmitir más cantidad de símbolos por ciclo.

<div class="row mt-3" style="text-align: center">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="assets/img/TICs/el-espectro-y-la-multiplexion-en-LTE/2.jpg" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Figura #2: Representación de frecuencia y tiempo para una señal OFDM [7].
</div>

Las diferentes frecuencias ($$n-ésimas$$) denominadas **subportadoras**, en la figura anterior deben tener una separación igual entre ellas y debe permanecer constante para no generar un traslape de las señales produciendo interferencias entre ellas. Dicha separación entre subportadoras viene dada por la siguiente expresión:

$$
\frac{\vert \omega_{n} - \omega_{n-1} \vert}{2\pi} = \Delta f, n \in [1, N-1]
$$

Donde $$w$$ es la frecuencia, $$n$$ la cantidad de subportadoras y $$f$$ la separación entre ellas.

Por otro lado, el 3GPP ha definido una separación entre canales OFDM, dicha separación se le conoce como **guarda banda o intervalo de guarda** y tiene la finalidad de generar una distancia en frecuencia entre canales adyacentes para que **no hallan interferencias entre ellos**, en general, lo que se realiza es anular la transmisión de una cantidad de subportadoras en la sección en el espectro donde termina un canal y empieza el siguiente en la parte superior e inferior del canal, reduciendo así el ancho de banda útil por canal, esto se puede ver en la Figura #3.

<div class="row mt-3" style="text-align: center">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="assets/img/TICs/el-espectro-y-la-multiplexion-en-LTE/3.jpg" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Figura #3: Subportadoras inactivas para un canal OFDM [7].
</div>

En general, el estudio realizado por el 3GPP [7] expone la viabilidad del uso de OFDM en la UTRAN para el enlace descendente y valida su inserción, afirma que **OFDM mejora el rendimiento en comparación con HSDPA** Realease 5, sin embargo, la introducción de un sistema más avanzado y de mayor complejidad, como lo es OFDM, no genera una diferencia significativa en el rendimiento del lado del receptor, y por lo tanto, **se recomienda solamente para el enlace descendente**.

## References

1. Ericsson , Gerhard, Fritze, SAE - The Core Network for LTE , 2008
2. Nortel, Long-Term Evolution (LTE): The vision beyond 3G, 2008
3. Motorola, long Term Evolution (LTE): A Technical Overview, 2010
4. 3GPP 25.913, Requirements for Evolved UTRA (E-UTRA) and Evolved UTRAN (E-UTRAN) (Release 8), 2008
5. Santosh KD, LTE Whitepaper, 2009
6. 3GPP 36.300, EUTRA and EUTRAN overall description, Stage 2, 2009
7. 3GPP 25.892, Multiplexing (OFDM) for UTRAN enhancement (Release 6), 2004
8. Rohde &amp; Schwarz, UMTS Long Term Evolution (LTE) Tecnologi Introduccion, 2007
9. Telefónica I+D, ¿Qué podemos esperar de LTE? Ventajas y prestaciones, 2010
10. [http://www.3gpp.org/LTE](http://www.3gpp.org/LTE)
11. [http://sociedadinformacion.fundacion.telefonica.com/DYC/SHI/seccion=1188&amp;idioma=es_ES&amp;id=2009100116310140&amp;activo=4.do?elem=7096](http://sociedadinformacion.fundacion.telefonica.com/DYC/SHI/seccion=1188&amp;idioma=es_ES&amp;id=2009100116310140&amp;activo=4.do?elem=7096)
12. [http://www.gradiant.org/index.php?option=com_content&amp;view=article&amp;id=289:mimo-en-wimax-y-lte&amp;catid=1:noticias&amp;Itemid=7&amp;lang=es](http://www.gradiant.org/index.php?option=com_content&amp;view=article&amp;id=289:mimo-en-wimax-y-lte&amp;catid=1:noticias&amp;Itemid=7&amp;lang=es)
