---
layout: post
title:  The 2 best tools for the capture and the interpretation of network data
date:   2013-12-02 06:00:00
description: The applications to capture packets on the network, e.g. tcpdump and wireshark are well known for their features, in addition to data capture, these applications are useful for certain packets analysis with the obtained data.
tags: telemática medidas-de-red wireshark tcpdump captura
categories: Tools
---
<p>
<!--StartFragment--></p>
<p style="margin-bottom: 0in">
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;">I present you <b>my favorite applications to capture</b> packets on the network, although they are well known for their features, I decided to give a little space to discuss some of their features. In addition to data capture, these applications are useful for certain packets <b>analysis</b> with the obtained data, on the other hand, when the analysis that we need to do is a bit complex or very specific, it is always advisable to build our own scripts, but there is no doubt that no matter for what we use them, this applications will <b>help us to obtain useful network information</b>. This applicacions can also be combined with <a href="index.php/en/research/tools/item/39-traffic-generators.html">traffic generators</a> in order to analyze some network issues.</span></span></p>
<p style="margin-bottom: 0in">
&nbsp;</p>
<h2>
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;">TCPDUM</span></span></h2>
<p>
<span style="font-family: arial, helvetica, sans-serif; font-size: 14px;">TCPDUMP </span><span style="font-family: arial, helvetica, sans-serif; font-size: 14px; color: rgb(255, 140, 0);"><strong>[1]&nbsp;</strong></span><span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;">is a tool for capturing <b>traffic flowing through the network in real time</b>, this includes packets <b>transmitted and received</b> on a specific network interface. This tool has no graphical interface, this makes for one of the favorite applications when you want to use <b>minimum resources as possible</b>, also be suitable for <b>unattended</b> packet capture, because it can be managed by <b>command line</b></span></span><span style="font-family: arial, helvetica, sans-serif; font-size: 14px;">&nbsp;as it can seen in&nbsp;</span><span style="font-family: arial, helvetica, sans-serif; font-size: 14px; color: rgb(0, 0, 255);"><strong>Figure # 1</strong></span><span style="font-family: arial, helvetica, sans-serif; font-size: 14px;">.</span></p>
<p>
&nbsp;</p>
<p>
<img alt="" class="caption" src="images/Research/las-dos-mejores-herramientas-para-la-captura-de-trafico/1.jpg" style="text-align: center; background-color: rgb(255, 255, 255);" title="Vista del contenido de varios paquetes por línea de comando utilizando TCPDUMP." /></p>
<p style="text-align: center;">
<strong style="font-family: arial, helvetica, sans-serif; font-size: 14px;"><span style="color:#0000ff;">Figure # 1</span></strong><span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;">:&nbsp;View of the contents of various packets for command line using</span></span><span style="font-family: arial, helvetica, sans-serif; font-size: 14px;">&nbsp;TCPDUMP.</span></p>

