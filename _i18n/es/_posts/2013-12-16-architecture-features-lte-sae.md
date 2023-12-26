---
layout: post
title:  Características de la arquitectura LTE/SAE
date:   2013-12-19 06:00:00
description: La cuarta generación de telefonía móvil (4G), es muy común que los que nos gusta estar actualizados, nos interesemos por aspectos generales de la arquitectura de esta nueva tecnología. Pues bien, “System Architecture Evolution” (SAE) o también conocida como EPC (“Evolved Packed Core”) tiene su desarrollo a partir del año 2004 y hasta el 2009, durante ese tiempo se han desarrollado estudios que han permitido realizar los estándares que definen la arquitectura del núcleo de la red.
tags: LTE 4G wireless arquitectura
categories: Networks
thumbnail: assets/img/TICs/caracteristicas-de-la-arquitectura-LTE/5.jpg
---
Con tanta información que surge día a día entorno a la [cuarta generación de telefonía móvil (4G)]({% post_url 2013-11-04-what-is-4g-and-what-are-the-most-important-technical-characteristics %}), es muy común que los que nos gusta estar actualizados, nos interesemos por aspectos generales de la **arquitectura de esta nueva tecnología**. Pues bien, “System Architecture Evolution” (SAE) o también conocida como EPC (“Evolved Packed Core”) tiene su desarrollo a partir del año 2004 y hasta el 2009, durante ese tiempo se han desarrollado estudios que han permitido realizar los estándares que definen la arquitectura del núcleo de la red. Las especificaciones pueden verse de manera cronológica en la siguiente figura:

<div class="row mt-3" style="text-align: center">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="assets/img/TICs/caracteristicas-de-la-arquitectura-LTE/1.jpg" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Figura #1: Evolución de SAE [1].
</div>

La arquitectura SAE presenta varias **ventajas** con respecto a las tecnologías que se han desarrollado anteriormente para redes celulares, **mejorando la latencia, el throughput y la capacidad de la red**, además, el núcleo de la red presenta simplicidad en la arquitectura, optimiza el tráfico de los servicios, los cuales son **totalmente basados en IP**. De una manera muy simplificada se puede describir la arquitectura LTE como se puede apreciar en la Figura #2, donde se observa la interacción de los eNodosB, a través de una red IP, con los gateway's que proporcionan comunicación y accesos a diversos servicios o redes, permitiendo una interacción entre la parte móvil y las otras redes con las que cuenta el ISP o incluso externas.

<div class="row mt-3" style="text-align: center">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="assets/img/TICs/caracteristicas-de-la-arquitectura-LTE/2.jpg" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Figura #2: Arquitectura LTE [2].
</div>

