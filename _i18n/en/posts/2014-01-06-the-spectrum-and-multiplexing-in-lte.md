---
layout: post
title:  The spectrum and multiplexing in LTE
date:   2014-01-06 06:00:00
description: Regarding the spectrum, LTE becomes quite flexible, allowing bandwidths of 1.25MHz, 1.6MHz, 2.5MHz, 5MHz, 10MHz, 15MHz and 20MHz in the downlink and uplink. Furthermore, it supports broadcast transmission in downlink and uplink-downlink modes, on the other hand, radio resources for broadcast transmissions can be modified according to the operator needs. Orthogonal Frequency Division Multiplexing (OFDM) is a frequency multiplexing scheme characterized by sending a certain amount of carrier frequencies in a specified bandwidth, each of these carriers, transports information using modulation schemes such as QAM or PSK (QPSK, 16QAM and 64QAM). One of the main advantages of this type of multiplexing is about the fading of signals, delays and in general against interference, also has excellent characteristics against multipath. Furthermore, with QAM and PSK modulations is possible to transmit more amount symbols per cycle.
tags: LTE 4G wireless access-network broadband multiplexing OFDM QAM PSK
categories: LTE (4G)
---
<h2>
<span style="font-family: arial, helvetica, sans-serif; font-size: 14px;">The spectrum</span></h2>
<p>
<span style="font-family: arial, helvetica, sans-serif; font-size: 14px;">Regarding the spectrum, LTE becomes quite flexible, allowing <strong>bandwidths</strong> of 1.25MHz, 1.6MHz, 2.5MHz, 5MHz, 10MHz, 15MHz and 20MHz in the downlink and uplink <span style="color:#ff8c00;"><strong>[4]</strong></span>. Furthermore, it supports broadcast transmission in downlink and uplink-downlink modes, on the other hand, <strong>radio resources for broadcast transmissions can be modified</strong> according to the operator needs.</span></p>
<p>
<span style="font-family: arial, helvetica, sans-serif; font-size: 14px;">The various scenarios which may present between the interaction of different service providers and other networks that they have, are not largely affected because manufacturers have planned <strong>coexistence</strong>, within the same geographic area, of the <a href="http://www.telecomsharing.com/en/library/lte-4g/item/44-architecture-features-lte-sae">EUTRAN with other networks such as 3G and <strong>coexistence between adjacent operators</strong></a>, so too, is the case of the overlapping in <strong>countries boundaries</strong> <span style="color:#ff8c00;"><strong>[4]</strong></span>.</span></p>
<p>
<span style="font-family: arial, helvetica, sans-serif; font-size: 14px;">The LTE spectral efficiency exceeds largely to HSPA +, these are the results of Telefónica <span style="color:#ff8c00;"><strong>[9]</strong></span>, the study provides a scenario of urban centers with <strong>high density of buildings</strong>, 2x2 MIMO antenna configuration for both cases and using 64QAM as modulation scheme, with this, the study says that <strong>LTE spectral efficiency exceeds to HSPA +</strong> by 20% at full load. It is apparent from <span style="color:#0000ff;"><strong>Figure # 1</strong></span> than for rural or suburban centers LTE benefits will outweigh, furthermore along the chart, the LTE superiority is denoted.</span></p>
<p>
&nbsp;</p>
<p style="text-align: center;">
<img alt="" src="images/TICs/el-espectro-y-la-multiplexion-en-LTE/1.jpg" /></p>
<p style="text-align: center;">
<span style="font-family: arial, helvetica, sans-serif; font-size: 14px; color: rgb(0, 0, 255);"><strong>Figure # 1</strong></span><span style="font-family: arial, helvetica, sans-serif; font-size: 14px;">: </span><span style="font-family: arial, helvetica, sans-serif; font-size: 14px;">Spectral efficiency in terms of resource use </span><span style="font-family: arial, helvetica, sans-serif; font-size: 14px; color: rgb(255, 140, 0);"><strong>[9]</strong></span><span style="font-family: arial, helvetica, sans-serif; font-size: 14px;">.</span></p>

