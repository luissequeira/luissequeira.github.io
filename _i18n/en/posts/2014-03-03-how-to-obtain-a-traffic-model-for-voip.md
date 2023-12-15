---
layout: post
title:  How to obtain a traffic model for VoIP?
date:   2014-03-03 06:00:00
description: In this article, we describe how to obtain a traffic model for VoIP which is quite easy to interpret and it provides some of the things that must be done.
tags: traffic-model voip multimedia
categories: Research
---
<p>
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;">In order to perform estimations of a traffic model for multimedia flows, it is necessary for the researcher to have precise control of the test environment, minimizing errors and interference that may occur, leaving a test scenario that allows a smooth development to the application to be modeled. <strong>As an example, we have selected a <a href="en/library/services/item/64-what-is-voip">VoIP</a> traffic</strong> which is quite easy to interpret and it provides some of the things that must be done.</span></span></p>
<p>
&nbsp;</p>
<h1>
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;">Scenario for testing</span></span></h1>
<p>
<span style="font-family: arial, helvetica, sans-serif; font-size: 14px;"><strong><span style="color:#0000ff;">Figure # 1 </span>shows the diagram used for testing in order to obtain the pattern of traffic on the transmission of voice over IP is shown</strong>. In this case, we use a voice over IP gateway <em>Linksys SPA 3102</em>, with the aim of connecting a conventional telephone system with an IP network. A sniffer can capture traffic using the network for later analysis.</span></p>
<p>
&nbsp;</p>
<p style="text-align: center;">
<img alt="" src="images/Research/como-obtener-modelo-trafico-voip/1.png" style="height: 332px; width: 500px;" /></p>
<p style="text-align: center;">
<span style="font-family: arial, helvetica, sans-serif; font-size: 14px; color: rgb(0, 0, 255);"><strong>Figure # 1</strong></span><span style="font-family: arial, helvetica, sans-serif; font-size: 14px;">: Scenario used to determine the voice traffic.</span></p>

<h1>
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;">Procedure</span></span></h1>
<p>
<span style="font-family: arial, helvetica, sans-serif; font-size: 14px;"><strong>First, we must configure the gateway</strong>, this can be done with relative ease by an IVR (Interative Voice Response) menu or through any Internet browser. The most relevant aspects of the configuration are the use of SIP (Session Initiation Protocol) as the signaling protocol, assigning IP addresses to each gateway and disabling NAT (Network Address Translation). For audio settings: the G.729 codec is used, a packetization&nbsp;</span><span style="font-family: arial, helvetica, sans-serif; font-size: 14px;">of two samples per packet and no silence suppression is performed.</span></p>
<p>
<strong style="font-family: arial, helvetica, sans-serif; font-size: 14px;">After the equipment configuration, a sniffer is launched</strong><span style="font-family: arial, helvetica, sans-serif; font-size: 14px;"> in order to make the traffic captures, </span><strong style="font-family: arial, helvetica, sans-serif; font-size: 14px;">subsequently a call between terminals is made</strong><span style="font-family: arial, helvetica, sans-serif; font-size: 14px;">. Packet capture is performed by sniffer, while the call is in progress and the data is stored for later analysis.</span></p>
<p>
&nbsp;</p>
<h1>
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;">VoIP model</span></span></h1>
<p>
<span style="font-family: arial, helvetica, sans-serif; font-size: 14px;">If we analyze the captured trace, with any of the recommended <a href="en/laboratory/tools/item/40-the-2-best-tools-for-the-capture-and-the-interpretation-of-network-data">tools for the capture and the interpretation of network data</a>, <strong>we can reconstruct the headers distribution of each captured packet</strong> and thus deduce the <strong><span style="color:#0000ff;">Figure # 2</span></strong>.</span></p>
<p>
&nbsp;</p>
<p style="text-align: center;">
<img alt="" src="images/Research/como-obtener-modelo-trafico-voip/2_en.png" /></p>
<p style="text-align: center;">
<span style="font-family: arial, helvetica, sans-serif; font-size: 14px; color: rgb(0, 0, 255);"><strong>Figure # 2</strong></span><span style="font-family: arial, helvetica, sans-serif; font-size: 14px;">: Header description for each packet for voice traffic.</span></p>
<p style="text-align: center;">
&nbsp;</p>
<p>
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;">As we can be seen, <strong>VoIP uses RTP (Real-Time Transport Protocol) for transmitting data in real time and this is transported by UDP</strong>, <span style="color:#0000ff;"><strong>Figure # 2</strong></span> allows checking the use of those protocols. <strong>We also highlight in the analysis of packet capture, that the transmission of each packet has a constant distribution (no packet bursts)</strong>. In addition, we confirm that each terminal sends packets every 20 ms and the data content in packets corresponds to the type of used codec (G.729) and the number of defined samples in the configuration for each gateway (two samples per packet).</span></span></p>
<p>
<span style="font-family: arial, helvetica, sans-serif; font-size: 14px;">An important aspect to consider for a traffic model is time, or variation thereof, in which each packet is forwarded. This requires to extract from trace file, the time between the beginning (or arrivals) of each packet. </span><span style="font-family: arial, helvetica, sans-serif; font-size: 14px; color: rgb(0, 0, 255);"><strong>Figure # 3</strong></span><span style="font-family: arial, helvetica, sans-serif; font-size: 14px;"> shows the variation in the duration of each packet, for the sent and received voice traffic, based on the transmission time. </span><strong style="font-family: arial, helvetica, sans-serif; font-size: 14px;">For samples taken in this case, an average inter-packet time of 20 ms with a standard deviation of 0.62 ms was obtained. Each voice connection has a bandwidth consumption, on IP level of BW = (60x8) / 20X10<sup>-3</sup>, which corresponds to 24 Kbps</strong><span style="font-family: arial, helvetica, sans-serif; font-size: 14px;">.</span></p>
<p>
&nbsp;</p>
<p style="text-align: center;">
<img alt="" src="images/Research/como-obtener-modelo-trafico-voip/3_en.png" style="height: 542px; width: 500px;" /></p>
<p style="text-align: center;">
<span style="font-family: arial, helvetica, sans-serif; font-size: 14px; color: rgb(0, 0, 255);"><strong>Figure # 3</strong></span><span style="font-family: arial, helvetica, sans-serif; font-size: 14px;">: Time detail between the beginnings of each packet for voice traffic.</span></p>
<p style="text-align: center;">
&nbsp;</p>
<h1>
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;">Conclusion</span></span></h1>
<p>
<span style="font-family: arial, helvetica, sans-serif; font-size: 14px;">The voice transmission model is relatively simple and stable in terms of time and size because <strong>no burst behavior is detected, or it can be consider as only one. Generating this type of IP flow, consists on the sending of 60-byte packets (including headers) every 20 ms with a standard deviation of 0.62 ms, this if the G.729 codec and a packetization of two samples are used</strong>. In the case, where the change of codec or the number of samples per packet is required, the changes are simple to make. For this, we must take into account the sampling frequency defined by the new used codec and the amount of samples that we want to package which would be included after the RTP header.</span></p>
<p>
&nbsp;</p>