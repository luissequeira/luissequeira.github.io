---
layout: post
title:  General architecture for Software Defined Networking (SDN)
date:   2020-08-24 09:00:00
description: The terminology and layered architecture for SDN systems has been defined by the Software Defined Networking Research Group (SDNRG) of the Internet Research Task Force (IRTF) in [1]. Although it is not intended to standardize any layer or interface, it provides a reference for approaches that can be followed when defining SDN architectures.
tags: SDN architecture cloud
categories: Cloud Networks
thumbnail: assets/img/Cloud/general-architecture-for-sdn/sdn.png
---

<div class="row mt-3" style="text-align: center">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="assets/img/Cloud/general-architecture-for-sdn/sdn.png" class="img-fluid rounded z-depth-1" %}
    </div>
</div>

The terminology and layered architecture for **SDN** systems has been defined by the **Software Defined Networking Research Group (SDNRG)** of the **Internet Research Task Force (IRTF)** in [1]. Although it is not intended to standardize any layer or interface, it provides a reference for approaches that can be followed when defining **SDN** architectures. The **Open Networking Foundation (ONF)** proposed a different architecture in [2], more service-oriented, while the one proposed by the IRTF has a more functional vision [3].

Figure #1 describes the proposed IRTF architecture which consisting of:

- **Application Plane**: this layer is where the applications that define the behavior of the network reside.
- **Network Services Abstraction Layer (NSAL)**: provides access to applications to the control and management plane.
- **Control Plane**: is responsible for decisions on how packets should be forwarded by one or more network devices and for forwarding those decisions to the network devices for execution.
- **Management Plane**: this layer is in charge of monitoring, configuring and maintaining network devices, e.g., generating decisions based on the state of a network device.
- **Device and resource Abstraction Layer (DAL)**: abstracts resources from the operational and device forwarding planes to the control and management planes.

<div class="row mt-3" style="text-align: center">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="assets/img/Cloud/general-architecture-for-sdn/rfc_architecture.png" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Figure #1: **SDN** layer architecture according to RFC 7426.
</div>

Following a **SDN** approach, some examples of proposed architectures can be found in the literature: in [4], the EmPOWER architecture was presented which integrates different Radio Access Technologies (RAT) and proposes a set of programming abstractions in order to model some important aspects of wireless networks. This architecture was also used in [5], where an algorithm for mobility management was proposed; the objective of the algorithm is the adaptation rate for multicast communications in 802.11 networks. Another architecture was presented in [6], which is aimed at minimizing packet-level delay; in this case, all base stations (BSs) are configured to use the same MAC address; specific virtual BSs are created to manage each service. All these proposals include a central controller in charge of network management.

## References

- E.Haleplidis, K. Pentikousis, S. Denazis, J.H. Salim, D. Meyer, O. Koufopavlou, (2015). Software-defined networking (SDN): Layers and architecture terminology (No. RFC 7426).
- Open Networking Foundation, “SDN architecture,” vol. 1.0, Jun 2014. [https://www.opennetworking.org/ images/stories/downloads/sdn-resources/technical-reports/TRSDN ARCH_1.0_06062014.pdf](https://www.opennetworking.org/images/stories/downloads/sdn-resources/technical-reports/TRSDN ARCH_1.0_06062014.pdf)
- J. Schultz, R. Szczepanski, K. Haensge, M. Maruschke, N. Bayer and H. Einsiedler, “OpenGUFI: An Extensible Graphical User Flow Interface for an SDN-Enabled Wireless Testbed,” 2015 IEEE International Conference on Computer and Information Technology; Ubiquitous Computing and Communications; Dependable, Autonomic and Secure Computing; Pervasive Intelligence and Computing, Liverpool, 2015, pp. 770-776.
- R. Riggio, M. K. Marina, J. Schulz-Zander, S. Kuklinski, and T. Rasheed, “Programming abstractions for software-defined wireless networks,” IEEE Transactions on Network and Service Management, vol. 12, no. 2, pp. 146–162, 2015.
- E. Coronado, R. Riggio, J. Villalón and A. Garrido, “Joint Mobility Management and Multicast Rate Adaptation in Software–Defined Enterprise WLANs,” in IEEE Transactions on Network and Service Management. In press. doi: 10.1109/TNSM.2018.2798296
- K. Nakauchi and Y. Shoji, “WiFi Network Virtualization to Control the Connectivity of a Target Service,” IEEE Transactions on Network and Service Management, vol. 12, no. 2, pp. 308–319, 2015.
