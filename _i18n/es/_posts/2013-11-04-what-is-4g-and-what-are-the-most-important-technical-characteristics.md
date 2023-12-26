---
layout: post
title:  ¿Qué es 4G y cuales son las características técnicas más importantes?
date:   2013-11-07 00:00:00
description: La cuarta generación de telefonía celular (4G), “Long Term Evolution” (LTE) es la nueva generación de redes móviles. LTE es una red inalámbrica que proporcionar banda ancha inalámbrica a un costo y un rendimiento mejor que el que se consigue con las tecnologías xDSL. 
tags: LTE 4G wireless movil inalámbrico
categories: Networks
thumbnail: assets/img/TICs/que-es-4G/3.jpg
---
Las comunicaciones móviles han tenido un incremento exponencial debido al alto grado de aceptación debido a la necesidad de información y acceso a diferentes servicios por parte de la comunidad mundial, esto ha hecho que los dispositivos inalámbricos como PDA's, smartphones y otros dispositivos hayan tenido índices de crecimiento, en cuanto a ventas, muy altos en los últimos años, además, el crecimiento de dichas ventas tiende a tener una distribución exponencial como se muestra en la Figura #1.

<div class="row mt-3" style="text-align: center">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="assets/img/TICs/que-es-4G/1.jpg" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Figura #1: Cantidades de dispositivos móviles vendidos por año [1].
</div>

El incremento en el uso de este tipo de dispositivos ha generado que los fabricantes y proveedores de servicios de telecomunicaciones provean a la sociedad de nuevos y mejores servicios. Es por esto, que **las redes de telefonía celular brindan ahora una gran cantidad de servicios y no solamente comunicación de voz**, además, esta demanda de servicios de telecomunicaciones por parte de los usuarios presiona a los fabricantes a desarrollar nuevas tecnologías en el ámbito de redes móviles, este es el caso de la llamada **cuarta generación de telefonía celular (4G)**, “Long Term Evolution” (LTE) es la nueva generación de este tipo de redes más allá de la conocida “Universal Mobile Telecomunication System” (UMTS), o también llamada 3G.

El “3rd Generation Partnership Project” (3GPP) es la organización encargada de producir especificaciones e informes técnicos para redes móviles basadas en evoluciones de centrales GSM (“Global System for Mobile Communications”). Según [1], el desarrollo de LTE (o 4G) inicia con los estudios técnicos realizados por el 3GPP a finales del año 2004 y se prolongan hasta el años 2006, a mediados del 2006 el 3GPP inicia la descripción de especificaciones para el nuevo estándar finalizando para el año 2008, como se aprecia en la Figura #2.

LTE es una red inalámbrica que proporcionar **banda ancha inalámbrica** a un costo y un rendimiento mejor que el que se consigue con las tecnologías xDSL, pero manteniendo la movilidad en las aplicaciones de Internet tales como Voz sobre IP (VoIP), video streaming, descarga de música, TV móvil y muchos otros [2].

<div class="row mt-3" style="text-align: center">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="assets/img/TICs/que-es-4G/2.jpg" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Figura #2: Evolución del estándar LTE [1].
</div>

La mayoría de los ISP's (“Internet Service Provider”) tienen una estructura como la se aprecia en la Figura #3. Las redes de acceso son las que interactúan con el usuario final, como su nombre lo indica, permiten el acceso de los usuarios al núcleo de la red del proveedor, algunas de este tipo de redes son ISDN, ADSL, GSM entre otras. LTE se cataloga como una **red de acceso móvil**, que gracias al ancho de banda que permite a los usuarios, supera a las antes mencionadas. El núcleo de la red consta, comúnmente, de una capa física basada en fibra, usualmente con tecnologías CWDM o DWDM y para el transporte de paquetes IP (“Internet Protocol”) puede implementarse protocolos en los enrutadores como MPLS (“MultiProtocol Label Switching”), a través del núcleo los usuarios pueden tener acceso a los servicios que se hayan contratado y la posibilidad de interactuar con otros tipos de redes con los que disponga el ISP (PSTN, NGN, etc.), o bien, acceso a Internet. Además, los ISP's cuentan con servidores dedicados a diversas tareas para la gestión de la red, control, autenticación de usuarios y servicios, entre otros.

