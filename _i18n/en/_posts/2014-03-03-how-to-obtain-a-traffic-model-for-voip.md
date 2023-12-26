---
layout: post
title:  How to obtain a traffic model for VoIP?
date:   2014-03-03 06:00:00
description: In this article, we describe how to obtain a traffic model for VoIP which is quite easy to interpret and it provides some of the things that must be done.
tags: traffic voip multimedia
categories: Networks Innovation 
thumbnail: assets/img/Research/como-obtener-modelo-trafico-voip/1.png
---
In order to perform estimations of a traffic model for multimedia flows, it is necessary for the researcher to have precise control of the test environment, minimizing errors and interference that may occur, leaving a test scenario that allows a smooth development to the application to be modeled. **As an example, we have selected a [VoIP]({% post_url 2014-02-24-what-is-voip %}) traffic** which is quite easy to interpret and it provides some of the things that must be done.

## Scenario for testing

**Figure #1 shows the diagram used for testing in order to obtain the pattern of traffic on the transmission of voice over IP is shown**. In this case, we use a voice over IP gateway *Linksys SPA 3102*, with the aim of connecting a conventional telephone system with an IP network. A sniffer can capture traffic using the network for later analysis.

<div class="row mt-3" style="text-align: center">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="assets/img/Research/como-obtener-modelo-trafico-voip/1.png" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Figure #1: Scenario used to determine the voice traffic.
</div>

## Procedure

**First, we must configure the gateway**, this can be done with relative ease by an IVR (Interative Voice Response) menu or through any Internet browser. The most relevant aspects of the configuration are the use of SIP (Session Initiation Protocol) as the signaling protocol, assigning IP addresses to each gateway and disabling NAT (Network Address Translation). For audio settings: the G.729 codec is used, a packetization of two samples per packet and no silence suppression is performed.<

**After the equipment configuration, a sniffer is launched** in order to make the traffic captures, **subsequently a call between terminals is made**. Packet capture is performed by sniffer, while the call is in progress and the data is stored for later analysis.

## VoIP model

If we analyze the captured trace, with any of the recommended [tools for the capture and the interpretation of network data]({% post_url 2013-12-02-the-2-best-tools-for-the-capture-and-the-interpretation-of-network-data %}), **we can reconstruct the headers distribution of each captured packet** and thus deduce the Figure #2.

<div class="row mt-3" style="text-align: center">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="assets/img/Research/como-obtener-modelo-trafico-voip/2_en.png" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Figure #2: Header description for each packet for voice traffic.
</div>

As we can be seen, **VoIP uses RTP (Real-Time Transport Protocol) for transmitting data in real time and this is transported by UDP**, Figure #2 allows checking the use of those protocols. **We also highlight in the analysis of packet capture, that the transmission of each packet has a constant distribution (no packet bursts)**. In addition, we confirm that each terminal sends packets every $$20 ms$$ and the data content in packets corresponds to the type of used codec (G.729) and the number of defined samples in the configuration for each gateway (two samples per packet).

An important aspect to consider for a traffic model is time, or variation thereof, in which each packet is forwarded. This requires to extract from trace file, the time between the beginning (or arrivals) of each packet. Figure #3 shows the variation in the duration of each packet, for the sent and received voice traffic, based on the transmission time. **For samples taken in this case, an average inter-packet time of $$20 ms$$ with a standard deviation of $$0.62 ms$$ was obtained. Each voice connection has a bandwidth consumption, on IP level of $$BW = (60x8) / 20X10^{-3}$$, which corresponds to $$24 Kbps$$**.

<div class="row mt-3" style="text-align: center">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="assets/img/Research/como-obtener-modelo-trafico-voip/3_en.png" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Figure #3: Time detail between the beginnings of each packet for voice traffic.
</div>

## Conclusion

The voice transmission model is relatively simple and stable in terms of time and size because **no burst behavior is detected, or it can be consider as only one. Generating this type of IP flow, consists on the sending of 60-byte packets (including headers) every $$20 ms$$ with a standard deviation of $$0.62 ms$$, this if the G.729 codec and a packetization of two samples are used**. In the case, where the change of codec or the number of samples per packet is required, the changes are simple to make. For this, we must take into account the sampling frequency defined by the new used codec and the amount of samples that we want to package which would be included after the RTP header.
