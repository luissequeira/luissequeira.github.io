---
layout: post
title:  Generalidades de AES (Advanced Encryption Standard) II Parte
date:   2014-02-06 06:00:00
description: Ahora, comentaremos algunos detalles de las llamadas transformaciones (ByteSub, ShiftRow, MixColumns y AddRoundKey) y el proceso de generación de subclaves. Para ver más detalles de una manera más dinámica se recomienda la aplicación Rijndael Animation.
tags: AES seguridad criptografía criptografía-simétrica algoritmo
categories: Security
---
<p>
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;">En la I Parte de Generalidades de AES (Advanced Encryption Standard) se describieron los aspectos más relevantes de AES y las S-Box. <strong>Ahora, comentaremos algunos detalles de las llamadas transformaciones (ByteSub, ShiftRow, MixColumns y AddRoundKey) y el proceso de generación de subclaves</strong>. Para ver más detalles de una manera más dinámica se recomienda la aplicación Rijndael Animation.</span></span></p>
<p>
&nbsp;</p>
<h1>
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;">ByteSub</span></span></h1>
<p>
<span style="font-family: arial, helvetica, sans-serif; font-size: 14px; line-height: 24px;">Esta transformación realiza una <strong>sustitución byte por byte en cada uno de los elementos de la matriz de estado</strong>, es decir, la matriz de estado <em>[a<sub>ij</sub>]</em> se sustituye por la matriz <em>[S<sub>ij</sub>]</em>, la <span style="color:#0000ff;"><strong>Figura # 1</strong></span> muestra dicho proceso. Utilizando la aplicación <a href="http://www.formaestudio.com/rijndaelinspector/">Rijndael Animation</a> de <span style="color:#ff8c00;"><strong>[1]</strong></span>, se puede observar como el primer byte de la matriz de estado (<em>[a<sub>00</sub>]</em>) <strong>se divide en dos grupos de cuatro bits cada uno y se utilizan como apuntadores a filas y columnas de la S-Box</strong>, respectivamente, para realizar la sustitución, en la <span style="color:#0000ff;"><strong>Figura # 1</strong></span> se muestra como el valor 19 será reemplazado por d4.</span></p>
<p style="text-align: center;">
&nbsp;</p>
<p style="text-align: center;">
<img alt="" src="images/TICs/generalidades-aes-parte-2/1.png" style="height: 248px; width: 500px;" /></p>
<p style="text-align: center;">
<span style="font-family: arial, helvetica, sans-serif; font-size: 14px; line-height: 24px; color: rgb(0, 0, 255);"><strong>Figura # 1</strong></span><span style="font-family: arial, helvetica, sans-serif; font-size: 14px; line-height: 24px;">: Utilización de S-Box </span><span style="font-family: arial, helvetica, sans-serif; font-size: 14px; line-height: 24px; color: rgb(255, 140, 0);"><strong>[1]</strong></span><span style="font-family: arial, helvetica, sans-serif; font-size: 14px; line-height: 24px;">.</span></p>

