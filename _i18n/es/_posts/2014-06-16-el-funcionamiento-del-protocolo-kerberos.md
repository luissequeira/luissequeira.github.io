---
layout: post
title:  El funcionamiento del protocolo Kerberos
date:   2014-06-16 05:00:00
description: El protocolo de autenticación Kerberos permite a una serie de ordenadores demostrar su identidad entre ellos de una manera segura en una red insegura. El funcionamiento de dicho protocolo está basado en el protocolo Needham-Schroeder, el cual define un 'tercero de confianza.
tags: seguridad kerberos criptografía
categories: Networks
thumbnail: assets/img/TICs/funcionamiento-protocolo-kerberos/1.png
---
**El protocolo de autenticación Kerberos permite a una serie de ordenadores demostrar su identidad entre ellos** de una manera segura en una red insegura. El funcionamiento de dicho protocolo está basado en el protocolo Needham-Schroeder, el cual define un "tercero de confianza" denominado Centro de Distribución de Claves (KDC). William Stallings en su libro Fundamentos de Seguridad de Redes: Aplicaciones y Estándares, Segunda Edición (pag. 394), define un KDC de la siguiente manera:

> Sistema autorizado para transmitir claves de sesión temporales a usuarios. Cada clave de sesión se transmite cifrada, usando una clave maestra que el centro de distribución de claves comparte con el usuario destino. *William Stallings*

**El KDC se puede ver como el conjunto de dos etapas lógicas compuesta por un servidor de autenticación (AS) y un servidor emisor de *tickets* (TGS)**. El AS tiene como función identificar a cada usuario, validar su identidad y entregar al cliente una clave que le permite comunicarse con el TGS. Por otro lado, el TGS es el servidor encargado de comprobar que el cliente posea el *ticket* de autenticación y entrega una clave al usuario que le permite acceder a los servicios que ha solicitado. Este escenario se muestra en la Figura #1.

<div class="row mt-3" style="text-align: center">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="assets/img/TICs/funcionamiento-protocolo-kerberos/1.png" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Figura #1: Componentes y flujo de comunicación del protocolo Kerberos.
</div>

Kerberos realiza una gestión de *tickets* que le permite a los usuarios demostrar su identidad y obtener las claves se sesión para un determinado servicio, estas claves le permite a dos entidades interaccionar de manera segura. Para ello es necesario que dicho protocolo realice una gestión adecuada de diferentes bases de datos con el fin de identificar a los usuarios, y a la vez, mantener otra base de datos de claves secretas para poder asignar a cada entidad, ya sea cliente o servidor.

La Figura #2 muestra el flujo de mensajes producidos por el protocolo Kerberos, donde claramente se ve la información que contiene cada uno de los mensajes enviados entre las diferente entidades que participan en el intercambio de claves. Se debe aclarar que no se muestra la comunicación previa que debe establecer el cliente con el AS, donde le brinda el nombre de usuario y contraseña que ha introducido el usuario en el cliente. Sin embargo, la gestión de los **tickets** es bastante claro.

Cuando el cliente realiza una solicitud al AS, el AS contesta con dos mensajes: **en el primero envía la clave cifrada que va a compartir el cliente con el TGS, y en el segundo paquete debe ser reenviado al TGS**, dicho paquete no puede ser descifrado por el cliente y contiene información acerca de la validación hecha por el AS.

Luego, el cliente envía dos mensajes al TGS: **en el primer mensaje reenvía el paquete que le dió el AS agregando el tipo de servicio solicitado y el segundo mensaje es un autenticador** cifrado con la clave generada por el AS para la comunicación entre cliente y TGS.

Ahora el TGS responde al cliente con la clave que va a compartir con el servidor del servicio solicitado y un **ticket** que solamente el servidor de servicio puede descifrar y que el cliente debe reenviar. **El cliente reenvía el *ticket*; hacia el servidor del servicio y además un autenticador** cifrado con la clave entregada por el TGS para dicha comunicación, de modo que la comunicación entre cliente y servicio ya puede ser realizada de manera cifrada con dicha clave.

<div class="row mt-3" style="text-align: center">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="assets/img/TICs/funcionamiento-protocolo-kerberos/2.png" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Figura #2: Intercambio de mensajes del protocolo Kerberos.
</div>

## References

1. William Stallings. Fundamentals of Network Security: Applications and Standards, Second Edition. Pearson Education. 2004.
