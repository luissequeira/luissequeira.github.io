---
layout: post
title:  Los dos pilares de un algoritmo de criptografía simétrica
date:   2013-12-26 06:00:00
description: Para que un algoritmo de criptografía simétrica sea robusto pueda considerarse como seguro, es necesario que haya sido sometido al análisis por la comunidad científica en esta área, de esta manera se podría dar evidencia de que es inmune a los ataque más conocidos. En general, se puede decir que un algoritmo de este tipo debe tener en cuenta dos pilares fundamentales
tags: criptografía AES criptografía-simétrica algoritmo seguridad
categories: Innovation
thumbnail: assets/img/TICs/los-dos-pilares-de-un-algoritmo-de-criptografia-simetrica/1.jpg
---

<div class="row mt-3" style="text-align: center">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="assets/img/TICs/los-dos-pilares-de-un-algoritmo-de-criptografia-simetrica/1.jpg" class="img-fluid rounded z-depth-1" %}
    </div>
</div>

La **criptografía simétrica**, o también llamada criptografía de clave secreta, **es un método criptográfico que utiliza la misma clave para cifrar como para descifrar**, es decir, que la seguridad del algoritmo se basa en la clave y no en el algoritmo. Algunos ejemplos de algoritmos criptográficos de este tipo son: AES, DES, 3DES y RC5.

Es claro que todo algoritmo puede ser roto, ya sea por los métodos comúnmente conocidos, o bien, por algún nuevo ataque. El ataque más básico y que comúnmente se utiliza como referencia para realizar comparaciones entre diversa técnicas de criptoanálisis es el **ataque a fuerza bruta o búsqueda exhaustiva de clave**. Es básicamente, un **método de prueba y error de todas las posibles claves**, consiste en que el atacante conoce el algoritmo, posee un texto en claro y su correspondiente cifrado; al texto lo cifra probando cada una de las posibles claves hasta obtener su correspondiente texto cifrado, o bien, en sentido inverso respectivamente. Es de esperarse que dicho método sea **el más costoso en recursos computacionales y en tiempo**. Si una clave tiene una longitud de $$n$$ bits, la cantidad de posibles combinaciones de clave será de $$2^n$$ y por lo tanto se requerirá de $$2^n-1$$ pruebas de claves, suponiendo que la clave correcta será la última.

Para que un algoritmo de criptografía simétrica sea robusto pueda considerarse como seguro, **es necesario que haya sido sometido al análisis por la comunidad científica en esta área**, de esta manera se podría dar evidencia de que es inmune a los ataque más conocidos. En general, se puede decir que un **algoritmo de este tipo debe tener en cuenta dos pilares fundamentales**:

- **La no linealidad entre las entradas y las salidas**, o la correlación de las entradas con las salidas.
- **La propagación de las diferencias de los bits**, o el medir la probabilidad de que tanto se confunden los bits.

El primer punto se refiere a que **el algoritmo debe ser inmune al criptoanálisis lineal**, es decir, que **no debe haber dependencia lineal entre la entrada y la salida del algoritmo**, como por ejemplo, sea $$f$$ la función de salida y $$h$$ la de entrada, si la información de entrada es 1, 2, 3, 4 y la salida es 5, 10, 15, 20, claramente se deduce que la relación es $$f(x)=5h(x)$$, de tal manera no será muy difícil deducir cual es la información contenida en algún tipo de mensaje cifrado con $$f$$.

El segundo punto se refiere a que **el algoritmo debe soportar un criptoanálisis diferencial**, que es un análisis del tipo “Chosen Plaintext Attack”, el cual consiste en un ataque donde el atacante puede escoger los textos en claro y después obtener sus correspondientes textos cifrados utilizando la misma clave, para luego **realizar comparaciones y pequeñas variaciones en los textos y poder así ir deduciendo las diferencias de los textos cifrados**, con esto, se puede ir asignado probabilidades para las posibles claves, analizando cada estado intermedio dentro de cada una de las rondas. También, existe una variante de este tipo de criptoanálisis denominado ataque de diferencial imposible, en este caso se busca diferencias entre pares de textos en claro, que se mantienen con cierta probabilidad en las diferencias correspondientes de los textos cifrados que no pueden ocurrir.

## References

1. J A. AES - Advanced Encryption Standard. (2005)
2. A M. Seguridad Europea para EEUU Algoritmo criptográfico Rijndael. Madrid (2004)
3. Joan Daemen VR. AES Proposal: Rijndael. *NIST AES Proposal* (1998)
4. [http://www.criptored.upm.es/](http://www.criptored.upm.es/)
5. [http://www.kriptopolis.es/](http://www.kriptopolis.es/)