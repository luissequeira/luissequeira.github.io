---
layout: post
title:  What is a Light Virtual Access Point (LVAP)?
date:   2020-09-07 18:16:08
description: Wireless networks are widely used in areas such as business centres, airports, university campuses or even in many city areas. Light Virtual Access Point (LVAP) are a solution for coordinating Wi-Fi access points. 
tags: SDN access-point architecture
categories: Cloud Innovation
thumbnail: assets/img/Cloud/what-is-lvaps/sticky-client.png
---

<div class="row mt-3" style="text-align: center">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="assets/img/Cloud/what-is-lvaps/sticky-client.png" class="img-fluid rounded z-depth-1" %}
    </div>
</div>

Wireless networks are widely used in areas such as business centres, airports, university campuses or even in many city areas. For this scenarios there are solutions for **coordinating Wi-Fi access points**, usually known as Enterprise Wi-Fi. Although commercial solutions exist, these are proprietary, closed and costly, which in most of the cases make them infeasible for many organizations.

In this context, there are some proposals for inter access points **coordination solutions enabling advanced features** such as load balancing, frequency planning or power control. Some works have proposed the adaptation of certain abstractions and concepts from **Software Defined Networks (SDNs)**, for its use in wireless networks [1, 2].

One of the problems that arise when coordinating a wireless network is that the stations (STAs) have their own algorithms for selecting the access point. This means that each STA is free to select the access point to associate to, not coordinated with the rest of the clients. This complicates client management, generating the “sticky client”, that never leaves the access point to which it was associated initially. 

One way to solve these problems is using **Light Virtual Access Point (LVAP)** abstraction [3]. The idea is that a physical access point will use a different **LVAP** (which includes a specific MAC) for communicating with each STA. Therefore, the STA will only “see” a single access point, even if it is actually moving between a set of them, thus avoiding the need for re-association. 

The **LVAP** is dynamically assigned to a physical access point near the current location of the terminal. As long as the STA only “sees” a single access point, it will not make any roaming decision, thus enabling the network to run a coordinated management of clients. This is achieved without any modification in the STA which runs standard IEEE 802.11.

There are some initiatives in this area, in [4] a distributed solution using **LVAPs** was introduced, proposing a protocol for the direct exchange of information between access points. The main limitation is the absence of a central controller, so each access point has to build a list of neighbour access points by itself. In [5], a solution based on **LVAPs**, managed by a central controller, combines two southbound protocols: OpenFlow and Odin. OpenFlow tells the internal switches of the access points where to steer the traffic and the Odin protocol is in charge of the wireless issues. The central manager of the Wi-Fi network runs within the **SDN** controller. The controller is in charge of creating an **LVAP** for each terminal which consists of a tuple with four fields: the real MAC of the STA, a fake MAC for the Access Points to communicate with the STA, the IP of the STA and the SSID to be used in the communication.

Fast and seamless handover are essential part of all these solutions because the STAs can be redistributed dynamically. Therefore, in order not to interrupt the user's session, a seamless access point re-assign can be very convenient when a user is walking, or whenever a load balancing decision is made. 

## References

1. R. Riggio, T. Rasheed, and M. K. Marina, “Poster: programming software-defined wireless networks.” in MobiCom, S.-J. Lee, A. Sabharwal, and P. Sinha, Eds. ACM, p. 413416.
2. R. Riggio, T. M. Rasheed, and R. Narayanan, “Virtual network functions orchestration in enterprise WLANs.” in IM, R. Badonnel, J. Xiao, S. Ata, F. D. Turck, V. Groza, and C. R. P. dos Santos, Eds. IEEE, p. 12201225.
3. Y. Grunenberger and F. Rousseau, “Virtual Access Points for Transparent Mobility in Wireless LANs.” in WCNC. IEEE, p. 16.
4. M. E. Berezin, F. Rousseau, and A. Duda, “Multichannel Virtual Access Points for Seamless Handoffs in IEEE 802.11 Wireless Networks.” in VTC Spring. IEEE, p. 15.
5. J. Schulz-Zander, L. Suresh, N. Sarrar, A. Feldmann, T. Hhn, and R. Merz, “Programmatic Orchestration of WiFi Networks,” in 2014 USENIX Annual Technical Conference (USENIX ATC 14). Philadelphia, PA: USENIX Association, Jun., p. 347358.
