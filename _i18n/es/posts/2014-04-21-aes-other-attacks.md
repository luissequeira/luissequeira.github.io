---
layout: post
title:  AES otros ataques
date:   2014-04-24 05:00:00
description: Es claro que hasta este momento, ninguno de los ataques realizado a full-AES ha tenido éxito, los ataques usualmente se concentran en la reducción de rondas. Muchos autores afirman que ninguno de los siguientes tipos de ataques, han podido ser más efectivos que una búsqueda exhaustiva de clave.
tags: AES seguridad ataque
categories: Research
---
<p>
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;">Es claro que hasta este momento, <strong>ninguno de los ataques realizado a full-AES ha tenido éxito</strong>, los ataques usualmente se concentran en la reducción de rondas. Muchos autores afirman que ninguno de los siguientes tipos de ataques, han podido ser más efectivos que una búsqueda exhaustiva de clave:</span></span></p>
<ul>
<li>
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;">Criptoanálisis lineal</span></span></li>
<li>
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;">Criptoanálisis diferencial</span></span></li>
<li>
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;">Truncated diferencials</span></span></li>
<li>
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;">Interpolation attacks</span></span></li>
<li>
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;">Square attack</span></span></li>
</ul>
<p>
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;">Sin embargo, la estructura ordenada y las profundas bases matemáticas que utiliza, lo hacen un objeto de estudio para nuevas propuestas de ataques, como lo son los ataques algebraicos. Dichos ataques consisten en plantear un sistema de ecuaciones y con las incógnitas de dicho sistema deducir la clave; una de las ventajas que presenta este tipo de ataque, es la poca cantidad de textos conocidos que se necesitan.</span></span></p>
<p>
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;">En 2002 Asiacrypt hace una publicación de Nicolas Courtois y Josef Pieprzyk <span style="color:#ff8c00;"><strong>[1]</strong></span> donde proponen un modelo teórico de AES, en el que aseguran se caracteriza como un sistema de ecuaciones cuadráticas, dicho sistema consta de 8000 ecuaciones con 1600 variables binarias, <strong>sin embargo, dicho ataque falló tratando de romper AES</strong>, como menciona el mismo Courtois en <span style="color:#ff8c00;"><strong>[2]</strong></span>. Además, varios expertos en criptografía han comentado que hay problemas en las matemáticas detrás de dicho ataque, probablemente los autores hayan cometido algún error, a pesar de esto, teniendo en cuenta la forma ordenada y la completa estructura matemática de AES, es posible que este tipo de criptoanálisis pueda llegar a ser uno de los más potentes para romper AES.</span></span></p>
<p>
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;">Otras publicaciones conocidas son:</span></span></p>
<ol>
<li>
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;"><strong>Impossible Differentials Attack:</strong> existe un ataque de este tipo a 5 rondas de AES, requiriendo 2<sup>29</sup> plaintext elegidos, 2<sup>30</sup> encripciones, 2<sup>42</sup> bytes de memoria, 2<sup>26</sup> pasos de precálculo. Estas condiciones fueron mejoradas en <span style="color:#ff8c00;"><strong>[3]</strong></span> y <span style="color:#ff8c00;"><strong>[4]</strong></span> para alcanzar un ataque a 6 rondas de AES.</span></span></li>
<li>
<span style="font-family: arial, helvetica, sans-serif; font-size: 14px;"><strong>Square Attack:</strong> es un ataque dirigido a un algoritmo del tipo de Rijndael que basa su diseño en estructuras de bytes. Precisamente el primer ataque de este tipo fue hecho al algoritmo predecesor llamado <em>“Square”</em>. Este ataque puede romper a Rijndael de 6 a 7 rondas, que puede ser mejorado para atacar a 9 rondas de AES-256 con 2<sup>77</sup> plaintexts, con 2<sup>56</sup> claves relacionadas, y 2<sup>224</sup> encripciones <span style="color:#ff8c00;"><strong>[5]</strong></span>.</span></li>
<li>
<span style="font-family: arial, helvetica, sans-serif; font-size: 14px;"><strong>Collision Attack:</strong> trata de encontrar dos entradas que producen el mismo valor hash, es decir, una colisión de hash. Este ataque afecta a todas las versiones de AES, 128, 192 y 256 con 7 rondas <span style="color:#ff8c00;"><strong>[6]</strong></span>.</span></li>
</ol>
<p>
&nbsp;</p>
<p>
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;">Referencias</span></span></p>
<ol>
<li>
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;">Nicolas C &amp; Josef P. Cryptanalysis of Block Ciphers with Overdefined Systems of Equations. ASIACRYPT '02 Proceedings of the 8th International Conference on the Theory and Application of Cryptology and Information Security: Advances in Cryptology (2002), pp. 267-287.</span></span></li>
<li>
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;"><a href="http://www.cryptosystem.net/aes/">http://www.cryptosystem.net/aes/</a></span></span></li>
<li>
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;">J H C, M K, K K, J L &amp; S K. Improved Impossible Differential Cryptanalysis of Rijndael and Crypton. ICISC (2001) LNCS 2288: pp. 39-49.</span></span></li>
<li>
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;">Raphael CP &amp; M U S. Generalised impossible differentials of advanced encryption standard. IEE Electronics Letters (2001) Vol. 37, Issue 14: pp. 896-898.</span></span></li>
<li>
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;">N F, J K, S L, B S, M S, D W, D W &amp; D W. Improved cryptanalysis of Rijndael. FSE 00, LNCS 1978, pp. 213-230.</span></span></li>
<li>
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;">H G &amp; M M. A collision Attack on 7 rounds of Rijndael. AES3papers, pp. 2-11.</span></span></li>
</ol>
