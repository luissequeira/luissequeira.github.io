---
layout: post
title:  Ataque contra AES Omisión de MixColumns
date:   2014-03-13 06:00:00
description: Un estudio reciente realizado por Orr Dunkelman y Nathan Keller, muestra que si se ve comprometida la seguridad por la omisión de dicha transformación. Los resultados obtenidos reflejan que en el caso del análisis omitiendo MixColumns se reduce la complejidad del algoritmo por un factor de 2^16. 
tags: AES criptografía seguridad criptografía-simétrica ataque
categories: Networks Innovation 
thumbnail: assets/img/Research/ataque-contra-AES-omision-mixcoloumns/1_en.png
---
Como se ha mencionado en un [artículo anterior]({% post_url 2014-01-27-aes-advanced-encryption-standard-overview-part-i %}), las rondas que componen el algoritmo AES se pueden dividir en **tres categorías diferentes: rondas inicial, ronda estándar y ronda final**. A la hora del cifrado, la información es sometida a una cantidad diferente de rondas ($$10$$, $$12$$ y $$14$$ respectivamente) en cada caso en función de la longitud de la clave ($$128$$, $$192$$ y $$256$$ bits respectivamente). Cada una de dichas rondas se compone de combinaciones de transformaciones, las posibles transformaciones son: ByteSub, ShiftRow, MixColumns y AddRoundKey. La Figura # 
1 muestra la relación de las transformaciones y las correspondientes rondas.

<div class="row mt-3" style="text-align: center">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="assets/img/Research/ataque-contra-AES-omision-mixcoloumns/1_en.png" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Figura #1: Distribución de las transformaciones en cada ronda.
</div>

Como se puede observar en la Figura #1, en el algoritmo original, **la ronda final difiere de las rondas estándares por la omisión de la transformación MixColumns, además, la ronda inicial está compuesta solamente por la transformación AddRoundKey**. En relación a estas dos variantes en las rondas inicial y final, con respecto las rondas estándares, los autores de AES Joan Daemen y Vincent Rijmen mencionan que las han propuesto con la finalidad de guardar la simetría entre la cifrado y descifrado, como ellos mismos mencionan [1]:

> In order to make the cipher and its inverse more similar in structure, the linear mixing layer of the last round is different from the mixing layer in the other rounds. It can be shown that this does not improve or reduce the security of the cipher in any way. This is similar to the absence of the swap operation in the last round of the DES.

Comúnmente se sabe y los mismos autores lo afirman en la cita anterior, que la omisión de MixColumns no afecta o reduce la seguridad del cifrado, sin embargo, **un estudio reciente realizado por Orr Dunkelman y Nathan Keller [2], muestra que si se ve comprometida la seguridad por la omisión de dicha transformación**.

Dicho estudio, toma un texto en claro con su correspondiente cifrado para el análisis (para el caso más simple de una sola ronda) omitiendo MixColumns y lo compara con otro ataque realizado donde no ha sido omitida esta transformación. **Los resultados obtenidos reflejan que en el caso del análisis omitiendo MixColumns se reduce la complejidad del algoritmo por un factor de $$2^{16}$$**. Este mismo método se aplicó al [ataque propuesto por Raphael C.-W. Phan (comentado con anterioridad)]({% post_url 2014-02-17-cryptographic-attack-on-aes-impossible-differential-attack %}) obteniendo los mismos resultados para ese ataque a $$7$$ rondas con una longitud de la clave de $$192$$ bits.

Por otro lado, las observaciones obtenidas en [2], **parecen no aplicarse para cualquier tipo de ataque, siendo algunos de ellos inmunes, en la reducción de la complejidad, a la omisión de la transformación de MixColumns en la ronda final de AES**. Pese a esto, los autores afirma que la seguridad de AES se ve afectada por la omisión de MixColumns para los ataques donde se utiliza una reducción de la cantidad de rondas estándares, y por lo tanto, el algoritmo completo también podría verse afectado.

Es importante aclarar que el ataque presentado se trata de un **ataque a rondas reducidas ($$7$$ rondas)**. Esto significa, que pese al ataque exitoso que plantean los autores, AES mantiene un margen de seguridad bastante amplio con respecto a este estudio.

## References

1. Joan Daemen VR. AES Proposal: Rijndael. NIST AES Proposal (1998).
2. Orr Dunkelman NK. The effects of the omission of last round's MixColumns on AES. Information Processing Letters (2010) 110: pp. 304-308.
3. Raphael CP. Impossible differential cryptanalysis of 7-round Advanced Encryption Standard (AES). Information Processing Letters (2004) 91: pp. 33-38.
