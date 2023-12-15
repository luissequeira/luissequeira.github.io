---
layout: post
title:  Generalidades de AES (Advanced Encryption Standard) I Parte
date:   2014-01-30 06:00:00
description: El algoritmo AES (Advanced Encryption Standard), conocido como Rijndael, fue nombrado así por sus creadores Joan Daemen y Vincent Rijmen, es el actual estándar internacional de cifrado para comunicaciones desde octubre del 2000. Dicho algoritmo se caracteriza por ser un cifrado simétrico por bloques con longitud de clave variable; la longitud de la clave por defecto es de 128 bits pero también puede establecerse a 192 o 256 bits.
tags: AES seguridad criptografía criptografía-simétrica algoritmo
categories: Security
---
<p>
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;"><strong>El algoritmo AES (Advanced Encryption Standard)</strong> <span style="color:#ff8c00;"><strong>[1]</strong></span>, conocido como Rijndael, fue nombrado así por sus creadores Joan Daemen y Vincent Rijmen, <strong>es el actual estándar internacional de cifrado para comunicaciones desde octubre del 2000</strong>. Dicho algoritmo se caracteriza por ser un <strong><a href="http://www.telecomsharing.com/es/biblioteca/seguridad/item/51-los-dos-pilares-de-un-algoritmo-de-criptografia-simetrica">cifrado simétrico por bloques</a> con longitud de clave variable</strong>; la longitud de la clave por defecto es de 128 bits pero también puede establecerse a 192 o 256 bits.</span></span></p>

