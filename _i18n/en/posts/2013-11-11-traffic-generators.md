---
layout: post
title:  Traffic Generators
date:   2013-11-11 00:00:00
description: The traffic generators are useful for injecting traffic of certain applications or network services and not have the need to run such applications, in my case I used to generate the traffic of VoIP, video streaming, video surveillance, and even to make some reverse engineering on certain commercial devices.
tags: tráfico generadores-de-tráfico jtg ditg etg
categories: Tools
thumbnail: assets/img/Research/generadores-de-trafico/topology.jpg
---

<div class="row mt-3">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="assets/img/Research/generadores-de-trafico/topology.jpg" class="img-fluid rounded z-depth-1" %}
    </div>
</div>

For some time I have been using various traffic generators, and today I want to share 3 of the that I most use for their interesting features. The traffic generators are useful for injecting traffic of certain applications or network services and not have the need to run such applications, in my case I used to generate the traffic of VoIP, video streaming, video surveillance, and even to make some reverse engineering on certain commercial devices. Then I leave a short review of each of them:</

## JTG

The JTG ("Jugi's Traffic Generator") is an IP traffic generator managed by command line, developed by the University of Helsinki [1], it can generate parametric traffic and also traffic from a file with inter-packet time and packet sizes sending in each time interval. Furthermore, it provides a receiver to collect the traffic from which statistics can be calculated. The JTG includes a program called `jtg_calc` which performs a statistical analysis of loss, delay and jitter from a log of received packets. In the case of IPv6 there is a version called JTG6.

## ITG

Other multiprotocol IP traffic generator (IPv4 and IPv6), developed by the University of Naples, is the D-ITG [2]. This generator also allows the analysis of the sent or received data, so the [capturing in the communication can be taken in both ends]("http://www.telecomsharing.com/en/laboratory/tools/item/40-the-2-best-tools-for-the-capture-and-the-interpretation-of-network-data"). It also permits measurement of OWD (one-way-delay) and RTT (round-trip-time), it supports protocols such as TCP ("Transmission Control Protocol"), UDP ("User Datagram Protocol"), SCTP ("Stream Control Transmission Protocol") and DCCP ("Datagram Congestion Control Protocol"). It can be managed using command line or GUI ("Graphical User Interface") which can be obtained in the same project website.

## ETG

Recently, the GTC (Communications Technology Group), University of Zaragoza [3] has developed a tool called ETG ("E2E Trafic Generator") [4], originally implemented for link analysis of VoIP transport and currently it has been generalized to generate different types of IP flows.

This tool allows to calculate objective quality parameters such as delay, jitter, and loss rate, and other subjective parameters of QoS: R factor and MOS. It is a tool able to perform E2E communications between users by sending and receiving multiple streams of UDP traffic bursts. ETG allows the traffic generation of one-way and round-trip, and captures at both ends of communication, furthermore we can analyze the received traffic and obtain parameters as delay, loss and jitter, with which we can calculate the R factor that determines the MOS for each communication.

An advantage of this application:

- The easiness to the repeatability of the tests in that it provides mechanisms that allow automation of certain functions facilitating work to researchers, for example, each stream may renew from time to time between a date and start and end time.
- It generates traffic equivalent to different services.
- It allows sending packets from a file with the packet transmission intervals and size.<
- In addition, it emulates communications when times and packet sizes are not constant and guarantees to repeat the tests under the same conditions.

## References

- [http://www.cs.helsinki.fi/u/jmanner/software/](http://www.cs.helsinki.fi/u/jmanner/software/)
- [http://traffic.comics.unina.it/software/ITG/](http://traffic.comics.unina.it/software/ITG/)
- [http://www.gtc.cps.unizar.es/](http://www.gtc.cps.unizar.es/)
- L. A. Casadesus Pazos, J. Fernández Navajas, J. Ruiz Mas, J. M. Saldana Medina, J. I. Aznar Baranda, E. Viruete Navarro. Herramienta para Automatización de Medidas de Tiempo Real Extremo a Extremo. Actas del XXVI Simposium Nacional de la Unión Científica Internacional de Radio (URSI 2011). Leganés (España). ISBN 9788493393458. Sept. 2011.