---
layout: post
title:  What is VoIP?
date:   2014-02-24 06:00:00
description: VoIP refers to the technology required for voice communication over IP, while ToIP is a telephone service for users, which uses VoIP technology to give such service. VoIP allows voice transmission via an IP network, including those connected to the Internet. It involves digitizing voice signals, via a codec. 
tags: network voip traffic
categories: Networks
thumbnail: assets/img/TICs/what-is-voip/1_en.png
---
The development of VoIP (Voice over Internet Protocol) technologies have been widely accepted by **companies seeking lower costs for voice communications** mainly in SMEs (Small and Medium Enterprises) environments. The term VoIP should not be confused with ToIP (Telephony over IP), **VoIP refers to the technology required for voice communication over IP, while ToIP is a telephone service for users, which uses VoIP technology to give such service**.

**VoIP allows voice transmission via an IP network, including those connected to the Internet. It involves digitizing voice signals, via a codec**. The bandwidth consumption of such communication is directly related to the codec as shown in Table #1.

| Codec | Bit-rate |
| --- | --- |
| G.711 | $$56$$ or $$64 Kbps$$ |
| G.722 | $$48$$, $$56$$ or $$64 Kbps$$ |
| G.723 | bit-rate $$5,3$$ or $$6,4 Kbps$$ |
| G.728 | $$16 Kbps$$ |
| G.729 | $$8$$ or $$13 Kbps$$ |

<div class="caption">
    Table #1: Bandwidth consumption for different codec.
</div>

Furthermore, VoIP uses various types of techniques for call signaling, not having a defined protocol in this field. SIP (Session Initiation Protocol) is one of the protocols used for this purpose, also deployments with H.323 (a recommendation from the ITU Telecommunication Standardization Sector, ITU-T) or IAX (Inter-Asterisk eXchange protocol, native to the Asterisk private branch exchange, PBX) can be found.

SIP is one of the most widespread protocol in the implementation of ToIP. **This protocol is responsible for the end-to-end communication signaling, call establishment procedures, communication modification and its termination**. For transmitting real-time data, VoIP uses the RTP (Real time Transport Protocol) protocol, which is responsible for transmission control in the multimedia sessions and uses UDP (User Datagram Protocol) as the transport protocol. In Figure #1, the header distribution for each VoIP packet is observed.

<div class="row mt-3" style="text-align: center">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="assets/img/TICs/what-is-voip/1_en.png" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Figure #1: VoIP Packet transmitted by the stations.
</div>

There are various devices that act as a VoIP gateway to a conventional telephone network and vice-versa, using the SIP signaling protocol for communication. Typically, **these devices can be configured with relative facility, through an IVR (Interative Voice Response) menu or with a web server from any browser**.

The IVR menu allows the device basic configuration, for example, assigning IP addresses to each terminal. The advanced configuration of the VoIP gateway, consists in the allocation of the corresponding parameters for the router functionality and others associated to voice. This configuration is done through a web browser. Among the most relevant aspects of the configuration, the **use of SIP as the signaling protocol is included, the NAT (Network Address Translation) configuration and others routing functionalities. On the other hand, in the audio settings we can select different codecs**, for example G729, the number of samples per packet and the silence suppression.

<div class="row mt-3" style="text-align: center">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="assets/img/TICs/what-is-voip/2.png" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Figure #2: Sample audio settings.
</div>
