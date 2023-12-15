---
layout: post
title:  What is VoIP?
date:   2014-02-24 06:00:00
description: VoIP refers to the technology required for voice communication over IP, while ToIP is a telephone service for users, which uses VoIP technology to give such service. VoIP allows voice transmission via an IP network, including those connected to the Internet. It involves digitizing voice signals, via a codec. 
tags: network voip
categories: Services
---
<p>
<span style="font-family: arial, helvetica, sans-serif; font-size: 14px;">The development of VoIP (Voice over Internet Protocol) technologies have been widely accepted by <strong>companies seeking lower costs for voice communications</strong> mainly in SMEs (Small and Medium Enterprises) environments. The term VoIP should not be confused with ToIP (Telephony over IP), <strong>VoIP refers to the technology required for voice communication over IP, while ToIP is a telephone service for users, which uses VoIP technology to give such service</strong>.</span></p>
<p>
<span style="font-family: arial, helvetica, sans-serif; font-size: 14px;"><strong>VoIP allows voice transmission via an IP network, including those connected to the Internet. It involves digitizing voice signals, via a codec</strong>. The bandwidth consumption of such communication is directly related to the codec as shown in <span style="color:#0000ff;"><strong>Table # 1</strong></span>.</span></p>
<p>
&nbsp;</p>
<table align="center" border="1" cellpadding="1" cellspacing="1" style="width: 262px;">
<tbody>
<tr>
<td style="width: 94px; text-align: center;">
<h1>
<strong><span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;">Codec</span></span></strong></h1>
</td>
<td style="width: 154px; text-align: center;">
<h1>
<strong><span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;">Bit-rate</span></span></strong></h1>
</td>
</tr>
<tr>
<td style="width: 94px; text-align: center;">
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;">G.711</span></span></td>
<td style="width: 154px; text-align: center;">
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;">56 or 64 Kbps</span></span></td>
</tr>
<tr>
<td style="width: 94px; text-align: center;">
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;">G.722</span></span></td>
<td style="width: 154px; text-align: center;">
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;">48, 56 or 64 Kbps</span></span></td>
</tr>
<tr>
<td style="width: 94px; text-align: center;">
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;">G.723</span></span></td>
<td style="width: 154px; text-align: center;">
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;">bit-rate 5,3 or 6,4 Kbps</span></span></td>
</tr>
<tr>
<td style="width: 94px; text-align: center;">
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;">G.728</span></span></td>
<td style="width: 154px; text-align: center;">
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;">16 Kbps</span></span></td>
</tr>
<tr>
<td style="width: 94px; text-align: center;">
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;">G.729</span></span></td>
<td style="width: 154px; text-align: center;">
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;">8 or 13 Kbps</span></span></td>
</tr>
</tbody>
</table>
<p style="text-align: center;">
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;"><span style="color:#0000ff;"><strong>Tabla # 1</strong></span>: Bandwidth consumption for different codec</span></span></p>
<p>
&nbsp;</p>
<p>
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;"><!--StartFragment-->Furthermore, VoIP uses various types of techniques for call signaling, not having a defined protocol in this field. SIP (Session Initiation Protocol) is one of the protocols used for this purpose, also deployments with H.323 (a recommendation from the&nbsp;ITU Telecommunication Standardization Sector, ITU-T) or IAX (Inter-Asterisk eXchange protocol, native to the&nbsp;Asterisk&nbsp;private branch exchange, PBX) can be found.</span></span><!--EndFragment--></p>
<p>
<span style="font-family: arial, helvetica, sans-serif; font-size: 14px;">SIP is one of the most widespread protocol in the implementation of ToIP. </span><span style="font-family: arial, helvetica, sans-serif; font-size: 14px;">This protocol <strong>is responsible for the end-to-end communication signaling, call establishment procedures, communication modification and its termination</strong>.</span><span style="font-family: arial, helvetica, sans-serif; font-size: 14px;">For transmitting real-time data, VoIP uses the RTP (Real time Transport Protocol) protocol, which is responsible for transmission control in the multimedia sessions and uses UDP (User Datagram Protocol) as the transport protocol. In <span style="color:#0000ff;"><strong>Figure # 1</strong></span>, the header distribution for each VoIP packet is observed.</span></p>
<p>
&nbsp;</p>
<p style="text-align: center;">
<img alt="" src="images/TICs/what-is-voip/1_en.png" style="height: 136px; width: 500px;" /></p>
<p style="text-align: center;">
<span style="font-family: arial, helvetica, sans-serif; font-size: 14px; color: rgb(0, 0, 255);"><strong>Figure # 1</strong></span><span style="font-family: arial, helvetica, sans-serif; font-size: 14px;">: VoIP Packet transmitted by the stations.</span></p>

<p>
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;"><!--StartFragment-->There are various devices that act as a VoIP gateway to a conventional telephone network and vice-versa, using the SIP signaling protocol for communication. Typically, <strong>these devices can be configured with relative facility, through an IVR (Interative Voice Response) menu or with a web server from any browser</strong>.</span></span><!--EndFragment--></p>
<p>
<span style="font-family: arial, helvetica, sans-serif; font-size: 14px;">The IVR menu allows the device basic configuration, for example, assigning IP addresses to each terminal. The advanced configuration of the VoIP gateway, consists in the allocation of the corresponding parameters for the router functionality and others associated to voice. This configuration is done through a web browser. </span><span style="font-family: arial, helvetica, sans-serif; font-size: 14px;">Among the most relevant aspects of the configuration, the <strong>use of SIP as the signaling protocol is included, the NAT (Network Address Translation) configuration and others routing functionalities. On the other hand, in the audio settings we can select different codecs</strong>, for example G729, the number of samples per packet and the silence suppression.</span></p>
<p style="text-align: center;">
&nbsp;</p>
<p style="text-align: center;">
<img alt="" src="images/TICs/what-is-voip/2.png" style="height: 204px; width: 500px;" /></p>
<p style="text-align: center;">
<span style="font-family: arial, helvetica, sans-serif; font-size: 14px; color: rgb(0, 0, 255);"><strong>Figure # 2</strong></span><span style="font-family: arial, helvetica, sans-serif; font-size: 14px;">: Sample audio settings.</span></p>