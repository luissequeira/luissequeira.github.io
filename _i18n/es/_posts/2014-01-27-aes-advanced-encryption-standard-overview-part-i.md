---
layout: post
title:  Generalidades de AES (Advanced Encryption Standard) I Parte
date:   2014-01-30 06:00:00
description: El algoritmo AES (Advanced Encryption Standard), conocido como Rijndael, fue nombrado así por sus creadores Joan Daemen y Vincent Rijmen, es el actual estándar internacional de cifrado para comunicaciones desde octubre del 2000. Dicho algoritmo se caracteriza por ser un cifrado simétrico por bloques con longitud de clave variable; la longitud de la clave por defecto es de 128 bits pero también puede establecerse a 192 o 256 bits.
tags: AES seguridad criptografía criptografía-simétrica algoritmo
categories: Networks
thumbnail: assets/img/TICs/generalidades-aes-parte-1/1.png
---
**El algoritmo AES (Advanced Encryption Standard)** [1], conocido como Rijndael, fue nombrado así por sus creadores Joan Daemen y Vincent Rijmen, **es el actual estándar internacional de cifrado para comunicaciones desde octubre del 2000**. Dicho algoritmo se caracteriza por ser un [**cifrado simétrico por bloques**]({% post_url 2013-12-23-the-two-pillars-of-a-symmetric-key-algorithm %}) con longitud de clave variable; la longitud de la clave por defecto es de $$128$$ bits pero también puede establecerse a $$192$$ o $$256$$ bits.

El funcionamiento de dicho algoritmo puede separarse en dos partes o procesos diferentes, **el primero, sería el proceso de cifrado y el segundo correspondiente al proceso de generación de subclaves**, la Figura #1 muestra la interacción de ambos procesos.

<div class="row mt-3" style="text-align: center">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="assets/img/TICs/generalidades-aes-parte-1/1.png" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Figura #1: Cifrado con AES.
</div>

El bloque a cifrar tiene una longitud de $$128$$ bit, mientras que la clave puede variar de $$128$$, $$192$$ o $$256$$ bits, según la cantidad de rondas estándar que se apliquen al texto $$10$$, $$12$$ y $$14$$ respectivamente [2]. En general, el cifrado de AES está descrito por cuatro funciones básicas o también **llamadas transformaciones**, estas son:

- **ByteSub**
- **ShiftRow**
- **MixColumns**
- **AddRoundKey**

Las rondas a las que se somete el texto se pueden dividir en tres categorías: **ronda inicial, rondas estándar y ronda final**. Cada una de estas rondas se compone de alguna o varias combinaciones de las transformaciones antes mencionadas (ver Figura #1). Los diferentes tipos de rondas difieren entre sí por la combinación de las transformaciones que se aplican al bloque que se desea cifrar.

AES interpreta los bloque de entrada de $$128$$ bits, como una matriz $$4x4$$ de entradas de bytes [3], si el bloque es de $$192$$ bits se agregan $$2$$ columnas, si es de $$256$$ se agregan $$4$$ columnas, a dichas matrices se les llama **matrices de estado** y su forma es como se muestra a continuación:

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

Básicamente, **una S-Box (substitution box) es una matriz para sustitución de valores, utilizado por los algoritmos de cifrado de clave simétrica**. Las S-Boxes son seleccionadas cuidadosamente para ser resistentes al criptoanálisis. En el caso de AES, dicha matriz es el resultado de aplicar dos funciones a la matriz de estado, $$[a_{ij}]$$, en primer lugar su inverso multiplicativo $$[a_{ij}]$$ a $$a_{ij}^{-1} \in GF(2^8)$$ y posteriormente una transformación lineal:

1. Todo byte puede verse como un elemento del cuerpo finito $$GF(2^8)$$, como todo elemento tiene inverso multiplicativo, se asocia el inverso multiplicativo en $$GF(2^8)$$, es decir$$[a_{ij}]$$ a $$a_{ij}^{-1} \in GF(2^8)$$, al elemento cero se le asocia el mismo cero.
2. La transformación lineal se aplica bit por bit con la siguiente regla: transformación lineal en $$GF(2^8) \rightarrow GF(2^8)$$.

$$
b'_i = b_i \oplus b_{(1+4)mod8} \oplus b_{(1+5)mod8} \oplus b_{(1+6)mod8} \oplus b_{(1+7)mod8} \oplus c_i
$$

en bits queda:

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

**Esta es la operación más costosa, en cuanto a tiempo se refiere, del algoritmo AES**, por esto, la operación es precalculada. Finalmente, este proceso puede resumirse en la siguiente tabla conocida como S-Box [3] que puede ser utilizada para un byte cualquiera $$xy$$.

<div class="row mt-3" style="text-align: center">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="assets/img/TICs/generalidades-aes-parte-1/5.png" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Tabla #1: S-Box para el cifrado.
</div>

Por otro lado, para el proceso de descifrado se calcula una tabla inversa a la utilizada en el proceso de cifrado, dicha tabla es:

<div class="row mt-3" style="text-align: center">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="assets/img/TICs/generalidades-aes-parte-1/6.png" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Tabla #2: S-Box para el descifrado.
</div>

## References

1. Joan Daemen VR. AES Proposal: Rijndael. NIST AES Proposal (1998)
2. J A. AES - Advanced Encryption Standard. (2005) Versión 2005
3. A M. Seguridad Europea para EEUU Algoritmo criptográfico Rijndael. Madrid (2004)
4. [http://www.formaestudio.com/rijndaelinspector/](http://www.formaestudio.com/rijndaelinspector/)
5. [http://www.cryptosystem.net/aes/](http://www.cryptosystem.net/aes/)
6. [http://www.criptored.upm.es/](http://www.criptored.upm.es/)
7. [http://www.kriptopolis.es/](http://www.kriptopolis.es/)
