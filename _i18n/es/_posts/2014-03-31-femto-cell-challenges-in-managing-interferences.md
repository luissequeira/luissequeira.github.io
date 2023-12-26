---
layout: post
title:  Femto celdas desafíos en la gestión de interferencias
date:   2014-04-03 05:00:00
description: En este contexto, los operadores han impulsado la implementación de femto-celdas para disminuir la distancia con el UE y poder mantener una buena calidad de la señal. Sin embargo, las femto-celdas deben operar en la banda de frecuencias designadas para dicha comunicación y coincidir con las frecuencias asignadas al operador.
tags: 4G LTE femtoceldas macroceldas
categories: Networks Innovation
thumbnail: assets/img/Research/femtoceldas-desafios-gestion-interferencias/1.png
---
Algunos estudios muestran que m ás del $$50%$$ de las llamadas de voz y el $$70%$$ del tráfico de datos proviene de interiores [1], las llamadas de voz no requieren grandes anchos de banda, pero si ciertos par ámetros de calidad que garantice el reconocimiento de la voz por el usuario en el otro extremo de la comunicación, por el contrario, el tráfico de datos requiere altas tazas de transmisión para poder enviar información con gran cantidad de megabytes, como las aplicaciones multimedia lo requieren, por mencionar un ejemplo. **Una forma de garantizar altas tazas de transmisión en sistemas de radio, consiste en poder mantener una alta calidad de la señal en ambos extremos de la comunicación, y por lo tanto, mitigar los efectos de las pérdidas e interferencias que pueda tener el canal de comunicación**.

En este contexto, los operadores han impulsado la implementación de femto-celdas para disminuir la distancia con el UE y poder mantener una buena calidad de la señal. Sin embargo, **las femto-celdas deben operar en la banda de frecuencias designadas para dicha comunicación y coincidir con las frecuencias asignadas al operador**, desde esta perspectiva, las femto-celdas generarán interferencias y estas se pueden dar de las siguientes maneras [2]:

- Femto-celda a femto-celda.
- Femto-celda a macro-celda.
- Macro-celda a femto-celda.

**Los problemas de la interferencias entre femto-celdas radica en la cobertura que cada una de éstas tenga**, este tipo de interferencia se producirá principalmente en los límites de cobertura donde interaccionan las femto-celdas, en la Figura #1 se puede observar este fenómeno, **en la cual la cobertura del FAP 1 se solapa con la del FAP 2, produciendo degradación de la señal para los usuarios de ambas femto-celdas en esa zona**.

<div class="row mt-3" style="text-align: center">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="assets/img/Research/femtoceldas-desafios-gestion-interferencias/1.png" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Figura #1: Problemas de interferencia entre macro/femto celdas.
</div>

Otro caso de interferencia es la interferencia que percibe el móvil 2, suponemos que este móvil se encuentra gestionado por la macro-celda y no tiene permiso de acceder a la femto-celda 1, sin embargo, se encuentra dentro del  área de cobertura de dicha femto-celda, esto provocaría interferencias en el móvil ya que los canales de frecuencia por los que se comunica con la macro-celda se encuentran dentro del mismo ancho de banda que la femto-celda, **este tipo de interferencia que produce la femto-celda a la macro-celda, también se puede dar en el sentido inverso, de macro-celda a femto-celda**.

Cuando un móvil asociado a una macro-celda se encuentra lejos del eNodeB y cercano a una femto-celda, éste transmitirá con una potencia mayor para cubrir con las pérdidas asociadas al enlace, sin embargo, al hacer esto, genera más interferencia hacia la femto-celda. Por otro lado, la femto-celda solicitará a los móviles que gestiona, un incremento en la potencia de transmisión para poder cubrir las interferencias, esto a su vez, generará un nivel de interferencia mayor para el móvil que se encuentra gestionado por la macro-celda. **Los métodos de acceso a la red tendrán que gestionar el problema de la administración de la potencia, de manera eficiente para permitir la coexistencia y asegurar la calidad de servicio**.

En este contexto se genera un problema en cuanto a la gestión de la cobertura de las femto-celdas, ya que se deben minimizar las interferencias que generen, y a la vez, cubrir con los requerimientos de calidad de servicio. Por lo tanto, el proveedor del servicio debe tener un control preciso de la femto-celda en varios sentidos:

- **Se debe asegurar el uso del espectro asignado y verificar que la femto-celda no se encuentra transmitiendo fuera de la banda de frecuencias correspondiente.**
- **Los traslados de ubicación deben ser gestionados adecuadamente, ya que esto podría desarrollar localidades con una gran cantidad de interferencias por la acumulación de femto-celdas cercanas.**
- **Debe de tenerse en cuenta que las técnicas tradicionales de planificación, como la reutilización de frecuencias, carece de sentido ya que el usuario es el que instala las femto-celdas.**

Por otro lado, se han encontrado **problemas con la implementación de femto-celdas en  áreas donde se encuentra una red Wi-Fi**, en [1] se comentan casos donde los FAP experimentan dificultades en la transferencia de datos, incluso en los servicios de voz.

## References

1. Vikram C, Jeffrey GA, Alan G. Femtocell Networks: A Survey. IEEE Comunication Magzine (2008) 46: pp. 59-67.
2. G DLR, A V, D L Jie Z. Access control Mechanisms for Femtocells. IEEE Communications Magazine (2010) 48: pp. 33-39.