<div class="row mt-3" style="text-align: center">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="assets/img/TICs/que-es-4G/3.jpg" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Figura #3: Modelo simplificado de un ISP [2].
</div>

Algunas de las características más relevantes de LTE son [3]:

- **Velocidad de transmisión**: en el enlace ascendente se pueden obtener hasta $$100Mbps$$ y $$50Mbps$$ en el enlace descendente para un ancho de banda de $$20Mhz$$ [4].
- **Cobertura**: el área de las celdas puede ir de $$5Km$$ hasta $$100Km$$ con una degradación después de los $$30Km$$.
- **Movilidad**: soporta movilidad de hasta $$500Km/h$$ pero presenta mejores características para velocidades menores, de $$0Km/h$$ a $$15Km/h$$ [4].
- **Latencia**: menor a $$5ms$$, lo cual proporciona una ventaja directa en el servicio para los entornos de aplicaciones tridimensionales y de gran interacción, como software de jugadores múltiples y comunicaciones multimedia [4].
- **Capacidad del plano de control**: mayor a $$200$$ usuarios por celda para un ancho de banda de $$5MHz$$ [4].
- **Eficiencia espectral**: de $$3$$ a $$4$$ veces la de HSDPA en el enlace descendente y de $$2$$ a $$3$$ veces en el enlace ascendente [4].

Las avanzadas características de la interfaz de radio en LTE resuelven varios inconvenientes que históricamente han disminuido la capacidad de las redes celulares, incluyendo las **interferencias de multitrayecto y multiusuario**. LTE utiliza OFDMA (“Orthogonal Frequency Division Multiple Access”) y configuraciones de antenas MIMO (“Multiple Input Multiple Output”) en el enlace descendente lo cual **elimina eficazmente las interferencias intracelulares de multiusuario y disminuye la interferencia intercelular de multiusuario**, optimizando el funcionamiento. Por otro lado, la transmisión de enlace ascendente utiliza una variante de FDMA denominada SC-FDMA que permite al dispositivo móvil transmitir señales de baja potencia sin necesidad de usar costosos amplificadores de potencia.

En conclusión, **4G o LTE es una red móvil de banda ancha** con características bastante superiores que las redes de telefonía móvil que la ha precedido.

## Referencias

1. Ericsson , Gerhard, Fritze, SAE - The Core Network for LTE , 2008
2. Nortel, Long-Term Evolution (LTE): The vision beyond 3G, 2008
3. Motorola, long Term Evolution (LTE): A Technical Overview, 2010
4. 3GPP 25.913, Requirements for Evolved UTRA (E-UTRA) and Evolved UTRAN (E-UTRAN) (Release 8), 2008
5. Santosh KD, LTE Whitepaper, 2009 
6. 3GPP 36.300, EUTRA and EUTRAN overall description, Stage 2, 2009 
7. 3GPP 25.892, Multiplexing (OFDM) for UTRAN enhancement (Release 6), 2004 
8. Rohde & Schwarz, UMTS Long Term Evolution (LTE) Tecnologi Introduccion, 2007 
9. Telefónica I+D, ¿Qué podemos esperar de LTE? Ventajas y prestaciones, 2010 
1. [http://www.3gpp.org/LTE](http://www.3gpp.org/LTE)
1. [http://sociedadinformacion.fundacion.telefonica.com/DYC/SHI/seccion=1188&amp;idioma=es_ES&amp;id=2009100116310140&amp;activo=4.do?elem=7096](http://sociedadinformacion.fundacion.telefonica.com/DYC/SHI/seccion=1188&amp;idioma=es_ES&amp;id=2009100116310140&amp;activo=4.do?elem=7096)
1. [http://www.gradiant.org/index.php?option=com_content&amp;view=article&amp;id=289:mimo-en-wimax-y-lte&amp;catid=1:noticias&amp;Itemid=7&amp;lang=es](http://www.gradiant.org/index.php?option=com_content&amp;view=article&amp;id=289:mimo-en-wimax-y-lte&amp;catid=1:noticias&amp;Itemid=7&amp;lang=es)
