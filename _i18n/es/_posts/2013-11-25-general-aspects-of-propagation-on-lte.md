---
layout: post
title:  Aspectos generales de propagación en LTE
date:   2013-11-28 06:00:00
description: La propagación de señales de radio presenta una serie de problemas intrínsecos de las ondas electromagnéticas, de las cuales LTE o 4G no está exenta. Aspectos como la absorción, refracción, difracción, desvanecimiento, así como otras propiedades pueden causar serios problemas de cobertura, interferencia, y en general degradación de la señal transmitida. Algunos de estos parámetros son, en buena medida, impredecibles, principalmente los derivados de los fenómenos meteorológico o del terreno, y por lo tanto, pocas medidas pueden ser tomadas en estos casos.
tags: LTE 4G wireless propagación multitrayecto 
categories: Networks
thumbnail: assets/img/TICs/aspectos-generales-de-propagacion-en-LTE/1.jpg
---
La propagación de señales de radio presenta una serie de problemas intrínsecos de las ondas electromagnéticas, de las cuales [LTE or 4G]({% post_url 2013-11-04-what-is-4g-and-what-are-the-most-important-technical-characteristics %}) no está exenta. Aspectos como la **absorción, refracción, difracción, desvanecimiento**, así como otras propiedades pueden causar serios problemas de cobertura, interferencia, y en general degradación de la señal transmitida. Algunos de estos parámetros son, en buena medida, **impredecibles**, principalmente los derivados de los fenómenos **meteorológico o del terreno**, y por lo tanto, pocas medidas pueden ser tomadas en estos casos.

Por otro lado, las **pérdidas por espacio libre** (PEL) se encuentra directamente relacionadas a la **frecuencia de operación del sistema y a la distancia entre el transmisor y el receptor**. El caso de la [frecuencia es un parámetro ya definido para este tipo de tecnogía]({% post_url 2014-01-06-the-spectrum-and-multiplexing-in-lte %}) por la Unión Internacional de Telecomunicaciones [1], además, depende de las asignaciones de frecuencia de cada país, y por lo tanto, no es algo que los operadores puedan manejar fácilmente para aumentar la cobertura de sus sistemas móviles.

El caso del **multitrayecto es un problema** que se encuentra asociado la propagación del haz radioeléctrico por diversos trayectos, apoyado en los fenómenos de **reflexión, difracción y dispersión**. Este tipo de fenómeno produce una diferencia en la distancia que recorren un haz que viaja con linea vista con respecto a otro que ha sufrido el efecto de una reflexión (por mencionar un ejemplo) y en consecuencia los tiempos de llegada de las señales al receptor difieren, **provocando que la superposición de las señales** en la antena receptora pueda provocar **interferencia entre símbolos** (ISI), o bien, potencias demasiado bajas para ser demoduladas, además, es posible que un determinado haz ni siquiera incida en la antena receptora como puede apreciarse en la siguiente Figura #1.

<div class="row mt-3" style="text-align: center">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="assets/img/TICs/aspectos-generales-de-propagacion-en-LTE/1.jpg" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Figura #1: Ejemplo de multitrayecto.
</div>

Otro de los problemas que provocan degradación de la señal transmitida son los efectos de la **penetración** en cualquier tipo de edificación, cada vez que la señal se refracta dentro de las paredes de un edificio o vivienda ésta pierde potencia, lo que se traduce en una baja señal percibida por el móvil o la radio base, según sea la dirección del enlace. La penetración tiene un impacto importante en lo que respecta redes móviles, ya que las celdas en LTE puede tener una cobertura típica de $$30Km$$ [2] y 
[3] (incluso más, entre $$5Km$$ a $$100Km$$), esto provoca que la potencia decrezca mientras más se aleja el UE (“User Equipment”) del eNodeB, esto se puede apreciar en la Figura #2, donde se encuentran diferentes micro-celdas que brindan cobertura a un área determinada, cada una de estas micro-celdas tiene su punto de más baja potencia en los límites con otras micro-celdas. Si combinamos los efectos de la dispersión mencionados con la penetración en edificios o casas, fácilmente se deduce que las localidades más alejadas del transmisor tendrán más **problemas de potencia** y por lo tanto de cobertura dentro de las edificaciones.

<div class="row mt-3" style="text-align: center">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="assets/img/TICs/aspectos-generales-de-propagacion-en-LTE/2.jpg" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Figura #2: Conjunto de micro-celdas [4].
</div>

Se podría pensar que la solución consiste solo en **aumentar la potencia de transmisión** para contrarrestar las pérdidas por penetración, y a la vez, se aprovecharía para una mayor cobertura, sin embargo, los niveles de potencia con que una estación puede irradiar potencia se encuentran **normalizados** dentro de las políticas de administración del espectro de cada país, además, el aumento de la potencia de transmisión **provocaría un aumento en el área de cobertura**, como se menciono con anterioridad, esto provocaría que la cobertura de un eNodeB genere interferencia en los eNodeB adyacentes provocando una degradación de la señal percibida por el usuario.

## Referencias

1. UIT, Disposiciones de frecuencias para la implementación de la componente terrenal de las telecomunicaciones móviles internacionales-2000 (IMT-2000), 2007.
2. Motorola, long Term Evolution (LTE): A Technical Overview, 2010
3. 3GPP 25.913, Requirements for Evolved UTRA (E-UTRA) and Evolved UTRAN (E-UTRAN) (Release 8), 2008
4. Vikram Chandrasekhar, Jeffrey G. Andrews, Alan Gatherer. Femtocell Networks: A Survey. Communications Magazine, IEEE, vol. 46, no. 9, pp. 59-67, 2008.