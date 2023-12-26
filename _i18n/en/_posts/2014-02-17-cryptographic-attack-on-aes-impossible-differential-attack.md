---
layout: post
title:  Cryptographic attack on AES Impossible Differential Attack
date:   2014-02-17 06:00:00
description: Some time ago, I read an interesting article of a "successful attack" against AES, the famous symmetric-key algorithm. Raphael C.-W. Phan presented a seven rounds "impossible differential attack" for AES-192 and AES-256. Someone may ask what kind of attack is this?, well, it is a crypt-analysis that takes advantage of the differences that are impossible to be, in a data block through encryption, in order to discover the key?. Without going into many details of the method used, below I comment some of the most important results of this study.
tags: AES criptography simetrickey algorithm attack security
categories: Networks Innovation 
thumbnail: assets/img/Research/ataque-criptografico-aes-impossible-differential-attack/1.png
---
Some time ago, I read an interesting article of a **"successful attack" against AES**, the famous symmetric-key algorithm. Raphael C.-W. Phan [1] presented a $$7$$ rounds **"impossible differential attack" for AES-192 and AES-256**. Someone may ask: what kind of attack is this?, well, **it is a crypt-analysis that takes advantage of the differences that are impossible to be**, in a data block through encryption, in order to discover the key?. Without going into many details of the method used, below I comment some of the most important results of this study.

The attack involves taking pairs of identical texts in all bytes except one and encrypt these texts, then, analyze the data produced at the outputs of each rounds in order to observe the evolution of the information during the encryption process. With this information, a impossible key's probability (or probability $$0$$) can be assigned.

The attack is based on the algorithm outlined in [1], which is used to break AES-192 and AES-256, it consists in $$9$$ steps and focuses on the key expansion system. The algorithm permits to perform certain calculations and assigns probabilities when some sub-keys have been determined. In summary, **the author hopes to determine the key in the seventh round with the mathematical model presented in this study**, by observing the movements made by the various transformations.

Summarizing the results obtained in [1], for the case of AES-192, $$2^{92}$$ plain texts, $$2^{153}$$ memory words and $$2^{186}$$ encryptions were required, in the case of AES-256, $$2^{92.5}$$ plain texts, the same memory space $$2^{153}$$ and $$2^{250.5}$$ encryptions were requiered. The Table #1 shows a comparison between the results presented by [1] and two earlier attacks with fewer rounds.

<div class="row mt-3" style="text-align: center">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="assets/img/Research/ataque-criptografico-aes-impossible-differential-attack/1.png" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Table #1: Comparison of results to attacks on AES [1].
</div>

Aside from the process itself, and analyzing the results of this attack, we can see that to break the algorithm, the test has needed $$2^{186}$$ and $$2^{250.5}$$ encryptions for AES-192 and AES-256 respectively. Taking into account that an exhaustive search would have taken $$2^{192}$$ and $$2^{256}$$ for each algorithm respectively, we could say that the attack presented by [1] **has been successful**.

Now, **it is important to clarify that this is an attack on reduced-rounds ($$7$$ rounds)** and AES may have a key length of $$128$$, $$192$$ or $$256$$ bits for an amount of standard rounds: $$10$$, $$12$$ and $$14$$ respectively. This means that despite the successful attack presented, **AES maintains a large margin of safety with respect to this study**, because there are $$5$$ rounds of difference (for AES-192), and thus, **the decoding complexity of an information packet is increased by applying the number of rounds which is defined by the standard**.

## Reference

1. Raphael CP. Impossible differential cryptanalysis of 7-round Advanced Encryption Standard (AES). Information Processing Letters (2004) 91: pp. 33-38.
