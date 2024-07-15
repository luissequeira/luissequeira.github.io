---
layout: post
title:  La computación en nube se une a la 5G
date:   2024-07-11 20:00:00
description: Hoy en día, muchos componentes 5G pueden virtualizarse y ejecutarse en entornos de nube. En las redes núcleo y de acceso radioeléctrico en 5G, el hardware y el software se están claramente separandos [1]. Esto significa que las funciones de software 5G se virtualizan y se entregan sobre hardware de propósito general, donde se ejecutan como máquinas virtuales o contenedores en entornos de nube privada o pública.
tags: cloud 5G
categories: Cloud
thumbnail: assets/img/Cloud/cloud-computing-5g/fig1.png
---

Hoy en día, muchos componentes 5G pueden virtualizarse y ejecutarse en entornos de nube. En las redes núcleo y de acceso radioeléctrico en 5G, el hardware y el software se están claramente separandos [1]. Esto significa que las funciones de software 5G se virtualizan y se entregan sobre hardware de propósito general, donde se ejecutan como máquinas virtuales o contenedores en entornos de nube privada o pública. Esta disociación es importante, ya que permite a las empresas y a los investigadores innovar de forma independiente y en su respectivo espacio o área. En el pasado, esto ha demostrado ser un enfoque muy exitoso en la industria informática, donde el hardware (ordenador), el middleware (sistema operativo) y el software (aplicaciones) se desarrollan de forma independiente y son impulsados por sus propios objetivos de diseño y desarrollo.

La clara separación de las funcionalidades de software permite sustituir potencialmente ciertas características o nueva funcionalidades mucho más rápido por otras más avanzadas. Por lo tanto, las mejoras incrementales de la tecnología pueden producirse ahora más fácilmente y sin tener que cambiar los dispCloud Computing meets 5Gositivos físicos o el firmware. De este modo, los componentes de software pueden virtualizarse mucho más fácilmente, y luego organizarse y desplegarse según las necesidades en diferentes ubicaciones físicas, centros de datos e incluso en diferentes proveedores de nube. De este modo, es posible trasladar o migrar con flexibilidad funcionalidades avanzadas o nuevas características, instanciar recursos en un momento determinado y prestar servicios a escala [2]. 

Un sistema 5G desplegado de extremo a extremo consta de múltiples componentes habilitados para 5G, así como de la integración de arquitecturas de sistemas a los que podríamos llamar heredados. Las funciones de red pueden virtualizarse por completo y ejecutarse en máquinas virtuales y algunas de ellas como contenedores en diferentes infraestructuras en la nube, todas ellas gestionadas y orquestadas mediante un marco de orquestación común. 

Un sistema 5G requiere de la interacción con redes heredadas, como las redes 4G comerciales, mediante soluciones basadas en la nube para arquitecturas móviles, incluidas las divisiones funcionales de la red de acceso radioeléctrico (RAN) en la nube y la red de núcleo. Un sistema de banco de pruebas habilitado para 5G podría parecerse al sistema que se muestra en la Figura 1. 

<div class="row mt-3" style="text-align: center">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="assets/img/Cloud/cloud-computing-5g/fig1.png" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Figura 1: Ejemplo de banco de pruebas de alto nivel que incluye tecnologías de acceso, redes de acceso, red núcleo y orquestación de servicios.
</div>

Como cualquier otra tecnología basada en radio, los sistemas 5G consisten de un conjunto de emplazamientos exteriores que transmiten en diferentes bandas, como $$3,5GHz$$ y $$28GHz$$ en este caso, lo que permite aumentar el rendimiento y reducir la latencia en la red de acceso. Las funciones virtualizadas de RAN y Core Network pueden ejecutarse ahora en entornos de nube separados, incluso a través de diferentes proveedores de nube, que deben interconectarse con un marco de gestión y orquestación. 

La red de núcleo 5G puede virtualizarse y soportar el denominado "slicing" de red de extremo a extremo, lo que puede utilizarse, por ejemplo, para permitir múltiples instancias de funciones de red virtualizadas (VNF) para satisfacer diferentes niveles de calidad de servicio (QoS), también puede utilizarse para el aislamiento de servicios, lo que abre la flexibilidad para proporcionar redes a medida para clientes o para casos de uso particulares en lugar del enfoque tradicional de "talla única". La fragmentación de la red también facilita el desmantelamiento o la actualización de toda una sección o servicio cuando sea necesario. 

## References

1. B. Han, V. Gopalakrishnan, L. Ji and S. Lee, “Network function virtualization: Challenges and opportunities for innovations”, in IEEE Communications Magazine, vol. 53, no. 2, pp. 90-97, Feb. 2015.
2. X. Sun and N. Ansari, "EdgeIoT: Mobile Edge Computing for the Internet of Things," in IEEE Communications Magazine, vol. 54, no. 12, pp. 22-29, December 2016.