<p>
<span style="font-family: arial, helvetica, sans-serif; font-size: 14px; line-height: 24px;">El funcionamiento de dicho algoritmo puede separarse en dos partes o procesos diferentes, <strong>el primero, sería el proceso de cifrado y el segundo correspondiente al proceso de generación de subclaves</strong>, la <span style="color:#0000ff;"><strong>Figura # 1</strong></span> muestra la interacción de ambos procesos.</span></p>
<p style="text-align: center;">
&nbsp;</p>
<p style="text-align: center;">
<img alt="" src="images/TICs/generalidades-aes-parte-1/1.png" style="width: 343.9772644042969px; height: 518.991455078125px;" /></p>
<p style="text-align: center;">
<span style="font-family: arial, helvetica, sans-serif; font-size: 14px; line-height: 24px; color: rgb(0, 0, 255);"><strong>Figura # 1</strong></span><span style="font-family: arial, helvetica, sans-serif; font-size: 14px; line-height: 24px;">: Cifrado con AES.</span></p>
<p style="text-align: center;">
&nbsp;</p>
<p>
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;">El bloque a cifrar tiene una longitud de 128 bit, mientras que la clave puede variar de 128, 192 o 256 bits, según la cantidad de rondas estándar que se apliquen al texto 10, 12 y 14 respectivamente <span style="color:#ff8c00;"><strong>[2]</strong></span>. En general, el cifrado de AES está descrito por cuatro funciones básicas o también <strong>llamadas transformaciones</strong>, estas son:</span></span></p>
<ul>
<li>
<strong><span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;">ByteSub</span></span></strong></li>
<li>
<strong><span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;">ShiftRow</span></span></strong></li>
<li>
<strong><span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;">MixColumns</span></span></strong></li>
<li>
<strong><span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;">AddRoundKey</span></span></strong></li>
</ul>
<p>
<span style="font-family: arial, helvetica, sans-serif; font-size: 14px; line-height: 24px;">Las rondas a las que se somete el texto se pueden dividir en tres categorías: <strong>ronda inicial, rondas estándar y ronda final</strong>. Cada una de estas rondas se compone de alguna o varias combinaciones de las transformaciones antes mencionadas (ver <span style="color:#0000ff;"><strong>Figura # 1</strong></span>). Los diferentes tipos de rondas difieren entre sí por la combinación de las transformaciones que se aplican al bloque que se desea cifrar.</span></p>
<p>
<span style="font-family: arial, helvetica, sans-serif; font-size: 14px; line-height: 24px;">AES interpreta los bloque de entrada de 128 bits, como una matriz 4x4 de entradas de bytes <span style="color:#ff8c00;"><strong>[3]</strong></span>, si el bloque es de 192 bits se agregan 2 columnas, si es de 256 se agregan 4 columnas, a dichas matrices se les llama <strong>matrices de estado</strong> y su forma es como se muestra a continuación:</span></p>
<p>
&nbsp;</p>
<p style="text-align: center;">
<img alt="" src="images/TICs/generalidades-aes-parte-1/2.png" style="height: 517px; width: 500px;" /></p>
<p>
&nbsp;</p>
<h1>
<span style="font-family: arial, helvetica, sans-serif; font-size: 14px; color: rgb(68, 68, 68); line-height: 24px;">S-Box</span></h1>
<p>
<span style="font-family: arial, helvetica, sans-serif; font-size: 14px; line-height: 24px;">Básicamente, <strong>una S-Box (substitution box) es una matriz para sustitución de valores, utilizado por los algoritmos de cifrado de clave simétrica</strong>. Las S-Boxes son seleccionadas cuidadosamente para ser resistentes al criptoanálisis. En el caso de AES, dicha matriz es el resultado de aplicar dos funciones a la matriz de estado, <em>[a<sub>ij</sub>]</em>, en primer lugar su inverso multiplicativo&nbsp;</span><em style="line-height: 24px; font-family: arial, helvetica, sans-serif; font-size: 13.63636302947998px;">[a<sub>ij</sub>]</em><span style="font-family: arial, helvetica, sans-serif; font-size: 14px; line-height: 24px;">&nbsp;a&nbsp;</span><em style="line-height: 24px; font-family: arial, helvetica, sans-serif; font-size: 13.63636302947998px;">a<sub>ij</sub><sup>-1&nbsp;</sup>E GF(2<sup>8</sup>)</em><span style="font-family: arial, helvetica, sans-serif; font-size: 14px; line-height: 24px;">&nbsp;y posteriormente una transformación lineal:</span></p>
<ol>
<li>
<span style="font-family: arial, helvetica, sans-serif; font-size: 14px; line-height: 24px;">Todo byte puede verse como un elemento del cuerpo finito&nbsp;<em>GF(2<sup>8</sup>)</em>, como todo elemento tiene inverso multiplicativo, se asocia el inverso multiplicativo en&nbsp;<em>GF(2<sup>8</sup>)</em>, es decir&nbsp;<em style="line-height: 24px;">[a<sub>ij</sub>]</em>&nbsp;a&nbsp;<em style="line-height: 24px;">a<sub>ij</sub><sup>-1&nbsp;</sup>E GF(2<sup>8</sup>)</em>, al elemento cero se le asocia el mismo cero.</span></li>
<li>
<span style="font-family: arial, helvetica, sans-serif; font-size: 14px; line-height: 24px;">La transformación lineal se aplica bit por bit con la siguiente regla: transformación lineal en&nbsp;<em>GF(2<sup>8</sup>)</em><em>→GF(2<sup>8</sup>)</em>.</span></li>
</ol>
<p style="text-align: center;">
<img alt="" src="images/TICs/generalidades-aes-parte-1/3.png" style="width: 375.9942932128906px; height: 55.99431610107422px;" /></p>
<p>
<span style="font-family: arial, helvetica, sans-serif; font-size: 14px; line-height: 24px;">en bits queda:</span></p>
<p style="text-align: center;">
<img alt="" src="images/TICs/generalidades-aes-parte-1/4.png" style="width: 244.99998474121094px; height: 221.98863220214844px;" /></p>
<p>
<span style="font-family: arial, helvetica, sans-serif; font-size: 14px; line-height: 24px;"><strong>Esta es la operación más costosa, en cuanto a tiempo se refiere, del algoritmo AES</strong>, por esto, la operación es precalculada. Finalmente, este proceso puede resumirse en la siguiente tabla conocida como S-Box </span><span style="font-family: arial, helvetica, sans-serif; font-size: 14px; line-height: 24px; color: rgb(255, 140, 0);"><strong>[3]</strong></span><span style="font-family: arial, helvetica, sans-serif; font-size: 14px; line-height: 24px;"> que puede ser utilizada para un byte cualquiera <em>xy</em>.</span></p>
<p>
&nbsp;</p>
<p style="text-align: center;">
<img alt="" src="images/TICs/generalidades-aes-parte-1/5.png" style="height: 325px; width: 500px;" /></p>
<p style="text-align: center;">
<span style="font-family: arial, helvetica, sans-serif; font-size: 14px; line-height: 24px; color: rgb(0, 0, 255);"><strong>Tabla # 1</strong></span><span style="font-family: arial, helvetica, sans-serif; font-size: 14px; line-height: 24px;">: S-Box para el cifrado.</span></p>
<p style="text-align: center;">
&nbsp;</p>
<p>
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;">Por otro lado, para el proceso de descifrado se calcula una tabla inversa a la utilizada en el proceso de cifrado, dicha tabla es:</span></span></p>
<p>
&nbsp;</p>
<p style="text-align: center;">
<img alt="" src="images/TICs/generalidades-aes-parte-1/6.png" style="height: 322px; width: 500px;" /></p>
<p style="text-align: center;">
<span style="font-family: arial, helvetica, sans-serif; font-size: 14px; line-height: 24px; color: rgb(0, 0, 255);"><strong>Tabla # 2</strong></span><span style="font-family: arial, helvetica, sans-serif; font-size: 14px; line-height: 24px;">: S-Box para el descifrado.</span></p>
<p style="text-align: center;">
&nbsp;</p>
<h1>
<font face="arial, helvetica, sans-serif" size="2">Referencias</font></h1>
<div dir="LTR" id="Bibliografía1">
<ol>
<li>
<span style="font-size: 14px;"><span style="font-family: arial, helvetica, sans-serif;">Joan Daemen VR. AES Proposal: Rijndael. NIST AES Proposal (1998)</span></span></li>
<li>
<span style="font-size: 14px;"><span style="font-family: arial, helvetica, sans-serif;">J A. AES - Advanced Encryption Standard. (2005) Versión 2005</span></span></li>
<li>
<span style="font-size: 14px;"><span style="font-family: arial, helvetica, sans-serif;">A M. Seguridad Europea para EEUU Algoritmo criptográfico Rijndael. Madrid (2004)</span></span></li>
<li>
<a href="http://www.formaestudio.com/rijndaelinspector/" style="font-family: arial, helvetica, sans-serif; line-height: 24px; font-size: 13px;">http://www.formaestudio.com/rijndaelinspector/</a></li>
<li>
<span style="font-size: 14px;"><span style="font-family: arial, helvetica, sans-serif;"><a href="http://www.cryptosystem.net/aes/" style="font-size: 13px; line-height: 24px;">http://www.cryptosystem.net/aes/</a></span></span></li>
<li>
<span style="font-size: 14px;"><span style="font-family: arial, helvetica, sans-serif;"><a href="http://www.criptored.upm.es/" style="font-size: 13px; line-height: 24px;">http://www.criptored.upm.es</a></span></span></li>
<li>
<span style="font-size: 14px;"><span style="font-family: arial, helvetica, sans-serif;"><a href="http://www.kriptopolis.es/" style="font-size: 13px; line-height: 24px;">http://www.kriptopolis.es</a></span></span></li>
</ol>
</div>