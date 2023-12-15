---
layout: post
title:  Architecture Features LTE / SAE
date:   2013-12-16 06:00:00
description: The fourth generation mobile (4G), it is very common that we like to be updated, we care about general aspects of the architecture of this new technology. Well, "System Architecture Evolution" (SAE) or also known as EPC ("Evolved Packed Core") has its development from the year 2004 until 2009, during that time many studies have been deployed which allowed to define the standards that describes the architecture of the core network.
tags: LTE 4G wireless network access-network architecture
categories: LTE (4G)
---
<p>
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;">With so much information that comes every day around the <a href="index.php/en/information-tecnologies/lte-4g/item/37-what-is-4g-and-what-are-the-most-important-technical-characteristics.html"><strong>fourth generation mobile (4G)</strong></a>, it is very common that we like to be updated, we care about general aspects of the <strong>architecture of this new technology</strong>. Well, "System Architecture Evolution" (SAE) or also known as EPC ("Evolved Packed Core") has its development from the year 2004 until 2009, <!--StartFragment-->during that time many studies have been deployed which allowed to define the standards that describes the architecture of the core network. The specifications are in chronological order in the following figure:</span></span><!--EndFragment--></p>
<p>
&nbsp;</p>
<p style="text-align: center;">
<img alt="" src="images/TICs/caracteristicas-de-la-arquetectura-LTE/1.jpg" /></p>
<p style="text-align: center;">
<span style="font-family: arial, helvetica, sans-serif; font-size: 14px;"><span style="color:#0000ff;"><strong>Figura # 1</strong></span>: SAE evolution <span style="color:#ffa500;"><strong>[1]</strong></span>.</span></p>