<p>
<!--StartFragment--></p>
<p style="margin-bottom: 0in">
<span style="font-family:arial,helvetica,sans-serif;"><span style="font-size:14px;">This application is available for almost all operating systems (in Windows is called WinDump). It uses the libpcap library in the cases of UNIX systems and winpcap for Windows, which is responsible for packet captures. This tool allows debugging of the output obtained by means of filters, <b>allowing capture specific port filtering</b>, or filtering by protocol type, source or destination address, on a <b>specific interface</b> and others.</span></span></p>
<!--StartFragment--><p>
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;">The installation of Linux operating systems tcpdump is usually not necessary, since it comes installed by default on most distributions, but if required, simply install using the package manager of your distribution, I am sure it is on the repositories, but if you want to compile it yourself you can download it</span></span><span style="font-family: arial, helvetica, sans-serif; font-size: 14px;">&nbsp;</span><a href="http://www.tcpdump.org/#latest-release" style="font-family: arial, helvetica, sans-serif; font-size: 14px;" target="_blank">here</a><span style="font-family: arial, helvetica, sans-serif; font-size: 14px;">. For Windows systems you can download it&nbsp;</span><a href="http://www.winpcap.org/windump/install/default.htm" style="font-family: arial, helvetica, sans-serif; font-size: 14px;" target="_blank">here</a><span style="font-family: arial, helvetica, sans-serif; font-size: 14px;">.</span></p>
<p>
&nbsp;</p>
<h2>
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;">Wireshark</span></span></h2>
<p>
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;">Wireshark <span style="color:#ff8c00;"><strong>[2]&nbsp;</strong></span>is an <b>analysis program</b>, held under GNU GPL (GNU General Public License), also uses the same packet capture libraries those used in TCPDUMP, depending on the operating system. Unlike TCPDUMP, Wireshark allows management through a <b>friendly graphical interface</b>&nbsp;</span></span><span style="font-size: 14px;"><span style="font-family:arial,helvetica,sans-serif;">(see&nbsp;</span></span><strong style="text-align: center; font-family: arial, helvetica, sans-serif; font-size: 14px;"><span style="color: rgb(0, 0, 255);">Figure # 2</span></strong><span style="font-family: arial, helvetica, sans-serif; font-size: 14px;">),</span><span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;">&nbsp;so the user has no possibility of an unattended management. Also it permits <b>filtering and traffic analysis</b> with <b>statistics, graphics</b> and other utilities. It supports the TCPDUMP file format and recognizes a lot of protocols.</span></span></p>
<p>
&nbsp;</p>
<p>
<img alt="" src="images/Research/las-dos-mejores-herramientas-para-la-captura-de-trafico/2.jpg" style="text-align: center;" /></p>
<p style="text-align: center;">
<strong style="font-family: arial, helvetica, sans-serif; font-size: 14px;"><span style="color: rgb(0, 0, 255);">Figure # 2</span></strong><span style="font-size: 14px;"><span style="font-family: arial, helvetica, sans-serif;">:&nbsp;</span></span><span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;">View of the content of a UDP packet using&nbsp;</span></span><span style="font-family: arial, helvetica, sans-serif; font-size: 14px;">Wireshark.</span></p>
<p style="text-align: center;">
&nbsp;</p>
<p>
<!--StartFragment--></p>
<p style="margin-bottom: 0in">
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;">Another interesting feature for researchers is that it allows the <b>export of capture files</b> to different formats for use with oriented applications of mathematical analysis or databases, which can be useful for further analysis, such as calculations of delays, MOS, statistics and other quantities that can be extracted from the packet capture in the network.</span></span></p>
<p>
<span style="font-size: 14px;"><span style="font-family:arial,helvetica,sans-serif;">For installation on Linux systems, this application is usually found in the repositories, so you use the package manager as distribution, if you can not find it or you are using Windows you can download it</span></span><span style="font-family: arial, helvetica, sans-serif; font-size: 14px;">&nbsp;</span><a href="http://www.wireshark.org/download.html" style="font-family: arial, helvetica, sans-serif; font-size: 14px;" target="_blank">here</a><span style="font-family: arial, helvetica, sans-serif; font-size: 14px;">.</span></p>
<p>
&nbsp;</p>
<h2>
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;">References</span></span></h2>
<ol>
<li>
<a href="http://www.tcpdump.org/" target="_blank"><span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;">http://www.tcpdump.org/</span></span></a></li>
<li>
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;"><a href="http://www.wireshark.org/" target="_blank">http://www.wireshark.org/</a></span></span></li>
</ol>
<div id="ckimgrsz" style="left: 8px; top: 322.34375px;">
<div class="preview" style="background-image: url(http://localhost/telecomsharing/images/Research/las-dos-mejores-herramientas-para-la-captura-de-trafico/1.jpg); display: none; top: 0px; left: 0px; width: 875px; height: 407.453125px;">
&nbsp;</div>
</div>