---
layout: post
title:  Quality of Service end-to-end in femto-cells environments
date:   2013-12-30 06:00:00
description: From the point of view of LTE management, it is permitted to define profiles and classes of services, which are key points when negotiating QoS mobile requirements during the communication establishment, the transit of packets, even in handovers. However, it is necessary to consider the access and transport network if we want to ensure end-to-end QoS. The access network should have clearly configured the types of services, traffic types, among others, by suitably adjusting parameters, that define the modulation and coding schemes, maximum latency, jitter, guaranteed minimum bandwidth, allowed delay, and other parameters that technology allows to adapt depending on the service type we access.
tags: LTE 4G QoS femtocell wireless
categories: Networks
thumbnail: assets/img/TICs/quality-of-service-end-to-end-in-femto-cells-environments/1.jpg
---
The telecommunications network of an ISP (Internet Service Provider) **is actually an interaction of various networks types**, within LTE (4G) can be highlighted as an access network to the end user. The information flow reaches to the user through several infrastructures, on which the ISP carries data traffic, from this perspective, **some necessary points will be discussed in order to ensure the Quality of Service** (QoS) in such environments.

From the LTE management point of view, **it is permitted to define profiles and classes of services**, which are key points when negotiating QoS mobile requirements during the communication establishment, the transit of packets, even in handovers. However, **it is necessary to consider the access and transport network if we want to ensure end-to-end QoS**.

## Transport Network

A typical scenario of an Internet service provider could be described as shown in Figure #1, it can be seen that LTE is only a part of the provider's access network. The ISP has different types of access networks depending on the provided services. All the necessary infrastructure to transport information from the access networks, must transit through the core network. The core is also connected with other different network types, where the end service is usually located (Internet, PSTN, ftp services, video streaming, voice or other), which the user wants to access.

<div class="row mt-3" style="text-align: center">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="assets/img/TICs/quality-of-service-end-to-end-in-femto-cells-environments/1.jpg" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Figure #1: ISP's simplified topology [2].
</div>

**The use of managing QoS protocols and traffic engineering are commonly used in the transport network**. One of the protocols that can help in this aspect is: Diffserv which uses 8 bits located in the IP header called Diffserv Code Point (DSCP), thus **all packets marked with the same DSCP have the same routers treatment (same priority) within the network**. This mechanism will reduce the packet delay, depending on the priority which have been marked.

Although, IPv6 is not a QoS protocol, it takes into account some aspects because **it allows traffic classification (CoS) and flow identification, oriented to DiffServ and IntServ trends** respectively. On the other hand, MPLS neither is a QoS protocol, however, is a switching method that allows traffic engineering functions for **allocating resources to different traffic types with certain QoS guarantees in a specific path**. Using this protocol in packets with the same label will follow the same path in the network, generating that delay tends to be constant between the packets with identical label.

## Network access

From this perspective, providing end-to-end QoS becomes a problem that must be addressed to the care of the case. **The access network should have clearly configured the types of services, traffic types, among others, by suitably adjusting parameters, that define the modulation and coding schemes, maximum latency, jitter, guaranteed minimum bandwidth, allowed delay**, and other parameters that technology allows to adapt depending on the service type we access.

Femtocells carry data and voice traffic, for this reason, certain QoS requirements must be guaranteed to meet the minimum delays that some types of services needed. **If the mobile service provider is the same provider of the broadband services (ADSL typically), it can adequately manage QoS for traffic access from the femto-cell to the network transport to guarantee a minimum bandwidth**, for example, and managing resources in the case of larger bandwidth requirements.

Another scenario that can occur in these cases, is that the **line broadband service and mobile access are provided by different vendors** (see Figure #2), for these cases, a possible solution would be a **Service Level Agreement (SLA)** between these operators in terms of QoS for traffic coming from the femto-cell, so **it could ensure the user QoS levels for the different types of traffic classes**.

<div class="row mt-3" style="text-align: center">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="assets/img/TICs/quality-of-service-end-to-end-in-femto-cells-environments/2.jpg" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Figure #2: Broadband and mobile access provided by different ISPs.
</div>

## Related Aspects

From the end-to-end control point of view, we might consider other protocols that may be a solution more related to application management, such as video, voice, streaming, among others. In this sense, we could mention protocols as e.g.: RTP, RTCP and RTSP.

RTP is an IP-based protocol that provides support for the transport of real-time data (streaming video and audio), it was designed to work with the RTCP protocol for maintaining transmission quality, **one of its functions is the QoS monitoring and congestion control, providing information about the quality of the transmitted data and it allows to adjust its transmission based on the receiver reports**. On the other hand, RTSP is a application layer protocol in a client-server environment which controls the multimedia data flow over the IP network. In summary, **RSTP sets and controls the flow of audio and video between servers and clients, acting as a "network remote control" between the server and the client**.

## References

1. Ericsson , Gerhard, Fritze, SAE - The Core Network for LTE , 2008
2. Nortel, Long-Term Evolution (LTE): The vision beyond 3G, 2008
3. Motorola, long Term Evolution (LTE): A Technical Overview, 2010
4. 3GPP 25.913, Requirements for Evolved UTRA (E-UTRA) and Evolved UTRAN (E-UTRAN) (Release 8), 2008
5. [http://www.3gpp.org/LTE](http://www.3gpp.org/LTE)
