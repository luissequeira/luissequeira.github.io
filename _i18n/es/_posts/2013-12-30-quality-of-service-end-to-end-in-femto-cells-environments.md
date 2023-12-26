---
layout: post
title:  Calidad de servicio extremo a extremo en entornos femtocelulares
date:   2014-01-02 06:00:00
description: Desde el punto de vista de gestión, LTE permite definir perfiles y clases de servicios, los cuales son claves cuando se negocian los requerimiento de QoS del móvil durante el establecimiento de una comunicación, el tránsito de los paquetes durante la misma, incluso en los traspasos. Sin embargo, para asegurar la QoS extremo a extremo es necesario tener en cuenta tanto la red de acceso como la de transporte. La red de acceso debe tener configurado con claridad las clases de servicios, tipos de tráfico, entre otros, ajustando adecuadamente los parámetros que definen los esquemas de modulación y codificación, la máxima latencia, jitter, ancho de banda mínimos garantizados, retardo permitido y demás parámetros que la tecnología permita adecuar en función de la clase de servicio al que se acceda.
tags: LTE 4G QoS femtoceldas wireless
categories: Networks
thumbnail: assets/img/TICs/quality-of-service-end-to-end-in-femto-cells-environments/1.jpg
---
La red de telecomunicaciones de un ISP (Proveedor de Servicios de Internet) **es en realidad una interacción de diversos tipos de redes**, dentro de las que puede destacar LTE (4G) como una red de acceso al usuario final. El flujo de información que llega al usuario, atraviesa diversas infraestructuras por las que el proveedor de servicios realiza el tránsito de los datos, bajo esta perspectiva **se comentarán algunos de los puntos necesarios de tener en cuenta a la hora de asegurar la QoS** (Calidad de Servicio) en este tipo de entornos.

Desde el punto de vista de gestión, **LTE permite definir perfiles y clases de servicios**, los cuales son claves cuando se negocian los requerimiento de QoS del móvil durante el establecimiento de una comunicación, el tránsito de los paquetes durante la misma, incluso en los traspasos. Sin embargo, **para asegurar la QoS extremo a extremo es necesario tener en cuenta tanto la red de acceso como la de transporte**

## Red de transporte

Un escenario típico de un proveedor se servicios de Internet podría describirse como se muestra en la Figura #1, en ella se puede ver como **LTE solamente forman parte de la red de acceso de un proveedor**. El ISP posee diversos tipos de redes de acceso, en función de los servicios que brinda. Toda la infraestructura necesaria para el transporte de la información proveniente de las redes de acceso, debe de transitar por el núcleo de red, éste también se interconecta con otros tipos diferentes de redes, donde usualmente se ubica el servicio final al que el usuario desea acceder (Internet, PSTN, servicios ftp, video streaming, voz u otros).

<div class="row mt-3" style="text-align: center">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="assets/img/TICs/quality-of-service-end-to-end-in-femto-cells-environments/1.jpg" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Figura #1: Topología simplificada de un ISP [2].
</div>

**En la red de transporte es común que se utilicen protocolos para la gestión de QoS e ingeniería de tráfico**. Uno de los protocolos que pueden colaborar en este aspecto es: Diffserv el cual utiliza 8 bits situados en la cabecera IP denominado Diffserv Code Point (DSCP), de tal manera que todos **los paquetes marcados con el mismo DSCP tienen el mismo tratamiento (misma prioridad) dentro de los routers de la red**. Dependiendo de la prioridad con que han sido marcados, este mecanismo permitirá reducir el retardo de los paquetes.

IPv6 a pesar que este no es un protocolo de QoS, tiene en cuenta algunos aspectos ya que **permite la clasificación de tráfico CoS y la identificación de flujos orientados a las tendencias DiffServ e IntServ** respectivamente. Por otro lado, MPLS tampoco es un protocolo de QoS, sin embargo, es un método de conmutación que permite realizar funciones de ingeniería de tráfico para **asignar recursos a diferentes tipos de tráfico con ciertas garantías de QoS en una ruta específica**. Mediante el uso de este protocolo los paquetes que tengan la misma etiqueta seguirán el mismo camino en la red generando que el retardo tienda a ser constante entre los paquetes con etiqueta idéntica.

## Red de acceso

Desde esta perspectiva, el brindar QoS extremo a extremo se vuelve un problema que debe ser abordado con los cuidados del caso. **La red de acceso debe tener configurado con claridad las clases de servicios, tipos de tráfico, entre otros, ajustando adecuadamente los parámetros que definen los esquemas de modulación y codificación, la máxima latencia, jitter, ancho de banda mínimos garantizados, retardo permitido** y demás parámetros que la tecnología permita adecuar en función de la clase de servicio al que se acceda.

Las femto-celdas transportan tráfico de datos y voz, por este motivo ciertos requerimientos de QoS deben ser garantizados para poder cubrir con los retardos mínimos que que necesitan algunos tipos de servicios. **Si el proveedor de servicios del servicio móvil es el mismo que le brinda el servicios de banda ancha (ADSL típicamente), él puede gestionar QoS de manera adecuada para el acceso del tráfico proveniente de la femto-celda hacia la red de transporte garantizando un ancho de banda mínimo**, por ejemplo, y gestionando recursos en el caso de requerimientos mayores de ancho de banda.

Otro escenario que se puede presentar para estos casos, es que los servicios de **la línea de banda ancha y del acceso móvil sean proporcionados por proveedores diferentes** (ver figura 2), para estos casos una posible solución sería un **Acuerdo de Nivel de Servicio (SLA)** entre dichos operadores en cuanto a QoS para el tráfico proveniente de la femto-celda, de esta manera **se podría garantizar al usuario los niveles de QoS para los diferentes tipos de clases de tráfico**.

<div class="row mt-3" style="text-align: center">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="assets/img/TICs/quality-of-service-end-to-end-in-femto-cells-environments/2.jpg" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Figura #2: Banda ancha y acceso móvil proporcionados por ISPs diferentes.
</div>

## Aspectos relacionados

Desde el punto de vista de control extremo a extremo, se podría tener en cuenta otro tipo de protocolos más relacionados con el manejo de la aplicación, como por ejemplo video, voz, streaming, entre otros. En este sentido se podría mencionar protocolos como por ejemplo: RTP, RTCP y RTSP.

RTP es un protocolo basado en IP que proporciona soporte para el transporte de datos en tiempo real (flujos de video y de audio), ha sido diseñado para funcionar con el protocolo de control RTCP para conseguir mantener la calidad en la transmisión, **una de sus funciones es la monitorización de la QoS y control de congestión, proporcionando información sobre la calidad de los datos transmitidos y permitiendo ajustar su transmisión basándose en los informes del receptor**. Por otro lado, RTSP es un protocolo de la capa de aplicación en un entorno cliente-servidor que permite controlar el flujo de datos multimedia sobre la red IP. En resumen, **RSTP establece y controla los flujos de audio y de vídeo entre los servidores y los clientes, actuando como un “control remoto en red” entre el servidor y el cliente**.

## References

1. Ericsson , Gerhard, Fritze, SAE - The Core Network for LTE , 2008
2. Nortel, Long-Term Evolution (LTE): The vision beyond 3G, 2008
3. Motorola, long Term Evolution (LTE): A Technical Overview, 2010
4. 3GPP 25.913, Requirements for Evolved UTRA (E-UTRA) and Evolved UTRAN (E-UTRAN) (Release 8), 2008
5. [http://www.3gpp.org/LTE](http://www.3gpp.org/LTE)
