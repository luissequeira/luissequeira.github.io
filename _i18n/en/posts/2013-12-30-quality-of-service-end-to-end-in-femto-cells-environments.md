---
layout: post
title:  Quality of Service end-to-end in femto-cells environments
date:   2013-12-30 06:00:00
description: From the point of view of LTE management, it is permitted to define profiles and classes of services, which are key points when negotiating QoS mobile requirements during the communication establishment, the transit of packets, even in handovers. However, it is necessary to consider the access and transport network if we want to ensure end-to-end QoS. The access network should have clearly configured the types of services, traffic types, among others, by suitably adjusting parameters, that define the modulation and coding schemes, maximum latency, jitter, guaranteed minimum bandwidth, allowed delay, and other parameters that technology allows to adapt depending on the service type we access.
tags: LTE 4G QoS femtocell access-network core-network network transport-network RTP RTSP RTCP
categories: QoS
---
<p style="margin-bottom: 0in">
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;"><span style="line-height: 24px;">The telecommunications network of an ISP (Internet Service Provider) </span><b style="font-size: 13px; line-height: 24px;">is actually an interaction of various networks types</b><span style="line-height: 24px;">, within LTE (4G) can be highlighted as an access network to the end user. The information flow reaches to the user through several infrastructures, on which the ISP carries data traffic, from this perspective, </span><b style="font-size: 13px; line-height: 24px;">some necessary points will be discussed in order to ensure the Quality of Service</b><span style="line-height: 24px;"> (QoS) in such environments.</span></span></span></p>
<p>
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;"><span style="line-height: 24px;">From the point of view of LTE management, </span><b style="font-size: 13px; line-height: 24px;">it is permitted to define profiles and classes of services</b><span style="line-height: 24px;">, which are key points when negotiating QoS mobile requirements during the communication establishment, the transit of packets, even in handovers. However, </span><b style="font-size: 13px; line-height: 24px;">it is necessary to consider the access and transport network if we want to ensure end-to-end QoS</b><span style="line-height: 24px;">.</span></span></span></p>
<p>
&nbsp;</p>
<p>
<span style="font-family: arial, helvetica, sans-serif; font-size: 14px; color: rgb(68, 68, 68); line-height: 24px;">Transport Network</span></p>
<p style="margin-bottom: 0in">
<span style="font-family: arial, helvetica, sans-serif; font-size: 14px; line-height: 24px;">A typical scenario of an Internet service provider could be described as shown in <span style="color:#0000ff;"><strong>Figure # 1</strong></span>, it can be seen that </span><b style="font-family: arial, helvetica, sans-serif; font-size: 14px; line-height: 24px;">LTE is only a part of the provider's access network</b><span style="font-family: arial, helvetica, sans-serif; font-size: 14px; line-height: 24px;">. The ISP has different types of access networks depending on the provided services. </span><span style="font-family: arial, helvetica, sans-serif; font-size: 14px; line-height: 24px;">All the necessary infrastructure to transport information from the access networks, must transit through the core network. The core is also connected with other different network types, where the end service is usually located (Internet, PSTN, ftp services, video streaming, voice or other), which the user wants to access.</span></p>
<p>
&nbsp;</p>
<p style="margin-bottom: 0in; text-align: center;">
<img alt="" src="images/TICs/quality-of-service-end-to-end-in-femto-cells-environments/1.jpg" style="height: 259px; width: 500px;" /></p>
<p style="margin-bottom: 0in; text-align: center;">
<span style="font-family: arial, helvetica, sans-serif; font-size: 14px; line-height: 24px;"><span style="color:#0000ff;"><strong>Figure # 1</strong></span>. ISP's simplified topology <span style="color:#ff8c00;"><strong>[2]</strong></span>.</span></p>