<h2>
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;">Orthogonal Frequency Division <!--StartFragment-->Multiplexing (OFDM)</span></span><!--EndFragment--></h2>
<p>
<span style="font-family: arial, helvetica, sans-serif; font-size: 14px;">Orthogonal Frequency Division Multiplexing (OFDM) is a <strong>frequency multiplexing scheme</strong> characterized by sending a certain amount of carrier frequencies in a specified bandwidth <span style="color:#ff8c00;"><strong>[7] [8]</strong></span>, each of these carriers, transports information using <strong>modulation schemes such as QAM or PSK (QPSK, 16QAM and 64QAM)</strong> <span style="color:#ff8c00;"><strong>[10]</strong></span>. One of the <strong>main advantages</strong> of this type of multiplexing is about the <strong>fading of signals, delays and in general against interference</strong>, <a href="http://www.telecomsharing.com/en/library/lte-4g/item/38-general-aspects-of-propagation-on-lte">also has excellent characteristics against multipath</a>. Furthermore, with QAM and PSK modulations is possible to transmit more amount symbols per cycle.</span></p>
<p>
&nbsp;</p>
<p style="text-align: center;">
<img alt="" src="images/TICs/el-espectro-y-la-multiplexion-en-LTE/2.jpg" /></p>
<p style="text-align: center;">
<span style="font-family: arial, helvetica, sans-serif; font-size: 14px; color: rgb(0, 0, 255);"><strong>Figure # 2</strong></span><span style="font-family: arial, helvetica, sans-serif; font-size: 14px;">: </span><span style="font-family: arial, helvetica, sans-serif; font-size: 14px;">Representation of frequency and time for an OFDM signal&nbsp;</span><span style="font-family: arial, helvetica, sans-serif; font-size: 14px; color: rgb(255, 140, 0);"><strong>[7]</strong></span><span style="font-family: arial, helvetica, sans-serif; font-size: 14px;">.</span></p>
<p style="text-align: center;">
&nbsp;</p>
<p>
<span style="font-family: arial, helvetica, sans-serif; font-size: 14px;">The different frequencies (n-th) called <strong>sub-carriers</strong>, in </span><span style="font-family: arial, helvetica, sans-serif; font-size: 14px; color: rgb(0, 0, 255);"><strong>Figure # 2</strong></span><span style="font-family: arial, helvetica, sans-serif; font-size: 14px;">, must have equal spacing between them, and should remain constant in order to avoid the signal overlapping which cause interference between them.</span><span style="font-family: arial, helvetica, sans-serif; font-size: 14px;">This separation between sub-carriers is given by the following expression:</span></p>
<p>
&nbsp;</p>
<p style="text-align: center;">
<img alt="" src="images/TICs/el-espectro-y-la-multiplexion-en-LTE/eq1.jpg" /><span style="font-family: arial, helvetica, sans-serif; font-size: 14px;">[7]</span></p>
<p style="text-align: center;">
&nbsp;</p>
<p>
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;"><!--StartFragment-->Where <em>w</em> is the frequency, <em>n</em> the number of subcarriers and <em>f</em> the separation between them.</span></span><!--EndFragment--></p>
<p>
<span style="font-family: arial, helvetica, sans-serif; font-size: 14px;">For this, the 3GPP has defined a separation between OFDM channels, it is known as a <strong>guard band or guard interval</strong> and aims to create a distance between adjacent frequency channels <strong>to avoid interference between them</strong>. In the practice, we cancel the transmission of a number of sub-carriers in the spectrum section where the channel ends and the next begins, repeating at the top and bottom of the channel, thus reducing the usable bandwidth per channel, seen <span style="color:#0000ff;"><strong>Figure # 3</strong></span>.</span></p>
<p style="text-align: center;">
<br />
<img alt="" src="images/TICs/el-espectro-y-la-multiplexion-en-LTE/3.jpg" /></p>
<p style="text-align: center;">
<span style="font-family: arial, helvetica, sans-serif; font-size: 14px; color: rgb(0, 0, 255);"><strong>Figure # 3</strong></span><span style="font-family: arial, helvetica, sans-serif; font-size: 14px;">: </span><span style="font-family: arial, helvetica, sans-serif; font-size: 14px;">Inactive sub-carriers for an OFDM channel&nbsp;</span><span style="font-family: arial, helvetica, sans-serif; font-size: 14px; color: rgb(255, 140, 0);"><strong>[7]</strong></span><span style="font-family: arial, helvetica, sans-serif; font-size: 14px;">.</span></p>
<p style="text-align: center;">
&nbsp;</p>
<p>
<span style="font-family: arial, helvetica, sans-serif; font-size: 14px;">Overall, the study by the 3GPP <span style="color:#ff8c00;"><strong>[7]</strong></span> discussed the feasibility of using OFDM for downlink UTRAN and validates their inclusion, it says that <strong>OFDM improves performance compared to HSDPA</strong> Realease 5, however, the introduction of a more advanced and more complex system, such as OFDM, does not generate a significant difference in performance at the receiver side, and therefore, <strong>only recommended for the downlink</strong>.</span></p>
<p>
&nbsp;</p>
<h1>
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;">References</span></span></h1>
<ol>
<li>
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;">Ericsson , Gerhard, Fritze, SAE - The Core Network for LTE , 2008</span></span></li>
<li>
<span style="font-family: arial, helvetica, sans-serif; font-size: 14px;">Nortel, Long-Term Evolution (LTE): The vision beyond 3G, 2008</span></li>
<li>
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;">Motorola, long Term Evolution (LTE): A Technical Overview, 2010</span></span></li>
<li>
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;">3GPP 25.913, Requirements for Evolved UTRA (E-UTRA) and Evolved UTRAN (E-UTRAN) (Release 8), 2008</span></span></li>
<li>
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;">Santosh KD, LTE Whitepaper, 2009</span></span></li>
<li>
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;">3GPP 36.300, EUTRA and EUTRAN overall description, Stage 2, 2009</span></span></li>
<li>
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;">3GPP 25.892, Multiplexing (OFDM) for UTRAN enhancement (Release 6), 2004</span></span></li>
<li>
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;">Rohde &amp; Schwarz, UMTS Long Term Evolution (LTE) Tecnologi Introduccion, 2007</span></span></li>
<li>
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;">Telefónica I+D, ¿Qué podemos esperar de LTE? Ventajas y prestaciones, 2010</span></span></li>
<li>
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;"><a href="http://www.3gpp.org/LTE">http://www.3gpp.org/LTE</a></span></span></li>
<li>
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;"><a href="http://sociedadinformacion.fundacion.telefonica.com/DYC/SHI/seccion=1188&amp;idioma=es_ES&amp;id=2009100116310140&amp;activo=4.do?elem=7096">http://sociedadinformacion.fundacion.telefonica.com/DYC/SHI/seccion=1188&amp;idioma=es_ES&amp;id=2009100116310140&amp;activo=4.do?elem=7096</a></span></span></li>
<li>
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;"><a href="http://www.gradiant.org/index.php?option=com_content&amp;view=article&amp;id=289:mimo-en-wimax-y-lte&amp;catid=1:noticias&amp;Itemid=7&amp;lang=es">http://www.gradiant.org/index.php?option=com_content&amp;view=article&amp;id=289:mimo-en-wimax-y-lte&amp;catid=1:noticias&amp;Itemid=7&amp;lang=es</a></span></span></li>
</ol>