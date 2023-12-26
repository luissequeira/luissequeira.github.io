---
layout: post
title:  Ataque criptográfico contra AES Impossible Differential Attack
date:   2014-02-20 06:00:00
description: Hace algún tiempo leí un artículo interesante de un “ataque exitoso” contra AES, el famoso algoritmo de criptografía simétrica. Raphael C.-W. Phan presentó un “impossible differential attack” a 7 rondas para AES-192 y AES-256. Algunos se preguntarán que tipo de ataque es este?, pues bien, es un criptoanálisis que se aprovecha de las diferencias que son imposible de darse, de un bloque de datos a través del cifrado, con la finalidad de descubrir la clave. Sin entrar en muchos detalles del método utilizado, a continuación comento algunos de los resultados más importantes de dicho estudio.
tags: AES criptografía seguridad criptografía-simétrica ataque
categories: Networks Innovation 
thumbnail: assets/img/Research/ataque-criptografico-aes-impossible-differential-attack/1.png
---
Hace algún tiempo leí; un artículo interesante de **un ataque exitoso contra AES**, el famoso algoritmo de criptografía simétrica. Raphael C.-W. Phan [1] presentó un **impossible differential attack** a $$7$$ rondas para AES-192 y AES-256. Algunos se preguntarán: que tipo de ataque es este?, pues bien, **es un criptoanálisis que se aprovecha de las diferencias que son imposible de darse**, de un bloque de datos a través del cifrado, con la finalidad de descubrir la clave. Sin entrar en muchos detalles del método utilizado, a continuación comento algunos de los resultados más importantes de dicho estudio.

El ataque consiste en tomar parejas de textos idénticos en todos los bytes excepto en uno y comenzar a cifrar dichos textos, luego, se analizan los datos producidos a las salidas de cada una de las rondas con la finalidad de observar la evolución de la información durante el proceso de cifrado. Con esta información se van asignando las probabilidades para las claves imposibles o de probabilidad de $$0$$.

El ataque se basa en el algoritmo expuesto en [1], que es utilizado para romper AES-192 y AES-256, consta de $$9$$ pasos a seguir y se concentra en el sistema de expansión de claves. El algoritmo permite realizar ciertos cálculos y asignar probabilidades en el momento que se ha determinado alguna de las subclaves. En resumen, **el autor espera determinar la clave en la séptima ronda, con el modelo matemático expuesto en dicho estudio**, mediante la observación de los movimientos realizados por las diferentes transformaciones.

Resumiendo los resultados obtenidos en [1], para el caso de AES-192, se requirió de $$2^{92}$$ textos en claro, $$2^{153}$$ palabras de memoria y $$2^{186}$$ encripciones, para el caso de AES-256 los textos en claro fueron $$2^{92.5}$$, el mismo espacio de memoria $$2^{153}$$ y $$2^{250.5}$$ encripciones. La Tabla #1 muestra una comparación entre los resultados presentados por [1] y otros dos ataques anteriores con menor cantidad de rondas.

<div class="row mt-3" style="text-align: center">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="assets/img/Research/ataque-criptografico-aes-impossible-differential-attack/1.png" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Tabla #1: Comparación de los resultados a ataques a AES [1].
</div>

Dejando de lado el proceso como tal, y analizando los resultados obtenidos en dicho ataque, se puede apreciar que para romper el algoritmo se han necesitado $$2^{186}$$ y $$2^{250.5}$$ encripciones para AES-192 y AES-256 respectivamente. Si se toma en cuenta que una búsqueda exhaustiva de clave hubiera tomado $$2^{192}$$ y $$2^{256}$$ para cada uno de los algoritmos respectivamente, se podría decir que el ataque presentado por [1] **ha sido exitoso**.

Ahora, **es importante aclarar que se trata de un ataque a rondas reducidas ($$7$$ rondas)** y que AES puede tener una longitud de clave de $$128$$, $$192$$ o $$256$$ bits según sea el caso, para la cantidad de rondas estándar: $$10$$, $$12$$ y $$14$$ respectivamente. Esto significa, que pese al ataque exitoso que se presenta, **AES mantiene un margen de seguridad bastante amplio con respecto a este estudio**, porque hay $$5$$ rondas de diferencia (para AES-192) y por lo tanto, **la complejidad para descifrar un paquete de información se incrementa al aplicar la cantidad de vueltas que define el estándar**.

## Reference

1. Raphael CP. Impossible differential cryptanalysis of 7-round Advanced Encryption Standard (AES). Information Processing Letters (2004) 91: pp. 33-38.
