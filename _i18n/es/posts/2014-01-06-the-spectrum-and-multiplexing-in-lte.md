---
layout: post
title:  El espectro y la multiplexión en LTE
date:   2014-01-09 06:00:00
description: En relación al espectro, LTE se torna bastante flexible permitiendo anchos de banda de 1.25MHz, 1.6MHz, 2.5MHz, 5MHz, 10MHz, 15MHz and 20MHz en el enlace descendente así como en el ascendente. La Multiplexación por División de Frecuencias Ortogonales (OFDM) es un esquema de multiplexación de frecuencia que se caracteriza por enviar una cantidad determinada de frecuencias portadoras dentro de un ancho de banda específico.
tags: LTE 4G wireless red red-de-acceso espectro multiplexión ancho-de-banda radio OFDM
categories: LTE (4G)
---
<h2>
<span style="font-family: arial, helvetica, sans-serif; font-size: 14px;">El espectro</span></h2>
<p>
<span style="font-family: arial, helvetica, sans-serif; font-size: 14px;">En relación al espectro, LTE se torna bastante flexible permitiendo <strong>anchos de banda</strong> de 1.25MHz, 1.6MHz, 2.5MHz, 5MHz, 10MHz, 15MHz and 20MHz en el enlace descendente así como en el ascendente <span style="color:#ff8c00;"><strong>[4]</strong></span>. Además, soporta transmisión broadcast en modos solamente descendente y descendente-ascendente, por otro lado, <strong>los recursos de radio pueden modificarse</strong> para transmisiones broadcast según las necesidades del operador.</span></p>
<p>
<span style="font-family: arial, helvetica, sans-serif; font-size: 14px;">Los diversos escenarios que se presentan entre la interacción de diferentes proveedores de servicios y las otras redes de las que disponen, no se ven afectados en gran medida ya que los fabricantes han previsto la <strong>coexistencia</strong> dentro de la misma área geográfica de la <a href="http://www.telecomsharing.com/es/biblioteca/lte-4g/item/33-caracteristicas-de-la-arquitectura-lte-sae">EUTRAN con otro tipo de redes como 3G</a> y la <strong>coexistencia entre operadores adyacentes</strong>, así también, es el caso del solapamiento en los <strong>límites de los países</strong> <strong><span style="color:#ff8c00;">[4]</span></strong>.</span></p>
<p>
<span style="font-family: arial, helvetica, sans-serif; font-size: 14px;">La eficiencia espectral que presenta LTE supera en buena medida a HSPA+, estos son los resultados de Telefónica <strong><span style="color:#ff8c00;">[9]</span></strong>, el estudio contempla un escenario de centros urbanos con <strong>alta densidad de edificios</strong>, configuración de antenas MIMO 2x2 para los dos casos y utilizando 64QAM como esquema de modulación, con esto, el estudio asegura que <strong>LTE supera en eficiencia espectral a HSPA+</strong> por un 20% a plena carga. De la <strong><span style="color:#0000ff;">Figura #1</span></strong> se deduce que para centros rurales o suburbanos las prestaciones de LTE serán mayores, además, a lo largo de la gráfica se denota la superioridad de LTE.</span></p>
<p>
&nbsp;</p>
<p style="text-align: center;">
<img alt="" src="images/TICs/el-espectro-y-la-multiplexion-en-LTE/1.jpg" /></p>
<p style="text-align: center;">
<span style="font-family: arial, helvetica, sans-serif; font-size: 14px; color: rgb(0, 0, 255);"><strong>Figura # 1</strong></span><span style="font-family: arial, helvetica, sans-serif; font-size: 14px;">: Eficiencia espectral en función del uso de recursos </span><strong style="font-family: arial, helvetica, sans-serif; font-size: 14px;"><span style="color:#ff8c00;">[9]</span></strong><span style="font-family: arial, helvetica, sans-serif; font-size: 14px;">.</span></p>

