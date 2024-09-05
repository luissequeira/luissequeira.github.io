---
layout: post
title:  "Internet táctil: El papel de la QoS en sistemas de teleoperación"
date:   2024-09-05 20:30:00
description: El sentido del tacto se percibe actualmente como la modalidad que complementará la audición y la visión, convirtiéndose en una tercera vía de transmisión de datos a través de Internet en una variedad de aplicaciones hápticas del futuro. 
tags: QoS tactile-internet teleoperation haptic urllc
categories: Innovation Networks
thumbnail: assets/img/Research/tactile-internet-the-role-of-qos/fig1.jpg
---
<div class="row mt-3" style="text-align: center">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="assets/img/Research/tactile-internet-the-role-of-qos/fig1.jpg" class="img-fluid rounded z-depth-1" %}
    </div>
</div>

**El sentido del tacto** se percibe actualmente como la modalidad que complementará la audición y la visión, convirtiéndose en una tercera vía de transmisión de datos a través de Internet en una variedad de aplicaciones hápticas del futuro. Estas aplicaciones permitirán una inmersión total y, en muchos aspectos, tendrán un impacto significativo en la sociedad. Sin embargo, los altos requerimientos técnicos de estas aplicaciones exigen redes que soporten comunicaciones ultra confiables y de baja latencia (URLLC), con el fin de garantizar la calidad de servicio (QoS) necesaria para mantener una experiencia óptima del usuario (QoE).

## Internet táctil

En los **sistemas de teleoperación para la telemanipulación háptica**, también conocidos como sistemas telehápticos, generalmente un operador humano usa una interfaz háptica (dispositivo maestro) en un extremo del canal de comunicación para controlar un dispositivo teleoperador (actuador esclavo) en el otro extremo. Las aplicaciones de teleoperación pueden ser de corta distancia, donde el canal de comunicación puede ser cableado o inalámbrico sin necesidad de infraestructura de red, o de larga distancia, aprovechando infraestructuras de redes conmutadas por paquetes para transmitir los datos. El alcance del canal de comunicación para la teleoperación a larga distancia puede variar desde redes de área local (LAN) hasta el propio Internet.

El objetivo de los sistemas de teleoperación es proporcionar al usuario la sensación de presencia en el entorno remoto donde se encuentra el teleoperador. Esto se logra mediante la mejora continua del hardware y software relacionados, permitiendo que los usuarios humanos reciban retroalimentación multimodal (visual, auditiva y háptica). Para alcanzar este objetivo, es necesario cumplir con los requisitos adecuados de QoS, lo cual maximiza la experiencia del usuario (QoE).

## Requisitos de calidad de servicio

Los sistemas de Telepresencia y Teleacción (TPTA) basados en Internet implementan esquemas de control en bucle cerrado sobre una infraestructura de comunicación en tiempo real, permitiendo la interacción entre un operador humano y un entorno remoto mediante sensores y actuadores. Este tipo de sistema se conoce como Sistema de Control Basado en Redes (NBCS).

Dado que uno de los componentes centrales de estos sistemas es el canal de comunicación, se han utilizado o creado varios protocolos de red para los diferentes marcos de teleoperación y su implementación en Internet, garantizando un funcionamiento eficiente tanto en aplicaciones de entornos virtuales como en sistemas físicos.

Como en cualquier sistema de red, el correcto funcionamiento de los NBCS está sujeto a diversos obstáculos que afectan negativamente su rendimiento. Estos factores también actúan como indicadores de desempeño, permitiendo comparar diferentes protocolos y cuantificar la calidad de servicio que pueden ofrecer, aspecto crítico en aplicaciones como la telecirugía. Dado que los sistemas de teleoperación son NBCS, heredan estos aspectos de rendimiento relacionados con los requisitos de los sistemas TPTA. Entre los parámetros de rendimiento más comunes se incluyen:

- **Retardo de red**: es el tiempo promedio que tarda un paquete en viajar desde la entrada hasta la salida del canal de comunicación. Una revisión exhaustiva de las principales fuentes de retardo de red y sus soluciones se encuentra en [2].
- **Jitter**: es la variación del retardo en paquetes individuales, también conocida como Variación del Retardo de Paquetes (PDV), que afecta la secuencia de los paquetes. Una forma común de mitigar el jitter es mediante el uso de números de secuencia o marcas de tiempo en los paquetes. Sin embargo, esto implica el uso de búferes, lo que incrementa el retardo total.
- **Pérdida de paquetes**: ocurre debido a la congestión del tráfico en la red, obligando a los sistemas maestro y esclavo de un sistema TPTA a operar con falta de información. Las soluciones incluyen sustituir los valores perdidos por valores nulos, mantener el último valor recibido o usar interpolación (por ejemplo, mediante métodos de predicción).
- **Tasa de datos**: está influenciada por la frecuencia de muestreo, la resolución de las muestras y el overhead del protocolo.

Además, factores como la cuantización de señales y otras fuentes de ruido también pueden afectar el rendimiento del sistema.

Los efectos de la pérdida de paquetes, con y sin latencia, en la percepción de eventos visuales y hápticos se han analizado en [3], mostrando que ambos factores se suman entre sí. No obstante, según [4], los efectos de la pérdida de paquetes pueden mitigarse mediante mecanismos que aumentan la fiabilidad de la comunicación, aunque esto incrementa la latencia total. Por lo tanto, es esencial encontrar un equilibrio entre fiabilidad y retardo.

## References

1. S.G. Tzafestas.Web-Based Control and Robotics Education.  IntelligentSystems,  Control  and  Automation:  Science  and  Engineering.  Springer Netherlands, 2009.  ISBN 9789048125050.
2.  B. Briscoe, A. Brunstrom, A. Petlund, D. Hayes, D. Ros, I. J. Tsang,S. Gjessing, G. Fairhurst, C. Griwodz, and M. Welzl.  Reducing internetlatency: A survey of techniques and their merits. IEEE Communications Surveys Tutorials, 18(3):2149–2196, thirdquarter 2016. ISSN 1553-877X.
3. Z. Shi, H. Zou, M. Rank, L. Chen, S. Hirche, and H. J. Muller. Effects ofpacket loss and latency on the temporal discrimination of visual-hapticevents. IEEE Transactions on Haptics, 3(1):28–36, Jan 2010. ISSN 1939-1412. 
4. Changhoon   Seo,   Jong-Phil   Kim,   Jaeha   Kim,   Hyo-Sung   Ahn,   andJeha   Ryu.Robustly   stable   bilateral   teleoperation   under   time-varying   delays   and   data   losses:   an   energy-bounding   approach.Journal   of   Mechanical   Science   and   Technology,   25(8):2089,   Sep2011.ISSN   1976-3824.