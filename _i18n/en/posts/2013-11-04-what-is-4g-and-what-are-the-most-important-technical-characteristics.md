---
layout: post
title:  What is 4G? and what are the most important technical characteristics?
date:   2013-11-04 00:00:00
description: The fourth generation of mobile phones (4G), "Long Term Evolution" (LTE) is the next generation of mobile networks. LTE is a wireless network that provides wireless broadband at a better cost and performance than that achieved with xDSL technologies.
tags: LTE 4G mobile mobile-networks network
categories: LTE (4G)
thumbnail: assets/img/TICs/que-es-4G/3.jpg
---
Mobile communications have had an exponential increase due to the high level of acceptance due to the need for information and access to different services from the world community, for this reason wireless devices such as PDA's, smartphones and other devices have a growth in sales, extremely high in recent years, as it is shown in Figure #1.

<div class="row mt-3">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="assets/img/TICs/que-es-4G/1.jpg" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Figure #1: Amounts of mobile devices sold per year [1].
</div>

The increase in the use of these devices has led to manufacturers and telecommunications service providers to provide new and better services for the society. For this reason **mobile networks now provide a lot of services and not just voice communication**, in addition, the demand for telecommunications services by users press manufacturers to develop new technologies in the field of mobile networks, this is the case of the so-called **fourth generation of mobile phones** (4G), "Long Term Evolution" (LTE) is the next generation of this type of networks beyond the known "Universal Mobile Telecomunication System" (UMTS) , or also called 3G.

The "3rd Generation Partnership Project" (3GPP) is the organization responsible for producing specifications and technical reports for mobile networks based on GSM core evolutions ("Global System for Mobile Communications"). According to [1], the development of LTE (or 4G) begins with the technical studies undertaken by 3GPP in late 2004 and last until the year 2006, in the middle of 2006 the 3GPP begins to describe specifications for the new standard which end in 2008, as it is described in Figure #2.

LTE is a wireless network that provides **wireless broadband** at a better cost and performance than that achieved with xDSL technologies while maintaining mobility in Internet applications such as Voice over IP (VoIP), video streaming, downloads music, mobile TV and many others [2].

<div class="row mt-3">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="assets/img/TICs/que-es-4G/2.jpg" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Figure #2: LTE standard evolution [1].
</div>

Most ISP's ("Internet Service Provider") have a structure as shown in Figure #3. Access networks are those that interact with the end user, allowing to the user access to the core of the provider's network, some of these networks are ISDN, ADSL, GSM and others. LTE is classified as a **mobile access network**, thanks to its bandwidth, it enables users to exceed the capacity of the networks cited above. The network core is commonly a fiber-based physical layer, usually with CWDM or DWDM technologies and to transport IP packets ("Internet Protocol"), protocols as MPLS ("Multiprotocol Label Switching" ) can be implemented. Through the core, users can access to the services to be hired and the ability to interact with other types of networks which the ISP have (e.g. PSTN, NGN, etc..), or Internet access. In addition, ISP's have dedicated servers to different tasks for network management, control, and user authentication services, among others.

<div class="row mt-3">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="assets/img/TICs/que-es-4G/3.jpg" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Figure #3: Simplified model of an ISP [2].
</div>

Some of the most important characteristics of LTE are [3]:
- **Transmission rate**: in the uplink can reach up to 100Mbps and 50Mbps in the downlink for a 20MHz bandwidth [4].
- **Coverage**: The area of the cells can vary from 5Km to 100km with a degradation after 30Km.
- **Mobility**: Mobility supports up to 500km/h but has better features for lower speeds of 0Km/h to 15Km/h [4].
- **Latency**: less than 5ms, which provides a direct benefit in the service for three-dimensional application environments and highly interactive, multiplayer and software and multimedia communications [4].
- **Control plane capacity**: more than 200 users per cell for a 5MHz bandwidth [4].
- **Spectral efficiency**: 3 to 4 times the HSDPA in the downlink and 2 to 3 times in the uplink [4].

The advanced features of the radio interface in **LTE can solve several drawbacks that have historically decreased capacity of cellular networks, including multiuser interference and multipath**. LTE uses OFDMA ("Orthogonal Frequency Division Multiple Access") and MIMO antenna configurations ("Multiple Input Multiple Output") on the downlink **which effectively removes intracellular multiuser interference and decreases multiuser interference intercellular** in order to optimize the operation. Moreover, the uplink transmission uses a FDMA variant called SC-FDMA which allows the mobile device to transmit low power signals without using expensive power amplifiers.

In conclusion, **4G or LTE is a wireless broadband network** with far superior features that mobile phone networks that preceded it.

## References

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
