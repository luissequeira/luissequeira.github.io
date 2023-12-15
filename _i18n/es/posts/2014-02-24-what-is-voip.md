---
layout: post
title:  ¿Qué es VoIP?
date:   2014-02-27 06:00:00
description:  VoIP se refiere a la tecnología necesaria para la comunicación de voz a través de IP, mientras que, ToIP es un servicio telefónico para los usuarios que utiliza VoIP como tecnología para dar dicho servicio. VoIP permite la transmisión de voz por medio de una red IP, incluyendo aquellas conectadas a Internet, consiste en la digitalización de la señales de voz por medio de un codec
tags: red voip
categories: Services
---
<p>
<span style="font-family: arial, helvetica, sans-serif; font-size: 14px;">El desarrollo de tecnolog&iacute;as de VoIP (Voice over Internet Protocol) han tenido una gran aceptaci&oacute;n por parte de <strong>empresas que buscan una reducci&oacute;n de costes para sus comunicaciones de voz</strong>, principalmente PYMES (Peque&ntilde;as y Medianas Empresas). El t&eacute;rmino VoIP no debe confundirse con ToIP (Telephony over IP), <strong>VoIP se refiere a la tecnolog&iacute;a necesaria para la comunicaci&oacute;n de voz a trav&eacute;s de IP, mientras que, ToIP es un servicio telef&oacute;nico para los usuarios que utiliza VoIP como tecnolog&iacute;a para dar dicho servicio</strong>.</span></p>
<p>
<span style="font-family: arial, helvetica, sans-serif; font-size: 14px;"><strong>VoIP permite la transmisi&oacute;n de voz por medio de una red IP, incluyendo aquellas conectadas a Internet, consiste en la digitalizaci&oacute;n de la se&ntilde;ales de voz por medio de un codec</strong>. El consumo de ancho de banda de una comunicaci&oacute;n de este tipo est&aacute; directamente relacionada al codec como se muestra en la <span style="color:#0000ff;"><strong>Tabla # 1</strong></span>.</span></p>
<p>
&nbsp;</p>
<table align="center" border="1" cellpadding="1" cellspacing="1" style="width: 269px;">
<tbody>
<tr>
<td style="text-align: center; width: 105px;">
<h1>
<strong><span style="font-size: 13.63636302947998px;">Codec</span></strong></h1>
</td>
<td style="text-align: center; width: 154px;">
<h1>
<strong><span style="font-size: 13.63636302947998px;">Bit-rate</span></strong></h1>
</td>
</tr>
<tr>
<td style="text-align: center; width: 105px;">
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;">G.711</span></span></td>
<td style="text-align: center; width: 154px;">
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;">56 o 64 Kbps</span></span></td>
</tr>
<tr>
<td style="text-align: center; width: 105px;">
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;">G.722</span></span></td>
<td style="text-align: center; width: 154px;">
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;">48, 56 o 64 Kbps</span></span></td>
</tr>
<tr>
<td style="text-align: center; width: 105px;">
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;">G.723</span></span></td>
<td style="text-align: center; width: 154px;">
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;">5,3 o 6,4 Kbps</span></span></td>
</tr>
<tr>
<td style="text-align: center; width: 105px;">
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;">G.728</span></span></td>
<td style="text-align: center; width: 154px;">
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;">16 Kbps</span></span></td>
</tr>
<tr>
<td style="text-align: center; width: 105px;">
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;">G.729</span></span></td>
<td style="text-align: center; width: 154px;">
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;">8 o 13 Kbps</span></span></td>
</tr>
</tbody>
</table>
<p style="text-align: center;">
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;"><span style="color:#0000ff;"><strong>Tabla # 1</strong></span>: Ancho de banda seg&uacute;n codec.</span></span></p>
<p>
&nbsp;</p>
<p>
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;">Por otro lado, VoIP hace uso de diversos tipos de t&eacute;cnicas para la se&ntilde;alizaci&oacute;n de la llamada, no habiendo un protocolo definido en este &aacute;mbito. Uno de los protocolo utilizados con este fin en SIP (Session Initiation Protocol), adem&aacute;s, se encuentran implementaciones con H.323 (una recomendaci&oacute;n del sector de telecomunicaciones de la ITU, ITU-T) o IAX (Inter-Asterisk eXchange protocol, nativo de Asterisk private branch exchange, PBX).</span></span></p>
<p>
<span style="font-family: arial, helvetica, sans-serif; font-size: 14px;">SIP es uno de los protocolo con mayor impacto en la implementaci&oacute;n de ToIP. Dicho protocolo, <strong>se encarga de la se&ntilde;alizaci&oacute;n extremo a extremo de la comunicaci&oacute;n, realiza los procedimientos necesarios para el establecimiento de la llamada, la modificaci&oacute;n y la finalizaci&oacute;n de la comunicaci&oacute;n</strong>. Para la transmisi&oacute;n de datos en tiempo real, VoIP hace uso del protocolo RTP (Real-time Transport Protocol), dicho protocolo se encarga del control de la transmisi&oacute;n en las sesiones de aplicaciones multimedia y utiliza como protocolo de transporte UDP (User Datagram Protocol). En la <span style="color:#0000ff;"><strong>Figura # 1</strong></span>, se observa la distribuci&oacute;n de los encabezados de cada uno de los paquetes de VoIP.</span></p>
<p>
&nbsp;</p>
<p style="text-align: center;">
<img alt="" src="images/TICs/what-is-voip/1_es.png" style="height: 138px; width: 500px;" /></p>
<p style="text-align: center;">
<span style="font-family: arial, helvetica, sans-serif; font-size: 14px;"><span style="color:#0000ff;"><strong>Figura # 1</strong></span>: Paquete VoIP transmitido por las estaciones.</span></p>

