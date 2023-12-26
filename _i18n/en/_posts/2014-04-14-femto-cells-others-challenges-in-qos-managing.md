---
layout: post
title:  Femto-cells others challenges in QoS managing
date:   2014-04-14 05:00:00
description: The transmission of a information packet over an IP network is susceptible to delays, so the femto-cell may experience problems for obtaining an immune base time to jitter. Operators should ensure the concept of QoS in Femto-cells, the parameters of these scenarios should be comparable to those offered by the macro-cells.
tags: femtocell 4G LTE QoS
categories: Networks Innovation
thumbnail: assets/img/TICs/femtocelda-otros-desafios-gestionando-qos/1.jpg
---

<div class="row mt-3" style="text-align: center">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="assets/img/TICs/femtocelda-otros-desafios-gestionando-qos/1.jpg" class="img-fluid rounded z-depth-1" %}
    </div>
</div>

## QoS managing

An important point with regard to providing QoS is to **reduce signaling and interference**. With this, operators can properly manage resources without such problems, in order to improve the services provided to users.

In this new scenario, the traffic generated from the UE to the eNodeB is deflected by an IP network before reaching the mobile network. **The transmission of a information packet over an IP network is susceptible to delays, so the femto-cell may experience problems for obtaining an immune base time to jitter**. **Operators should ensure the concept of QoS in femto-cells**, the parameters of these scenarios should be comparable to those offered by the macro-cells.

Another aspect that stand in implementing femtocell, is **how to ensure certain parameters of QoS which are necessary for delay-sensitive traffic**. Not forgetting, that the provided solutions must give sufficient capacity in order to not cause a bottleneck at critical network points, since the broadband used by femto-cell is shared with other services of the user. Moreover, the problems found by Telefónica (mentioned above) can cause a degradation in the quality of service provided to users in environments where there are Wi-Fi networks nearby, in this aspect operators must be careful to provide this type of solutions, since it is usual that subscribers implement wireless networks at home for internet access.

## Synchronization, timing and others aspects

Femto-cells need synchronization to align the received signals and to minimize interference, further, for ensure an acceptable carrier. On the other hand, **the macro-cells and femto-cells must be properly synchronized to perform handoff because without a centralized coordinating**, this work is more difficult. Moreover, without a proper timing, the cells transmissions may overlapping, since the lack of a reference between the femtocell, generates variations in the instants of transmission and reception, so the uplink of one cell may overlap with the downlink of the other and vice versa.

Mobility is one of the aspects that must be managed carefully, since the **user should not perceive the complexity of the access infrastructure and the necessary procedures to perform the mobility and let alone have any intervention**. However, the increasing deployment of femto-cells, and in particular, the access techniques and mobility management can cause an increase in signaling for a handoff.

Another aspect that is not clear so far is related to the portability issues. The case of WiFi networks is clearer, as they operate in unlicensed frequency band and therefore users can easily move it, but the case of femto-cells do not appear to be as simple. On the one hand, they operate in licensed frequency bands, so they make use of a frequency space that has been allocated to a specific operator. On the other hand, if a user has contracted a service with an operator and transfers the femto-cell to a certain location where the operator does not have coverage, and the coverage in that area is provided by a second operator of telecommunications services, **this scenario tends to have an aspect not yet defined with certainty**.

## References

1. Assen G, Mona M Leo BP. Femtocell Access Control Strategy in UMTS and LTE. IEEE Comunication Magazine (2009) 47: pp. 117-123.
2. G DLR, A V, D L Jie Z. Access control Mechanisms for Femtocells. IEEE Communications Magazine (2010) 48: pp. 33-39.
