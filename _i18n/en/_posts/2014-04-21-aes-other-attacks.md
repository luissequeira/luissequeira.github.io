---
layout: post
title:  AES Other attacks
date:   2014-04-21 05:00:00
description: It is clear that so far, none of the attacks carried out against full-AES has been successful, these attacks usually focus on reducing rounds. Many authors claim that none of the following types of attacks have been more effective than an exhaustive-key search.
tags: AES criptography simetrickey algorithm attack security
categories: Innovation
thumbnail: assets/img/Research/aes-otros-ataques/1.jpg
---

<div class="row mt-3" style="text-align: center">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="assets/img/Research/aes-otros-ataques/1.jpg" class="img-fluid rounded z-depth-1" %}
    </div>
</div>

It is clear that so far, **none of the attacks carried out against full-AES has been successful**, these attacks usually focus on reducing rounds. Many authors claim that none of the following types of attacks have been more effective than an exhaustive-key search:

- Linear cryptanalysis
 - Differential Cryptanalysis
 - Truncated diferencials
 - Interpolation attacks
 - Square attack
 
 However, the ordered structure and the deep mathematical basis that AES uses, make it an object of study for new attacks proposals such as algebraic attacks. These attacks consist on propose an equation system, and with the unknowns of the system, it can deduce the key; one of the advantages of this type of attack, is the small number of known texts needed.
 
 In 2002, Asiacrypt made a publication of Nicolas Courtois and Josef Pieprzyk [1] where they propose a theoretical model of AES, which ensure characterization it as a quadratic equations system, the system consists on $$8000$$ equations with $$1600$$ binary variables, however, the attack failed in trying to break AES, as Courtois mentioned in [2]. In addition, several cryptography experts have commented that there are mathematics problems behind the attack, the authors have probably made a mistake, despite this, considering the orderly shape and the mathematical complete structure of AES, it is possible that this type of cryptanalysis can become one of the most powerful to break AES.
 
 Other known publications are:
 
 - **Impossible Differentials Attack**: there is an attack of this type on $$5$$ rounds of AES, requiring $$2^{29}$$ chosen plaintext, $$2^{30}$$ encryptions, $$2^{42}$$ bytes of memory, $$2^{26}$$ precalculus steps. These conditions were improved in [3] and [4] to achieve an attack on $$6$$ rounds of AES.
 - **Square Attack**: is an attack aimed at a type of Rijndael algorithm, it has been designed based on bytes structures. Just the first such attack was made on the predecessor algorithm called *Square*. This attack can break Rijndael on $$6-7$$ rounds, which may be upgraded to attack on $$9$$ rounds of AES-256 with $$2^{77}$$ plaintexts, $$2^{56}$$ related keys and $$2^{224}$$ encryptions [5].
 - **Collision Attack**: it tries to find two inputs that produce the same hash value, i.e., a hash collision. This attack affects all versions of AES, $$128$$, $$192$$ and $$256$$ with $$7$$ rounds [6].
 
 ## References
 
 1. Nicolas C, Josef P. Cryptanalysis of Block Ciphers with Overdefined Systems of Equations. ASIACRYPT '02 Proceedings of the 8th International Conference on the Theory and Application of Cryptology and Information Security: Advances in Cryptology (2002), pp. 267-287.
 2. [http://www.cryptosystem.net/aes/](http://www.cryptosystem.net/aes/)
 3. J H C, M K, K K, J L, S K. Improved Impossible Differential Cryptanalysis of Rijndael and Crypton. ICISC (2001) LNCS 2288: pp. 39-49.
 4. Raphael CP, M U S. Generalised impossible differentials of advanced encryption standard. IEE Electronics Letters (2001) Vol. 37, Issue 14: pp. 896-898.
 5. N F, J K, S L, B S, M S, D W, D W, D W. Improved cryptanalysis of Rijndael. FSE 00, LNCS 1978, pp. 213-230.
 6. H G, M M. A collision Attack on 7 rounds of Rijndael. AES3papers, pp. 2-11.
 