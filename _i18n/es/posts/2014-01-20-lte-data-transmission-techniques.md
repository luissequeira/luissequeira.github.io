---
layout: post
title:  Técnicas para la transmisión de datos en LTE
date:   2014-01-23 06:00:00
description: FDD (Frecuency Division Duplex) es un esquema de transmisión y recepción de señales, este sistema permite una comunicación full duplex utilizando dos frecuencias diferentes, una para el enlace descendente y otra para el ascendente, manteniendo una banda de separación entre dichas frecuencias con la finalidad de no traslapar los canales. La técnica de modulación y codificación del canal es uno de los puntos importantes en cuanto a las velocidades que permite LTE. Este nuevo modelo de red móvil utiliza AMC (Modulación y Codificación Adaptativa), esta técnica consiste en valorar las condiciones del canal de radio.
tags: LTE 4G FDD TDD transmisión propagación modulación codificación red-de-acceso
categories: LTE (4G)
---
<h2>
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;">Sistemas Duplex para transmisión: LTE-FDD y LTE-TDD</span></span></h2>
<p>
<span style="font-family: arial, helvetica, sans-serif; font-size: 14px;">FDD (Frecuency Division Duplex) es un <strong>esquema de transmisión y recepción de señales</strong>, este sistema permite una comunicación <strong>full duplex</strong> utilizando dos frecuencias diferentes, una para el enlace descendente y otra para el ascendente, manteniendo una <a href="http://www.telecomsharing.com/es/biblioteca/lte-4g/item/34-el-espectro-y-la-multiplexion-en-lte">banda de separación entre dichas frecuencias</a> con la finalidad de <strong>no traslapar los canales</strong>, esto hace que la eficiencia espectral de FDD no sea muy buena. Sin embargo, una de las ventajas de este esquema de multiplexación es que <strong>no introduce retardos ni latencia adicional</strong>.</span></p>
<p>
<span style="font-family: arial, helvetica, sans-serif; font-size: 14px;">Por otro lado, TDD (Time Division Duplex) es otra <strong>técnica de multiplexado</strong> para comunicaciones que utiliza <strong>un solo canal, o frecuencia</strong>, para la transmisión de información, en este caso la transmisión y la recepción se realiza por la misma frecuencia pero con diferencias de tiempo y una <strong>separación temporal entre los dos sentidos de la comunicación</strong>, haciendo más eficiente el uso del espectro. La multiplexación TDD realiza una asignación temporal para los sentidos de comunicación, además del tiempo de guarda, esto hace que sea <strong>más sensible a los retardos y la latencia</strong>.</span></p>
<p>
<span style="font-family: arial, helvetica, sans-serif; font-size: 14px;">Algunas comparaciones:</span></p>
<ul>
<li>
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;"><strong>En cuanto a la distancia</strong> FDD presenta mejores características a más largas distancias que TDD, de tal manera que TDD tiene más aceptación en escenarios donde las distancias son más cortas.</span></span></li>
<li>
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;"><strong>La propagación de las señales también presenta características diferentes</strong>, ya que TDD utiliza una sola frecuencia, esto hace que el canal como tal, presente las mismas características en las transmisión y en la recepción.</span></span></li>
<li>
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;">En FDD cada uno de <strong>los canales presenta diferentes características de propagación</strong> en función de la frecuencia utilizada.</span></span></li>
<li>
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;">La diferencia de frecuencias de los canales FDD, produce que <strong>la capacidad de cada canal dependa de la frecuencia</strong> asignada por las autoridades reguladoras.</span></span></li>
<li>
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;">En TDD es <strong>más sencillo hacer una distribución dinámica</strong> de la capacidad del downlink y el uplink con la finalidad de satisfacer las características de la demanda de recursos.</span></span></li>
</ul>
<p>
<span style="font-family: arial, helvetica, sans-serif; font-size: 14px;">Las asignaciones de frecuencias que ha establecido el 3GPP para el uso de TDD y FDD se muestran la siguiente figura:</span></p>
<p>
&nbsp;</p>
<p style="text-align: center;">
<img alt="" src="images/TICs/tecnicas-para-la-transmision-de-datos-en-LTE/1.jpg" style="height: 257px; width: 500px;" /></p>
<p style="text-align: center;">
<strong style="font-family: arial, helvetica, sans-serif; font-size: 14px;"><span style="color:#0000ff;">Figura # 1</span></strong><span style="font-family: arial, helvetica, sans-serif; font-size: 14px;">: Bandas de frecuencias para LTE FDD y TDD </span><strong style="font-family: arial, helvetica, sans-serif; font-size: 14px;"><span style="color:#ff8c00;">[1]</span></strong><span style="font-family: arial, helvetica, sans-serif; font-size: 14px;">.</span></p>

