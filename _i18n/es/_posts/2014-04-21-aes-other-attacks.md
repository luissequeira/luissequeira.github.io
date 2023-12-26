---
layout: post
title:  AES otros ataques
date:   2014-04-24 05:00:00
description: Es claro que hasta este momento, ninguno de los ataques realizado a full-AES ha tenido éxito, los ataques usualmente se concentran en la reducción de rondas. Muchos autores afirman que ninguno de los siguientes tipos de ataques, han podido ser más efectivos que una búsqueda exhaustiva de clave.
tags: AES criptografía seguridad criptografía-simétrica ataque
categories: Innovation
thumbnail: assets/img/Research/aes-otros-ataques/1.jpg
---

<div class="row mt-3" style="text-align: center">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="assets/img/Research/aes-otros-ataques/1.jpg" class="img-fluid rounded z-depth-1" %}
    </div>
</div>

Es claro que hasta este momento, **ninguno de los ataques realizado a full-AES ha tenido éxito**, los ataques usualmente se concentran en la reducción de rondas. Muchos autores afirman que ninguno de los siguientes tipos de ataques, han podido ser más efectivos que una búsqueda exhaustiva de clave:

- Criptoanálisis lineal
- Criptoanálisis diferencial
- Truncated diferencials
- Interpolation attacks
- Square attack<

Sin embargo, la estructura ordenada y las profundas bases matemáticas que utiliza, lo hacen un objeto de estudio para nuevas propuestas de ataques, como lo son los ataques algebraicos. Dichos ataques consisten en plantear un sistema de ecuaciones y con las incógnitas de dicho sistema deducir la clave; una de las ventajas que presenta este tipo de ataque, es la poca cantidad de textos conocidos que se necesitan.

En 2002 Asiacrypt hace una publicación de Nicolas Courtois y Josef Pieprzyk [1] donde proponen un modelo teórico de AES, en el que aseguran se caracteriza como un sistema de ecuaciones cuadráticas, dicho sistema consta de $$8000$$ ecuaciones con $$1600$$ variables binarias, **sin embargo, dicho ataque falló tratando de romper AES**, como menciona el mismo Courtois en [2]. Además, varios expertos en criptografía han comentado que hay problemas en las matemáticas detrás de dicho ataque, probablemente los autores hayan cometido algún error, a pesar de esto, teniendo en cuenta la forma ordenada y la completa estructura matemática de AES, es posible que este tipo de criptoanálisis pueda llegar a ser uno de los más potentes para romper AES.

Otras publicaciones conocidas son:

- **Impossible Differentials Attack**: existe un ataque de este tipo a $$5$$ rondas de AES, requiriendo $$2^{29}$$ plaintext elegidos, $$2^{30}$$ encripciones, $$2^{42}$$ bytes de memoria, $$2^{26}$$ pasos de precálculo. Estas condiciones fueron mejoradas en [3] y [4] para alcanzar un ataque a $$6$$ rondas de AES.
- **Square Attack**: es un ataque dirigido a un algoritmo del tipo de Rijndael que basa su diseño en estructuras de bytes. Precisamente el primer ataque de este tipo fue hecho al algoritmo predecesor llamado *Square*. Este ataque puede romper a Rijndael de $$6$$ a $$7$$ rondas, que puede ser mejorado para atacar a $$9$$ rondas de AES-256 con $$2^{77}$$ plaintexts, con $$2^{56}$$ claves relacionadas, y $$2^{224}$$ encripciones [5].
- **Collision Attack**: trata de encontrar dos entradas que producen el mismo valor hash, es decir, una colisión de hash. Este ataque afecta a todas las versiones de AES, $$128$$, $$192$$ y $$256$$ con $$7$$ rondas [6].
 
 ## References
 
 1. Nicolas C, Josef P. Cryptanalysis of Block Ciphers with Overdefined Systems of Equations. ASIACRYPT '02 Proceedings of the 8th International Conference on the Theory and Application of Cryptology and Information Security: Advances in Cryptology (2002), pp. 267-287.
 2. [http://www.cryptosystem.net/aes/](http://www.cryptosystem.net/aes/)
 3. J H C, M K, K K, J L, S K. Improved Impossible Differential Cryptanalysis of Rijndael and Crypton. ICISC (2001) LNCS 2288: pp. 39-49.
 4. Raphael CP, M U S. Generalised impossible differentials of advanced encryption standard. IEE Electronics Letters (2001) Vol. 37, Issue 14: pp. 896-898.
 5. N F, J K, S L, B S, M S, D W, D W, D W. Improved cryptanalysis of Rijndael. FSE 00, LNCS 1978, pp. 213-230.
 6. H G, M M. A collision Attack on 7 rounds of Rijndael. AES3papers, pp. 2-11.
 