La arquitectura LTE consta de **dos partes** (ver Figura #3) la EPC y la EUTRAN (Envolved UTRAN). La EUTRAN es la parte de la red que se encarga de todas la funciones relacionadas a la **interfaz de radio y el control de los móviles**, por otro lado, la EPC brinda **acceso a otras redes de paquetes IP**, además, es aquí donde se gestiona los aspectos relacionados a la seguridad, calidad de servicio, gestión de recursos y movilidad [1].

<div class="row mt-3" style="text-align: center">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="assets/img/TICs/caracteristicas-de-la-arquitectura-LTE/3.jpg" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Figura #3: Arquitectura LTE simplificada [1].
</div>

La EUTRAN está compuesta por los eNodosB (ver Figura #4) **brindando aspectos de control de móviles y el manejo del medio**, estos elementos de red se interconectan entre ellos por medio de interfaces X2, los eNodeB interactúan con la EPC por medio de los MME (“Mobility Management Entity”) con interfaces S1 para el **control de la movilidad**, gestión y otros aspectos. Ambas son interfaces IP que además usan el protocolo SCTP (“Stream Control Transmission Protocol”) [5]. Por otro lado, algunas de las funciones del eNodeB son [6]:

- **Funciones de gestión de recursos de radio**: como conexión, control de admisión de radio, control de movilidad en el plano de usuario.
- **Compresión de encabezados IP** y encripción de datos de usuario.
- **Enrutamiento** en el plano de usuario.
- **Transmisión** de información broadcast.
- **Reportes de configuración** para movilidad.

Las funciones de la MME son las siguientes [6]:

- **Proveer señalización**, seguridad y control de la seguridad.
- Proveer señalización entre los nodos para **gestionar la movilidad** entre nodos.
- Es el encargado de **administrar tarifas** para cobros.
- Gestiona la **movilidad entre otras redes** como 2G y 3G.

<div class="row mt-3" style="text-align: center">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="assets/img/TICs/caracteristicas-de-la-arquitectura-LTE/4.jpg" class="img-fluid rounded z-depth-1" %}
    </div>
</div>

Una visión más amplia de la arquitectura planteada por LTE se muestra en la Figura #5, donde se aprecia la interacción de LTE con **diversos tipos de redes** como GSM, UMTS, IP y otras. En color naranja se presenta los bloques funcionales que representan los elementos que conforman la SAE, los cuales son: los eNodosB, MME y SAE GW (también denominado SWG, “Serving Gateway”), en este último bloque se han incluido el PGW (PDN Gateway, “Public Data Network Gateway”). El dicha figura las líneas continuas representan el **flujo de datos** por medio de las interfaces correspondientes y con líneas discontinuas se representa la **señalización** entre los diferentes bloques funcionales o equipos.

<div class="row mt-3" style="text-align: center">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="assets/img/TICs/caracteristicas-de-la-arquitectura-LTE/5.jpg" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Figure #5: Arquitectura LTE interconectada con otras redes [1].
</div>

El MME obtiene información del abonado a través de la información almacenada en el HSS para autorizar al usuario a los servicios a los que tiene acceso. **El MME autentica, autoriza y selecciona el PDN (“Public Data Network”)** apropiado para establecer el enlace entre el EUTRAN a las redes o servicios externos, al mismo tiempo **gestiona la movilidad y obtiene información de cobro**. El MME proporciona conectividad entre el eNodoB y una red GSM o UMTS a través del SGSN (“Serving GPRS Support Node”). En general se puede decir que MME tiene toda la responsabilidad por las operaciones concernientes al **plano de control**, además, es el primer contacto de LTE con GSM o UMTS.

El SGW es controlado por el MME, es un punto donde se monitorizan las políticas de conexión y servicio establecidas en el PCRF (“Policy and Charging Rules Function”) para poder **administrar QoS**, además, es responsable de la organización del tráfico y los buffers para almacenamiento de paquetes. **El PGW gestiona la asignación de direcciones IP** a los UE (“User Equipment”), tiene que ver con todo lo relacionada a la inspección de paquete IP y realiza las funciones que en GSM realizaba el GGSN (“Gateway GPRS Support Node”) pero además tiene la función de **control de la movilidad**. Por otro lado, el **HSS almacena y administra** todo lo relativo a los datos de suscripciones de los usuarios.

## References

1. Ericsson , Gerhard, Fritze, SAE - The Core Network for LTE , 2008
2. Nortel, Long-Term Evolution (LTE): The vision beyond 3G, 2008
3. Motorola, long Term Evolution (LTE): A Technical Overview, 2010<
4. 3GPP 25.913, Requirements for Evolved UTRA (E-UTRA) and Evolved UTRAN (E-UTRAN) (Release 8), 2008
5. Santosh KD, LTE Whitepaper, 2009
6. 3GPP 36.300, EUTRA and EUTRAN overall description, Stage 2, 2009
7. 3GPP 25.892, Multiplexing (OFDM) for UTRAN enhancement (Release 6), 2004
8. Rohde & Schwarz, UMTS Long Term Evolution (LTE) Tecnologi Introduccion, 2007
9. Telefónica I+D, ¿Qué podemos esperar de LTE? Ventajas y prestaciones, 2010
10. [http://www.3gpp.org/LTE](http://www.3gpp.org/LTE)
11. [http://sociedadinformacion.fundacion.telefonica.com/DYC/SHI/seccion=1188&amp;idioma=es_ES&amp;id=2009100116310140&amp;activo=4.do?elem=7096](http://sociedadinformacion.fundacion.telefonica.com/DYC/SHI/seccion=1188&amp;idioma=es_ES&amp;id=2009100116310140&amp;activo=4.do?elem=7096)
12. [http://www.gradiant.org/index.php?option=com_content&amp;view=article&amp;id=289:mimo-en-wimax-y-lte&amp;catid=1:noticias&amp;Itemid=7&amp;lang=es](http://www.gradiant.org/index.php?option=com_content&amp;view=article&amp;id=289:mimo-en-wimax-y-lte&amp;catid=1:noticias&amp;Itemid=7&amp;lang=es)