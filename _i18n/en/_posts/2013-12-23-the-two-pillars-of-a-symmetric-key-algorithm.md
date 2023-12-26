---
layout: post
title:  The two pillars of a symmetric-key algorithm
date:   2013-12-23 06:00:00
description: In order to consider a symmetric-key algorithm robust and safe, it is necessary to have been subjected to analysis by the scientific community in this area, so they could give evidence that it is immune to most known attacks. In general, we can say that this type of algorithms must consider two fundamental pillars
tags: AES security algorithm simetrickey criptography
categories: Innovation
thumbnail: assets/img/TICs/los-dos-pilares-de-un-algoritmo-de-criptografia-simetrica/1.jpg
---

<div class="row mt-3" style="text-align: center">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="assets/img/TICs/los-dos-pilares-de-un-algoritmo-de-criptografia-simetrica/1.jpg" class="img-fluid rounded z-depth-1" %}
    </div>
</div>

The symmetric-key cryptography, also called secret key cryptography, is a cryptographic method using the same key to encrypt and decrypt, ie, that the security of the algorithm is based on the key and not in algorithm. Examples of this type of cryptographic algorithms are: AES, DES, 3DES and RC5.

It is clear that any algorithm can be broken either by methods commonly known, or, for some new attack. The most basic attack which is commonly used as a reference for comparisons between different cryptanalysis techniques, is the **brute force attack or exhaustive key search**. It is basically a **trial and error method for all possible keys**, it consists in that the attacker knows the algorithm, has a plaintext and its corresponding ciphertext; the plaintext is encrypted with all possible keys until the corresponding ciphertext is found, or in reverse direction respectively. As it is expected, **this method is the most expensive in computational resources and time**. If a key has a length of $$n$$ bits, the number of possible key combinations will be $$2^n$$, therefore it will require $$2^n-1$$ testing keys, assuming that the correct key will be the last.

In order to consider a symmetric-key algorithm robust and safe, **it is necessary to have been subjected to analysis by the scientific community in this area**, so they could give evidence that it is immune to most known attacks. In general, we can say that **this type of algorithms must consider two fundamental pillars**:

- **The nonlinearity between inputs and outputs**, or the correlation of the inputs and the outputs.
- **The propagation of the differences of bits**, or measuring the probability that such bits has been confused.

The first concerns that **the algorithm must be immune to linear cryptanalysis**, ie there should be **no linear dependence between the input and output of the algorithm**, for example, let $$f$$ be the output function and $$h$$ the input one, if the input data is 1, 2, 3, 4 and the output is 5, 10, 15, 20, it clearly shows that the relationship is $$f(x)=5h(x)$$, so it will not be very difficult to deduce which is the information contained in any encrypted message with $$f$$.

The second refers that **the algorithm must overcome a differential cryptanalysis**, which is an analysis of the type "Chosen Plaintext Attack", which is an attack where the attacker can choose the plaintexts and obtains the corresponding ciphertexts using the same key, and **then make comparisons and small variations in the plaintexts, so we can infer differences in ciphertexts**, with this, we can assign probabilities to the possible keys, analyzing intermediate state in each rounds. Also, there is a variant of this type of attack, called impossible differential cryptanalysis, in this case, searching differences between pairs of plaintext, which are maintained with some probability in the corresponding differences of the ciphertexts, that can not happen.

## References

1. J A. AES - Advanced Encryption Standard. (2005)
2. A M. Seguridad Europea para EEUU Algoritmo criptográfico Rijndael. Madrid (2004)
3. Joan Daemen VR. AES Proposal: Rijndael. *NIST AES Proposal* (1998)
4. [http://www.criptored.upm.es/](http://www.criptored.upm.es/)
5. [http://www.kriptopolis.es/](http://www.kriptopolis.es/)
