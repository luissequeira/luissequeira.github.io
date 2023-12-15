---
layout: post
title:  Ataque contra AES Omisión de MixColumns
date:   2014-03-13 06:00:00
description: Un estudio reciente realizado por Orr Dunkelman y Nathan Keller, muestra que si se ve comprometida la seguridad por la omisión de dicha transformación. Los resultados obtenidos reflejan que en el caso del análisis omitiendo MixColumns se reduce la complejidad del algoritmo por un factor de 2^16. 
tags: ataque AES seguridad
categories: Research
---
<p>
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;">Como se ha mencionado en un <a href="es/biblioteca/seguridad/item/55-generalidades-de-aes-advanced-encryption-standard-i-parte">art&iacute;culo anterior</a>, las rondas que componen el algoritmo AES se pueden dividir en <strong>tres categor&iacute;as diferentes: rondas inicial, ronda est&aacute;ndar y ronda final</strong>. A la hora del cifrado, la informaci&oacute;n es sometida a una cantidad diferente de rondas (10, 12 y 14 respectivamente) en cada caso en funci&oacute;n de la longitud de la clave (128, 192 y 256 bits respectivamente). Cada una de dichas rondas se compone de combinaciones de transformaciones, las posibles transformaciones son: ByteSub, ShiftRow, MixColumns y AddRoundKey. La <span style="color:#0000ff;"><strong>Figura # 1</strong></span> muestra la relaci&oacute;n de las transformaciones y las correspondientes rondas.</span></span></p>
<p>
&nbsp;</p>
<p style="text-align: center;">
<img alt="" src="images/Research/ataque-contra-AES-omision-mixcoloumns/1_es.png" style="height: 500px; width: 500px;" /></p>
<p style="text-align: center;">
<span style="font-family: arial, helvetica, sans-serif; font-size: 14px; color: rgb(0, 0, 255);"><strong>Figura # 1</strong></span><span style="font-family: arial, helvetica, sans-serif; font-size: 14px;">: Distribuci&oacute;n de las transformaciones en cada ronda.</span></p>

<p>
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;">Como se puede observar en la <span style="color:#0000ff;"><strong>Figura # 1</strong></span>, en el algoritmo original, <strong>la ronda final difiere de las rondas est&aacute;ndares por la omisi&oacute;n de la transformaci&oacute;n MixColumns, adem&aacute;s, la ronda inicial est&aacute; compuesta solamente por la transformaci&oacute;n AddRoundKey</strong>. En relaci&oacute;n a estas dos variantes en las rondas inicial y final, con respecto las rondas est&aacute;ndares, los autores de AES Joan Daemen y Vincent Rijmen mencionan que las han propuesto con la finalidad de guardar la simetr&iacute;a entre la cifrado y descifrado, como ellos mismos mencionan <span style="color:#ff8c00;"><strong>[1]</strong></span>:</span></span></p>
<p>
&nbsp;</p>
<p>
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;">&ldquo;In order to make the cipher and its inverse more similar in structure, the linear mixing layer of the last round is different from the mixing layer in the other rounds. It can be shown that this does not improve or reduce the security of the cipher in any way. This is similar to the absence of the swap operation in the last round of the DES.&rdquo;</span></span></p>
<p>
&nbsp;</p>
<p>
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;">Com&uacute;nmente se sabe y los mismos autores lo afirman en la cita anterior, que la omisi&oacute;n de MixColumns no afecta o reduce la seguridad del cifrado, sin embargo, <strong>un estudio reciente realizado por Orr Dunkelman y Nathan Keller <span style="color:#ff8c00;">[2]</span>, muestra que si se ve comprometida la seguridad por la omisi&oacute;n de dicha transformaci&oacute;n</strong>.</span></span></p>
<p>
<span style="font-family: arial, helvetica, sans-serif; font-size: 14px;">Dicho estudio, toma un texto en claro con su correspondiente cifrado para el an&aacute;lisis (para el caso m&aacute;s simple de una sola ronda) omitiendo MixColumns y lo compara con otro ataque realizado donde no ha sido omitida esta transformaci&oacute;n. <strong>Los resultados obtenidos reflejan que en el caso del an&aacute;lisis omitiendo MixColumns se reduce la complejidad del algoritmo por un factor de 2</strong></span><strong><sup style="font-family: arial, helvetica, sans-serif;">16</sup></strong><span style="font-family: arial, helvetica, sans-serif; font-size: 14px;">. Este mismo m&eacute;todo se aplic&oacute; al <a href="es/laboratorio/resultados/item/63-ataque-criptografico-contra-aes-impossible-differential-attack">ataque propuesto por Raphael C.-W. Phan </a></span><a href="es/laboratorio/resultados/item/63-ataque-criptografico-contra-aes-impossible-differential-attack"><span style="font-family: arial, helvetica, sans-serif; font-size: 14px; color: rgb(255, 140, 0);"><strong>[3]</strong></span></a><span style="font-family: arial, helvetica, sans-serif; font-size: 14px;"><a href="es/laboratorio/resultados/item/63-ataque-criptografico-contra-aes-impossible-differential-attack"> (comentado con anterioridad)</a> obteniendo los mismos resultados para ese ataque a 7 rondas con una longitud de la clave de 192 bits.</span></p>
<p>
<span style="font-family: arial, helvetica, sans-serif; font-size: 14px;">Por otro lado, las observaciones obtenidas en <span style="color:#ff8c00;"><strong>[2]</strong></span>, <strong>parecen no aplicarse para cualquier tipo de ataque, siendo algunos de ellos inmunes, en la reducci&oacute;n de la complejidad, a la omisi&oacute;n de la transformaci&oacute;n de MixColumns en la ronda final de AES</strong>. Pese a esto, los autores afirma que la seguridad de AES se ve afectada por la omisi&oacute;n de MixColumns para los ataques donde se utiliza una reducci&oacute;n de la cantidad de rondas est&aacute;ndares, y por lo tanto, el algoritmo completo tambi&eacute;n podr&iacute;a verse afectado.</span></p>
<p>
<span style="font-family: arial, helvetica, sans-serif; font-size: 14px;">Es importante aclarar que el ataque presentado se trata de un <strong>ataque a rondas reducidas (7 rondas)</strong>. Esto significa, que pese al ataque exitoso que plantean los autores, AES mantiene un margen de seguridad bastante amplio con respecto a este estudio.</span></p>
<p>
&nbsp;</p>
<h1>
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;">Referencias</span></span></h1>
<ol>
<li>
<span style="font-family: arial, helvetica, sans-serif; font-size: 14px;">Joan Daemen VR. AES Proposal: Rijndael. NIST AES Proposal (1998).</span></li>
<li>
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;">Orr Dunkelman NK. The effects of the omission of last round&rsquo;s MixColumns on AES. Information Processing Letters (2010) 110: pp. 304-308.</span></span></li>
<li>
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;">Raphael CP. Impossible differential cryptanalysis of 7-round Advanced Encryption Standard (AES). Information Processing Letters (2004) 91: pp. 33-38.</span></span></li>
</ol>