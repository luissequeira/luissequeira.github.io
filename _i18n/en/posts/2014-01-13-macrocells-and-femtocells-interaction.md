---
layout: post
title:  Macrocells and femtocells Interaction
date:   2014-01-13 06:00:00
description: Macro-cells are not very efficient in the residential area due to penetration problems that have been mentioned in a previous article, also in the macro-cells there are many users and is more difficult to provide QoS to all of them. For these reasons Internet Service Providers (ISP) have opted for femto-cell implementation at residential level, in order to increase the quality of services provided.
tags: LTE femtocell macrocell wireless access-network 4G broadband QoS
categories: LTE (4G)
---
<p>
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;">Macro-cells are not very efficient <span style="color:#ff8c00;"><strong>[1]</strong></span> in the residential area due to penetration problems that have been mentioned in a previous article, also in the macro-cells there are many users and is more difficult to provide QoS to all of them. <!--StartFragment-->For these reasons Internet Service Providers (ISP) have opted for femto-cell implementation at residential level, in order to increase the quality of services provided.</span></span></p>
<p>
<span style="font-family: arial, helvetica, sans-serif; font-size: 14px;">Femto-cells are low-power base stations that provide low cost and high quality wireless services to residential, in this area offer a coverage of approximately 10 m </span><span style="font-family: arial, helvetica, sans-serif; font-size: 14px; color: rgb(255, 140, 0);"><strong>[2]</strong></span><span style="font-family: arial, helvetica, sans-serif; font-size: 14px;">, which are designed to integrate automatically with macro-cell networks. Femto-cells integrate with mobile operator through a broadband connection, typically DSL </span><span style="font-family: arial, helvetica, sans-serif; font-size: 14px; color: rgb(255, 140, 0);"><strong>[2]</strong></span><span style="font-family: arial, helvetica, sans-serif; font-size: 14px;"> and </span><span style="font-family: arial, helvetica, sans-serif; font-size: 14px; color: rgb(255, 140, 0);"><strong>[3]</strong></span><span style="font-family: arial, helvetica, sans-serif; font-size: 14px;">, as can be seen in </span><span style="font-family: arial, helvetica, sans-serif; font-size: 14px; color: rgb(0, 0, 255);"><strong>Figure # 1</strong></span><span style="font-family: arial, helvetica, sans-serif; font-size: 14px;">. However it can also be performed by a wireless link as mentioned in </span><span style="font-family: arial, helvetica, sans-serif; font-size: 14px; color: rgb(255, 140, 0);"><strong>[4]</strong></span><span style="font-family: arial, helvetica, sans-serif; font-size: 14px;">. In General, the femto-cell redirects the traffic from the home cellular system, through the broadband connection, releasing the resource consumption of the macro-cell.</span></p>
<p>
&nbsp;</p>
<p style="text-align: center;">
<img alt="" src="images/TICs/interaccion-de-macroceldas-y-femtoceldas/macro_femto_1.jpg" /></p>
<p style="text-align: center;">
<span style="font-family: arial, helvetica, sans-serif; font-size: 14px; color: rgb(0, 0, 255);"><strong>Figure # 1</strong></span><span style="font-family: arial, helvetica, sans-serif; font-size: 14px;">. Typical </span><span style="font-family: arial, helvetica, sans-serif; font-size: 14px;">Femto-cell </span><span style="font-family: arial, helvetica, sans-serif; font-size: 14px; color: rgb(255, 140, 0);"><strong>[3]</strong></span><span style="font-family: arial, helvetica, sans-serif; font-size: 14px;">.</span></p>

<p>
<span style="font-family: arial, helvetica, sans-serif; font-size: 14px;">Femtocells have a number of advantages for both mobile service providers and users, these last may receive better signal level, since the distance between the femto-cell and the EU is reduced, it causes the SINR is higher increasing capacity and encouraging higher levels of QoS. In turn, the spectral efficiency is increased due to the number of users per hertz per unit area, in addition, the low levels of transmission power generates a lower power consumption because the mobile does not require too much power for transmission. Furthermore, when implemented in residential scenarios, the number of users is small and may share resources <span style="color:#ff8c00;"><strong>[4]</strong></span></span><span style="font-family: arial, helvetica, sans-serif; font-size: 14px;">.</span></p>
<p>
<span style="font-family: arial, helvetica, sans-serif; font-size: 14px;"><span style="color:#0000ff;"><strong>Figure # 2</strong></span> shows two scenarios: in <span style="color:#0000ff;"><strong>a)</strong></span>, a traditional macrocell where eNodeB provides coverage to a particular area, if the case of two UEs that are at the same distance from the eNodeB, is analyzed, in which the difference between both is that one of them is outdoors (UE1) and the other in a house room (EU4), the EU4 will have more losses due to penetration in house. </span><span style="font-family: arial, helvetica, sans-serif; font-size: 14px;">On the other hand, in <span style="color:#0000ff;"><strong>b)</strong></span> the implementation of two femto-cells is proposed, one in each house, to increase the quality of the signal within the property, and therefore the throughput and quality of service provided.</span></p>
<p>
&nbsp;</p>
<p style="text-align: center;">
<img alt="" src="images/TICs/interaccion-de-macroceldas-y-femtoceldas/propagacion_2.jpg" /></p>
<p style="text-align: center;">
<span style="font-family: arial, helvetica, sans-serif; font-size: 14px; color: rgb(0, 0, 255);"><strong>Figure # 2</strong></span><span style="font-family: arial, helvetica, sans-serif; font-size: 14px;">. </span><span style="font-family: arial, helvetica, sans-serif; font-size: 14px; color: rgb(0, 0, 255);"><strong>a)</strong></span><span style="font-family: arial, helvetica, sans-serif; font-size: 14px;"> </span><span style="font-family: arial, helvetica, sans-serif; font-size: 14px;">Traditional macro-cell</span><span style="font-family: arial, helvetica, sans-serif; font-size: 14px;">; </span><span style="font-family: arial, helvetica, sans-serif; font-size: 14px; color: rgb(0, 0, 255);"><strong>b)</strong></span><span style="font-family: arial, helvetica, sans-serif; font-size: 14px;"> </span><span style="font-family: arial, helvetica, sans-serif; font-size: 14px;">Interaction of macro-cell with femto-cells&nbsp;</span><span style="font-family: arial, helvetica, sans-serif; font-size: 14px; color: rgb(255, 140, 0);"><strong>[2]</strong></span><span style="font-family: arial, helvetica, sans-serif; font-size: 14px;">.</span></p>
<p style="text-align: center;">
&nbsp;</p>
<h2>
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;">References</span></span></h2>
<ol>
<li>
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;">G. de la Roche, A. Valcarce, D. Lopez-Perez, Jie Zhang. Access control Mechanisms for Femtocells. Communications Magazine, IEEE, vol. 48, no. 1, pp. 33-39, 2010.</span></span></li>
<li>
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;">D. Calin, H. Claussen, H. Uzunalioglu. On Femto Deployment Architectures and Macrocell Offloading Benefits in Joint Macro-Femto Deployments. Communications Magazine, IEEE, vol. 48, no. 1, pp. 26-32, 2010.</span></span></li>
<li>
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;"><a href="http://www.femtoforum.org/">http://www.femtoforum.org</a></span></span></li>
<li>
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;">Vikram Chandrasekhar, Jeffrey G. Andrews, Alan Gatherer. Femtocell Networks: A Survey. Communications Magazine, IEEE, vol. 46, no. 9, pp. 59-67, 2008.</span></span></li>
</ol>
<p>
&nbsp;</p>
<p>
&nbsp;</p>