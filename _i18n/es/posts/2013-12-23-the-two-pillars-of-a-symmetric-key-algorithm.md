---
layout: post
title:  Los dos pilares de un algoritmo de criptografía simétrica
date:   2013-12-26 06:00:00
description: Para que un algoritmo de criptografía simétrica sea robusto pueda considerarse como seguro, es necesario que haya sido sometido al análisis por la comunidad científica en esta área, de esta manera se podría dar evidencia de que es inmune a los ataque más conocidos. En general, se puede decir que un algoritmo de este tipo debe tener en cuenta dos pilares fundamentales
tags: criptografía AES criptografía-simétrica algoritmo seguridad
categories: Security
---
<p style="margin-bottom: 0in">
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;">La <b>criptografía simétrica</b>, o también llamada criptografía de clave secreta, <b>es un método criptográfico que utiliza la misma clave para cifrar como para descifrar</b>, es decir, que la seguridad del algoritmo se basa en la clave y no en el algoritmo. Algunos ejemplos de algoritmos criptográficos de este tipo son: AES, DES, 3DES y RC5.</span></span></p>

<p style="margin-bottom: 0in">
<span style="font-family: arial, helvetica, sans-serif; font-size: 14px; line-height: 24px;">Es claro que todo algoritmo puede ser roto, ya sea por los métodos comúnmente conocidos, o bien, por algún nuevo ataque. El ataque más básico y que comúnmente se utiliza como referencia para realizar comparaciones entre diversa técnicas de criptoanálisis es el </span><b style="font-family: arial, helvetica, sans-serif; font-size: 14px; line-height: 24px;">ataque a fuerza bruta o búsqueda exhaustiva de clave</b><span style="font-family: arial, helvetica, sans-serif; font-size: 14px; line-height: 24px;">. Es básicamente, un </span><b style="font-family: arial, helvetica, sans-serif; font-size: 14px; line-height: 24px;">método de prueba y error de todas las posibles claves</b><span style="font-family: arial, helvetica, sans-serif; font-size: 14px; line-height: 24px;">, consiste en que el atacante conoce el algoritmo, posee un texto en claro y su correspondiente cifrado; al texto lo cifra probando cada una de las posibles claves hasta obtener su correspondiente texto cifrado, o bien, en sentido inverso respectivamente. Es de esperarse que dicho método sea </span><b style="font-family: arial, helvetica, sans-serif; font-size: 14px; line-height: 24px;">el más costoso en recursos computacionales y en tiempo</b><span style="font-family: arial, helvetica, sans-serif; font-size: 14px; line-height: 24px;">. Si una clave tiene una longitud de <em>n</em> bits, la cantidad de posibles combinaciones de clave será de <em>2<sup>n</sup></em> y por lo tanto se requerirá de <em>2<sup>n</sup>-1</em> pruebas de claves, suponiendo que la clave correcta será la última.</span></p>
<p style="margin-bottom: 0in">
<span style="font-family: arial, helvetica, sans-serif; font-size: 14px; line-height: 24px;">Para que un algoritmo de criptografía simétrica sea robusto pueda considerarse como seguro, </span><b style="font-family: arial, helvetica, sans-serif; font-size: 14px; line-height: 24px;">es necesario que haya sido sometido al análisis por la comunidad científica en esta área</b><span style="font-family: arial, helvetica, sans-serif; font-size: 14px; line-height: 24px;">, de esta manera se podría dar evidencia de que es inmune a los ataque más conocidos. En general, se puede decir que un </span><b style="font-family: arial, helvetica, sans-serif; font-size: 14px; line-height: 24px;">algoritmo de este tipo debe tener en cuenta dos pilares fundamentales</b><span style="font-family: arial, helvetica, sans-serif; font-size: 14px; line-height: 24px;">:</span></p>
<p style="margin-bottom: 0in">
&nbsp;</p>
<ol>
<li>
<p style="margin-bottom: 0in">
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;"><b>La no linealidad entre las entradas y las salidas</b>, o la correlación de las entradas con las salidas.</span></span></p>
</li>
<li>
<p style="margin-bottom: 0in">
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;"><b>La propagación de las diferencias de los bits</b>, o el medir la probabilidad de que tanto se confunden los bits.</span></span></p>
</li>
</ol>
<p style="margin-bottom: 0in">
&nbsp;</p>
<p style="margin-bottom: 0in">
<span style="font-family: arial, helvetica, sans-serif; font-size: 14px; line-height: 24px;">El primer punto se refiere a que </span><b style="font-family: arial, helvetica, sans-serif; font-size: 14px; line-height: 24px;">el algoritmo debe ser inmune al criptoanálisis lineal</b><span style="font-family: arial, helvetica, sans-serif; font-size: 14px; line-height: 24px;">, es decir, que </span><b style="font-family: arial, helvetica, sans-serif; font-size: 14px; line-height: 24px;">no debe haber dependencia lineal entre la entrada y la salida del algoritmo</b><span style="font-family: arial, helvetica, sans-serif; font-size: 14px; line-height: 24px;">, como por ejemplo, sea <em>f</em> la función de salida y <em>h</em> la de entrada, si la información de entrada es 1,2,3,4 y la salida es 5, 10, 15, 20, claramente se deduce que la relación es <em>f(x)=5h(x)</em>, de tal manera no será muy difícil deducir cual es la información contenida en algún tipo de mensaje cifrado con <em>f</em>.</span></p>
<p style="margin-bottom: 0in">
<span style="font-family: arial, helvetica, sans-serif; font-size: 14px; line-height: 24px;">El segundo punto se refiere a que </span><b style="font-family: arial, helvetica, sans-serif; font-size: 14px; line-height: 24px;">el algoritmo debe soportar un criptoanálisis diferencial</b><span style="font-family: arial, helvetica, sans-serif; font-size: 14px; line-height: 24px;">, que es un análisis del tipo “Chosen Plaintext Attack”, el cual consiste en un ataque donde el atacante puede escoger los textos en claro y después obtener sus correspondientes textos cifrados utilizando la misma clave, para luego </span><b style="font-family: arial, helvetica, sans-serif; font-size: 14px; line-height: 24px;">realizar comparaciones y pequeñas variaciones en los textos y poder así ir deduciendo las diferencias de los textos cifrados</b><span style="font-family: arial, helvetica, sans-serif; font-size: 14px; line-height: 24px;">, con esto, se puede ir asignado probabilidades para las posibles claves, analizando cada estado intermedio dentro de cada una de las rondas. También, existe una variante de este tipo de criptoanálisis denominado ataque de diferencial imposible, en este caso se busca diferencias entre pares de textos en claro, que se mantienen con cierta probabilidad en las diferencias correspondientes de los textos cifrados que no pueden ocurrir.</span></p>
<p align="JUSTIFY" style="margin-bottom: 0in;">
<span style="color: rgb(255, 255, 255); font-family: arial, helvetica, sans-serif; font-size: 14px; line-height: 24px;">Bibliografía</span></p>
<div dir="LTR" id="Bibliografía1">
<div dir="LTR" id="Bibliografía1_Head">
<h1>
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;">Bibliografía</span></span></h1>
</div>
<ol>
<li style="margin-bottom: 0in;">
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;">J A. AES - Advanced Encryption Standard. (2005)&nbsp;</span></span></li>
<li style="margin-bottom: 0in;">
<span style="font-family: arial, helvetica, sans-serif; font-size: 14px; line-height: 24px;">A M. Seguridad Europea para EEUU Algoritmo criptográfico Rijndael. </span><i style="font-family: arial, helvetica, sans-serif; font-size: 14px; line-height: 24px;">Madrid</i><span style="font-family: arial, helvetica, sans-serif; font-size: 14px; line-height: 24px;"> (2004)</span></li>
<li style="margin-bottom: 0in;">
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;">Joan Daemen VR. AES Proposal: Rijndael. <i>NIST AES Proposal</i> (1998)</span></span></li>
<li style="margin-bottom: 0in;">
<a href="http://www.criptored.upm.es/" style="font-family: arial, helvetica, sans-serif; font-size: 14px; line-height: 24px;">http://www.criptored.upm.es</a></li>
<li style="margin-bottom: 0in;">
<a href="http://www.kriptopolis.es/" style="font-family: arial, helvetica, sans-serif; font-size: 14px; line-height: 24px;">http://www.kriptopolis.es</a></li>
</ol>
</div>