<h1>
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;">ShiftRow</span></span></h1>
<p>
<span style="font-family: arial, helvetica, sans-serif; font-size: 14px; line-height: 24px;"><strong>ShiftRow aplica corrimientos circulares a la izquierda</strong>, a cada una de las filas de la matriz de estado de la siguiente forma: primera fila cero corrimientos, segunda fila un corrimiento, tercera fila dos corrimientos y cuarta fila tres corrimientos, de esta forma, la matriz resultante se puede apreciar en la <span style="color:#0000ff;"><strong>Figura # 2</strong></span>.</span></p>
<p>
&nbsp;</p>
<p style="text-align: center;">
<img alt="" src="images/TICs/generalidades-aes-parte-2/2.png" style="height: 123px; width: 500px;" /></p>
<p style="text-align: center;">
<span style="font-family: arial, helvetica, sans-serif; font-size: 14px; line-height: 24px; color: rgb(0, 0, 255);"><strong>Figura # 2</strong></span><span style="font-family: arial, helvetica, sans-serif; font-size: 14px; line-height: 24px;">: Transformación ShiftRow </span><span style="font-family: arial, helvetica, sans-serif; font-size: 14px; line-height: 24px; color: rgb(255, 140, 0);"><strong>[2]</strong></span><span style="font-family: arial, helvetica, sans-serif; font-size: 14px; line-height: 24px;">.</span></p>
<p style="text-align: center;">
&nbsp;</p>
<p>
<span style="font-family: arial, helvetica, sans-serif; font-size: 14px; color: rgb(68, 68, 68); line-height: 24px;">MixColumns</span></p>
<p>
<span style="font-family: arial, helvetica, sans-serif; font-size: 14px; line-height: 24px;"><strong>Esta función permite la mezcla de los bytes de las columnas, considerando los bytes de cada columna</strong>, como polinomios cuyos coeficientes pertenecen a <em>GF(2<sup>8</sup>)</em>. Dicha función consiste en multiplicar las columnas módulo <em>x4+1</em> por el polinomio <em>c(x)</em> donde:</span></p>
<p style="text-align: center;">
<span style="font-size:20px;"><em>c(x)=03x<sup>3</sup>+01x<sup>2</sup>+01x+02</em></span></p>
<p>
<span style="font-family: arial, helvetica, sans-serif; font-size: 14px; line-height: 24px;">O bien, en forma matricial,</span></p>
<p style="text-align: center;">
<img alt="" src="images/TICs/generalidades-aes-parte-2/3.png" style="width: 272.9971618652344px; height: 150.9801025390625px;" /></p>
<p>
<span style="font-family: arial, helvetica, sans-serif; font-size: 14px; line-height: 24px;">Utilizando la aplicación <a href="http://www.formaestudio.com/rijndaelinspector/">Rijndael Animation</a> </span><span style="font-family: arial, helvetica, sans-serif; font-size: 14px; line-height: 24px; color: rgb(255, 140, 0);"><strong>[1]</strong></span><span style="font-family: arial, helvetica, sans-serif; font-size: 14px; line-height: 24px;">, se puede comprobar el resultado de aplicar el procedimiento anterior, a la primera columna de una matriz de estado (ver </span><span style="font-family: arial, helvetica, sans-serif; font-size: 14px; line-height: 24px; color: rgb(0, 0, 255);"><strong>Figura # 3</strong></span><span style="font-family: arial, helvetica, sans-serif; font-size: 14px; line-height: 24px;">), la cual va ha ser sustituida en la primera columna de la nueva matriz.</span></p>
<p>
&nbsp;</p>
<p style="text-align: center;">
<img alt="" src="images/TICs/generalidades-aes-parte-2/4.png" style="height: 274px; width: 500px;" /></p>
<p style="text-align: center;">
<span style="font-family: arial, helvetica, sans-serif; font-size: 14px; line-height: 24px; color: rgb(0, 0, 255);"><strong>Figura # 3</strong></span><span style="font-family: arial, helvetica, sans-serif; font-size: 14px; line-height: 24px;">: Transformación MixColumns </span><span style="font-family: arial, helvetica, sans-serif; font-size: 14px; line-height: 24px; color: rgb(255, 140, 0);"><strong>[1]</strong></span><span style="font-family: arial, helvetica, sans-serif; font-size: 14px; line-height: 24px;">.</span></p>
<p style="text-align: center;">
&nbsp;</p>
<h1>
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;">AddRoundKey</span></span></h1>
<p>
<span style="font-family: arial, helvetica, sans-serif; font-size: 14px; line-height: 24px;">Sea la matriz <em>[a<sub>ij</sub>]</em> la matriz de estado y <em>[k<sub>ij</sub>]</em> la matriz de la clave correspondiente a dicha ronda. <strong>La función AddRoundKey consiste en realizar una xor entre las matrices de estado y la de la clave</strong> (<span style="color:#0000ff;"><strong>Figura # 4</strong></span>), para luego, sustituir con el valor correspondiente.</span></p>
<p style="text-align: center;">
<span style="font-size:20px;"><em>AddRoundKey<sub>AES128bits</sub>=[a<sub>ij</sub>]xor[k<sub>ij</sub>]</em></span></p>
<p>
&nbsp;</p>
<p style="text-align: center;">
<img alt="" src="images/TICs/generalidades-aes-parte-2/5.png" style="height: 321px; width: 500px;" /></p>
<p style="text-align: center;">
<span style="font-family: arial, helvetica, sans-serif; font-size: 14px; line-height: 24px; color: rgb(0, 0, 255);"><strong>Figura # 4</strong></span><span style="font-family: arial, helvetica, sans-serif; font-size: 14px; line-height: 24px;">: Transformación AddRoundKey </span><span style="font-family: arial, helvetica, sans-serif; font-size: 14px; line-height: 24px; color: rgb(255, 140, 0);"><strong>[2]</strong></span><span style="font-family: arial, helvetica, sans-serif; font-size: 14px; line-height: 24px;">.</span></p>
<p style="text-align: center;">
&nbsp;</p>
<h1>
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;">Generación de subclaves</span></span></h1>
<p>
<span style="font-family: arial, helvetica, sans-serif; font-size: 14px; line-height: 24px;">Este proceso permite generar subclaves a partir de la clave del sistema. <strong>La clave se extiende a una lista de palabras de 4 bytes</strong> que llamados <em>W</em> y que contiene <em>N<sub>b</sub>(N<sub>r</sub>+1)</em> palabras, donde,</span></p>
<p style="text-align: center;">
<img alt="" src="images/TICs/generalidades-aes-parte-2/6_es.png" style="width: 366.9886169433594px; height: 60.99431610107422px;" /></p>
<p style="text-align: center;">
<em><span style="font-size:20px;">N<sub>r</sub>=Max(N<sub>k</sub>,N<sub>b</sub>)+6=Número de rondas</span></em></p>
<p>
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;">Los primeros <em>N<sub>k</sub></em> elementos de <em>W</em> corresponden a la clave. El resto de los elementos de <em>W</em> se definen recursivamente utilizando la función SubByte, desplazamientos cíclicos y operaciones <em>xor</em>. En la <span style="color:#0000ff;"><strong>Figura # 5</strong></span> se puede apreciar <em>W</em> en forma de arreglo.</span></span></p>
<p style="text-align: center;">
&nbsp;</p>
<p style="text-align: center;">
<img alt="" src="images/TICs/generalidades-aes-parte-2/7.png" style="height: 220px; width: 500px;" /></p>
<p style="text-align: center;">
<span style="font-family: arial, helvetica, sans-serif; font-size: 14px; line-height: 24px; color: rgb(0, 0, 255);"><strong>Figura # 5</strong></span><span style="font-family: arial, helvetica, sans-serif; font-size: 14px; line-height: 24px;">: Expanción de claves </span><span style="font-family: arial, helvetica, sans-serif; font-size: 14px; line-height: 24px; color: rgb(255, 140, 0);"><strong>[3]</strong></span><span style="font-family: arial, helvetica, sans-serif; font-size: 14px; line-height: 24px;">.</span></p>
<p style="text-align: center;">
&nbsp;</p>
<p>
<span style="font-family: arial, helvetica, sans-serif; font-size: 14px; line-height: 24px;">Ahora, se utiliza la función RotByte, la cual devuelve una palabra, cuyos bytes se han desplazado cíclicamente una posición a la izquierda. Se utilizan unas constantes cuyos valores son:</span></p>
<p style="text-align: center;">
<span style="font-size:20px;"><em>R<sub>con</sub>[i]=(RC[i],0x00,0x00,0x00)</em></span></p>
<p>
<span style="font-family: arial, helvetica, sans-serif; font-size: 14px; line-height: 24px;">Siendo <em>RC[i]</em> un elemento de <em>GF[2<sup>8</sup>]</em> definido por:</span></p>
<p style="text-align: center;">
<span style="font-size:20px;"><em>RC[1]=0x01, RC[i]=0x02*RC[i-1]</em></span></p>
<p>
<span style="font-family: arial, helvetica, sans-serif; font-size: 14px; line-height: 24px;">Ahora bien, para <em>N<sub>k</sub></em></span><em><span style="font-size: 13px; line-height: 24px;">&lt;=6</span></em><span style="font-family: arial, helvetica, sans-serif; font-size: 14px; line-height: 24px;">&nbsp;y para todo <em>i</em> que no sea múltiplo de <em>N<sub>k</sub></em>, las palabras claves se calculan:</span></p>
<p style="text-align: center;">
<em><span style="font-size:20px;"><span style="font-family: arial, helvetica, sans-serif; line-height: 24px;">W(i)=W(i-N<sub>k</sub>) xor W(i-1)</span></span></em></p>
<p>
<span style="font-family: arial, helvetica, sans-serif; font-size: 14px; line-height: 24px;">y para todo </span><em style="font-family: arial, helvetica, sans-serif; font-size: 14px; line-height: 24px;">i</em><span style="font-family: arial, helvetica, sans-serif; font-size: 14px; line-height: 24px;"> que sea múltiplo de </span><em style="font-family: arial, helvetica, sans-serif; font-size: 14px; line-height: 24px;">N<sub>k</sub></em><span style="font-family: arial, helvetica, sans-serif; font-size: 14px; line-height: 24px;">, las <strong>palabras claves se calculan</strong>:</span></p>
<p style="text-align: center;">
<em><span style="font-size:20px;">W(i)=W(i-N<sub>k</sub>) xor [ByteSub(RotByte[W(i-1)]) xor R<sub>con</sub>(i/N<sub>k</sub>)]</span></em></p>
<p>
<span style="font-family: arial, helvetica, sans-serif; font-size: 14px; line-height: 24px;">Para el caso de <em>N<sub>k</sub>&gt;6</em> el funcionamiento es el mismo que para&nbsp;</span><span style="line-height: 24px; font-family: arial, helvetica, sans-serif; font-size: 14px;"><em>N<sub>k</sub></em></span><em style="font-size: 13px; line-height: 24px;"><span style="font-size: 13px; line-height: 24px;">&lt;=6</span></em><span style="font-family: arial, helvetica, sans-serif; font-size: 14px; line-height: 24px;">&nbsp;excepto que cuando <em>i</em> satisface <em>i mod N<sub>k</sub>=4</em> las <strong>subclaves se calculan</strong>:</span></p>
<p style="text-align: center;">
<em><span style="font-size: 20px;">W(i)=W(i-N<sub>k</sub>) xor ByteSub(W[i-1])</span></em></p>
<div>
&nbsp;</div>
<h1>
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;">Referencias</span></span></h1>
<div dir="LTR" id="Bibliografía1">
<div dir="LTR" id="Bibliografía1_Head">
<ol>
<li>
<a href="http://www.formaestudio.com/rijndaelinspector/">http://www.formaestudio.com/rijndaelinspector/</a></li>
<li>
<span style="font-size: 13px; line-height: 24px;">J A. AES - Advanced Encryption Standard. (2005) Versión 2005: .</span></li>
<li>
<span style="font-size: 13px; line-height: 24px;">A M. Seguridad Europea para EEUU Algoritmo criptográfico Rijndael. Madrid (2004) : .</span></li>
<li>
<span style="font-size: 13px; line-height: 24px;">Joan Daemen VR. AES Proposal: Rijndael. NIST AES Proposal (1998) : .</span></li>
<li>
<a href="http://www.cryptosystem.net/aes/" style="font-size: 13px; line-height: 24px;">http://www.cryptosystem.net/aes/</a></li>
<li>
<a href="http://www.criptored.upm.es/" style="font-size: 13px; line-height: 24px;">http://www.criptored.upm.es</a></li>
<li>
<a href="http://www.kriptopolis.es/" style="font-size: 13px; line-height: 24px;">http://www.kriptopolis.e</a>s</li>
</ol>
</div>
</div>