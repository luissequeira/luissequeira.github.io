---
layout: post
title:  Femto celdas desafíos en la gestión de interferencias
date:   2014-04-03 05:00:00
description: En este contexto, los operadores han impulsado la implementación de femto-celdas para disminuir la distancia con el UE y poder mantener una buena calidad de la señal. Sin embargo, las femto-celdas deben operar en la banda de frecuencias designadas para dicha comunicación y coincidir con las frecuencias asignadas al operador.
tags: 4G LTE femtoceldas
categories: Research
---
<p>
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;">Algunos estudios muestran que m&aacute;s del 50% de las llamadas de voz y el 70% del tr&aacute;fico de datos proviene de interiores <span style="color:#ff8c00;"><strong>[1]</strong></span>, las llamadas de voz no requieren grandes anchos de banda, pero si ciertos par&aacute;metros de calidad que garantice el reconocimiento de la voz por el usuario en el otro extremo de la comunicaci&oacute;n, por el contrario, el tr&aacute;fico de datos requiere altas tazas de transmisi&oacute;n para poder enviar informaci&oacute;n con gran cantidad de megabytes, como las aplicaciones multimedia lo requieren, por mencionar un ejemplo. <strong>Una forma de garantizar altas tazas de transmisi&oacute;n en sistemas de radio, consiste en poder mantener una alta calidad de la se&ntilde;al en ambos extremos de la comunicaci&oacute;n, y por lo tanto, mitigar los efectos de las p&eacute;rdidas e interferencias que pueda tener el canal de comunicaci&oacute;n</strong>.</span></span></p>
<p>
<span style="font-family: arial, helvetica, sans-serif; font-size: 14px;">En este contexto, los operadores han impulsado la implementaci&oacute;n de femto-celdas para disminuir la distancia con el UE y poder mantener una buena calidad de la se&ntilde;al. Sin embargo, <strong>las femto-celdas deben operar en la banda de frecuencias designadas para dicha comunicaci&oacute;n y coincidir con las frecuencias asignadas al operador</strong>, desde esta perspectiva, las femto-celdas generar&aacute;n interferencias y estas se pueden dar de las siguientes maneras <span style="color:#ff8c00;"><strong>[2]</strong></span>:</span></p>
<ul>
<li>
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;">Femto-celda a femto-celda.</span></span></li>
<li>
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;">Femto-celda a macro-celda</span></span></li>
<li>
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;">Macro-celda a femto-celda.</span></span></li>
</ul>
<p>
<span style="font-family: arial, helvetica, sans-serif; font-size: 14px;"><strong>Los problemas de la interferencias entre femto-celdas radica en la cobertura que cada una de &eacute;stas tenga</strong>, este tipo de interferencia se producir&aacute; principalmente en los l&iacute;mites de cobertura donde interaccionan las femto-celdas, en la <span style="color:#0000ff;"><strong>Figura # 1</strong></span> se puede observar este fen&oacute;meno, <strong>en la cual la cobertura del FAP 1 se solapa con la del FAP 2, produciendo degradaci&oacute;n de la se&ntilde;al para los usuarios de ambas femto-celdas en esa zona</strong>.</span></p>
<p>
&nbsp;</p>
<p style="text-align: center;">
<img alt="" src="images/Research/femtoceldas-desafios-gestion-interferencias/1.png" style="height: 408px; width: 500px;" /></p>
<p style="text-align: center;">
<span style="font-family: arial, helvetica, sans-serif; font-size: 14px; color: rgb(0, 0, 255);"><strong>Figura # 1</strong></span><span style="font-family: arial, helvetica, sans-serif; font-size: 14px;">. Problemas de interferencia entre macro/femto celdas.</span></p>

<p>
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;">Otro caso de interferencia es la interferencia que percibe el m&oacute;vil 2, suponemos que este m&oacute;vil se encuentra gestionado por la macro-celda y no tiene permiso de acceder a la femto-celda 1, sin embargo, se encuentra dentro del &aacute;rea de cobertura de dicha femto-celda, esto provocar&iacute;a interferencias en el m&oacute;vil ya que los canales de frecuencia por los que se comunica con la macro-celda se encuentran dentro del mismo ancho de banda que la femto-celda, <strong>este tipo de interferencia que produce la femto-celda a la macro-celda, tambi&eacute;n se puede dar en el sentido inverso, de macro-celda a femto-celda</strong>.</span></span></p>
<p>
<span style="font-family: arial, helvetica, sans-serif; font-size: 14px;">Cuando un m&oacute;vil asociado a una macro-celda se encuentra lejos del eNodeB y cercano a una femto-celda, &eacute;ste transmitir&aacute; con una potencia mayor para cubrir con las p&eacute;rdidas asociadas al enlace, sin embargo, al hacer esto, genera m&aacute;s interferencia hacia la femto-celda. Por otro lado, la femto-celda solicitar&aacute; a los m&oacute;viles que gestiona, un incremento en la potencia de transmisi&oacute;n para poder cubrir las interferencias, esto a su vez, generar&aacute; un nivel de interferencia mayor para el m&oacute;vil que se encuentra gestionado por la macro-celda. <strong>Los m&eacute;todos de acceso a la red tendr&aacute;n que gestionar el problema de la administraci&oacute;n de la potencia, de manera eficiente para permitir la coexistencia y asegurar la calidad de servicio</strong>.</span></p>
<p>
<span style="font-family: arial, helvetica, sans-serif; font-size: 14px;">En este contexto se genera un problema en cuanto a la gesti&oacute;n de la cobertura de las femto-celdas, ya que se deben minimizar las interferencias que generen, y a la vez, cubrir con los requerimientos de calidad de servicio. Por lo tanto, el proveedor del servicio debe tener un control preciso de la femto-celda en varios sentidos:</span></p>
<ul>
<li>
<strong><span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;">Se debe asegurar el uso del espectro asignado y verificar que la femto-celda no se encuentra transmitiendo fuera de la banda de frecuencias correspondiente.</span></span></strong></li>
<li>
<strong><span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;">Los traslados de ubicaci&oacute;n deben ser gestionados adecuadamente, ya que esto podr&iacute;a desarrollar localidades con una gran cantidad de interferencias por la acumulaci&oacute;n de femto-celdas cercanas.</span></span></strong></li>
<li>
<strong><span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;">Debe de tenerse en cuenta que las t&eacute;cnicas tradicionales de planificaci&oacute;n, como la reutilizaci&oacute;n de frecuencias, carece de sentido ya que el usuario es el que instala las femto-celdas.</span></span></strong></li>
</ul>
<p>
<span style="font-family: arial, helvetica, sans-serif; font-size: 14px;">Por otro lado, se han encontrado <strong>problemas con la implementaci&oacute;n de femto-celdas en &aacute;reas donde se encuentra una red Wi-Fi</strong>, en <span style="color:#ff8c00;"><strong>[1]</strong></span> se comentan casos donde los FAP experimentan dificultades en la transferencia de datos, incluso en los servicios de voz.</span></p>
<p>
&nbsp;</p>
<h1>
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;">Referencias</span></span></h1>
<ol>
<li>
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;">Vikram C, Jeffrey GA &amp; Alan G. Femtocell Networks: A Survey. IEEE Comunication Magzine (2008) 46: pp. 59-67.</span></span></li>
<li>
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;">G DLR, A V, D L &amp; Jie Z. Access control Mechanisms for Femtocells. IEEE Communications Magazine (2010) 48: pp. 33-39.</span></span></li>
</ol>