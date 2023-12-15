---
layout: post
title:  Attack on AES Omission of MixColumns
date:   2014-03-10 06:00:00
description: A recent study by Orr Dunkelman and Nathan Keller shows that security can be compromised by the omission of such transformation. The results show that in the case of the analysis by omitting MixColumns, the algorithm complexity is reduced by a factor of 2^16.
tags: AES security attack
categories: Research
---
<p>
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;">As we mentioned in a <a href="en/library/security/item/54-aes-advanced-encryption-standard-overview-part-i">previous article</a>, rounds that make up the AES algorithm can be divided into <strong>three different categories: initial rounds, standard round and final round</strong>. When encryption, the information is subjected to a different number of rounds (10, 12 and 14 respectively) in each case depending on the length of the key (128, 192 and 256 respectively). Each such round is made up of combinations of transformations, the possible transformations include: ByteSub, ShiftRow, MixColumns and AddRoundKey. <span style="color:#0000ff;"><strong>Figure # 1</strong></span> shows the relationship of the transformation and corresponding rounds.</span></span></p>
<p>
&nbsp;</p>
<p style="text-align: center;">
<img alt="" class="cke-resize" src="images/Research/ataque-contra-AES-omision-mixcoloumns/1_en.png" style="height: 501px; width: 500px;" /></p>
<p style="text-align: center;">
<span style="font-family: arial, helvetica, sans-serif; font-size: 14px; color: rgb(0, 0, 255);"><strong>Figure # 1</strong></span><span style="font-family: arial, helvetica, sans-serif; font-size: 14px;">: Distribution of the transformations in each round.</span></p>

<p>
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;">As we can see in <span style="color:#0000ff;"><strong>Figure # 1</strong></span>, in the original algorithm, <strong>the final round differs from standard rounds by omitting the MixColumns transformation, further, the initial round is only composed by the AddRoundKey transformation</strong>. In relation to these two variants in the initial and final rounds, relative to standard rounds, the authors of AES Joan Daemen and Vincent Rijmen have mentioned that they have proposed them in order <strong>to keep the symmetry between encryption and decryption</strong>, as they mention <span style="color:#ff8c00;"><strong>[1]</strong></span>:</span></span></p>
<p>
&nbsp;</p>
<p style="text-align: center;">
<em><span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;">&ldquo;In order to make the cipher and its inverse more similar in structure, the linear mixing layer of the last round is different from the mixing layer in the other rounds. It can be shown that this does not improve or reduce the security of the cipher in any way. This is similar to the absence of the swap operation in the last round of the DES.&rdquo;</span></span></em></p>
<p>
&nbsp;</p>
<p>
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;">It is commonly known, and the same authors say in the quote above, that the omission of MixColumns do not affect or reduce the security of the encryption, however, <strong>a recent study by Orr Dunkelman and Nathan Keller <span style="color:#ff8c00;">[2]</span> shows that security can be compromised by the omission of such transformation</strong>.</span></span></p>
<p>
<span style="font-family: arial, helvetica, sans-serif; font-size: 14px;">This study takes a plaintext with the corresponding encryption for analysis (for the simplest case of a single round) omitting MixColumns and compares it with other attack in which this transformation has not been omitted. <strong>The results show that in the case of the analysis by omitting MixColumns, the algorithm complexity is reduced by a factor of 2<sup>16</sup></strong>. This same method was applied to the proposed <a href="en/laboratory/results/item/62-cryptographic-attack-on-aes-impossible-differential-attack">attack by Raphael C.-W. Phan <span style="color:#ff8c00;"><strong>[3]</strong></span> (discussed above)</a> the same results for the attack on 7 rounds with a key length of 192 bits was obtained.</span></p>
<p>
<span style="font-family: arial, helvetica, sans-serif; font-size: 14px;">Furthermore, the observations obtained in <span style="color:#ff8c00;"><strong>[2]</strong></span>, <strong>appear not to apply to any type of attack, some of them being immune, in the complexity reduction, to the omission of MixColumns transformation in the final round of AES</strong>. Despite, the authors claimed that AES security is affected by the omission of MixColumns for attacks where a reduction in the number of standards rounds are used, and therefore, the complete algorithm may also be affected.</span></p>
<p>
<span style="font-family: arial, helvetica, sans-serif; font-size: 14px;">It is important to note that the presented attack is an <strong>attack on reduced rounds (7 rounds)</strong>. This means that despite the successful attack proposed by the authors, AES maintains a fairly wide margin of safety with respect to this research.</span></p>
<p>
&nbsp;</p>
<h1>
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;">References</span></span></h1>
<ol>
<li>
<span style="font-family: arial, helvetica, sans-serif; font-size: 14px;">Joan Daemen VR. AES Proposal: Rijndael. NIST AES Proposal (1998).</span></li>
<li>
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;">Orr Dunkelman NK. The effects of the omission of last round&rsquo;s MixColumns on AES. Information Processing Letters (2010) 110: pp. 304-308.</span></span></li>
<li>
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;">Raphael CP. Impossible differential cryptanalysis of 7-round Advanced Encryption Standard (AES). Information Processing Letters (2004) 91: pp. 33-38.</span></span></li>
</ol>
<p>
&nbsp;</p>
<div id="ckimgrsz" style="left: 44.815338134765625px; top: 228.7187498807907px;">
<div class="preview">
&nbsp;</div>
</div>