---
layout: post
title:  Cryptographic attack on AES Impossible Differential Attack
date:   2014-02-17 06:00:00
description: Some time ago, I read an interesting article of a "successful attack" against AES, the famous symmetric-key algorithm. Raphael C.-W. Phan presented a seven rounds "impossible differential attack" for AES-192 and AES-256. Someone may ask what kind of attack is this?, well, it is a crypt-analysis that takes advantage of the differences that are impossible to be, in a data block through encryption, in order to discover the key?. Without going into many details of the method used, below I comment some of the most important results of this study.
tags: AES criptography simetrickey algorithm attack security
categories: Research
---
<p>
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;">Some time ago, I read an interesting article of a <strong>"successful attack" against AES</strong>, the famous symmetric-key algorithm. Raphael C.-W. Phan <span style="color:#ff8c00;"><strong>[1]</strong></span> presented a seven rounds <strong>"impossible differential attack" for AES-192 and AES-256</strong>. Someone may ask: what kind of attack is this?, well, <strong>it is a crypt-analysis that takes advantage of the differences that are impossible to be</strong>, in a data block through encryption, in order to discover the key?. Without going into many details of the method used, below I comment some of the most important results of this study.</span></span></p>
<p>
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;"><!--StartFragment-->The attack involves taking pairs of identical texts in all bytes except one and encrypt these texts, then, analyze the data produced at the outputs of each rounds in order to observe the evolution of the information during the encryption process. With this information, a impossible key's probability (or probability 0) can be assigned.</span></span><!--EndFragment--></p>
<p>
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;">The attack is based on the algorithm outlined in <span style="color:#ff8c00;"><strong>[1]</strong></span>, which is used to break AES-192 and AES-256, it consists in 9 steps and focuses on the key expansion system. The algorithm permits to perform certain calculations and assigns probabilities when some sub-keys have been determined. In summary, <strong>the author hopes to determine the key in the seventh round with the mathematical model presented in this study</strong>, by observing the movements made by the various transformations.</span></span></p>
<p>
<span style="font-family: arial, helvetica, sans-serif; font-size: 14px;">Summarizing the results obtained in <span style="color:#ff8c00;"><strong>[1]</strong></span>, for the case of AES-192, 2<sup>92</sup> plain texts, 2<sup>153</sup> memory words and 2<sup>186</sup> encryptions were required, in the case of AES-256, 2<sup>92.5</sup> plain texts, the same memory space 2<sup>153</sup> and 2<sup>250.5</sup> encryptions were requiered. The <span style="color:#0000ff;"><strong>Table # 1</strong></span> shows a comparison between the results presented by <span style="color:#ff8c00;"><strong>[1]</strong></span> and two earlier attacks with fewer rounds.</span></p>
<p>
&nbsp;</p>
<p style="text-align: center;">
<img alt="" class="cke-resize" src="images/Research/ataque-criptografico-aes-impossible-differential-attack/1.png" style="height: 163px; width: 500px;" /></p>
<p style="text-align: center;">
<span style="font-family: arial, helvetica, sans-serif; font-size: 14px; color: rgb(0, 0, 255);"><strong>Table # 1</strong></span><span style="font-family: arial, helvetica, sans-serif; font-size: 14px;">: Comparison of results to attacks on AES </span><span style="font-family: arial, helvetica, sans-serif; font-size: 14px; color: rgb(255, 140, 0);"><strong>[1]</strong></span><span style="font-family: arial, helvetica, sans-serif; font-size: 14px;">.</span></p>
<p style="text-align: center;">
&nbsp;</p>
<p>
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;"><!--StartFragment-->Aside from the process itself, and analyzing the results of this attack, we can see that to break the algorithm, the test has needed 2<sup>186</sup> and 2<sup>250.5</sup> encryptions for AES-192 and AES-256 respectively. Taking into account that an exhaustive search would have taken 2<sup>192</sup> and 2<sup>256</sup> for each algorithm respectively, we could say that the attack presented by <span style="color:#ff8c00;"><strong>[1]</strong></span> <strong>has been successful</strong>.</span></span><!--EndFragment--></p>
<p>
<span style="font-family: arial, helvetica, sans-serif; font-size: 14px;">Now, <strong>it is important to clarify that this is an attack on reduced-rounds (7 rounds)</strong> and AES may have a key length of 128, 192 or 256 bits for an amount of standard rounds: 10, 12 and 14 respectively. This means that despite the successful attack presented, <strong>AES maintains a large margin of safety with respect to this study</strong>, because there are 5 rounds of difference (for AES-192), and thus, </span><strong><span style="font-family: arial, helvetica, sans-serif; font-size: 14px;">the decoding complexity of an information packet is increased by applying the number of rounds which is defined by the standard.</span></strong></p>
<p>
&nbsp;</p>
<h1>
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;">Reference</span></span></h1>
<ol>
<li>
<span style="font-family: arial, helvetica, sans-serif; font-size: 14px;">Raphael CP. Impossible differential cryptanalysis of 7-round Advanced Encryption Standard (AES). Information Processing Letters (2004) 91: pp. 33-38.</span></li>
</ol>
<p>
&nbsp;</p>
<p>
&nbsp;</p>
<div id="ckimgrsz" style="left: 44.815338134765625px; top: 588.2556800842285px;">
<div class="preview">
&nbsp;</div>
</div>
