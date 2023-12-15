---
layout: post
title:  AES (Advanced Encryption Standard) overview Part II
date:   2014-02-03 06:00:00
description: Now, we discuss some details of the so-called transformations (ByteSub, ShiftRow, MixColumns and AddRoundKey) and the subkey generation process. To see more details in a more dynamic way the Rijndael Animation application is recommended.
tags: AES security criptography simetrickey algorithm
categories: Security
---
<p>
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;">In Part I of the Overview of AES (Advanced Encryption Standard) the most relevant aspects of AES and S-Box was described. <strong>Now, we discuss some details of the so-called transformations (ByteSub, ShiftRow, MixColumns and AddRoundKey) and the subkey generation process</strong>. To see more details in a more dynamic way the Rijndael Animation application is recommended.</span></span></p>
<p>
&nbsp;</p>
<h1>
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;">ByteSub</span></span></h1>
<p>
<span style="font-family: arial, helvetica, sans-serif; font-size: 14px; line-height: 24px;">This transformation performs a </span><strong style="font-family: arial, helvetica, sans-serif; font-size: 14px; line-height: 24px;">byte-by-byte substitution in each of the state matrix elements</strong><span style="font-family: arial, helvetica, sans-serif; font-size: 14px; line-height: 24px;">, ie, the state matrix </span><em style="font-family: arial, helvetica, sans-serif; font-size: 14px; line-height: 24px;">[a<sub>ij</sub>]</em><span style="font-family: arial, helvetica, sans-serif; font-size: 14px; line-height: 24px;"> is replaced by the matrix </span><em style="font-family: arial, helvetica, sans-serif; font-size: 14px; line-height: 24px;">[S<sub>ij</sub>]</em><span style="font-family: arial, helvetica, sans-serif; font-size: 14px; line-height: 24px;">, </span><span style="font-family: arial, helvetica, sans-serif; font-size: 14px; line-height: 24px; color: rgb(0, 0, 255);"><strong>Figure # 1</strong></span><span style="font-family: arial, helvetica, sans-serif; font-size: 14px; line-height: 24px;"> shows this process. Using </span><a href="http://www.formaestudio.com/rijndaelinspector/" style="font-family: arial, helvetica, sans-serif; font-size: 14px; line-height: 24px;">Rijndael Animation</a><span style="font-family: arial, helvetica, sans-serif; font-size: 14px; line-height: 24px;"> </span><span style="font-family: arial, helvetica, sans-serif; font-size: 14px; line-height: 24px; color: rgb(255, 140, 0);"><strong>[1]</strong></span><span style="font-family: arial, helvetica, sans-serif; font-size: 14px; line-height: 24px;"> application, it can be seen as the first byte of the state matrix (</span><em style="font-family: arial, helvetica, sans-serif; font-size: 14px; line-height: 24px;">[a<sub>00</sub>]</em><span style="font-family: arial, helvetica, sans-serif; font-size: 14px; line-height: 24px;">) </span><strong style="font-family: arial, helvetica, sans-serif; font-size: 14px; line-height: 24px;">is divided into two groups of four bits each one and they are used as pointers to the S-Box rows and columns</strong><span style="font-family: arial, helvetica, sans-serif; font-size: 14px; line-height: 24px;">, respectively, for replacement, in </span><span style="font-family: arial, helvetica, sans-serif; font-size: 14px; line-height: 24px; color: rgb(0, 0, 255);"><strong>Figure # 1</strong></span><span style="font-family: arial, helvetica, sans-serif; font-size: 14px; line-height: 24px;"> is shown how the value 19 will be replaced by d4.</span></p>
<p>
&nbsp;</p>
<p style="text-align: center;">
<img alt="" src="images/TICs/generalidades-aes-parte-2/1.png" style="height: 248px; width: 500px;" /></p>
<p style="text-align: center;">
<span style="font-family: arial, helvetica, sans-serif; font-size: 14px; line-height: 24px; color: rgb(0, 0, 255);"><strong>Figure # 1</strong></span><span style="font-family: arial, helvetica, sans-serif; font-size: 14px; line-height: 24px;">: S-Box use </span><span style="font-family: arial, helvetica, sans-serif; font-size: 14px; line-height: 24px; color: rgb(255, 140, 0);"><strong>[1]</strong></span><span style="font-family: arial, helvetica, sans-serif; font-size: 14px; line-height: 24px;">.</span></p>