<h2>
<span style="font-family: arial, helvetica, sans-serif; font-size: 14px; color: rgb(68, 68, 68);">Modulación y codificación</span></h2>
<p>
<span style="font-family: arial, helvetica, sans-serif; font-size: 14px;">La técnica de modulación y codificación del canal es uno de los<strong> puntos importantes en cuanto a las velocidades</strong> que permite <a href="http://www.telecomsharing.com/es/biblioteca/lte-4g/item/31-que-es-4g-y-cuales-son-las-caracteristicas-tecnicas-mas-importantes">LTE</a>. Este nuevo modelo de red móvil utiliza AMC (Modulación y Codificación Adaptativa) <strong><span style="color:#ff8c00;">[9]</span></strong>, esta técnica <strong>consiste en valorar las condiciones del canal de radio</strong>, se usan distintos esquemas de codificación de canal y de modulación. El proceso para seleccionar la <strong>modulación óptima y el esquema de codificación</strong> se lleva a cabo muy en coordinación con el de “fast scheduling”. Los esquemas de modulación son: QPSK, 16QAM y 64QAM.</span></p>
<p>
&nbsp;</p>
<p style="text-align: center;">
<img alt="" src="images/TICs/tecnicas-para-la-transmision-de-datos-en-LTE/2.jpg" /></p>
<p style="text-align: center;">
<strong style="font-family: arial, helvetica, sans-serif; font-size: 14px;"><span style="color:#0000ff;">Figura # 2</span></strong><span style="font-family: arial, helvetica, sans-serif; font-size: 14px;">: Diagramas de constelación de 16QAM y 64QAM.</span></p>
<p style="text-align: center;">
&nbsp;</p>
<p>
<span style="font-family: arial, helvetica, sans-serif; font-size: 14px;">La codificación de canal en LTE se denomina HARQ (“Fast Hybrid ARQ, Fast Hybrid Automatic Repeat Request”) es una combinación de FEC+ARQ, si una trama no puede ser corregida, entonces, se solicita una retransmisión. Para este caso las tramas dañadas que han podido ser corregidas mediante el FEC </span><strong style="font-family: arial, helvetica, sans-serif; font-size: 14px;">no se descartan</strong><span style="font-family: arial, helvetica, sans-serif; font-size: 14px;">, sino, que se guardan para combinarse con otras tramas sucesivas dañadas y producir una correcta, esto se basa en el principio que para dos tramas sucesivas, que contengan la misma información, </span><strong style="font-family: arial, helvetica, sans-serif; font-size: 14px;">la probabilidad de que tengan los mismos bit erróneos es muy baja</strong><span style="font-family: arial, helvetica, sans-serif; font-size: 14px;">, por lo que </span><strong style="font-family: arial, helvetica, sans-serif; font-size: 14px;">la probabilidad de reconstruir un paquete sin errores de los dos anteriores es muy alta</strong><span style="font-family: arial, helvetica, sans-serif; font-size: 14px;">. Los mecanismos de corrección de errores se implementan en el eNodoB.</span></p>
<p>
&nbsp;</p>
<h2>
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;">Referencias</span></span></h2>
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