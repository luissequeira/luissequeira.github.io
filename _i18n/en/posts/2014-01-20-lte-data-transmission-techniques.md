---
layout: post
title:  LTE data transmission techniques
date:   2014-01-20 06:00:00
description: Duplex Systems transmission LTE-FDD and LTE-TDD. FDD (Frequency Division Duplex) is a scheme of transmitting and receiving signals, this system allows full duplex communication using two different frequencies. TDD (Time Division Duplex) is another multiplexing technique for communication that uses a single channel or frequency, for information transmission. The modulation technique and channel coding is one of the important points of the LTE speed ranges. This new model of mobile network uses AMC (Adaptive Modulation and Coding)
tags: LTE FDD TDD access-network wireless propagation modulation coding transmission 4G
categories: LTE (4G) 
---
<h2>
<span style="font-family: arial, helvetica, sans-serif; font-size: 14px;">Duplex Systems transmission: LTE-FDD and LTE-TDD</span></h2>
<p>
<span style="font-family: arial, helvetica, sans-serif; font-size: 14px;">FDD (Frequency Division Duplex) is a <strong>scheme of transmitting and receiving signals</strong>, this system allows <strong>full duplex communication</strong> using two different frequencies, one for the downlink and one for uplink, </span><span style="font-family: arial, helvetica, sans-serif; font-size: 14px;">maintaining a <a href="http://www.telecomsharing.com/en/library/lte-4g/item/49-the-spectrum-and-multiplexing-in-lte">separation band between said frequencies</a> in order <strong>no overlap of channels</strong>, </span><span style="font-family: arial, helvetica, sans-serif; font-size: 14px;">it makes that the FDD spectral efficiency is not very good. However, one advantage of this multiplexing scheme is that it does <strong>not introduce additional delays or latency</strong>.</span></p>
<p>
<span style="font-family: arial, helvetica, sans-serif; font-size: 14px;">On the other hand, TDD (Time Division Duplex) is another multiplexing technique for communication that uses a <strong>single channel or frequency</strong>, for information transmission. </span><span style="font-family: arial, helvetica, sans-serif; font-size: 14px;">In this case, the transmission and reception is performed by the same frequency but with differences in time and <strong>a temporal separation between the two directions of communication</strong>, making more efficient use of spectrum. </span><span style="font-family: arial, helvetica, sans-serif; font-size: 14px;">The TDD multiplexing takes a temporary assignment to the communication directions, and the guard time, which <strong>makes it more sensitive to delays and latency</strong>.</span></p>
<p>
<span style="font-family: arial, helvetica, sans-serif; font-size: 14px;">Some comparisons:</span></p>
<ul>
<li>
<p>
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;"><strong>Regarding FDD distance</strong> has better characteristics at longer distances than TDD, so TDD has more acceptation in scenarios where distances are shorter.</span></span><!--EndFragment--></p>
</li>
<li>
<p>
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;"><!--StartFragment--><strong>The signal propagation also has different characteristics</strong>, since TDD uses a single frequency, this makes the channel as such, presents the same characteristics in transmission and reception.</span></span><!--EndFragment--></p>
</li>
<li>
<p>
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;">In FDD each <strong>channel has different propagation characteristics</strong> depending on the frequency used.</span></span></p>
</li>
<li>
<p>
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;">The frequency difference of the FDD channels, causes that <strong>the capacity of each channel depends on the frequency</strong> allocated by regulatory authorities.</span></span></p>
</li>
<li>
<p>
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;">In TDD is <strong>easier to make a dynamic distribution</strong> of the uplink and downlink capacity in order to meet the demand characteristics of resources.</span></span><!--EndFragment--></p>
</li>
</ul>
<p>
<span style="font-family: arial, helvetica, sans-serif; font-size: 14px;"><span style="color:#0000ff;"><strong>Figure # 1</strong></span> shows the frequency assignments set by 3GPP for the use of TDD and FDD:</span></p>
<p>
&nbsp;</p>
<p style="text-align: center;">
<img alt="" src="images/TICs/tecnicas-para-la-transmision-de-datos-en-LTE/1.jpg" style="height: 257px; width: 500px;" /></p>
<p style="text-align: center;">
<span style="font-family: arial, helvetica, sans-serif; font-size: 14px;"><span style="color:#0000ff;"><strong>Figure # 1</strong></span>: </span><span style="font-family: arial, helvetica, sans-serif; font-size: 14px;">Frequency bands for LTE FDD and TDD</span><span style="font-family: arial, helvetica, sans-serif; font-size: 14px;"> <span style="color:#ff8c00;"><strong>[1]</strong></span>.</span></p>

<h2>
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;"><!--StartFragment-->Modulation and Coding</span></span><!--EndFragment--></h2>
<p>
<span style="font-family: arial, helvetica, sans-serif; font-size: 14px;">The modulation technique and channel coding is one of the <strong>important points of the LTE speed ranges</strong>. </span><span style="font-family: arial, helvetica, sans-serif; font-size: 14px;">This new model of mobile network uses AMC (Adaptive Modulation and Coding) <span style="color:#ff8c00;"><strong>[9]</strong></span>, this technique <strong>consist in to assess the conditions of the radio channel</strong> and using different channel coding and modulation schemes. The process for selecting the <strong>optimal modulation and coding scheme</strong> is carried out in coordination with the "fast scheduling". Modulation schemes are QPSK, 16QAM and 64QAM.</span></p>
<p>
&nbsp;</p>
<p style="text-align: center;">
<img alt="" src="images/TICs/tecnicas-para-la-transmision-de-datos-en-LTE/2.jpg" /></p>
<p style="text-align: center;">
<span style="font-family: arial, helvetica, sans-serif; font-size: 14px; color: rgb(0, 0, 255);"><strong>Figure # 2</strong></span><span style="font-family: arial, helvetica, sans-serif; font-size: 14px;">: </span><span style="font-family: arial, helvetica, sans-serif; font-size: 14px;">Constellation diagrams for 16QAM and 64QAM</span><span style="font-family: arial, helvetica, sans-serif; font-size: 14px;">.</span></p>
<p style="text-align: center;">
&nbsp;</p>
<p>
<span style="font-family: arial, helvetica, sans-serif; font-size: 14px;">In <a href="http://www.telecomsharing.com/en/library/lte-4g/item/37-what-is-4g-and-what-are-the-most-important-technical-characteristics">LTE</a>, the channel coding is called HARQ ("Fast Hybrid ARQ, Fast Hybrid Automatic Repeat Request"), it is a combination of FEC + ARQ, if a frame can not be corrected, then a re-transmission is requested. </span><span style="font-family: arial, helvetica, sans-serif; font-size: 14px;">For the case the damaged frames that have been corrected by the FEC <strong>are not discarded</strong>, but they are kept to be combined with other successive damaged frames to produce a correct one, this is based on the principle that for two successive frames, containing the same information, <strong>the probability of having the same error bit is very low, so that the probability of reconstructing a packet without error from the previous two is high</strong>. The error correction mechanisms are implemented in the eNodeB.</span></p>
<p>
&nbsp;</p>
<h2>
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;">References</span></span></h2>
<ol>
<li>
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;">Ericsson , Gerhard, Fritze, SAE - The Core Network for LTE , 2008</span></span></li>
<li>
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;">Nortel, Long-Term Evolution (LTE): The vision beyond 3G, 2008</span></span></li>
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