<h1>
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;">ShiftRow</span></span></h1>
<p>
<span style="font-family: arial, helvetica, sans-serif; font-size: 14px; line-height: 24px;"><strong>ShiftRow applies circular left shifts</strong>, to each state matrix rows as follows: first row zero shifts, second row one shift, third row two shifts and fourth row three shifts, thus, the resultant matrix can be seen in <span style="color:#0000ff;"><strong>Figure # 2</strong></span>.</span></p>
<p style="text-align: center;">
&nbsp;</p>
<p style="text-align: center;">
<img alt="" src="images/TICs/generalidades-aes-parte-2/2.png" style="height: 123px; width: 500px;" /></p>
<p style="text-align: center;">
<span style="font-family: arial, helvetica, sans-serif; font-size: 14px; line-height: 24px; color: rgb(0, 0, 255);"><strong>Figure # 2</strong></span><span style="font-family: arial, helvetica, sans-serif; font-size: 14px; line-height: 24px;">: ShiftRow transformation </span><span style="font-family: arial, helvetica, sans-serif; font-size: 14px; line-height: 24px; color: rgb(255, 140, 0);"><strong>[2]</strong></span><span style="font-family: arial, helvetica, sans-serif; font-size: 14px; line-height: 24px;">.</span></p>
<p style="text-align: center;">
&nbsp;</p>
<h1>
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;">MixColumns</span></span></h1>
<p>
<span style="font-family: arial, helvetica, sans-serif; font-size: 14px; line-height: 24px;"><strong>This transformation allows mixing the bytes of the columns, considering the bytes of each column</strong> as polynomials whose coefficients belong to <em>GF(2<sup>8</sup>)</em>. This function consists in multiplying the columns modulus <em>x4+1</em> by the polynomial <em>c(x)</em> where:</span></p>
<p style="text-align: center;">
<em style="font-size: 20px; text-align: center;">c(x)=03x<sup>3</sup>+01x<sup>2</sup>+01x+02</em></p>
<p>
<span style="font-family: arial, helvetica, sans-serif; font-size: 14px; line-height: 24px;">or, in matrix form,</span></p>
<p style="text-align: center;">
<img alt="" src="images/TICs/generalidades-aes-parte-2/3.png" style="width: 278.991455078125px; height: 153.99147033691406px;" /></p>
<p>
<span style="font-family: arial, helvetica, sans-serif; font-size: 14px; line-height: 24px;">By using <a href="http://www.formaestudio.com/rijndaelinspector/">Rijndael Animation</a> application <span style="color:#ff8c00;"><strong>[1]</strong></span>, we can check the result of applying the above procedure, to the first column in the state matrix (see <span style="color:#0000ff;"><strong>Figure # 3</strong></span>), which is going to be replaced in the first column of the new matrix .</span></p>
<p>
&nbsp;</p>
<p style="text-align: center;">
<img alt="" src="images/TICs/generalidades-aes-parte-2/4.png" style="height: 274px; width: 500px;" /></p>
<p style="text-align: center;">
<span style="font-family: arial, helvetica, sans-serif; font-size: 14px; line-height: 24px;"><span style="color:#0000ff;"><strong>Figure # 3</strong></span>: MixColumns transformation <span style="color:#ff8c00;"><strong>[1]</strong></span>.</span></p>
<p style="text-align: center;">
&nbsp;</p>
<h1>
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;">AddRoundKey</span></span></h1>
<p>
<span style="font-family: arial, helvetica, sans-serif; font-size: 14px; line-height: 24px;">Let <em>[a<sub>ij</sub>]</em> be the state matrix and <em>[k<sub>ij</sub>]</em> the key matrix corresponding to that round. <strong>The AddRoundKey function, consists in performing a <em>xor</em> between state and key matriz</strong> (<span style="color:#0000ff;"><strong>Figure # 4</strong></span>), and then, replace it with the appropriate value.</span></p>
<p style="text-align: center;">
<em style="font-size: 20px; text-align: center;">AddRoundKey<sub>AES128bits</sub>=[a<sub>ij</sub>]xor[k<sub>ij</sub>]</em></p>
<p>
&nbsp;</p>
<p style="text-align: center;">
<img alt="" src="images/TICs/generalidades-aes-parte-2/5.png" style="height: 321px; width: 500px;" /></p>
<p style="text-align: center;">
<span style="font-family: arial, helvetica, sans-serif; font-size: 14px; line-height: 24px;"><span style="color:#0000ff;"><strong>Figure # 4</strong></span>: AddRoundKey transformation <span style="color:#ff8c00;"><strong>[2]</strong></span>.</span></p>
<p style="text-align: center;">
&nbsp;</p>
<h1>
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;"><!--StartFragment-->Subkey generation</span></span><!--EndFragment--></h1>
<p>
<span style="font-family: arial, helvetica, sans-serif; font-size: 14px; line-height: 24px;">This process permits to generate sub-keys from the system key. <strong>The key is extended to a list of 4-byte words</strong> called <em>W</em>, and containing <em>N<sub>b</sub>(N<sub>r</sub>+1)</em> words, where,</span></p>
<p style="text-align: center;">
<img alt="" src="images/TICs/generalidades-aes-parte-2/6_en.png" style="width: 181.98863220214844px; height: 50.99431610107422px;" /></p>
<p style="text-align: center;">
<em><span style="font-size: 20px;">N<sub>r</sub>=Max(N<sub>k</sub>,N<sub>b</sub>)+6=Número de rondas</span></em></p>
<p>
<span style="font-family: arial, helvetica, sans-serif; font-size: 14px; line-height: 24px;">The firsts <em>N<sub>k</sub></em> elements of <em>W</em> correspond to the key. The rest of the <em>W</em> elements are defined recursively, using SubByte function, cyclic shifts and <em>xor</em> operations. The <span style="color:#0000ff;"><strong>Figure # 5</strong></span> shows it.</span></p>
<p>
&nbsp;</p>
<p style="text-align: center;">
<img alt="" src="images/TICs/generalidades-aes-parte-2/7.png" style="height: 220px; width: 500px;" /></p>
<p style="text-align: center;">
<span style="font-family: arial, helvetica, sans-serif; font-size: 14px; line-height: 24px; color: rgb(0, 0, 255);"><strong>Figure # 5</strong></span><span style="font-family: arial, helvetica, sans-serif; font-size: 14px; line-height: 24px;">: Expansion of keys </span><strong style="font-family: arial, helvetica, sans-serif; font-size: 14px; line-height: 24px;"><span style="color:#ff8c00;">[3]</span></strong><span style="font-family: arial, helvetica, sans-serif; font-size: 14px; line-height: 24px;">.</span></p>
<p style="text-align: center;">
&nbsp;</p>
<p>
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;"><!--StartFragment-->Now the RotByte function is used, which returns a word whose bytes are cyclically shifted one position to the left.</span></span><!--EndFragment--></p>
<p style="text-align: center;">
<em style="font-size: 20px; text-align: center;">R<sub>con</sub>[i]=(RC[i],0x00,0x00,0x00)</em></p>
<p>
<span style="font-family: arial, helvetica, sans-serif; font-size: 14px; line-height: 24px;">being <em>RC[i]</em> an <em>GF[2<sup>8</sup>]</em> element, defined by:</span></p>
<p style="text-align: center;">
<em style="font-size: 20px;">RC[1]=0x01, RC[i]=0x02*RC[i-1]</em></p>
<p>
<span style="font-family: arial, helvetica, sans-serif; font-size: 14px; line-height: 24px;">Now, for&nbsp;</span><span style="line-height: 24px; font-family: arial, helvetica, sans-serif; font-size: 14px;"><em>N<sub>k</sub></em></span><em style="font-size: 13px; line-height: 24px;"><span style="font-size: 13px; line-height: 24px;">&lt;=6</span></em><span style="font-family: arial, helvetica, sans-serif; font-size: 14px; line-height: 24px;">&nbsp;and for all <em>i</em> that is not a multiple of <em>N<sub>k</sub></em>, the keywords are calculated:</span></p>
<p style="text-align: center;">
<em><span style="font-size: 20px;"><span style="font-family: arial, helvetica, sans-serif; line-height: 24px;">W(i)=W(i-N<sub>k</sub>) xor W(i-1)</span></span></em></p>
<p>
<span style="font-family: arial, helvetica, sans-serif; font-size: 14px; line-height: 24px;">and for all <em>i</em> multiple of <em>N<sub>k</sub></em>, the <strong>keywords are calculated</strong>:</span></p>
<p style="text-align: center;">
<em><span style="font-size: 20px;">W(i)=W(i-N<sub>k</sub>) xor [ByteSub(RotByte[W(i-1)]) xor R<sub>con</sub>(i/N<sub>k</sub>)]</span></em></p>
<p>
<span style="font-family: arial, helvetica, sans-serif; font-size: 14px; line-height: 24px;">In the case of&nbsp;</span><em style="font-family: arial, helvetica, sans-serif; font-size: 13.63636302947998px;">N<sub>k</sub>&gt;6</em><span style="font-family: arial, helvetica, sans-serif; font-size: 14px; line-height: 24px;">&nbsp;the operation is the same used for&nbsp;</span><span style="line-height: 24px; font-family: arial, helvetica, sans-serif; font-size: 14px;"><em>N<sub>k</sub></em></span><em style="font-size: 13px; line-height: 24px;"><span style="font-size: 13px; line-height: 24px;">&lt;=6</span></em><span style="font-family: arial, helvetica, sans-serif; font-size: 14px; line-height: 24px;">, except when <em>i</em> satisfies&nbsp;</span><em style="line-height: 24px; font-family: arial, helvetica, sans-serif; font-size: 13.63636302947998px;">i mod N<sub>k</sub>=4</em><span style="font-family: arial, helvetica, sans-serif; font-size: 14px; line-height: 24px;">&nbsp;the <strong>sub-keys are calculated</strong>:</span></p>
<p style="text-align: center;">
<em style="text-align: center;"><span style="font-size: 20px;">W(i)=W(i-N<sub>k</sub>) xor ByteSub(W[i-1])</span></em></p>
<p>
&nbsp;</p>
<h1>
<span style="font-size: 14px;"><span style="font-family: arial, helvetica, sans-serif;">Referencias</span></span></h1>
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