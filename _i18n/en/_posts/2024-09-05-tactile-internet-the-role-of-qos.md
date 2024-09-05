---
layout: post
title:  "Tactile Internet: The role of QoS in teleoperation systems"
date:   2024-09-05 20:30:00
description: Touch is increasingly being recognized as a modality that will complement hearing and vision as a third media stream over the Internet in various future haptic applications, enabling full immersion and significantly impacting society in many ways. 
tags: QoS tactile-internet teleoperation haptic urllc
categories: Innovation Networks
thumbnail: assets/img/Research/tactile-internet-the-role-of-qos/fig1.jpg
---
<div class="row mt-3" style="text-align: center">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="assets/img/Research/tactile-internet-the-role-of-qos/fig1.jpg" class="img-fluid rounded z-depth-1" %}
    </div>
</div>

**Touch** is increasingly being recognized as a modality that will complement hearing and vision as a third media stream over the Internet in various future haptic applications, enabling full immersion and significantly impacting society in many ways. However, the high technical requirements of these applications demand networks that support Ultra-Reliable and Low-Latency Communication (URLLC) to meet the challenging task of delivering the necessary Quality of Service (QoS) and maintaining an optimal Quality of Experience (QoE) for users.

## Tactile Internet

In **teleoperation systems for haptic telemanipulation**, also known as telehaptic systems, a human operator typically uses a haptic interface (master device) on one end of the communication channel to control a teleoperator device (slave actuator) on the other end. Teleoperation applications can be short-range, where the communication channel is either wired or wireless without requiring network infrastructure, or long-range, leveraging packet-switched network infrastructures to transmit data. The communication channel for long-range teleoperation can span from local area networks (LANs) to the broader Internet.

The primary goal of teleoperation systems is to provide users with a sense of presence in the remote environment where the teleoperator is located. This is made possible by continuous advancements in relevant hardware and software, enabling users to receive multimodal feedback (visual, auditory, and haptic). Achieving this goal requires meeting appropriate QoS standards to maximize the user’s QoE.

## Quality of Service Requirements

Internet-based Telepresence and Teleaction (TPTA) systems implement closed-loop control mechanisms over a real-time communication framework, facilitating interaction between a human operator and a remote environment through sensors and actuators. Such systems are referred to as Network-Based Control Systems (NBCS).

Since communication channels are a core component of these systems, various network protocols have been developed or adapted for teleoperation frameworks and their Internet-based implementations, ensuring efficient functionality in both virtual environments and physical systems.

As with any networked system, the proper functioning of NBCS is susceptible to several challenges that can degrade performance. These challenges also serve as performance metrics, enabling the comparison of different protocols and the quantification of the QoS they deliver, which is critical in applications like telesurgery. Teleoperation systems, as a subset of NBCS, naturally inherit these performance considerations concerning TPTA systems. Common performance parameters include:

- **Network delay**: the average time required for a packet to travel from the input to the output of the communication channel. A comprehensive survey of the main sources of network delay and current solutions is provided in [2].
- **Jitter**: the variation in packet delay, formally known as Packet Delay Variation (PDV), which affects packet sequencing. Jitter can be mitigated by using packets with sequence numbers or timestamps, although this typically requires buffers, which in turn increase overall communication delay.
- **Packet loss**: occurs due to network congestion, resulting in the master and slave sides of a TPTA system needing to operate despite missing information. Approaches to handle packet loss include substituting missing values with nulls, holding the last received value, or using interpolation (e.g., predictive methods).
- **Data rate**: the communication channel’s capacity, which can be influenced by the sampling frequency, sample resolution, and protocol overhead.

Additionally, other factors such as signal quantization and sources of noise can also impact system performance.

The effects of packet loss, with or without latency, on the perception of visual and haptic events have been studied in [3], demonstrating an additive effect of both factors. However, as noted in [4], packet loss can be managed by mechanisms that enhance communication reliability, though these mechanisms inevitably increase total latency. Thus, achieving a balance between reliability and delay is essential.

## References

1. S.G. Tzafestas.Web-Based Control and Robotics Education.  IntelligentSystems,  Control  and  Automation:  Science  and  Engineering.  Springer Netherlands, 2009.  ISBN 9789048125050.
2.  B. Briscoe, A. Brunstrom, A. Petlund, D. Hayes, D. Ros, I. J. Tsang,S. Gjessing, G. Fairhurst, C. Griwodz, and M. Welzl.  Reducing internetlatency: A survey of techniques and their merits. IEEE Communications Surveys Tutorials, 18(3):2149–2196, thirdquarter 2016. ISSN 1553-877X.
3. Z. Shi, H. Zou, M. Rank, L. Chen, S. Hirche, and H. J. Muller. Effects ofpacket loss and latency on the temporal discrimination of visual-hapticevents. IEEE Transactions on Haptics, 3(1):28–36, Jan 2010. ISSN 1939-1412. 
4. Changhoon   Seo,   Jong-Phil   Kim,   Jaeha   Kim,   Hyo-Sung   Ahn,   andJeha   Ryu.Robustly   stable   bilateral   teleoperation   under   time-varying   delays   and   data   losses:   an   energy-bounding   approach.Journal   of   Mechanical   Science   and   Technology,   25(8):2089,   Sep2011.ISSN   1976-3824.