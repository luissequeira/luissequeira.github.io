---
layout: post
title:  Attack on AES Omission of MixColumns
date:   2014-03-10 06:00:00
description: A recent study by Orr Dunkelman and Nathan Keller shows that security can be compromised by the omission of such transformation. The results show that in the case of the analysis by omitting MixColumns, the algorithm complexity is reduced by a factor of 2^16.
tags: AES criptography simetrickey algorithm attack security
categories: Networks Innovation 
thumbnail: assets/img/Research/ataque-contra-AES-omision-mixcoloumns/1_en.png
---
As we mentioned in a [previous article]({% post_url 2014-01-27-aes-advanced-encryption-standard-overview-part-i %}), rounds that make up the AES algorithm can be divided into **three different categories: initial rounds, standard round and final round**. When encrypting, the information is subjected to a different number of rounds ($$10$$, $$12$$ and $$14$$ respectively) in each case depending on the length of the key ($$128$$, $$192$$ and $$256$$ respectively). Each such round is made up of combinations of transformations, the possible transformations include: ByteSub, ShiftRow, MixColumns and AddRoundKey. Figure #1 shows the relationship of the transformation and corresponding rounds.

<div class="row mt-3" style="text-align: center">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="assets/img/Research/ataque-contra-AES-omision-mixcoloumns/1_en.png" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Figure #1: Distribution of the transformations in each round.
</div>

As we can see in Figure #1, in the original algorithm, **the final round differs from standard rounds by omitting the MixColumns transformation, further, the initial round is only composed by the AddRoundKey transformation**. In relation to these two variants in the initial and final rounds, relative to standard rounds, the authors of AES Joan Daemen and Vincent Rijmen have mentioned that they have proposed them in order **to keep the symmetry between encryption and decryption**, as they mention [1]:

> In order to make the cipher and its inverse more similar in structure, the linear mixing layer of the last round is different from the mixing layer in the other rounds. It can be shown that this does not improve or reduce the security of the cipher in any way. This is similar to the absence of the swap operation in the last round of the DES.

It is commonly known, and the same authors say in the quote above, that the omission of MixColumns do not affect or reduce the security of the encryption, however, **a recent study by Orr Dunkelman and Nathan Keller [2] shows that security can be compromised by the omission of such transformation**.

This study takes a plaintext with the corresponding encryption for analysis (for the simplest case of a single round) omitting MixColumns and compares it with other attack in which this transformation has not been omitted. **The results show that in the case of the analysis by omitting MixColumns, the algorithm complexity is reduced by a factor of $$2^{16}$$**. This same method was applied to the proposed [attack by Raphael C.-W. Phan [3] (discussed above)]({% post_url 2014-02-17-cryptographic-attack-on-aes-impossible-differential-attack %}) the same results for the attack on $$7$$ rounds with a key length of $$192 bits$$ was obtained.

Furthermore, the observations obtained in [2], **appear not to apply to any type of attack, some of them being immune, in the complexity reduction, to the omission of MixColumns transformation in the final round of AES**. Despite, the authors claimed that AES security is affected by the omission of MixColumns for attacks where a reduction in the number of standards rounds are used, and therefore, the complete algorithm may also be affected.

It is important to note that the presented attack is an **attack on reduced rounds ($$7$$ rounds)**. This means that despite the successful attack proposed by the authors, AES maintains a fairly wide margin of safety with respect to this research.

## References

1. Joan Daemen VR. AES Proposal: Rijndael. NIST AES Proposal (1998).
2. Orr Dunkelman NK. The effects of the omission of last round's MixColumns on AES. Information Processing Letters (2010) 110: pp. 304-308.
3. Raphael CP. Impossible differential cryptanalysis of 7-round Advanced Encryption Standard (AES). Information Processing Letters (2004) 91: pp. 33-38.
