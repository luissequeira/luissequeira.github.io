---
layout: post
title:  Los métodos de acceso a las femtoceldas
date:   2014-05-08 05:00:00
description: Las femtoceldas pueden operar básicamente de tres modos diferentes acceso abierto, acceso cerrado y una combinación de los anteriores denominado acceso híbrido, a continuación se explican cada uno de los modelos de acceso
tags: 4G femtoceldas red-de-acceso
categories: QoS
---
<p>
<span style="font-family: arial, helvetica, sans-serif; font-size: 14px;"><strong>Las femtoceldas son estaciones base de baja potencia y bajo costo</strong> que proveen servicios celulares a nivel residencial, ofrecen una cobertura de aproximadamente 10 m <span style="color:#ff8c00;"><strong>[1]</strong></span>. Se integra con el operador m&oacute;vil mediante una <strong>conexi&oacute;n de banda ancha</strong>, t&iacute;picamente ADSL. En General, la femtocelda hace que el tr&aacute;fico del sistema celular proveniente del hogar, <strong>se desv&iacute;e por la conexi&oacute;n de banda ancha</strong>, liberando el consumo de recursos de la macrocelda.</span></p>
<p>
<span style="font-family: arial, helvetica, sans-serif; font-size: 14px;">El 3GPP ha introducido el concepto de Closed Subscriber Group (CSG), que en esencia identifica a un grupo de suscriptores que tienen <strong>permiso de acceso a una o varias celdas</strong>. Las femtoceldas pueden operar b&aacute;sicamente de tres modos diferentes: <strong>acceso abierto, acceso cerrado y una combinaci&oacute;n de los anteriores denominado acceso h&iacute;brido</strong> <span style="color:#ff8c00;"><strong>[2]</strong></span> y <span style="color:#ff8c00;"><strong>[3]</strong></span>, a continuaci&oacute;n se explican cada uno de los modelos de acceso:</span></p>
<ul>
<li>
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;"><strong>Acceso abierto:</strong> En este caso, el UE puede tener acceso a la femtocelda sin ning&uacute;n tipo de restricci&oacute;n, esto se aprecia en la <span style="color:#0000ff;"><strong>Figura # 1</strong></span> donde el UE2 tiene acceso sin restricci&oacute;n a la femtocelda en el edificio.</span></span></li>
<li>
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;"><strong>Acceso cerrado:</strong> El administrador de la femtocelda define los &uacute;nicos usuarios (CSG) que pueden tener acceso a la red. Para este modo, se except&uacute;an las llamadas de emergencia.</span></span></li>
<li>
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;"><strong>Acceso h&iacute;brido:</strong> En este tipo de acceso, una cantidad limitada de recursos es asignada para permitir acceso a usuarios que no forman parte del CSG.</span></span></li>
</ul>
<p style="text-align: center;">
<img alt="" src="images/TICs/metodos-acceso-femtoceldas/1.png" style="height: 317px; width: 500px;" /></p>
<p style="text-align: center;">
<span style="font-family: arial, helvetica, sans-serif; font-size: 14px; color: rgb(0, 0, 255);"><strong>Figura # 1</strong></span><span style="font-family: arial, helvetica, sans-serif; font-size: 14px;">. Ejemplo de diversos m&eacute;todos de acceso a femto-celdas </span><span style="font-family: arial, helvetica, sans-serif; font-size: 14px; color: rgb(255, 140, 0);"><strong>[2]</strong></span><span style="font-family: arial, helvetica, sans-serif; font-size: 14px;">: acceso abierto, acceso cerrado y acceso h&iacute;brido.</span></p>

<p>
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;">La <span style="color:#0000ff;"><strong>Figura # 1</strong></span> es un ejemplo de los diversos tipos de acceso a la femtoceldas definidos por el 3GPP. <strong>El acceso cerrado brinda los servicios contratados a los usuarios que forman parte del CSG</strong>, brindando cierto nivel de seguridad y privacidad en el acceso a la femtocelda,adem&aacute;s, que todos los recursos de la femtocelda est&aacute;n a disposici&oacute;n del usuario garantizando la QoS (en cierta medida). Sin embargo, los que no forman parte de este grupo de suscriptores no pueden tener acceso a la red, excepto para llamadas de emergencia. Este tipo de acceso genera m&aacute;s interferencia ya que los m&oacute;viles cercanos tratan de conectarse a una femtocelda, pero el m&eacute;todo de acceso los bloquea, por lo que se genera una gran cantidad de se&ntilde;alizaci&oacute;n impl&iacute;cita en dicha &aacute;rea.</span></span></p>
<p>
<span style="font-family: arial, helvetica, sans-serif; font-size: 14px;">Por otro lado,<strong> el acceso abierto presenta una buena ventaja para el proveedor de servicios ya que parte del tr&aacute;fico se desv&iacute;a por las femtoceldas, liberando en buena medida, la carga de la macrocelda</strong>. Sin embargo, este tipo de implementaci&oacute;n provee un incremento en el handover, debido a que un UE que se desplaza por una localidad donde hay diversas femtoceldas implementadas, realizar&aacute; traspasos en cada femtocelda donde encuentre mejor calidad de la se&ntilde;al, incrementando as&iacute; el tr&aacute;fico de se&ntilde;alizaci&oacute;n. Desde esta perspectiva <strong>el m&eacute;todo h&iacute;brido puede presentar ciertas ventajas, pero los recursos compartidos por cada femtocelda deben ser administrados con mucho cuidado</strong> con la finalidad de no degradar la calidad de servicio de los usuarios de la femtocelda.</span></p>
<p>
&nbsp;</p>
<h1>
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;">Referencias</span></span></h1>
<ol>
<li>
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;">D. Calin, H. Claussen, H. Uzunalioglu. On Femto Deployment Architectures and Macrocell Offloading Benefits in Joint Macro-Femto Deployments. Communications Magazine, IEEE, vol. 48, no. 1, pp. 26-32, 2010.</span></span></li>
<li>
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;">Assen, Golaup;Mona, Mustapha;Leo, Boonchin Patanapogpibul, Femtocell Access Control Strategy in UMTS and LTE, 2009.</span></span></li>
<li>
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;">G, de la Roche;A, Valcarce;D, Lopez-Perez;Jie, Zhang, Access control Mechanisms for Femtocells, 2010.</span></span></li>
<li>
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;"><a href="http://www.femtoforum.org/">http://www.femtoforum.org</a></span></span></li>
<li>
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;">http://www.3gpp.org/</span></span></li>
</ol>