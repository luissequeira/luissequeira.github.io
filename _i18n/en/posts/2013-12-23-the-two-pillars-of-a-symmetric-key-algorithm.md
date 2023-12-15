---
layout: post
title:  The two pillars of a symmetric-key algorithm
date:   2013-12-23 06:00:00
description: In order to consider a symmetric-key algorithm robust and safe, it is necessary to have been subjected to analysis by the scientific community in this area, so they could give evidence that it is immune to most known attacks. In general, we can say that this type of algorithms must consider two fundamental pillars
tags: AES security algorithm simetrickey criptography
categories: Security
---
<p class="western" style="margin-bottom: 0in">
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;"><span style="line-height: 24px;">The </span><b style="font-size: 13px; line-height: 24px;">symmetric-key cryptography</b><span style="line-height: 24px;">, also called secret key cryptography, </span><b style="font-size: 13px; line-height: 24px;">is a cryptographic method using the same key to encrypt and decrypt</b><span style="line-height: 24px;">, ie, that the security of the algorithm is based on the key and not in algorithm. Examples of this type of cryptographic algorithms are: AES, DES, 3DES and RC5.</span></span></span></p>

<p class="western" style="margin-bottom: 0in">
<span lang="en-US" style="font-family: arial, helvetica, sans-serif; font-size: 14px; line-height: 24px;">It is clear that any algorithm can be broken either by methods commonly known, or, for some new attack. The most basic attack which is commonly used as a reference for comparisons between different cryptanalysis techniques, is the </span><span lang="en-US" style="font-family: arial, helvetica, sans-serif; font-size: 14px; line-height: 24px;"><b>brute force attack or exhaustive key search</b></span><span lang="en-US" style="font-family: arial, helvetica, sans-serif; font-size: 14px; line-height: 24px;">. It is basically a </span><span lang="en-US" style="font-family: arial, helvetica, sans-serif; font-size: 14px; line-height: 24px;"><b>trial and error method for all possible keys</b></span><span lang="en-US" style="font-family: arial, helvetica, sans-serif; font-size: 14px; line-height: 24px;">, it consists in that the attacker knows the algorithm, has a plaintext and its corresponding ciphertext; </span><span style="font-family: arial, helvetica, sans-serif; font-size: 14px; line-height: 24px;">the plaintext is encrypted with all possible keys until the corresponding ciphertext is found</span><span lang="en-US" style="font-family: arial, helvetica, sans-serif; font-size: 14px; line-height: 24px;">, or in reverse direction respectively. As it is expected, </span><span lang="en-US" style="font-family: arial, helvetica, sans-serif; font-size: 14px; line-height: 24px;"><b>this method is the most expensive in computational resources and time</b></span><span lang="en-US" style="font-family: arial, helvetica, sans-serif; font-size: 14px; line-height: 24px;">. If a key has a length of <em>n</em> bits, the number of possible key combinations will be <em>2<sup>n</sup></em>, therefore it will require <em>2<sup>n</sup>-1</em> testing keys, assuming that the correct key will be the last.</span></p>
<p class="western" style="margin-bottom: 0in">
<span lang="en-US"><!--EndFragment--></span></p>
<p class="western" style="margin-bottom: 0in">
<span style="font-family: arial, helvetica, sans-serif; font-size: 14px; line-height: 24px;">In order to consider a symmetric-key algorithm robust and safe, </span><b style="font-family: arial, helvetica, sans-serif; font-size: 14px; line-height: 24px;">it is necessary to have been subjected to analysis by the scientific community in this area</b><span style="font-family: arial, helvetica, sans-serif; font-size: 14px; line-height: 24px;">, so they could give evidence that it is immune to most known attacks. In general, we can say that </span><b style="font-family: arial, helvetica, sans-serif; font-size: 14px; line-height: 24px;">this type of algorithms must consider two fundamental pillars</b><span style="font-family: arial, helvetica, sans-serif; font-size: 14px; line-height: 24px;">:</span></p>
<p class="western" style="margin-bottom: 0in">
&nbsp;</p>
<ol>
<li>
<p class="western" style="margin-bottom: 0in">
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;"><b>The nonlinearity between inputs and outputs</b>, or the correlation of the inputs and the outputs.</span></span></p>
</li>
<li>
<p class="western" style="margin-bottom: 0in">
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;"><!--StartFragment--><b>The propagation of the differences of bits</b>, or measuring the probability that such bits has been confused.</span></span></p>
</li>
</ol>
<p class="western" style="margin-bottom: 0in">
&nbsp;</p>
<p class="western" style="margin-bottom: 0in">
<span style="font-family: arial, helvetica, sans-serif; font-size: 14px; line-height: 24px;">The first concerns that </span><b style="font-family: arial, helvetica, sans-serif; font-size: 14px; line-height: 24px;">the algorithm must be immune to</b><span style="font-family: arial, helvetica, sans-serif; font-size: 14px; line-height: 24px;"> </span><b style="font-family: arial, helvetica, sans-serif; font-size: 14px; line-height: 24px;">linear cryptanalysis</b><span style="font-family: arial, helvetica, sans-serif; font-size: 14px; line-height: 24px;">, ie there should be </span><b style="font-family: arial, helvetica, sans-serif; font-size: 14px; line-height: 24px;">no linear dependence between the input and output of the algorithm</b><span style="font-family: arial, helvetica, sans-serif; font-size: 14px; line-height: 24px;">, for example, let <em>f</em> be the output function and <em>h</em> the input one, if input data is 1,2,3,4 and the output is 5, 10, 15, 20, it clearly shows that the relationship is <em>f(x)=5h(x)</em>, so it will not be very difficult to deduce which is the information contained in any encrypted message with <em>f</em>.</span></p>
<p class="western" style="margin-bottom: 0in;">
<span lang="en-US" style="font-family: arial, helvetica, sans-serif; font-size: 14px; line-height: 24px;">The second refers that </span><span lang="en-US" style="font-family: arial, helvetica, sans-serif; font-size: 14px; line-height: 24px;"><b>the algorithm must overcome a differential cryptanalysis</b></span><span lang="en-US" style="font-family: arial, helvetica, sans-serif; font-size: 14px; line-height: 24px;">, which is an analysis of the type "Chosen Plaintext Attack", which is an attack where the attacker can choose the plaintexts and obtains the corresponding ciphertexts using the same key, </span><span style="font-family: arial, helvetica, sans-serif; font-size: 14px; line-height: 24px;">and </span><b style="font-family: arial, helvetica, sans-serif; font-size: 14px; line-height: 24px;">then make comparisons and small variations in the plaintexts, so we can infer differences in ciphertexts</b><span style="font-family: arial, helvetica, sans-serif; font-size: 14px; line-height: 24px;">, </span><span lang="en-US" style="font-family: arial, helvetica, sans-serif; font-size: 14px; line-height: 24px;">with this, we can assign probabilities to the possible keys, analyzing intermediate state in each rounds. Also, there is a variant of this type of attack, called impossible differential cryptanalysis, in this case, searching differences between pairs of plaintext, which are maintained with some probability in the corresponding differences of the ciphertexts, that can not happen.</span></p>
<p class="western" style="margin-bottom: 0in">
<font color="#000000"><font face="Times New Roman, serif"><font size="3"><span lang="en-US"><b><!--EndFragment--></b></span></font></font></font></p>
<p align="JUSTIFY" class="western" style="margin-bottom: 0in;">
<span style="color: rgb(255, 255, 255); font-family: arial, helvetica, sans-serif; font-size: 14px; line-height: 24px;">ibliografía</span></p>
<div dir="LTR" id="Bibliografía1">
<div dir="LTR" id="Bibliografía1_Head">
<h1>
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;">References</span></span></h1>
</div>
<ol>
<li style="margin-bottom: 0in;">
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;"><span lang="en-US">J A. AES - Advanced Encryption Standard. (2005)&nbsp;</span></span></span></li>
<li style="margin-bottom: 0in;">
<span lang="en-US" style="font-family: arial, helvetica, sans-serif; font-size: 14px; line-height: 24px;">A M. Seguridad Europea para EEUU Algoritmo criptográfico Rijndael. </span><i style="font-family: arial, helvetica, sans-serif; font-size: 14px; line-height: 24px;"><span lang="en-US">Madrid</span></i><span lang="en-US" style="font-family: arial, helvetica, sans-serif; font-size: 14px; line-height: 24px;"> (2004).</span></li>
<li style="margin-bottom: 0in;">
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;"><span lang="en-US">Joan Daemen VR. AES Proposal: Rijndael. </span><i><span lang="en-US">NIST AES Proposal</span></i><span lang="en-US"> (1998) : .</span></span></span></li>
<li style="margin-bottom: 0in;">
<b style="color: rgb(0, 0, 0); font-family: arial, helvetica, sans-serif; font-size: 14px; line-height: 24px;"><a class="western" href="http://www.criptored.upm.es/">http://www.criptored.upm.es</a></b></li>
<li style="margin-bottom: 0in;">
<b style="color: rgb(0, 0, 0); font-family: arial, helvetica, sans-serif; font-size: 14px; line-height: 24px;"><a class="western" href="http://www.kriptopolis.es/">http://www.kriptopolis.es</a></b></li>
</ol>
</div>