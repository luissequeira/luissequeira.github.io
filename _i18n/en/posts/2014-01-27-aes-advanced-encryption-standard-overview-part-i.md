---
layout: post
title:  AES (Advanced Encryption Standard) Overview Part I
date:   2014-01-27 06:00:00
description: The AES (Advanced Encryption Standard) algorithm, known as Rijndael, was so-named by its creators Joan Daemen and Vincent Rijmen, it is the current international standard for communications encryption since october 2000. This algorithm is characterized by a symmetric block cipher with variable key length, the default key length is 128 bits but can also be set to 192 or 256 bits.
tags: AES security criptography simetrickey algorithm
categories: Security
---
<p>
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;">The <strong>AES (Advanced Encryption Standard) algorithm</strong> <span style="color:#ff8c00;"><strong>[1]</strong></span>, known as Rijndael, was so-named by its creators Joan Daemen and Vincent Rijmen, it i<!--StartFragment-->s the current <strong>international standard for communications encryption since october 2000</strong>. This algorithm is characterized by a <strong><a href="http://www.telecomsharing.com/en/library/security/item/50-the-two-pillars-of-a-symmetric-key-algorithm">symmetric block cipher</a> with variable key length</strong>, the default key length is 128 bits but can also be set to 192 or 256 bits.</span></span></p>