<p>
<span style="font-family: arial, helvetica, sans-serif; font-size: 14px;">SAE architecture has several <strong>advantages</strong> with respect to the technologies that have been previously developed for cellular networks, <strong>improving latency, throughput and network capacity</strong>, the core network provides simplicity in the architecture, optimizes traffic services, which are <strong>fully based on IP</strong>. In a very simplified way, LTE architecture can be described as shown in <span style="color:#0000ff;"><strong>Figure # 2</strong></span>. The chart shows the interaction of the eNodeB through an IP network with the gateways which provide communication and access to various services or networks, these gateways allow the interaction between the mobile network and the other networks that the ISP owns or even external networks.</span></p>
<p>
&nbsp;</p>
<p style="text-align: center;">
<img alt="" src="images/TICs/caracteristicas-de-la-arquetectura-LTE/2.jpg" /></p>
<p style="text-align: center;">
<span style="font-family: arial, helvetica, sans-serif; font-size: 14px; color: rgb(0, 0, 255);"><strong>Figure # 2</strong></span><span style="font-family: arial, helvetica, sans-serif; font-size: 14px;">: LTE architecture </span><span style="font-family: arial, helvetica, sans-serif; font-size: 14px; color: rgb(255, 165, 0);"><strong>[2]</strong></span><span style="font-family: arial, helvetica, sans-serif; font-size: 14px;">.</span></p>
<p style="text-align: center;">
&nbsp;</p>
<p>
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;"><!--StartFragment-->LTE architecture consists of <strong>two parts</strong> (see <span style="color:#0000ff;"><strong>Figure # 3</strong></span>) EPC and E-UTRAN (Evolved UTRAN). The EUTRAN is a part of the network that is responsible for all functions related to the <strong>radio interface and mobiles control</strong>, on the other hand, the EPC provides access to others <strong>IP packet networks</strong>, also here is where aspects related to security are managed, quality of service, resource management and mobility <span style="color:#ffa500;"><strong>[1]</strong></span>.</span></span><!--EndFragment--></p>
<p>
&nbsp;</p>
<p style="text-align: center;">
<img alt="" src="images/TICs/caracteristicas-de-la-arquetectura-LTE/3.jpg" /></p>
<p style="text-align: center;">
<span style="font-family: arial, helvetica, sans-serif; font-size: 14px; color: rgb(0, 0, 255);"><strong>Figure # 3</strong></span><span style="font-family: arial, helvetica, sans-serif; font-size: 14px;">: LTE simplified architecture </span><span style="font-family: arial, helvetica, sans-serif; font-size: 14px; color: rgb(255, 165, 0);"><strong>[1]</strong></span><span style="font-family: arial, helvetica, sans-serif; font-size: 14px;">.</span></p>
<p style="text-align: center;">
&nbsp;</p>
<p>
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;"><!--StartFragment-->The EUTRAN is composed by the eNodeBs (see <span style="color:#0000ff;"><strong>Figure # 4</strong></span>) providing <strong>aspects of mobile control and radio management</strong>, these network elements are interconnected with each other through X2 interfaces, the eNodeB interact with EPC via the MME ("Mobility Management Entity") with S1 interfaces for <strong>mobility control</strong>, management and other aspects. Both are IP interfaces which use the SCTP protocol ("Stream Control Transmission Protocol") <span style="color:#ffa500;"><strong>[5]</strong></span>. Additionally, some eNodeB functions are <span style="color:#ffa500;"><strong>[6]</strong></span>:</span></span><!--EndFragment--></p>
<ul>
<li>
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;"><strong>Resource radio management functions</strong>: connection, radio admission control, mobility control in the user plane.</span></span></li>
<li>
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;"><strong>IP header compression</strong> and encryption data user.</span></span></li>
<li>
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;"><strong>Routing</strong> in the user plane.</span></span></li>
<li>
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;"><strong>Transmission</strong> of broadcast information.</span></span></li>
<li>
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;">Mobility <strong>configuration reports</strong>.</span></span><!--EndFragment--></li>
</ul>
<p>
<span style="font-family: arial, helvetica, sans-serif; font-size: 14px;">The MME's functions are </span><span style="font-family: arial, helvetica, sans-serif; font-size: 14px; color: rgb(255, 165, 0);"><strong>[6]</strong></span><span style="font-family: arial, helvetica, sans-serif; font-size: 14px;">:</span></p>
<ul>
<li>
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;"><strong>Provide signaling</strong>, security and security control.</span></span></li>
<li>
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;">Providing signaling between nodes to <strong>manage mobility</strong> between nodes.</span></span></li>
<li>
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;"><!--StartFragment-->It is responsible for <strong>manage fees</strong> for the charges<!--EndFragment-->.</span></span></li>
<li>
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;">Manages <strong>mobility between other networks</strong> such as 2G and 3G.</span></span><!--EndFragment--></li>
</ul>
<p>
&nbsp;</p>
<p style="text-align: center;">
<img alt="" src="images/TICs/caracteristicas-de-la-arquetectura-LTE/4.jpg" /></p>
<p style="text-align: center;">
<span style="font-family: arial, helvetica, sans-serif; font-size: 14px; color: rgb(0, 0, 255);"><strong>Figura # 4</strong></span><span style="font-family: arial, helvetica, sans-serif; font-size: 14px;">: Interfaces entre eNodeB y MME </span><span style="font-family: arial, helvetica, sans-serif; font-size: 14px; color: rgb(255, 165, 0);"><strong>[1]</strong></span><span style="font-family: arial, helvetica, sans-serif; font-size: 14px;">.</span></p>
<p style="text-align: center;">
&nbsp;</p>
<p>
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;"><!--StartFragment-->A broader view of the architecture presented by LTE is shown in <span style="color:#0000ff;"><strong>Figure # 5</strong></span>, which shows the interaction of LTE with <strong>different types of networks</strong> such as GSM, UMTS, IP and others. <!--StartFragment-->In orange we present functional blocks that represent the elements of the SAE, which are:<!--EndFragment-->the eNodeBs, MME and SAE GW (also referred SWG "Serving Gateway"), in the latter block has been included PGW (PDN Gateway, "Public Data Network Gateway"). In this figure, solid lines represent the <strong>data flow</strong> through the appropriate interfaces and broken lines represent the <strong>signaling</strong> between different functional blocks or devices.</span></span><!--EndFragment--></p>
<p>
&nbsp;</p>
<p style="text-align: center;">
<img alt="" src="images/TICs/caracteristicas-de-la-arquetectura-LTE/5.jpg" /></p>
<p style="text-align: center;">
<span style="font-family: arial, helvetica, sans-serif; font-size: 14px; color: rgb(0, 0, 255);"><strong>Figura # 5</strong></span><span style="font-family: arial, helvetica, sans-serif; font-size: 14px;">: Arquitectura LTE interconectada con otras redes </span><span style="font-family: arial, helvetica, sans-serif; font-size: 14px; color: rgb(255, 165, 0);"><strong>[1]</strong></span><span style="font-family: arial, helvetica, sans-serif; font-size: 14px;">.</span></p>
<p style="text-align: center;">
&nbsp;</p>
<p>
<span style="font-family: arial, helvetica, sans-serif; font-size: 14px;">The MME obtains the subscribers information through the data stored in the HSS in order to authorize the users to the services which they have access. <strong>The MME authenticates, authorizes and selects the PDN ("Public Data Network")</strong> appropriate to establish the link between the EUTRAN to external networks or services, at the same time, it <strong>manages mobility and obtains charges information</strong>. The MME provides connectivity between the eNodeB and GSM or UMTS network via the SGSN ("Serving GPRS Support Node"). In general, we can say that MME has full responsibility for the operations relating to the <strong>control plane</strong>, also is the first LTE contact with GSM or UMTS.</span></p>
<p>
<span style="font-family: arial, helvetica, sans-serif; font-size: 14px;">The SGW is controlled by the MME, is a point where connection and service policies are monitored which are established in the PCRF ("Policy and Charging Rules Function") to <strong>administrate QoS</strong>, also the SGW is responsible for the traffic and buffers organization for packet storage. The <strong>PGW manages IP address allocation</strong> to the UE ("User Equipment"), deals with everything related to the inspection of IP packet and performs the functions that performed the GGSN GSM ("Gateway GPRS Support Node") but also has the </span><span style="font-family: arial, helvetica, sans-serif; font-size: 14px;"><strong>mobility control function</strong>. On the other hand, the <strong>HSS stores and manages all data</strong> on user subscriptions.</span></p>
<p>
&nbsp;</p>
<p>
<span style="font-family: arial, helvetica, sans-serif; font-size: 14px; color: rgb(68, 68, 68);">References</span></p>
<ol>
<li>
<span style="font-family:arial,helvetica,sans-serif;"><span style="font-size:14px;">Ericsson , Gerhard, Fritze, SAE - The Core Network for LTE , 2008</span></span></li>
<li>
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;">Nortel, Long-Term Evolution (LTE): The vision beyond 3G, 2008</span></span></li>
<li>
<span style="font-family: arial, helvetica, sans-serif;">Motorola, long Term Evolution (LTE): A Technical Overview, 2010</span></li>
<li>
<span style="font-family: arial, helvetica, sans-serif; font-size: 14px;">3GPP 25.913, Requirements for Evolved UTRA (E-UTRA) and Evolved UTRAN (E-UTRAN) (Release 8), 2008</span></li>
<li>
<span style="font-family: arial, helvetica, sans-serif; font-size: 14px;">Santosh KD, LTE Whitepaper, 2009</span></li>
<li>
<span style="font-family: arial, helvetica, sans-serif; font-size: 14px;">3GPP 36.300, EUTRA and EUTRAN overall description, Stage 2, 2009</span></li>
<li>
<span style="font-family: arial, helvetica, sans-serif; font-size: 14px;">3GPP 25.892, Multiplexing (OFDM) for UTRAN enhancement (Release 6), 2004</span></li>
<li>
<span style="font-family: arial, helvetica, sans-serif; font-size: 14px;">Rohde &amp; Schwarz, UMTS Long Term Evolution (LTE) Tecnologi Introduccion, 2007</span></li>
<li>
<span style="font-family: arial, helvetica, sans-serif; font-size: 14px;">Telefónica I+D, ¿Qué podemos esperar de LTE? Ventajas y prestaciones, 2010</span></li>
<li>
<a href="http://www.3gpp.org/LTE" style="font-family: arial, helvetica, sans-serif; font-size: 14px;">http://www.3gpp.org/LTE</a></li>
<li>
<a href="http://sociedadinformacion.fundacion.telefonica.com/DYC/SHI/seccion=1188&amp;idioma=es_ES&amp;id=2009100116310140&amp;activo=4.do?elem=7096" style="font-family: arial, helvetica, sans-serif; font-size: 14px;">http://sociedadinformacion.fundacion.telefonica.com/DYC/SHI/seccion=1188&amp;idioma=es_ES&amp;id=2009100116310140&amp;activo=4.do?elem=7096</a></li>
<li>
<a href="http://www.gradiant.org/index.php?option=com_content&amp;view=article&amp;id=289:mimo-en-wimax-y-lte&amp;catid=1:noticias&amp;Itemid=7&amp;lang=es" style="font-family: arial, helvetica, sans-serif; font-size: 14px;">http://www.gradiant.org/index.php?option=com_content&amp;view=article&amp;id=289:mimo-en-wimax-y-lte&amp;catid=1:noticias&amp;Itemid=7&amp;lang=es</a></li>
</ol>