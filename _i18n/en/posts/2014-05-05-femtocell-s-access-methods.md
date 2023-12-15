---
layout: post
title:  Femtocell's access methods
date:   2014-05-05 05:00:00
description: Femtocells basically have three different operating modes open access, closed access and a combination of both named hybrid access.
tags: 4G femtocell access-network
categories: QoS
---
<p>
<span style="font-family: arial, helvetica, sans-serif; font-size: 14px;"><strong>Femtocells are low-power and low-cost base stations</strong> that provide residential cellular services, providing a coverage of roughly 10 m <strong>[1]</strong>. They can integrate with mobile operator through a <strong>broadband connection</strong>, typically ADSL. In General, femtocell makes that the traffic from the home cellular system, <strong>deviates through the broadband connection</strong>, releasing the resource consumption of the macrocell.</span></p>
<p>
<span style="font-family: arial, helvetica, sans-serif; font-size: 14px;">The 3GPP has introduced the concept of Closed Subscriber Group (CSG), which essentially identifies a group of subscribers who have <strong>access permission to one or more cells</strong>. Femtocells basically have three different operating modes: <strong>open access, closed access and a combination of both named hybrid access</strong> <span style="color:#ff8c00;"><strong>[2]</strong></span> and<span style="color:#ff8c00;"> <strong>[3]</strong></span>, the access methods are:</span></p>
<ul>
<li>
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;"><strong>Open ccess:</strong> In this case, the UE can access the femtocell without any restrictions, this is seen in the <span style="color:#0000ff;"><strong>Figure # 1</strong></span> wherein the EU2 has unrestricted access to the femtocell in the building.</span></span></li>
<li>
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;"><strong>Closed Access:</strong> The administrator defines the only femtocell users (CSG) that can access the network. For this mode, emergency calls are exempt.</span></span></li>
<li>
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;"><strong>Hybrid Access:</strong> In this type of access, a limited amount of resources is allocated for access to users who are not part of CSG.</span></span></li>
</ul>
<p>
&nbsp;</p>
<p style="text-align: center;">
<img alt="" src="images/TICs/metodos-acceso-femtoceldas/1.png" style="height: 317px; width: 500px;" /></p>
<p style="text-align: center;">
<span style="font-family: arial, helvetica, sans-serif; font-size: 14px; color: rgb(0, 0, 255);"><strong>Figure # 1</strong></span><span style="font-family: arial, helvetica, sans-serif; font-size: 14px;">. Example of different femto-cell&#39;s access methods </span><span style="font-family: arial, helvetica, sans-serif; font-size: 14px; color: rgb(255, 140, 0);"><strong>[2]</strong></span><span style="font-family: arial, helvetica, sans-serif; font-size: 14px;">: Open access, closed access and hybrid access.</span></p>

<p>
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;"><span style="color:#0000ff;"><strong>Figure # 1</strong></span> is an example of the va</span></span><span style="font-family: arial, helvetica, sans-serif; font-size: 14px;">rious types of femtocell access which are defined by the 3GPP. </span><strong style="font-family: arial, helvetica, sans-serif; font-size: 14px;">The closed access provides the contracted services to users who are part of the CSG</strong><span style="font-family: arial, helvetica, sans-serif; font-size: 14px;">, providing some level of security and privacy when accessing the femtocell, further that all resources are available for femtocell users, </span><strong style="font-family: arial, helvetica, sans-serif; font-size: 14px;">guaranteeing certain level of QoS</strong><span style="font-family: arial, helvetica, sans-serif; font-size: 14px;">. However, the users who are not part of subscriber&#39;s group can not access the network, except for emergency calls. This type of access generates more interference, since nearby mobiles try to connect to the femtocell, but they will be blocked due the access method, so a large number of implicit signaling is generated in that area.</span></p>
<p>
&nbsp;</p>
<p>
<span style="font-family: arial, helvetica, sans-serif; font-size: 14px;">On the other hand, <strong>open access has a good advantage for the service provider because part of the traffic is diverted by femtocells, releasing in largely, the macrocell&#39;s load</strong>. However, this type of implementation provides an increasement in the handover because a UE who moves to an area where there are several deployed femtocells, it will perform handovers on each femtocell with better signal quality, thereby increasing signaling traffic. From this perspective,<strong> the hybrid method may have advantages, but the shared resources by each femtocell must be managed carefully</strong> in order to not degrade the quality of service for the users into the femtocell.</span></p>
<p>
&nbsp;</p>
<h1>
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;">References</span></span></h1>
<ol>
<li>
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;">D. Calin, H. Claussen, H. Uzunalioglu. On Femto Deployment Architectures and Macrocell Offloading Benefits in Joint Macro-Femto Deployments. Communications Magazine, IEEE, vol. 48, no. 1, pp. 26-32, 2010.</span></span></li>
<li>
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;">Assen, Golaup;Mona, Mustapha;Leo, Boonchin Patanapogpibul, Femtocell Access Control Strategy in UMTS and LTE, 2009.</span></span></li>
<li>
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;">G, de la Roche;A, Valcarce;D, Lopez-Perez;Jie, Zhang, Access control Mechanisms for Femtocells, 2010.</span></span></li>
<li>
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;"><a href="http://www.femtoforum.org/">http://www.femtoforum.org</a></span></span></li>
<li>
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;">http://www.3gpp.org/</span></span></li>
</ol>