<p>
<span style="font-family: arial, helvetica, sans-serif; font-size: 14px; color: rgb(68, 68, 68);">Multiplexación por División de Frecuencia Ortogonal (OFDM)</span></p>
<p>
<span style="font-family: arial, helvetica, sans-serif; font-size: 14px;">La Multiplexación por División de Frecuencias Ortogonales (OFDM) es un <strong>esquema de multiplexación de frecuencia</strong> que se caracteriza por enviar una cantidad determinada de frecuencias portadoras dentro de un ancho de banda específico <strong><span style="color:#ff8c00;">[7, 8]</span></strong>, cada una de estas portadoras transporta información utilizando esquemas de <strong>modulación como QAM o PSK (QPSK, 16QAM y 64QAM)</strong> <strong><span style="color:#ff8c00;">[10]</span></strong>. Una de las <strong>principales ventajas</strong> que presenta este tipo de multiplexación es en cuanto al <strong>desvanecimiento de las señales, retados y en general ante las interferencias</strong>, además <a href="http://www.telecomsharing.com/es/biblioteca/lte-4g/item/32-aspectos-generales-de-propagacion-en-lte">presenta características óptimas frente al multitrayecto</a>, por otro lado, con modulaciones QAM y PSK es posible transmitir más cantidad de símbolos por ciclo.</span></p>
<p>
&nbsp;</p>
<p style="text-align: center;">
<img alt="" src="images/TICs/el-espectro-y-la-multiplexion-en-LTE/2.jpg" /></p>
<p style="text-align: center;">
<strong style="font-family: arial, helvetica, sans-serif; font-size: 14px;"><span style="color:#0000ff;">Figura # 2</span></strong><span style="font-family: arial, helvetica, sans-serif; font-size: 14px;">: Representación de frecuenci</span><span style="font-family: arial, helvetica, sans-serif; font-size: 14px;">a y tiempo para una señal OFDM </span><strong style="font-family: arial, helvetica, sans-serif; font-size: 14px;"><span style="color:#ff8c00;">[7]</span></strong><span style="font-family: arial, helvetica, sans-serif; font-size: 14px;">.</span></p>
<p style="text-align: center;">
&nbsp;</p>
<p>
<span style="font-family: arial, helvetica, sans-serif; font-size: 14px;">Las diferentes frecuencias (n-ésimas) denominadas <strong>subportadoras</strong>, en la figura anterior deben tener una separación igual entre ellas y debe permanecer constante para no generar un traslape de las señales produciendo interferencias entre ellas. Dicha separación entre subportadoras viene dada por la siguiente expresión:</span></p>
<p>
&nbsp;</p>
<p style="text-align: center;">
<img alt="" src="images/TICs/el-espectro-y-la-multiplexion-en-LTE/eq1.jpg" /><strong><span style="color:#ff8c00;"><span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;">&nbsp;[7]</span></span></span></strong></p>
<p>
&nbsp;</p>
<p>
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;">Donde&nbsp;</span>w</span><span style="font-family: arial, helvetica, sans-serif; font-size: 14px;">&nbsp;es la frecuencia,&nbsp;</span><span style="font-size:14px;">n</span><span style="font-family: arial, helvetica, sans-serif; font-size: 14px;">&nbsp;la cantidad de subportadoras y&nbsp;</span><span style="font-size:14px;">f</span><span style="font-family: arial, helvetica, sans-serif; font-size: 14px;">&nbsp;la separación entre ellas.</span></p>
<p>
<span style="font-family: arial, helvetica, sans-serif; font-size: 14px;">Por otro lado, el 3GPP ha definido una separación entre canales OFDM, dicha separación se le conoce como <strong>guarda banda o intervalo de guarda</strong> y tiene la finalidad de generar una distancia en frecuencia entre canales adyacentes para que <strong>no hallan interferencias entre ellos</strong>, en general, lo que se realiza es anular la transmisión de una cantidad de subportadoras en la sección en el espectro donde termina un canal y empieza el siguiente en la parte superior e inferior del canal, reduciendo así el ancho de banda útil por canal, esto se puede ver en la </span><strong style="font-family: arial, helvetica, sans-serif; font-size: 14px;"><span style="color:#0000ff;">Figura # 3</span></strong><span style="font-family: arial, helvetica, sans-serif; font-size: 14px;">.</span></p>
<p>
&nbsp;</p>
<p style="text-align: center;">
<img alt="" src="images/TICs/el-espectro-y-la-multiplexion-en-LTE/3.jpg" /></p>
<p style="text-align: center;">
<strong style="font-family: arial, helvetica, sans-serif; font-size: 14px;"><span style="color:#0000ff;">Figura # 3</span></strong><span style="font-family: arial, helvetica, sans-serif; font-size: 14px;">: Subportadoras</span><span style="font-family: arial, helvetica, sans-serif; font-size: 14px;"> inactivas para un canal OFDM </span><strong style="font-family: arial, helvetica, sans-serif; font-size: 14px;"><span style="color:#ff8c00;">[7]</span></strong><span style="font-family: arial, helvetica, sans-serif; font-size: 14px;">.</span></p>
<p style="text-align: center;">
&nbsp;</p>
<p>
<span style="font-family: arial, helvetica, sans-serif; font-size: 14px;">En general, el estudio realizado por el 3GPP </span><strong style="font-family: arial, helvetica, sans-serif; font-size: 14px;"><span style="color:#ff8c00;">[7]</span></strong><span style="font-family: arial, helvetica, sans-serif; font-size: 14px;"> expone la viabilidad del uso de OFDM en la UTRAN para el enlace descendente y valida su inserción, afirma que<strong> OFDM mejora el rendimiento en comparación con HSDPA</strong> Realease 5, sin embargo, la introducción de un sistema más avanzado y de mayor complejidad, como lo es OFDM, no genera una diferencia significativa en el rendimiento del lado del receptor, y por lo tanto, <strong>se recomienda solamente para el enlace descendente</strong>.</span></p>
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