---
layout: post
title:  Ataque criptográfico contra AES Impossible Differential Attack
date:   2014-02-20 06:00:00
description: Hace algún tiempo leí un artículo interesante de un “ataque exitoso” contra AES, el famoso algoritmo de criptografía simétrica. Raphael C.-W. Phan presentó un “impossible differential attack” a 7 rondas para AES-192 y AES-256. Algunos se preguntarán que tipo de ataque es este?, pues bien, es un criptoanálisis que se aprovecha de las diferencias que son imposible de darse, de un bloque de datos a través del cifrado, con la finalidad de descubrir la clave. Sin entrar en muchos detalles del método utilizado, a continuación comento algunos de los resultados más importantes de dicho estudio.
tags: AES criptografía seguridad criptografía-simétrica ataque
categories: Research
---
<p>
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;">Hace alg&uacute;n tiempo le&iacute; un art&iacute;culo interesante de un <strong>&ldquo;ataque exitoso&rdquo; contra AES</strong>, el famoso algoritmo de criptograf&iacute;a sim&eacute;trica. Raphael C.-W. Phan <span style="color:#ff8c00;"><strong>[1]</strong></span> present&oacute; un <strong>&ldquo;impossible differential attack&rdquo;</strong> a 7 rondas para AES-192 y AES-256. Algunos se preguntar&aacute;n: que tipo de ataque es este?, pues bien, <strong>es un criptoan&aacute;lisis que se aprovecha de las diferencias que son imposible de darse</strong>, de un bloque de datos a trav&eacute;s del cifrado, con la finalidad de descubrir la clave. Sin entrar en muchos detalles del m&eacute;todo utilizado, a continuaci&oacute;n comento algunos de los resultados m&aacute;s importantes de dicho estudio.</span></span></p>
<p>
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;">El ataque consiste en tomar parejas de textos id&eacute;nticos en todos los bytes excepto en uno y comenzar a cifrar dichos textos, luego, se analizan los datos producidos a las salidas de cada una de las rondas con la finalidad de observar la evoluci&oacute;n de la informaci&oacute;n durante el proceso de cifrado. Con esta informaci&oacute;n se van asignando las probabilidades para las claves imposibles o de probabilidad de 0.</span></span></p>
<p>
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;">El ataque se basa en el algoritmo expuesto en <span style="color:#ff8c00;"><strong>[1]</strong></span>, que es utilizado para romper AES-192 y AES-256, consta de 9 pasos a seguir y se concentra en el sistema de expansi&oacute;n de claves. El algoritmo permite realizar ciertos c&aacute;lculos y asignar probabilidades en el momento que se ha determinado alguna de las subclaves. En resumen, <strong>el autor espera determinar la clave en la s&eacute;ptima ronda, con el modelo matem&aacute;tico expuesto en dicho estudio</strong>, mediante la observaci&oacute;n de los movimientos realizados por las diferentes transformaciones.</span></span></p>
<p>
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;">Resumiendo los resultados obtenidos en <span style="color:#ff8c00;"><strong>[1]</strong></span>, para el caso de AES-192, se requiri&oacute; de 2<sup>92</sup> textos en claro, 2<sup>153</sup> palabras de memoria y 2<sup>186</sup> encripciones, para el caso de AES-256 los textos en claro fueron 2<sup>92,5</sup>, el mismo espacio de memoria 2<sup>153</sup> y 2<sup>250,5</sup> encripciones. La <span style="color:#0000ff;"><strong>Tabla # 1</strong></span> muestra una comparaci&oacute;n entre los resultados presentados por <span style="color:#ff8c00;"><strong>[1]</strong></span> y otros dos ataques anteriores con menor cantidad de rondas.</span></span></p>
<p>
&nbsp;</p>
<p style="text-align: center;">
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;"><img alt="" src="images/Research/ataque-criptografico-aes-impossible-differential-attack/1.png" style="height: 163px; width: 500px;" /></span></span></p>
<p style="text-align: center;">
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;"><span style="color: rgb(0, 0, 255);"><strong>Tabla # 1</strong></span>: Comparaci&oacute;n de los resultados a ataques a AES <span style="color: rgb(255, 140, 0);"><strong>[1]</strong></span>.</span></span></p>
<p style="text-align: center;">
&nbsp;</p>
<p>
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;">Dejando de lado el proceso como tal, y analizando los resultados obtenidos en dicho ataque, se puede apreciar que para romper el algoritmo se han necesitado 2<sup>186</sup> y 2<sup>250,5</sup> encripciones para AES-192 y AES-256 respectivamente. Si se toma en cuenta que una b&uacute;squeda exhaustiva de clave hubiera tomado 2<sup>192</sup> y 2<sup>256</sup> para cada uno de los algoritmos respectivamente, se podr&iacute;a decir que el ataque presentado por <span style="color:#ff8c00;"><strong>[1]</strong></span> <strong>ha sido exitoso</strong>.</span></span></p>
<p>
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;">Ahora, <strong>es importante aclarar que se trata de un ataque a rondas reducidas (7 rondas)</strong> y que AES puede tener una longitud de clave de 128, 192 o 256 bits seg&uacute;n sea el caso, para la cantidad de rondas est&aacute;ndar: 10, 12 y 14 respectivamente. Esto significa, que pese al ataque exitoso que se presenta, <strong>AES mantiene un margen de seguridad bastante amplio con respecto a este estudio</strong>, porque hay 5 rondas de diferencia (para AES-192) y por lo tanto, <strong>la complejidad para descifrar un paquete de informaci&oacute;n se incrementa al aplicar la cantidad de vueltas que define el est&aacute;ndar</strong>.</span></span></p>
<p>
&nbsp;</p>
<h1>
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;">Referencias</span></span></h1>
<ol>
<li>
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;">Raphael CP. Impossible differential cryptanalysis of 7-round Advanced Encryption Standard (AES). Information Processing Letters (2004) 91: pp. 33-38.</span></span></li>
</ol>
