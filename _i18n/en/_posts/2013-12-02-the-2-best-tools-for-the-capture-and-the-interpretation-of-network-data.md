---
layout: post
title:  The 2 best tools for the capture and the interpretation of network data
date:   2013-12-02 06:00:00
description: The applications to capture packets on the network, e.g. tcpdump and wireshark are well known for their features, in addition to data capture, these applications are useful for certain packets analysis with the obtained data.
tags: wireshark tcpdump traffic
categories: Networks
thumbnail: assets/img/Research/las-dos-mejores-herramientas-para-la-captura-de-trafico/2.jpg
---
I present you **my favorite applications to capture** packets on the network, although they are well known for their features, I decided to give a little space to discuss some of their features. In addition to data capture, these applications are useful for certain packets **analysis** with the obtained data, on the other hand, when the analysis that we need to do is a bit complex or very specific, it is always advisable to build our own scripts, but there is no doubt that no matter for what we use them, this applications will **help us to obtain useful network information**. This applicacions can also be combined with [traffic generators]({% post_url 2013-11-11-traffic-generators %}) in order to analyze some network issues.


## TCPDUM

**TCPDUMP** [1] is a tool for capturing **traffic flowing through the network in real time**, this includes packets **transmitted and received** on a specific network interface. This tool has no graphical interface, this makes for one of the favorite applications when you want to use **minimum resources as possible**, also be suitable for **unattended** packet capture, because it can be managed by **command line** as it can be seen in Figure #1.

<div class="row mt-3" style="text-align: center">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="assets/img/Research/las-dos-mejores-herramientas-para-la-captura-de-trafico/1.jpg" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Figure #1: View of the contents of various packets for command line using **TCPDUMP**.
</div>

This application is available for almost all operating systems (in Windows is called WinDump). It uses the `libpcap` library in the cases of UNIX systems and `winpcap` for Windows, which is responsible for packet captures. This tool allows debugging of the output obtained by means of filters, **allowing capture specific port filtering**, or filtering by protocol type, source or destination address, on a **specific interface** and others.

The installation of `tcpdump` in Linux operating systems is usually not necessary, since it comes installed by default on most distributions, but if required, simply install using the package manager of your distribution, I am sure it is on the repositories, but if you want to compile it yourself you can download it [here](http://www.tcpdump.org/#latest-release). For Windows systems you can download it [here](http://www.winpcap.org/windump/install/default.htm).

## Wireshark

Wireshark [2] is an **packet analysis program** held under GNU GPL (GNU General Public License), also uses the same packet capture libraries those used in TCPDUMP, depending on the operating system. Unlike TCPDUMP, Wireshark allows management through a **friendly graphical interface** (see Figure #2), so the user has no possibility of an unattended management. Also it permits **filtering and traffic analysis** with **statistics, graphics** and other utilities. It supports the TCPDUMP file format and recognizes a lot of protocols.

<div class="row mt-3" style="text-align: center">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="assets/img/Research/las-dos-mejores-herramientas-para-la-captura-de-trafico/2.jpg" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Figure #2: View of the content of a UDP packet using Wireshark.
</div>

Another interesting feature for researchers is that it allows the **export of capture files** to different formats for use with oriented applications of mathematical analysis or databases, which can be useful for further analysis, such as calculations of delays, MOS, statistics and other quantities that can be extracted from the packet capture in the network.

For installation on Linux systems, this application is usually found in the repositories, so you use the package manager as distribution, if you can not find it or you are using Windows you can download it [here](http://www.wireshark.org/download.html).

## References

1. [http://www.tcpdump.org/](http://www.tcpdump.org/)
2. [http://www.wireshark.org/](http://www.wireshark.org/)