<p style="text-align: center;">
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;"><!--StartFragment--></span></span><!--EndFragment--></p>
<p style="margin-bottom: 0in">
<b style="line-height: 24px; font-family: arial, helvetica, sans-serif; font-size: 14px;">The use of managing QoS protocols and traffic engineering are commonly used in the transport network</b><span style="line-height: 24px; font-family: arial, helvetica, sans-serif; font-size: 14px;">. One of the protocols that can help in this aspect is: Diffserv which uses 8 bits located in the IP header called Diffserv Code Point (DSCP), thus </span><b style="line-height: 24px; font-family: arial, helvetica, sans-serif; font-size: 14px;">all packets marked with the same DSCP have the same routers treatment (same priority) within the network</b><span style="line-height: 24px; font-family: arial, helvetica, sans-serif; font-size: 14px;">. This mechanism will reduce the packet delay, depending on the priority which have been marked.</span></p>
<p style="margin-bottom: 0in">
<span lang="en-US" style="font-family: arial, helvetica, sans-serif; font-size: 14px; line-height: 24px;">Although, IPv6 is not a QoS protocol, it takes into account some aspects because </span><span lang="en-US" style="font-family: arial, helvetica, sans-serif; font-size: 14px; line-height: 24px;"><b>it allows traffic classification (CoS) and flow identification, oriented to DiffServ and IntServ trends</b></span><span lang="en-US" style="font-family: arial, helvetica, sans-serif; font-size: 14px; line-height: 24px;"> respectively. On the other hand, MPLS neither is a QoS protocol, however, is a switching method that allows traffic engineering functions for </span><span lang="en-US" style="font-family: arial, helvetica, sans-serif; font-size: 14px; line-height: 24px;"><b>allocating resources to different traffic types with certain QoS guarantees in a specific path</b></span><span lang="en-US" style="font-family: arial, helvetica, sans-serif; font-size: 14px; line-height: 24px;">. Using this protocol in packets with the same label will follow the same path in the network, generating that delay tends to be constant between the packets with identical label.</span></p>
<p style="margin-bottom: 0in">
<span lang="en-US"><!--EndFragment--></span></p>
<p style="margin-bottom: 0in">
&nbsp;</p>
<h1>
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;"><!--StartFragment-->Network access</span></span><!--EndFragment--></h1>
<p style="margin-bottom: 0in">
<span style="font-family: arial, helvetica, sans-serif; font-size: 14px; line-height: 24px;">From this perspective, providing end-to-end QoS becomes a problem that must be addressed to the care of the case. </span><b style="font-family: arial, helvetica, sans-serif; font-size: 14px; line-height: 24px;">The access network should have clearly configured the types of services, traffic types, among others, by suitably adjusting parameters, that define the modulation and coding schemes, maximum latency, jitter, guaranteed minimum bandwidth, allowed delay</b><span style="font-family: arial, helvetica, sans-serif; font-size: 14px; line-height: 24px;">, and other parameters that technology allows to adapt depending on the service type we access.</span></p>
<p style="margin-bottom: 0in">
<span style="font-family: arial, helvetica, sans-serif; font-size: 14px; line-height: 24px;">Femtocells carry data and voice traffic, for this reason, certain QoS requirements must be guaranteed to meet the minimum delays that some types of services needed. </span><b style="font-family: arial, helvetica, sans-serif; font-size: 14px; line-height: 24px;">If the mobile service provider is the same provider of the broadband services (ADSL typically), it can adequately manage QoS for traffic access from the femto-cell to the network transport to guarantee a minimum bandwidth</b><span style="font-family: arial, helvetica, sans-serif; font-size: 14px; line-height: 24px;">, for example, and managing resources in the case of larger bandwidth requirements.</span></p>
<p>
<span style="font-family: arial, helvetica, sans-serif; font-size: 14px; line-height: 24px;">Another scenario that can occur in these cases, is that the </span><b style="font-family: arial, helvetica, sans-serif; font-size: 14px; line-height: 24px;">line broadband service and mobile access are provided by different vendors</b><span style="font-family: arial, helvetica, sans-serif; font-size: 14px; line-height: 24px;"> (see <span style="color:#0000ff;"><strong>Figure # 2</strong></span>), for these cases, a possible solution would be a </span><b style="font-family: arial, helvetica, sans-serif; font-size: 14px; line-height: 24px;">Service Level Agreement (SLA)</b><span style="font-family: arial, helvetica, sans-serif; font-size: 14px; line-height: 24px;"> between these operators in terms of QoS for traffic coming from the femto-cell, so </span><b style="font-family: arial, helvetica, sans-serif; font-size: 14px; line-height: 24px;">it could ensure the user QoS levels for the different types of traffic classes</b><span style="font-family: arial, helvetica, sans-serif; font-size: 14px; line-height: 24px;">.</span></p>
<p>
&nbsp;</p>
<p style="margin-bottom: 0in; text-align: center;">
<img alt="" src="images/TICs/quality-of-service-end-to-end-in-femto-cells-environments/2.jpg" style="height: 293px; width: 500px;" /></p>
<p style="margin-bottom: 0in; text-align: center;">
<span style="font-family: arial, helvetica, sans-serif; font-size: 14px; line-height: 24px;"><span style="color:#0000ff;"><strong>Figure # 2</strong></span>. Broadband and mobile access provided by different ISPs.</span></p>
<p style="text-align: center;">
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;"><!--StartFragment--></span></span><!--EndFragment--></p>
<p style="margin-bottom: 0in">
&nbsp;</p>
<h1>
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;"><!--StartFragment-->Related Aspects</span></span><!--EndFragment--></h1>
<p style="margin-bottom: 0in">
<span style="font-family: arial, helvetica, sans-serif; font-size: 14px; line-height: 24px;">From the point of view of end-to-end control, we might consider other protocols that may be a solution more related to application management</span><span style="font-family: arial, helvetica, sans-serif; font-size: 14px; line-height: 24px;">, such as video, voice, streaming, among others. In this sense, we could mention protocols as e.g.: RTP, RTCP and RTSP.</span></p>
<p style="margin-bottom: 0in">
<span style="font-family: arial, helvetica, sans-serif; font-size: 14px; line-height: 24px;">RTP is an IP-based protocol that provides support for the transport of real-time data (streaming video and audio), it was designed to work with the RTCP protocol for maintaining transmission quality, </span><b style="font-family: arial, helvetica, sans-serif; font-size: 14px; line-height: 24px;">one of its functions is the QoS monitoring and congestion control, providing information about the quality of the transmitted data and it allows to adjust its transmission based on the receiver reports</b><span style="font-family: arial, helvetica, sans-serif; font-size: 14px; line-height: 24px;">. On the other hand, RTSP is a application layer protocol in a client-server environment which controls the multimedia data flow over the IP network. In summary, </span><b style="font-family: arial, helvetica, sans-serif; font-size: 14px; line-height: 24px;">RSTP sets and controls the flow of audio and video between servers and clients, acting as a "network remote control" between the server and the client</b><span style="font-family: arial, helvetica, sans-serif; font-size: 14px; line-height: 24px;">.</span></p>
<p>
<!--EndFragment--></p>
<p>
&nbsp;</p>
<h1>
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;">References</span></span></h1>
<ol style="padding: 0px; margin: 0px 0px 9px 25px; list-style-position: inside; list-style-image: initial; font-family: Arial, Helvetica, sans-serif;">
<li style="line-height: 18px;">
<span style="font-size: 14px;"><span style="font-family: arial, helvetica, sans-serif;">Ericsson , Gerhard, Fritze, SAE - The Core Network for LTE , 2008</span></span></li>
<li style="line-height: 18px;">
<span style="font-size: 14px;"><span style="font-family: arial, helvetica, sans-serif;">Nortel, Long-Term Evolution (LTE): The vision beyond 3G, 2008</span></span></li>
<li style="line-height: 18px;">
<span style="font-size: 14px;"><span style="font-family: arial, helvetica, sans-serif;">Motorola, long Term Evolution (LTE): A Technical Overview, 2010</span></span></li>
<li style="line-height: 18px;">
<span style="font-size: 14px;"><span style="font-family: arial, helvetica, sans-serif;">3GPP 25.913, Requirements for Evolved UTRA (E-UTRA) and Evolved UTRAN (E-UTRAN) (Release 8), 2008</span></span></li>
<li style="line-height: 18px;">
<a href="http://www.3gpp.org/LTE" style="font-family: arial, helvetica, sans-serif; font-size: 14px; line-height: 18px; text-decoration: none;">http://www.3gpp.org/LTE</a></li>
</ol>