---
layout: post
title:  AES Other attacks
date:   2014-04-21 05:00:00
description: It is clear that so far, none of the attacks carried out against full-AES has been successful, these attacks usually focus on reducing rounds. Many authors claim that none of the following types of attacks have been more effective than an exhaustive-key search.
tags: AES security attack
categories: Research
---
<p>
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;">It is clear that so far, <strong>none of the attacks carried out against full-AES has been successful</strong>, these attacks usually focus on reducing rounds. Many authors claim that none of the following types of attacks have been more effective than an exhaustive-key search:</span></span></p>
<ul>
<li>
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;">Linear cryptanalysis</span></span></li>
<li>
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;">Differential Cryptanalysis</span></span></li>
<li>
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;">Truncated diferencials</span></span></li>
<li>
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;">Interpolation attacks</span></span></li>
<li>
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;">Square attack</span></span></li>
</ul>
<p>
<span style="font-family: arial, helvetica, sans-serif; font-size: 14px;">However, the ordered structure and the deep mathematical basis that AES uses, make it an object of study for new attacks proposals such as algebraic attacks. These attacks consist on propose an equation system, and with the unknowns of the system, it can deduce the key; one of the advantages of this type of attack, is the small number of known texts needed.</span></p>

<p>
<span style="font-family: arial, helvetica, sans-serif; font-size: 14px;">In 2002, Asiacrypt made a publication of Nicolas Courtois and Josef Pieprzyk <span style="color:#ff8c00;"><strong>[1]</strong></span> where they propose a theoretical model of AES, which ensure characterization it as a quadratic equations system, the system consists on 8000 equations with 1600 binary variables, <strong>however, the attack failed in trying to break AES</strong>, as Courtois mentioned in <span style="color:#ff8c00;"><strong>[2]</strong></span>. In addition, several cryptography experts have commented that there are mathematics problems behind the attack, the authors have probably made a mistake, despite this, considering the orderly shape and the mathematical complete structure of AES, it is possible that this type of cryptanalysis can become one of the most powerful to break AES.</span></p>
<p>
<span style="font-family: arial, helvetica, sans-serif; font-size: 14px;">Other known publications are:</span></p>
<ul>
<li>
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;"><strong>Impossible Differentials Attack:</strong> there is an attack of this type on 5 rounds of AES, requiring 2<sup>29</sup> chosen plaintext, 2<sup>30</sup> encryptions, 2<sup>42</sup> bytes of memory, 2<sup>26</sup> precalculus steps. These conditions were improved in <span style="color:#ff8c00;"><strong>[3]</strong></span> and <span style="color:#ff8c00;"><strong>[4]</strong></span> to achieve an attack on 6 rounds of AES.</span></span></li>
<li>
<span style="font-family: arial, helvetica, sans-serif; font-size: 14px;"><strong>Square Attack:</strong> is an attack aimed at a type of Rijndael algorithm, it has been designed based on bytes structures. Just the first such attack was made on the predecessor algorithm called <em>"Square"</em>. This attack can break Rijndael on 6-7 rounds, which may be upgraded to attack on 9 rounds of AES-256 with 2<sup>77</sup> plaintexts, 2<sup>56</sup> related keys and 2<sup>224</sup> encryptions <span style="color:#ff8c00;"><strong>[5]</strong></span>.</span></li>
<li>
<span style="font-family: arial, helvetica, sans-serif; font-size: 14px;"><strong>Collision Attack:</strong> it tries to find two inputs that produce the same hash value, i.e., a hash collision. This attack affects all versions of AES, 128, 192 and 256 with 7 rounds <span style="color:#ff8c00;"><strong>[6]</strong></span>.</span></li>
</ul>
<p>
&nbsp;</p>
<h1>
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;">References</span></span></h1>
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