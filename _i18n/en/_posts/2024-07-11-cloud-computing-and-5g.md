---
layout: post
title:  Cloud Computing meets 5G
date:   2024-07-11 20:00:00
description: Nowadays, many 5G components can be virtualized and they can run in cloud environments. In the 5G radio access and core networks, hardware and software are becoming clearly separated from each other [1]. It means that 5G features are virtualized in software and delivered over commodity hardware where it runs as virtual machines or containers in private or public cloud environments. 
tags: cloud 5G
categories: Cloud
thumbnail: assets/img/Cloud/cloud-computing-5g/fig1.png
---

Nowadays, many 5G components can be virtualized and they can run in cloud environments. In the 5G radio access and core networks, hardware and software are becoming clearly separated from each other [1]. It means that 5G features are virtualized in software and delivered over commodity hardware where it runs as virtual machines or containers in private or public cloud environments. Such a decoupling is important as it enables companies and researches to innovate independently and in their respective space. In the past, this has been proven as a very successful approach in the computing industry, where hardware (computer), middleware (operating system) and software (applications) are developed independently and driven by their own design and development goals.

The clear separation of software functionalities allows to potentially replace certain features much quicker with more advanced embodiments. Therefore, incremental improvements of the technology can now occur more easily and without having to change physical devices or firmware. In this way, software components can be much easier virtualized, then arranged and deployed as per need across different physical locations, datacentres and even across different cloud providers. Advanced functionalities or new features can thus be moved or migrated flexibly, resources instantiated in a moment and services delivered at scale [2]. 

A deployed end-to-end 5G system consists of multiple 5G-enabled components as well as the integration of a - let's say - legacy system architectures. Network functions can be fully virtualized and run in virtual machines and some of them as containers in different cloud infrastructures, which are all managed and orchestrated using a common orchestration framework. 

A 5G system requires interaction with legacy commercial 4G networks using cloud based solutions for mobile architectures, including Cloud Radio Access Network (RAN) and Core Network functional splits. A 5G-enabled testbed system could look like as the system shown in Figure #1. 

<div class="row mt-3" style="text-align: center">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="assets/img/Cloud/cloud-computing-5g/fig1.png" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Figure #1: High level testbed example including access technologies, access networks, core network and orchestration.
</div>

As any other radio-based technology, a 5G systems consist of a set of outdoor sites transmitting at different bands, such as $$3.5GHz$$ and $$28GHz$$ in this case, allowing for increased throughputs and lower latencies in the access network. The virtualized RAN and Core Network functions can now run in separate cloud environments, even across different cloud providers, which need to be interfaced with a management and orchestration framework. 

The 5G core network can be virtualized and can support end-to-end network slicing, which can be used for instance to allow multiple instantiations of Virtualized Network Functions (VNF) to satisfy different levels of Qulity of Service (QoS), it can also be used for service isolation which opens the flexibility to provide bespoken networks for customers or for particular use cases instead of the traditional "one-size-fits-all" approach. Network slicing also makes it easier to decommission or update an entire slice or service when required. 

## References

1. B. Han, V. Gopalakrishnan, L. Ji and S. Lee, “Network function virtualization: Challenges and opportunities for innovations”, in IEEE Communications Magazine, vol. 53, no. 2, pp. 90-97, Feb. 2015.
2. X. Sun and N. Ansari, "EdgeIoT: Mobile Edge Computing for the Internet of Things," in IEEE Communications Magazine, vol. 54, no. 12, pp. 22-29, December 2016.