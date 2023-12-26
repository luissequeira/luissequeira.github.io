---
layout: post
title:  Arquitectura general para Software Defined Networking (SDN)
date:   2020-08-31 09:00:00
description: La terminología y arquitectura de capas para los sistemas SDN ha sido definida por el Software-Defined Networking Research Group (SDNRG) del Internet Research Task Force (IRTF) en [1]. Aunque no tiene como objetivo estandarizar ninguna capa o interfaz, proporciona una referencia de los enfoques que se pueden seguir al definir arquitecturas SDN.
tags: SDN arquitectura cloud
categories: Cloud Networks
thumbnail: assets/img/Cloud/general-architecture-for-sdn/sdn.png
---

<div class="row mt-3" style="text-align: center">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="assets/img/Cloud/general-architecture-for-sdn/sdn.png" class="img-fluid rounded z-depth-1" %}
    </div>
</div>

La terminología y arquitectura de capas para los sistemas **SDN** ha sido definida por el **Software-Defined Networking Research Group (SDNRG)** del **Internet Research Task Force (IRTF)** en [1]. Aunque no tiene como objetivo estandarizar ninguna capa o interfaz, proporciona una referencia de los enfoques que se pueden seguir al definir arquitecturas **SDN**. La **Open Networking Foundation (ONF)** propuso una arquitectura diferente en [2], que está más orientada a servicios, mientras que la propuesta por el IRTF tiene una visión más funcional [3].

La Figura #1 describe la arquitectura propuesta por el IRTF que consta de:

- **Application Plane**: en ésta capa es donde residen las aplicaciones que definen el comportamiento de la red.
- **Network Services Abstraction Layer (NSAL)**: proporciona acceso a las aplicaciones hacia el plano de control y gestión.
- **Control Plane**: es responsable de las decisiones sobre cómo los paquetes deben ser reenviados por uno o más dispositivos de red y enviar dichas decisiones a los dispositivos de red para su ejecución.
- **Management Plane**: esta capa está a cargo de monitorear, configurar y mantener los dispositivos de red, por ejemplo, generar decisiones con base en el estado de un dispositivo de red.
- **Device and resource Abstraction Layer (DAL)**: abstrae los recursos de los planos operativos y de reenvío del dispositivo a los planos de control y gestión.

<div class="row mt-3" style="text-align: center">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="assets/img/Cloud/general-architecture-for-sdn/rfc_architecture.png" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Figura #1: Arquitectura de capas **SDN** según RFC 7426.
</div>

Siguiendo un enfoque **SDN**, se pueden encontrar algunos ejemplos de propuestas de arquitecturas en la literatura: en [4], se presentó la arquitectura EmPOWER que integra diferentes Radio Access Technologies (RAT) y propone un conjunto de abstracciones de programación para modelar algunos aspectos importantes de redes inalámbricas. Esta arquitectura también se utilizó en [5], donde se propuso un algoritmo para la gestión de la movilidad, el objetivo del algoritmo es la adaptación de la velocidad para las comunicaciones de multidifusión en redes 802.11. Otra arquitectura se presentó en [6], la cual está destinada a minimizar el retardo a nivel de paquetes; en este caso, todas las estaciones base (BS) están configuradas para usar la misma dirección MAC; se crean BS virtuales específicas para gestionar cada servicio. Todas estas propuestas incluyen un controlador central a cargo de la gestión de la red.

## Referencias

- E.Haleplidis, K. Pentikousis, S. Denazis, J.H. Salim, D. Meyer, O. Koufopavlou, (2015). Software-defined networking (SDN): Layers and architecture terminology (No. RFC 7426).
- Open Networking Foundation, “SDN architecture,” vol. 1.0, Jun 2014. [https://www.opennetworking.org/ images/stories/downloads/sdn-resources/technical-reports/TRSDN ARCH_1.0_06062014.pdf](https://www.opennetworking.org/images/stories/downloads/sdn-resources/technical-reports/TRSDN ARCH_1.0_06062014.pdf)
- J. Schultz, R. Szczepanski, K. Haensge, M. Maruschke, N. Bayer and H. Einsiedler, “OpenGUFI: An Extensible Graphical User Flow Interface for an SDN-Enabled Wireless Testbed,” 2015 IEEE International Conference on Computer and Information Technology; Ubiquitous Computing and Communications; Dependable, Autonomic and Secure Computing; Pervasive Intelligence and Computing, Liverpool, 2015, pp. 770-776.
- R. Riggio, M. K. Marina, J. Schulz-Zander, S. Kuklinski, and T. Rasheed, “Programming abstractions for software-defined wireless networks,” IEEE Transactions on Network and Service Management, vol. 12, no. 2, pp. 146–162, 2015.
- E. Coronado, R. Riggio, J. Villalón and A. Garrido, “Joint Mobility Management and Multicast Rate Adaptation in Software–Defined Enterprise WLANs,” in IEEE Transactions on Network and Service Management. In press. doi: 10.1109/TNSM.2018.2798296
- K. Nakauchi and Y. Shoji, “WiFi Network Virtualization to Control the Connectivity of a Target Service,” IEEE Transactions on Network and Service Management, vol. 12, no. 2, pp. 308–319, 2015.