<p>
<span style="font-family: arial, helvetica, sans-serif; font-size: 14px;">Existen diversos dispositivos que act&uacute;an como una pasarela de voz sobre IP hacia una red telef&oacute;nica convencional y viceversa, utilizando el protocolo SIP para la se&ntilde;alizaci&oacute;n de la comunicaci&oacute;n. Normalmente, <strong>estos dispositivos pueden ser configurados, con relativa facilidad, por medio de un men&uacute; IVR (Interative Voice Response) o mediante un servidor web desde cualquier navegador</strong>.</span></p>
<p>
<span style="font-family: arial, helvetica, sans-serif; font-size: 14px;">El men&uacute; IVR permite la configuraci&oacute;n b&aacute;sica del dispositivo, como lo es la asignaci&oacute;n de direcciones IP a cada terminal. La configuraci&oacute;n avanzada de la pasarela VoIP, consiste en la asignaci&oacute;n de los par&aacute;metros correspondientes para las funcionalidades de enrutador y otras asociadas a la voz. Esta configuraci&oacute;n se realiza por medio de un navegador web. Dentro de los aspectos m&aacute;s relevantes de la configuraci&oacute;n, destacan la <strong>utilizaci&oacute;n de SIP como protocolo de se&ntilde;alizaci&oacute;n, la configuraci&oacute;n de NAT (Network Address Translation) y dem&aacute;s funcionalidades de enrutamiento. Por otro lado, en la configuraci&oacute;n de audio se puede seleccionar diferentes codecs</strong>, por ejemplo G729, la cantidad de muestras por paquete y la supresi&oacute;n de silencio.</span></p>
<p style="text-align: center;">
&nbsp;</p>
<p style="text-align: center;">
<img alt="" src="images/TICs/what-is-voip/2.png" style="height: 204px; width: 500px;" /></p>
<p style="text-align: center;">
<span style="font-family: arial, helvetica, sans-serif; font-size: 14px;"><span style="color:#0000ff;"><strong>Figura # 2</strong></span>: Ejemplo de configuraci&oacute;n de audio.</span></p>
<p style="text-align: center;">
&nbsp;</p>
<p>
&nbsp;</p>
<p>
&nbsp;</p>
<p>
&nbsp;</p>