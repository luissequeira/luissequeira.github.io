---
layout: post
title:  Interacción de macroceldas y femtoceldas
date:   2014-01-16 06:00:00
description: En las macroceldas se encuentran muchos usuarios y es más difícil proveer QoS a todos ellos. Por estos motivos los operadores han optado por la implementación de femtoceldas a nivel residencial con el fin de aumentar la calidad de los servicios brindados. Las femtoceldas son estaciones base de baja potencia y bajo costo que proveen una alta calidad de los servicios celulares a nivel residencial, en este ámbito ofrecen una cobertura de aproximadamente 10 m.
tags: LTE 4G wireless macroceldas femtoceldas banda-ancha QoS
categories: Networks Innovation
thumbnail: assets/img/TICs/interaccion-de-macroceldas-y-femtoceldas/macro_femto_1.jpg
---
Las macroceldas no son muy eficientes [1] en el ámbito residencial debido a los problemas de penetración que se han mencionado en un artículo anterior, además, **en las macroceldas se encuentran muchos usuarios y es más difícil proveer QoS a todos ellos**. Por estos motivos los Proveedores de Servicios de Internet (ISP) han optado por la implementación de femtoceldas a nivel residencial con el fin de aumentar la calidad de los servicios brindados.

**Las femtoceldas son estaciones base de baja potencia y bajo costo** que proveen una alta calidad de los servicios celulares a nivel residencial, en este ámbito ofrecen una cobertura de aproximadamente $$10m$$ [2], están diseñadas para integrarse de manera automática a las redes macrocelulares. Se integra con el operador móvil mediante una **conexión de banda ancha**, típicamente ADSL [2, 3], como puede apreciarse en la Figura #1. Sin embargo también se puede realizar por medio de un *enlace radio* como se menciona en [4]. En General, la femtocelda hace que el tráfico del sistema celular proveniente del hogar, **se desvíe por la conexión de banda ancha**, liberando el consumo de recursos de la macrocelda.

<div class="row mt-3" style="text-align: center">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="assets/img/TICs/interaccion-de-macroceldas-y-femtoceldas/macro_femto_1.jpg" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Figura #1: Femto-celda típica [3].
</div>

Las femtoceldas presentan una serie de ventajas tanto para los proveedores de servicios celulares como para los usuarios, éstos últimos, **pueden percibir mejor nivel de señal**, ya que se reduce la distancia entre la femtocelda y el UE, esto provoca que la **SINR sea más alta aumentando la capacidad y propiciando mejores niveles de QoS**. A su vez, la eficiencia espectral se ve incrementada debido a la cantidad de usuarios por hertz por unidad de área, además, los bajos niveles de potencia de transmisión generan un menor consumo de energía ya que el móvil no necesitará demasiada potencia para realizar sus transmisiones. Por otro lado, al implementarse en escenarios residenciales, la cantidad de usuarios es poca y es posible compartir más recursos [4].

La Figura #2 muestra dos escenarios: en a) se muestra una **macrocelda tradicional** donde un eNodeB brinda cobertura a un área particular, si se analiza el caso de dos UE's que se encuentran a la misma distancia del eNodeB, con la diferencia de que uno de ellos se encuentra al aire libre (UE1) y el otro dentro de un casa de habitación (UE4), este último tendrá más **pérdidas debido a la penetración en la vivienda**. Por otro lado, en b) se plantea la implementación de **dos femtoceldas** una en cada vivienda **aumentando la calidad de la señal dentro del inmueble, y en consecuencia el throughput y la calidad del servicio brindado**.

<div class="row mt-3" style="text-align: center">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="assets/img/TICs/interaccion-de-macroceldas-y-femtoceldas/propagacion_2.jpg" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Figure #1: a) Macro-celda tradicional; b) Interacción de macro-celda con femto-celdas [2].
</div>

## References

1. G. de la Roche, A. Valcarce, D. Lopez-Perez, Jie Zhang. Access control Mechanisms for Femtocells. Communications Magazine, IEEE, vol. 48, no. 1, pp. 33-39, 2010.
2. D. Calin, H. Claussen, H. Uzunalioglu. On Femto Deployment Architectures and Macrocell Offloading Benefits in Joint Macro-Femto Deployments. Communications Magazine, IEEE, vol. 48, no. 1, pp. 26-32, 2010.
3. [http://www.femtoforum.org/](http://www.femtoforum.org)
4. Vikram Chandrasekhar, Jeffrey G. Andrews, Alan Gatherer. Femtocell Networks: A Survey. Communications Magazine, IEEE, vol. 46, no. 9, pp. 59-67, 2008.