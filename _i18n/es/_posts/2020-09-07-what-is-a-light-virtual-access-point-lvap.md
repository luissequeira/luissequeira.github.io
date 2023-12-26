---
layout: post
title:  Qué es un Light Virtual Access Point (LVAP)?
date:   2020-09-14 18:29:24
description: Las redes inalámbricas se utilizan ampliamente en zonas como centros de negocios, aeropuertos, campus universitarios o incluso en muchas zonas urbanas. Los puntos de Light Virtual Access Point (LVAP) son una solución para coordinar los puntos de acceso Wi-Fi.
tags: SDN punto-de-acceso cloud
categories: Cloud Innovation
thumbnail: assets/img/Cloud/what-is-lvaps/sticky-client.png
---

<div class="row mt-3" style="text-align: center">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="assets/img/Cloud/what-is-lvaps/sticky-client.png" class="img-fluid rounded z-depth-1" %}
    </div>
</div>

Las redes inalámbricas se utilizan ampliamente en áreas como centros de negocios, aeropuertos, campus universitarios o incluso en muchas áreas de la ciudad. Para estos escenarios existen soluciones para **coordinar puntos de acceso Wi-Fi**, generalmente conocidos como Wi-Fi empresarial. Aunque existen soluciones comerciales, estas son propietarias, cerradas y costosas, lo que en la mayoría de los casos las hace inviables para muchas organizaciones.

En este contexto, existen algunas propuestas de soluciones de **coordinación entre puntos de acceso que permiten funciones avanzadas** como balanceo de carga, planificación de frecuencias o control de potencia. Algunos trabajos han propuesto la adaptación de ciertas abstracciones y conceptos de **Software Defined Network (SDN)**, para su uso en redes inalámbricas [1, 2].

Uno de los problemas que surgen al coordinar una red inalámbrica es que las estaciones (STA) tienen sus propios algoritmos para seleccionar el punto de acceso. Esto significa que cada STA es libre de seleccionar el punto de acceso al que asociarse, sin ser coordinado con el resto de los clientes. Esto complica la gestión del clientes, generando el *sticky client*, que nunca abandona el punto de acceso al que estaba asociado inicialmente.

Una forma de resolver estos problemas es utilizando la abstracción **Light Virtual Access Point (LVAP)** [3]. La idea es que un punto de acceso físico utilice un **LVAP** diferente (que incluye una MAC específica) para comunicarse con cada STA. Por lo tanto, la STA solo "verá" un único punto de acceso, incluso si se está moviendo entre un conjunto de ellos, evitando así la necesidad de volver a asociarlo.

El **LVAP** se asigna dinámicamente a un punto de acceso físico cerca de la ubicación actual del terminal. Siempre que la STA sólo “vea” un único punto de acceso, no tomará ninguna decisión de *roaming*, lo que permitirá que la red ejecute una gestión coordinada de clientes. Esto se logra sin ninguna modificación en la STA que ejecuta el estándar IEEE 802.11.

Existen algunas iniciativas en esta área, en [4] se introdujo una solución distribuida utilizando **LVAPs**, proponiendo un protocolo para el intercambio directo de información entre puntos de acceso. La principal limitación es la ausencia de un controlador central, por lo que cada punto de acceso debe crear una lista de puntos de acceso vecinos por sí mismo. En [5], una solución basada en **LVAP**, administrada por un controlador central, combina dos protocolos *southbound*: OpenFlow y Odin. OpenFlow le dice a los *switches* internos de los puntos de acceso dónde dirigir el tráfico y el protocolo Odin está a cargo de la gestión inalámbrica. El control central de la red Wi-Fi se ejecuta dentro del controlador **SDN**. El controlador se encarga de crear un **LVAP** para cada terminal que consta de una tupla con cuatro campos: la MAC real de la STA, una MAC falsa para que los puntos de acceso se comuniquen con la STA, la IP de la STA y el SSID que va a ser utilizado en la comunicación.

Los *handovers* rápidos y sin problemas de conexión, son una parte esencial de todas estas soluciones ya que las STA se pueden redistribuir dinámicamente. Por lo tanto, una reasignación del punto de acceso en donde no se pierda la sesión del cliente, puede ser muy conveniente cuando un usuario está caminando o cuando se hace un balanceo de carga. 

## References

1. R. Riggio, T. Rasheed, and M. K. Marina, “Poster: programming software-defined wireless networks.” in MobiCom, S.-J. Lee, A. Sabharwal, and P. Sinha, Eds. ACM, p. 413416.
2. R. Riggio, T. M. Rasheed, and R. Narayanan, “Virtual network functions orchestration in enterprise WLANs.” in IM, R. Badonnel, J. Xiao, S. Ata, F. D. Turck, V. Groza, and C. R. P. dos Santos, Eds. IEEE, p. 12201225.
3. Y. Grunenberger and F. Rousseau, “Virtual Access Points for Transparent Mobility in Wireless LANs.” in WCNC. IEEE, p. 16.
4. M. E. Berezin, F. Rousseau, and A. Duda, “Multichannel Virtual Access Points for Seamless Handoffs in IEEE 802.11 Wireless Networks.” in VTC Spring. IEEE, p. 15.
5. J. Schulz-Zander, L. Suresh, N. Sarrar, A. Feldmann, T. Hhn, and R. Merz, “Programmatic Orchestration of WiFi Networks,” in 2014 USENIX Annual Technical Conference (USENIX ATC 14). Philadelphia, PA: USENIX Association, Jun., p. 347358.
