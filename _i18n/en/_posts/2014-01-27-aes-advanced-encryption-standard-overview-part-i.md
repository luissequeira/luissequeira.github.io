---
layout: post
title:  AES (Advanced Encryption Standard) Overview Part I
date:   2014-01-27 06:00:00
description: The AES (Advanced Encryption Standard) algorithm, known as Rijndael, was so-named by its creators Joan Daemen and Vincent Rijmen, it is the current international standard for communications encryption since october 2000. This algorithm is characterized by a symmetric block cipher with variable key length, the default key length is 128 bits but can also be set to 192 or 256 bits.
tags: AES security criptography simetrickey algorithm
categories: Networks
thumbnail: assets/img/TICs/generalidades-aes-parte-1/1.png
---
The **AES (Advanced Encryption Standard) algorithm** [1], known as Rijndael, was so-named by its creators Joan Daemen and Vincent Rijmen, it is the current **international standard for communications encryption since october 2000**. This algorithm is characterized by a [**symmetric block cipher with variable key length**]({% post_url 2013-12-23-the-two-pillars-of-a-symmetric-key-algorithm %}), the default key length is $$128$$ bits but can also be set to $$192$$ or $$256$$ bits.

The operation of the algorithm can be split into **two parts or different processes, being the encryption process, the first one and the second corresponds to the sub-key generation process**, Figure #1 shows the interaction of both processes.

<div class="row mt-3" style="text-align: center">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="assets/img/TICs/generalidades-aes-parte-1/1.png" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Figure #1: Encryption with AES.
</div>

The block to be encrypt has a length of $$128$$ bits, while the key can vary from $$128$$, $$192$$ or $$256$$ bits, depending on the amount of standard rounds that apply to text $$10$$, $$12$$ and $$14$$ respectively [2]. Generally, the AES encryption is described by four basic features or **so-called transformations**, these are:

- **ByteSub**
- **ShiftRow**
- **MixColumns**
- **AddRoundKey**

The rounds, in which the text is subjected, can be divided into three categories: **initial round, standard rounds and final round**. These rounds consist in one or various combinations of the above transformations (see Figure #1). The different types of rounds differ by the combination of the transformations that are applied to the block to be encrypted.

AES interprets the input block of 128 bits, as a $$4x4$$ matrix with input of bytes [3], if the block is $$192$$ bits $$2$$ columns are added, if four columns $$256$$ are added, theses matrices are called **state matrices** and their shape is shown below:

$$
a_{ij_{128bits}} =
\begin{bmatrix} 
a_00 & a_01 & a_02 & a_03 \\ 
a_10 & a_11 & a_12 & a_13 \\ 
a_20 & a_21 & a_22 & a_23 \\ 
a_30 & a_31 & a_32 & a_33 \\ 
\end{bmatrix}
$$

$$
a_{ij_{192bits}} =
\begin{bmatrix} 
a_00 & a_01 & a_02 & a_03 & a_04 & a_05 \\ 
a_10 & a_11 & a_12 & a_13 & a_14 & a_15 \\ 
a_20 & a_21 & a_22 & a_23 & a_24 & a_25 \\ 
a_30 & a_31 & a_32 & a_33 & a_34 & a_35 \\ 
\end{bmatrix}
$$

$$
a_{ij_{256bits}} =
\begin{bmatrix} 
a_00 & a_01 & a_02 & a_03 & a_04 & a_05 & a_06 & a_07 \\ 
a_10 & a_11 & a_12 & a_13 & a_14 & a_15 & a_16 & a_17 \\ 
a_20 & a_21 & a_22 & a_23 & a_24 & a_25 & a_26 & a_27 \\ 
a_30 & a_31 & a_32 & a_33 & a_34 & a_35 & a_36 & a_37 \\ 
\end{bmatrix}
$$

## S-Box

Essentially, **an S-Box (substitution box) is a matrix of substitution values ​​used by algorithms symmetric-key cryptography**. The S-Boxes are carefully selected to be resistant to cryptanalysis. For AES, S-Box is the result of applying two functions to the state matrix, $$[a_{ij}]$$, firstly its multiplicative inverse $$[a_{ij}]$$ to $$a_{ij}^{-1} \in GF(2^8)$$ and then a linear transformation:

1. Any byte can be seen as an element of the finite field $$GF(2^8)$$, as every element has a multiplicative inverse, multiplicative inverse is associated to $$GF(2^8)$$, i.e. $$[a_{ij}]$$ to $$a_{ij}^{-1} \in GF(2^8)$$, the zero element is associated with the same zero.
2. The linear transformation is applied bit by bit with the following rule: linear transformation in $$GF(2^8) \rightarrow GF(2^8)$$.

$$
b'_i = b_i \oplus b_{(1+4)mod8} \oplus b_{(1+5)mod8} \oplus b_{(1+6)mod8} \oplus b_{(1+7)mod8} \oplus c_i
$$

in bits is:

$$
\begin{matrix}
b'_0 = b_0 \oplus b_4 \oplus b_5 \oplus b_6 \oplus b_7 \oplus c_0 \\
b'_1 = b_1 \oplus b_5 \oplus b_6 \oplus b_7 \oplus b_0 \oplus c_1 \\
b'_2 = b_2 \oplus b_6 \oplus b_7 \oplus b_0 \oplus b_1 \oplus c_2 \\
b'_3 = b_3 \oplus b_7 \oplus b_0 \oplus b_1 \oplus b_2 \oplus c_3 \\
b'_4 = b_4 \oplus b_0 \oplus b_1 \oplus b_2 \oplus b_3 \oplus c_4 \\
b'_5 = b_5 \oplus b_1 \oplus b_2 \oplus b_3 \oplus b_4 \oplus c_5 \\
b'_6 = b_6 \oplus b_2 \oplus b_3 \oplus b_4 \oplus b_5 \oplus c_6 \\
b'_7 = b_7 \oplus b_3 \oplus b_4 \oplus b_5 \oplus b_6 \oplus c_7 \\
\end{matrix}
$$

**This is the most expensive operation in terms of time for the AES algorithm**, therefore, this operation is precalculated. Finally, this process can be summarized in the following table, known as S-boxes [3] which can be used for any $$xy$$ byte.

<div class="row mt-3" style="text-align: center">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="assets/img/TICs/generalidades-aes-parte-1/5.png" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Table #1: S-Box for encryption.
</div>

Furthermore, for the decryption process an inverse table to the one used in the encryption process is calculated, said table is:

<div class="row mt-3" style="text-align: center">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="assets/img/TICs/generalidades-aes-parte-1/6.png" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Table #2: S-Box for decryption.
</div>

## References

1. Joan Daemen VR. AES Proposal: Rijndael. NIST AES Proposal (1998)
2. J A. AES - Advanced Encryption Standard. (2005) Versión 2005
3. A M. Seguridad Europea para EEUU Algoritmo criptográfico Rijndael. Madrid (2004)
4. [http://www.formaestudio.com/rijndaelinspector/](http://www.formaestudio.com/rijndaelinspector/)
5. [http://www.cryptosystem.net/aes/](http://www.cryptosystem.net/aes/)
6. [http://www.criptored.upm.es/](http://www.criptored.upm.es/)
7. [http://www.kriptopolis.es/](http://www.kriptopolis.es/)
