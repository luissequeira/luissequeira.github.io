---
layout: post
title:  Femtocell's access methods
date:   2014-05-05 05:00:00
description: Femtocells basically have three different operating modes open access, closed access and a combination of both named hybrid access.
tags: femtocell 4G LTE QoS
categories: Networks Innovation
thumbnail: assets/img/TICs/metodos-acceso-femtoceldas/1.png
---
**Femtocells are low-power and low-cost base stations** that provide residential cellular services, providing a coverage of roughly $$10 m$$ [1]. They can integrate with mobile operator through a **broadband connection**, typically ADSL. In General, femtocell makes that the traffic from the home cellular system, **deviates through the broadband connection**, releasing the resource consumption of the macrocell.

The 3GPP has introduced the concept of Closed Subscriber Group (CSG), which essentially identifies a group of subscribers who have **access permission to one or more cells**. Femtocells basically have three different operating modes: **open access, closed access and a combination of both named hybrid access** [2] and [3], the access methods are:

- **Open access**: In this case, the UE can access the femtocell without any restrictions, this is seen in the Figure #1 wherein the EU2 has unrestricted access to the femtocell in the building.
- **Closed Access**: The administrator defines the only femtocell users (CSG) that can access the network. For this mode, emergency calls are exempt.
- **Hybrid Access**: In this type of access, a limited amount of resources is allocated for access to users who are not part of CSG.

<div class="row mt-3" style="text-align: center">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="assets/img/TICs/metodos-acceso-femtoceldas/1.png" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Figure #1: Example of different femto-cell's access methods [2]: open access, closed access and hybrid access.
</div>

Figure #1 is an example of the various types of femtocell access which are defined by the 3GPP. **The closed access provides the contracted services to users who are part of the CSG**, providing some level of security and privacy when accessing the femtocell, further that all resources are available for femtocell users, **guaranteeing certain level of QoS**. However, the users who are not part of subscriber's group can not access the network, except for emergency calls. This type of access generates more interference, since nearby mobiles try to connect to the femtocell, but they will be blocked due the access method, so a large number of implicit signaling is generated in that area.

On the other hand, **open access has a good advantage for the service provider because part of the traffic is diverted by femtocells, releasing in largely, the macrocell's load**. However, this type of implementation provides an increasement in the handover because a UE who moves to an area where there are several deployed femtocells, it will perform handovers on each femtocell with better signal quality, thereby increasing signaling traffic. From this perspective, **the hybrid method may have advantages, but the shared resources by each femtocell must be managed carefully** in order to not degrade the quality of service for the users into the femtocell.

## References

1. D. Calin, H. Claussen, H. Uzunalioglu. On Femto Deployment Architectures and Macrocell Offloading Benefits in Joint Macro-Femto Deployments. Communications Magazine, IEEE, vol. 48, no. 1, pp. 26-32, 2010.
2. Assen, Golaup;Mona, Mustapha;Leo, Boonchin Patanapogpibul, Femtocell Access Control Strategy in UMTS and LTE, 2009.
3. G, de la Roche;A, Valcarce;D, Lopez-Perez;Jie, Zhang, Access control Mechanisms for Femtocells, 2010.
4. [http://www.femtoforum.org/](http://www.femtoforum.org)
5. [http://www.3gpp.org/](http://www.3gpp.org/)
