---
layout: post
title:  Architecture Features LTE / SAE
date:   2013-12-16 06:00:00
description: The fourth generation mobile (4G), it is very common that we like to be updated, we care about general aspects of the architecture of this new technology. Well, "System Architecture Evolution" (SAE) or also known as EPC ("Evolved Packed Core") has its development from the year 2004 until 2009, during that time many studies have been deployed which allowed to define the standards that describes the architecture of the core network.
tags: LTE 4G wireless architecture
categories: Networks
thumbnail: assets/img/TICs/caracteristicas-de-la-arquitectura-LTE/5.jpg
---
With so much information that comes every day around the [fourth generation mobile (4G)]({% post_url 2013-11-04-what-is-4g-and-what-are-the-most-important-technical-characteristics %}), it is very common that we like to be up-to-date, we care about general aspects of the **architecture of this new technology**. Well, "System Architecture Evolution" (SAE) or also known as EPC ("Evolved Packed Core") has its development from the year 2004 until 2009, during that time many studies have been deployed which allowed to define the standards that describes the architecture of the core network. The specifications are in chronological order in the following figure:

<div class="row mt-3" style="text-align: center">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="assets/img/TICs/caracteristicas-de-la-arquitectura-LTE/1.jpg" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Figure #1: SAE evolution [1].
</div>

SAE architecture has several **advantages** with respect to the technologies that have been previously developed for cellular networks, **improving latency, throughput and network capacity**, the core network provides simplicity in the architecture, optimizes traffic services, which are **fully based on IP**. In a very simplified way, LTE architecture can be described as shown in Figure #2. The chart shows the interaction of the eNodeB through an IP network with the gateways which provide communication and access to various services or networks, these gateways allow the interaction between the mobile network and the other networks that the ISP owns or even external networks.

<div class="row mt-3" style="text-align: center">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="assets/img/TICs/caracteristicas-de-la-arquitectura-LTE/2.jpg" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Figure #2: LTE architecture [2].
</div>

LTE architecture consists of **two parts** (see Figure #3) EPC and E-UTRAN (Evolved UTRAN). The EUTRAN is a part of the network that is responsible for all functions related to the **radio interface and mobiles control**, on the other hand, the EPC provides access to others **IP packet networks**, also here is where aspects related to security are managed, quality of service, resource management and mobility [1].

<div class="row mt-3" style="text-align: center">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="assets/img/TICs/caracteristicas-de-la-arquitectura-LTE/3.jpg" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Figure #3: LTE simplified architecture [1].
</div>

The EUTRAN is composed by the eNodeBs (see Figure #4) providing **aspects of mobile control and radio management**, these network elements are interconnected with each other through X2 interfaces, the eNodeB interact with EPC via the MME ("Mobility Management Entity") with S1 interfaces for **mobility control**, management and other aspects. Both are IP interfaces which use the SCTP protocol ("Stream Control Transmission Protocol") [5]. Additionally, some eNodeB functions are [6]:

- **Resource radio management functions**: connection, radio admission control, mobility control in the user plane.
- **IP header compression** and encryption data user.
- **Routing** in the user plane.
- **Transmission** of broadcast information.
- Mobility **configuration reports**

The MME's functions are [6]:

- **Provide signaling**, security and security control.
- Providing signaling between nodes to **manage mobility** between nodes.
- It is responsible for **manage fees** for the charges.
- Manages **mobility between other networks** such as 2G and 3G.

<div class="row mt-3" style="text-align: center">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="assets/img/TICs/caracteristicas-de-la-arquitectura-LTE/4.jpg" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Figure #4: Interfaces between eNodeB and MME [1].
</div>

A broader view of the architecture presented by LTE is shown in Figure #5, which shows the interaction of LTE with **different types of networks** such as GSM, UMTS, IP and others. In orange we present functional blocks that represent the elements of the SAE, which are:the eNodeBs, MME and SAE GW (also referred SWG "Serving Gateway"), in the latter block has been included PGW (PDN Gateway, "Public Data Network Gateway"). In this figure, solid lines represent the **data flow** through the appropriate interfaces and broken lines represent the **signaling** between different functional blocks or devices.

<div class="row mt-3" style="text-align: center">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="assets/img/TICs/caracteristicas-de-la-arquitectura-LTE/5.jpg" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Figure #5: LTE architecture interconnected with other networks [1].
</div>

The MME obtains the subscribers information through the data stored in the HSS in order to authorize the users to the services which they have access. **The MME authenticates, authorizes and selects the PDN ("Public Data Network")** appropriate to establish the link between the EUTRAN to external networks or services, at the same time, it **manages mobility and obtains charges information**. The MME provides connectivity between the eNodeB and GSM or UMTS network via the SGSN ("Serving GPRS Support Node"). In general, we can say that MME has full responsibility for the operations relating to the **control plane**, also is the first LTE contact with GSM or UMTS.

The SGW is controlled by the MME, is a point where connection and service policies are monitored which are established in the PCRF ("Policy and Charging Rules Function") to **administrate QoS**, also the SGW is responsible for the traffic and buffers organization for packet storage. The **PGW manages IP address allocation** to the UE ("User Equipment"), deals with everything related to the inspection of IP packet and performs the functions that performed the GGSN GSM ("Gateway GPRS Support Node") but also has the **mobility control function**. On the other hand, the **HSS stores and manages all data** on user subscriptions.

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
