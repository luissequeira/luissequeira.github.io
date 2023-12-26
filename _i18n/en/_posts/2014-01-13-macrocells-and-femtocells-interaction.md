---
layout: post
title:  Macrocells and femtocells Interaction
date:   2014-01-13 06:00:00
description: Macro-cells are not very efficient in the residential area due to penetration problems that have been mentioned in a previous article, also in the macro-cells there are many users and is more difficult to provide QoS to all of them. For these reasons Internet Service Providers (ISP) have opted for femto-cell implementation at residential level, in order to increase the quality of services provided.
tags: LTE 4G femtocell macrocell wireless broadband QoS
categories: Networks Innovation
thumbnail: assets/img/TICs/interaccion-de-macroceldas-y-femtoceldas/macro_femto_1.jpg
---
Macro-cells are not very efficient [1] in the residential area due to penetration problems that have been mentioned in a previous post, also in the macro-cells there are many users and is more difficult to provide QoS to all of them. For these reasons Internet Service Providers (ISP) have opted for femto-cell implementation at residential level, in order to increase the quality of services provided.

**Femto-cells are low-power base stations that provide low cost** and high quality wireless services to residential, in this area offer a coverage of approximately $$10m$$ [2], which are designed to integrate automatically with macro-cell networks. Femto-cells integrate with mobile operator through a broadband connection, typically DSL [2] and [3], as can be seen in Figure #1. However, it can also be performed by a wireless link as mentioned in [4]. In General, the femto-cell redirects the traffic from the home cellular system, through the broadband connection, releasing the resource consumption of the macro-cell.

<div class="row mt-3" style="text-align: center">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="assets/img/TICs/interaccion-de-macroceldas-y-femtoceldas/macro_femto_1.jpg" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Figure #1: Typical Femto-cell [3].
</div>

Femtocells have a number of advantages for both mobile service providers and users, these last **may receive better signal level**, since the distance between the femto-cell and the EU is reduced, it causes the **SINR is higher increasing capacity and encouraging higher levels of QoS**. In turn, the spectral efficiency is increased due to the number of users per hertz per unit area, in addition, the low levels of transmission power generates a lower power consumption because the mobile does not require too much power for transmission. Furthermore, when implemented in residential scenarios, the number of users is small and may share resources [4].

Figure #2 shows two scenarios: in a), a **traditional macrocell** where eNodeB provides coverage to a particular area, if the case of two UEs that are at the same distance from the eNodeB, is analyzed, in which the difference between both is that one of them is outdoors (UE1) and the other in a house room (EU4), the EU4 will have more **losses due to penetration in house**. On the other hand, in b) the implementation of two femto-cells is proposed, one in each house, **to increase the quality of the signal within the property, and therefore the throughput and quality of service provided**.

<div class="row mt-3" style="text-align: center">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="assets/img/TICs/interaccion-de-macroceldas-y-femtoceldas/propagacion_2.jpg" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Figure #1: a) Traditional macro-cell; b) Interaction of macro-cell with femto-cells [2].
</div>

## References

1. G. de la Roche, A. Valcarce, D. Lopez-Perez, Jie Zhang. Access control Mechanisms for Femtocells. Communications Magazine, IEEE, vol. 48, no. 1, pp. 33-39, 2010.
2. D. Calin, H. Claussen, H. Uzunalioglu. On Femto Deployment Architectures and Macrocell Offloading Benefits in Joint Macro-Femto Deployments. Communications Magazine, IEEE, vol. 48, no. 1, pp. 26-32, 2010.
3. [http://www.femtoforum.org/](http://www.femtoforum.org)
4. Vikram Chandrasekhar, Jeffrey G. Andrews, Alan Gatherer. Femtocell Networks: A Survey. Communications Magazine, IEEE, vol. 46, no. 9, pp. 59-67, 2008.