<p>
<span style="font-family: arial, helvetica, sans-serif; font-size: 14px; line-height: 24px;">The operation of the algorithm can be split into<strong> two parts or different processes, being the encryption process, the first one and the second corresponds to the sub-key generation process</strong>, <span style="color:#0000ff;"><strong>Figure # 1</strong></span> shows the interaction of both processes.</span></p>
<p>
&nbsp;</p>
<p style="text-align: center;">
<img alt="" src="images/TICs/generalidades-aes-parte-1/1.png" style="width: 343.9772644042969px; height: 415.96588134765625px;" /></p>
<p style="text-align: center;">
<span style="font-family: arial, helvetica, sans-serif; font-size: 14px; line-height: 24px; color: rgb(0, 0, 255);"><strong>Figure # 1</strong></span><span style="font-family: arial, helvetica, sans-serif; font-size: 14px; line-height: 24px;">: Encryption with AES.</span></p>
<p style="text-align: center;">
&nbsp;</p>
<p>
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;"><!--StartFragment-->The block to be encrypt has a length of 128 bit, while the key can vary from 128, 192 or 256 bits, depending on the amount of standard rounds that apply to text 10, 12 and 14 respectively <span style="color:#ff8c00;"><strong>[2]</strong></span>. Generally, the AES encryption is described by four basic features or <strong>so-called transformations</strong>, these are:</span></span><!--EndFragment--></p>
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
<span style="font-family: arial, helvetica, sans-serif; font-size: 14px; line-height: 24px;">The rounds, in which the text is subjected, can be divided into three categories: <strong>initial round, standard rounds and final round</strong>. These rounds consist in one or various combinations of the above transformations (see </span><span style="font-family: arial, helvetica, sans-serif; font-size: 14px; line-height: 24px; color: rgb(0, 0, 255);"><strong>Figure # 1</strong></span><span style="font-family: arial, helvetica, sans-serif; font-size: 14px; line-height: 24px;">). The different types of rounds differ by the combination of the transformations that are applied to the block to be encrypted.</span></p>
<p>
<span style="font-family: arial, helvetica, sans-serif; font-size: 14px; line-height: 24px;">AES interprets the input block of 128 bits, as a 4x4 matrix with input of bytes </span><span style="font-family: arial, helvetica, sans-serif; font-size: 14px; line-height: 24px; color: rgb(255, 140, 0);"><strong>[3]</strong></span><span style="font-family: arial, helvetica, sans-serif; font-size: 14px; line-height: 24px;">, if the block is 192 bits 2 columns are added, if four columns 256 are added, theses matrices are called <strong>state matrices</strong> and their shape is shown below:</span></p>
<p>
&nbsp;</p>
<p style="text-align: center;">
<img alt="" src="images/TICs/generalidades-aes-parte-1/2.png" style="height: 517px; width: 500px;" /></p>
<p>
&nbsp;</p>
<h1>
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;">S-Box</span></span></h1>
<p>
<span style="font-family: arial, helvetica, sans-serif; font-size: 14px; line-height: 24px;">Essentially, <strong>an S-Box (substitution box) is a matrix of substitution values ​​used by algorithms symmetric-key cryptography</strong>. The S-Boxes are carefully selected to be resistant to cryptanalysis. For AES, S-Box is the result of applying two functions to the state matrix, <em>[a<sub>ij</sub>]</em>, </span><span style="font-family: arial, helvetica, sans-serif; font-size: 14px; line-height: 24px;">firstly its multiplicative inverse <em>[a<sub>ij</sub>]</em> to <em>a<sub>ij</sub><sup>-1 </sup>E GF(2<sup>8</sup>)</em> and then a linear transformation:</span></p>
<ol>
<li>
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;">Any byte can be seen as an element of the finite field&nbsp;<em>GF(2<sup>8</sup>)</em>, as every element has a multiplicative inverse, multiplicative inverse is associated to&nbsp;<em>GF(2<sup>8</sup>)</em>, i.e. <em>[a<sub>ij</sub>]</em> to&nbsp;<em>a<sub>ij</sub><sup>-1&nbsp;</sup>E GF(2<sup>8</sup>)</em>, the zero element is associated with the same zero.</span></span></li>
<li>
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;">The linear transformation is applied bit by bit with the following rule: linear transformation in&nbsp;<em>GF(2<sup>8</sup>)</em><em>→GF(2<sup>8</sup>)</em>.</span></span></li>
</ol>
<p style="text-align: center;">
<img alt="" src="images/TICs/generalidades-aes-parte-1/3.png" style="width: 403.991455078125px; height: 46.9886360168457px;" /></p>
<p>
<span style="font-family: arial, helvetica, sans-serif; font-size: 14px; line-height: 24px;">in bits is:</span></p>
<p style="text-align: center;">
<img alt="" src="images/TICs/generalidades-aes-parte-1/4.png" style="width: 238.97726440429688px; height: 215.9943084716797px;" /></p>
<p>
&nbsp;</p>
<p>
<span style="font-family: arial, helvetica, sans-serif; font-size: 14px; line-height: 24px;"><strong>This is the most expensive operation in terms of time for the AES algorithm</strong>, therefore, this operation is precalculated. </span><span style="font-family: arial, helvetica, sans-serif; font-size: 14px; line-height: 24px;">Finally, this process can be summarized in the following table, known as S-boxes </span><span style="font-family: arial, helvetica, sans-serif; font-size: 14px; line-height: 24px; color: rgb(255, 140, 0);"><strong>[3]</strong></span><span style="font-family: arial, helvetica, sans-serif; font-size: 14px; line-height: 24px;"> which can be used for any <em>xy</em> byte.</span></p>
<p>
&nbsp;</p>
<p style="text-align: center;">
<img alt="" src="images/TICs/generalidades-aes-parte-1/5.png" style="height: 325px; width: 500px;" /></p>
<p style="text-align: center;">
<span style="font-family: arial, helvetica, sans-serif; font-size: 14px; line-height: 24px; color: rgb(0, 0, 255);"><strong>Table # 1</strong></span><span style="font-family: arial, helvetica, sans-serif; font-size: 14px; line-height: 24px;">: S-Box for encryption.</span></p>
<p style="text-align: center;">
&nbsp;</p>
<p>
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;"><!--StartFragment-->Furthermore, for the decryption process an inverse table to the one used in the encryption process is calculated, said table is:</span></span><!--EndFragment--></p>
<p>
&nbsp;</p>
<p style="text-align: center;">
<img alt="" src="images/TICs/generalidades-aes-parte-1/6.png" style="height: 322px; width: 500px;" /></p>
<p style="text-align: center;">
<span style="font-family: arial, helvetica, sans-serif; font-size: 14px; line-height: 24px; color: rgb(0, 0, 255);"><strong>Table # 2</strong></span><span style="font-family: arial, helvetica, sans-serif; font-size: 14px; line-height: 24px;">: S-Box for decryption.</span></p>
<p style="text-align: center;">
&nbsp;</p>
<h1>
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;">References</span></span></h1>
<div dir="LTR" id="Bibliografía1">
<ol>
<li>
<span style="font-size: 14px;"><span style="font-family: arial, helvetica, sans-serif;">Joan Daemen VR. AES Proposal: Rijndael. NIST AES Proposal (1998)</span></span></li>
<li>
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;">J A. AES - Advanced Encryption Standard. (2005) Versión 2005</span></span></li>
<li>
<span style="font-size: 14px;"><span style="font-family: arial, helvetica, sans-serif;">A M. Seguridad Europea para EEUU Algoritmo criptográfico Rijndael. Madrid (2004)</span></span></li>
<li>
<a href="http://www.formaestudio.com/rijndaelinspector/" style="font-family: arial, helvetica, sans-serif; line-height: 24px; font-size: 13px;">http://www.formaestudio.com/rijndaelinspector/</a></li>
<li>
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;"><a href="http://www.cryptosystem.net/aes/" style="font-size: 13px; line-height: 24px;">http://www.cryptosystem.net/aes/</a></span></span></li>
<li>
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;"><a href="http://www.criptored.upm.es/" style="font-size: 13px; line-height: 24px;">http://www.criptored.upm.es</a></span></span></li>
<li>
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;"><a href="http://www.kriptopolis.es/" style="font-size: 13px; line-height: 24px;">http://www.kriptopolis.es</a></span></span></li>
</ol>
</div>