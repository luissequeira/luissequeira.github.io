---
layout: post
title:  Femto-cell challenges in managing interferences
date:   2014-03-31 05:00:00
description: In this context, operators have deployed femto-cells systems in order to decrease the distance to the EU and to maintain good signal quality. However, femto-cells must operate in the designated band frequency for such communication and match to the assigned frequencies to the operator.
tags: 4G LTE femtocell
categories: Research
---
<p>
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;">Some studies show that over 50% of voice calls and 70% of the data traffic comes from inside <span style="color:#ff8c00;"><strong>[1]</strong></span>, voice calls do not require high bandwidth, but certain quality parameters are require to ensure the voice recognition of users at the other end of the communication, on the contrary, the data traffic requires high transmission rates to send information with a lot of megabytes, such as multimedia applications require, to name one example. <strong>One way to ensure high transmission rates on radio systems, is to maintain high signal quality at both ends of the communication, and hence, mitigate the effects of loss and interference in the communication channel</strong>.</span></span></p>
<p>
<span style="font-family: arial, helvetica, sans-serif; font-size: 14px;">In this context, operators have deployed femto-cells systems in order to decrease the distance to the EU and to maintain good signal quality. However, <strong>femto-cells must operate in the designated band frequency for such communication and match to the assigned frequencies to the operator</strong>, from this perspective, femto-cell generates interference and it can be given in the following ways <span style="color:#ff8c00;"><strong>[2]</strong></span>:</span></p>
<ul>
<li>
<p>
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;">Femto-cell to femto-cell.</span></span></p>
</li>
<li>
<p>
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;">Femto-cell to macro-cell</span></span></p>
</li>
<li>
<p>
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;">Macro-cell to femto-cell.</span></span></p>
</li>
</ul>
<p>
<span style="font-family: arial, helvetica, sans-serif; font-size: 14px;"><strong>The interference problems between femto-cell is due the coverage that they have</strong>, this type of interference will occur primarily within the coverage limits where the femto-cells interact each other, the <span style="color:#0000ff;"><strong>Figure # 1</strong></span> shows this phenomenon, in which the FAP 1 and FAP 2 <strong>coverage have overlaps producing signal degradation</strong> for users of both femto-cells in that area.</span></p>
<p style="text-align: center;">
<br />
<img alt="" src="images/Research/femtoceldas-desafios-gestion-interferencias/1.png" style="height: 408px; width: 500px;" /></p>
<p style="text-align: center;">
<span style="font-family: arial, helvetica, sans-serif; font-size: 14px; color: rgb(0, 0, 255);"><strong>Figure # 1</strong></span><span style="font-family: arial, helvetica, sans-serif; font-size: 14px;">. Interference problems between macro/femto cells.</span></p>

<p>
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;">Another case of interference is the interference received by the mobile 2, we assume that this device is managed by the macro-cell and does not have permission to access the femto-cell 1, however, it is within the coverage area of ​​the femto-cell, this will produce interference with the mobile device, since the frequency channels for communicating with the macro-cell and femto-cell are located in the same frequency band, this type of <strong>interference is produced from femto-cell to macro-cell, it can also occur in the opposite direction from macro-cell to femto-cell</strong>.</span></span></p>
<p>
<span style="font-family: arial, helvetica, sans-serif; font-size: 14px;">When a mobile is managed by a macrocell and it is far from eNodeB and close to a femto-cell, it will transmit at a higher power to cover losses associated with the link, however, in doing so, generates more interference to the femto-cell. Moreover, the femto-cell will request to the managed mobiles, an increment in the transmission power to cover the interference, this in turn, will generate a higher level of interference to the mobile which is managed by the macro-cell.<strong> The network access methods will have to manage the problem of power management in an efficient way to allow coexistence and ensure quality of service</strong>.</span></p>
<p>
<span style="font-family: arial, helvetica, sans-serif; font-size: 14px;">In this context, a problem arises concerning the femto-cell coverage management, since it should minimize interference from them, and simultaneously, meet the requirements of service quality. Therefore, the service provider must have a precise control of the femto-cell in several ways:</span></p>
<ul>
<li>
<strong><span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;">It must ensure the use of the allocated spectrum and verify that the femto-cell is not transmitting out the corresponding frequency band.</span></span></strong></li>
<li>
<strong><span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;">Moving of residences must be managed properly, as this could develop some communities with a lot of interference by the accumulation of femto-cells nearby.</span></span></strong></li>
<li>
<strong><span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;">It must be noted, that traditional planning techniques such as frequency reuse have no sense because the user is who installs the femto-cells.</span></span></strong></li>
</ul>
<p>
<span style="font-family: arial, helvetica, sans-serif; font-size: 14px;">On the other hand, some <strong>problems were found in the femto-cell implementation in areas where there is a Wi-Fi network</strong>, in <span style="color:#ff8c00;"><strong>[1]</strong></span>, the authors comment some cases where the FAP experiences difficulties in transferring data, even in voice services.</span></p>
<h1>
<br />
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;">References</span></span></h1>
<ol>
<li>
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;">Vikram C, Jeffrey GA &amp; Alan G. Femtocell Networks: A Survey. IEEE Comunication Magzine (2008) 46: pp. 59-67.</span></span></li>
<li>
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;">G DLR, A V, D L &amp; Jie Z. Access control Mechanisms for Femtocells. IEEE Communications Magazine (2010) 48: pp. 33-39.</span></span></li>
</ol>