---
layout: post
title:  Interacción de macroceldas y femtoceldas
date:   2014-01-16 06:00:00
description: En las macroceldas se encuentran muchos usuarios y es más difícil proveer QoS a todos ellos. Por estos motivos los operadores han optado por la implementación de femtoceldas a nivel residencial con el fin de aumentar la calidad de los servicios brindados. Las femtoceldas son estaciones base de baja potencia y bajo costo que proveen una alta calidad de los servicios celulares a nivel residencial, en este ámbito ofrecen una cobertura de aproximadamente 10 m.
tags: LTE 4G red red-de-acceso wireless macroceldas femtoceldas banda-ancha QoS
categories: LTE (4G)
---
<p>
<span style="font-family: arial, helvetica, sans-serif; font-size: 14px;">Las macroceldas no son muy eficientes <strong><span style="color:#ff8c00;">[1]</span></strong> en el ámbito residencial debido a los problemas de penetración que se han mencionado en un artículo anterior, además, <strong>en las macroceldas se encuentran muchos usuarios y es más difícil proveer QoS a todos ellos</strong>. Por estos motivos los Proveedores de Servicios de Internet (ISP) han optado por la implementación de femtoceldas a nivel residencial con el fin de aumentar la calidad de los servicios brindados.</span></p>
<p>
<span style="font-family: arial, helvetica, sans-serif; font-size: 14px;"><strong>Las femtoceldas son estaciones base de baja potencia y bajo costo</strong> que proveen una alta calidad de los servicios celulares a nivel residencial, en este ámbito ofrecen una cobertura de aproximadamente 10 m <strong><span style="color:#ff8c00;">[2]</span></strong>, están diseñadas para integrarse de manera automática a las redes macrocelulares. Se integra con el operador móvil mediante una <strong>conexión de banda ancha</strong>, típicamente ADSL <strong><span style="color:#ff8c00;">[2, 3]</span></strong>, como puede apreciarse en la <span style="color:#0000ff;"><strong>Figura # 1</strong></span>. Sin embargo también se puede realizar por medio de un <strong>enlace radio</strong> como se menciona en <strong><span style="color:#ff8c00;">[4]</span></strong>. En General, la femtocelda hace que el tráfico del sistema celular proveniente del hogar, <strong>se desvíe por la conexión de banda ancha</strong>, liberando el consumo de recursos de la macrocelda.</span></p>
<p>
&nbsp;</p>
<p style="text-align: center;">
<img alt="" src="images/TICs/interaccion-de-macroceldas-y-femtoceldas/macro_femto_1.jpg" /></p>
<p style="text-align: center;">
<span style="font-family: arial, helvetica, sans-serif; font-size: 14px; color: rgb(0, 0, 255);"><strong>Figura # 1</strong></span><span style="font-family: arial, helvetica, sans-serif; font-size: 14px;">: Femto-celda típica </span><strong style="font-family: arial, helvetica, sans-serif; font-size: 14px;"><span style="color:#ff8c00;">[3]</span></strong><span style="font-family: arial, helvetica, sans-serif; font-size: 14px;">.</span></p>

<p>
<span style="font-family: arial, helvetica, sans-serif; font-size: 14px;">Las femtoceldas presentan una serie de ventajas tanto para los proveedores de servicios celulares como para los usuarios, éstos últimos, pueden </span><strong style="font-family: arial, helvetica, sans-serif; font-size: 14px;">percibir mejor nivel de señal</strong><span style="font-family: arial, helvetica, sans-serif; font-size: 14px;">, ya que se reduce la distancia entre la femtocelda y el UE, esto provoca que la SINR sea más alta </span><strong style="font-family: arial, helvetica, sans-serif; font-size: 14px;">aumentando la capacidad y propiciando mejores niveles de QoS</strong><span style="font-family: arial, helvetica, sans-serif; font-size: 14px;">. A su vez, la eficiencia espectral se ve incrementada debido a la cantidad de usuarios por hertz por unidad de área, además, los bajos niveles de potencia de transmisión generan un </span><strong style="font-family: arial, helvetica, sans-serif; font-size: 14px;">menor consumo de energía</strong><span style="font-family: arial, helvetica, sans-serif; font-size: 14px;"> ya que el móvil no necesitará demasiada potencia para realizar sus transmisiones. Por otro lado, al implementarse en escenarios residenciales, la cantidad de usuarios es poca y es posible compartir más recursos </span><strong style="font-family: arial, helvetica, sans-serif; font-size: 14px;"><span style="color:#ff8c00;">[4]</span></strong><span style="font-family: arial, helvetica, sans-serif; font-size: 14px;">.</span></p>
<p>
&nbsp;</p>
<p>
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;">La <span style="color:#0000ff;"><strong>Figura # 2</strong></span> muestra dos escenarios: en a) se muestra una <strong>macrocelda tradicional</strong> donde un eNodeB brinda cobertura a un área particular, si se analiza el caso de dos UE's que se encuentran a la misma distancia del eNodeB, con la diferencia de que uno de ellos se encuentra al aire libre (UE1) y el otro dentro de un casa de habitación (UE4), este último tendrá más <strong>pérdidas debido a la penetración en la vivienda</strong>. Por otro lado, en b) se plantea la implementación de <strong>dos femtoceldas</strong> una en cada vivienda <strong>aumentando la calidad de la señal dentro del inmueble, y en consecuencia el throughput y la calidad del servicio brindado</strong>.</span></span></p>
<p>
&nbsp;</p>
<p style="text-align: center;">
<img alt="" src="images/TICs/interaccion-de-macroceldas-y-femtoceldas/propagacion_2.jpg" /></p>
<p style="text-align: center;">
<span style="font-family: arial, helvetica, sans-serif; font-size: 14px; color: rgb(0, 0, 255);"><strong>Figura # 2</strong></span><span style="font-family: arial, helvetica, sans-serif; font-size: 14px;">: a) Macro-celda tradicional; b) Interacción de macro-celda con femto-celdas </span><strong style="font-family: arial, helvetica, sans-serif; font-size: 14px;"><span style="color:#ff8c00;">[2]</span></strong><span style="font-family: arial, helvetica, sans-serif; font-size: 14px;">.</span></p>
<p style="text-align: center;">
&nbsp;</p>
<p>
<span style="font-family: arial, helvetica, sans-serif; font-size: 14px; color: rgb(68, 68, 68);">Referencias</span></p>
<ol>
<li>
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;">G. de la Roche, A. Valcarce, D. Lopez-Perez, Jie Zhang. Access control Mechanisms for Femtocells. Communications Magazine, IEEE, vol. 48, no. 1, pp. 33-39, 2010.</span></span></li>
<li>
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;">D. Calin, H. Claussen, H. Uzunalioglu. On Femto Deployment Architectures and Macrocell Offloading Benefits in Joint Macro-Femto Deployments. Communications Magazine, IEEE, vol. 48, no. 1, pp. 26-32, 2010.</span></span></li>
<li>
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;"><a href="http://www.femtoforum.org/">http://www.femtoforum.org</a></span></span></li>
<li>
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;">Vikram Chandrasekhar, Jeffrey G. Andrews, Alan Gatherer. Femtocell Networks: A Survey. Communications Magazine, IEEE, vol. 46, no. 9, pp. 59-67, 2008.</span></span></li>
</ol>
<p>
&nbsp;</p>