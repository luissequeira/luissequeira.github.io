---
layout: post
title:  ¿Qué es VoIP?
date:   2014-02-27 06:00:00
description:  VoIP se refiere a la tecnología necesaria para la comunicación de voz a través de IP, mientras que, ToIP es un servicio telefónico para los usuarios que utiliza VoIP como tecnología para dar dicho servicio. VoIP permite la transmisión de voz por medio de una red IP, incluyendo aquellas conectadas a Internet, consiste en la digitalización de la señales de voz por medio de un codec
tags: red voip tráfico
categories: Networks
thumbnail: assets/img/TICs/what-is-voip/1_en.png
---
El desarrollo de tecnologías de VoIP (Voice over Internet Protocol) han tenido una gran aceptación por parte de **empresas que buscan una reducción de costes para sus comunicaciones de voz**, principalmente PYMES (Pequeñas y Medianas Empresas). El término VoIP no debe confundirse con ToIP (Telephony over IP), **VoIP se refiere a la tecnología necesaria para la comunicación de voz a través de IP, mientras que, ToIP es un servicio telefónico para los usuarios que utiliza VoIP como tecnología para dar dicho servicio**.

**VoIP permite la transmisión de voz por medio de una red IP, incluyendo aquellas conectadas a Internet, consiste en la digitalización de la señales de voz por medio de un codec**. El consumo de ancho de banda de una comunicación de este tipo está directamente relacionada al codec como se muestra en la Tabla #1.

| Codec | Bit-rate |
| --- | --- |
| G.711 | $$56$$ or $$64 Kbps$$ |
| G.722 | $$48$$, $$56$$ or $$64 Kbps$$ |
| G.723 | bit-rate $$5,3$$ or $$6,4 Kbps$$ |
| G.728 | $$16 Kbps$$ |
| G.729 | $$8$$ or $$13 Kbps$$ |

<div class="caption">
    Tabla #1: Ancho de banda según codec.
</div>

Por otro lado, VoIP hace uso de diversos tipos de técnicas para la señalización de la llamada, no habiendo un protocolo definido en este ámbito. Uno de los protocolo utilizados con este fin en SIP (Session Initiation Protocol), además, se encuentran implementaciones con H.323 (una recomendación del sector de telecomunicaciones de la ITU, ITU-T) o IAX (Inter-Asterisk eXchange protocol, nativo de Asterisk private branch exchange, PBX).

SIP es uno de los protocolo con mayor impacto en la implementación de ToIP. Dicho protocolo, **se encarga de la señalización extremo a extremo de la comunicación, realiza los procedimientos necesarios para el establecimiento de la llamada, la modificación y la finalización de la comunicación**. Para la transmisión de datos en tiempo real, VoIP hace uso del protocolo RTP (Real-time Transport Protocol), dicho protocolo se encarga del control de la transmisión en las sesiones de aplicaciones multimedia y utiliza como protocolo de transporte UDP (User Datagram Protocol). En la Figura #1, se observa la distribución de los encabezados de cada uno de los paquetes de VoIP.

<div class="row mt-3" style="text-align: center">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="assets/img/TICs/what-is-voip/1_en.png" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Figura #1: Paquete VoIP transmitido por las estaciones.
</div>

Existen diversos dispositivos que actúan como una pasarela de voz sobre IP hacia una red telefónica convencional y viceversa, utilizando el protocolo SIP para la señalización de la comunicación. Normalmente, **estos dispositivos pueden ser configurados, con relativa facilidad, por medio de un menú IVR (Interative Voice Response) o mediante un servidor web desde cualquier navegador**.

El menú IVR permite la configuración básica del dispositivo, como lo es la asignación de direcciones IP a cada terminal. La configuración avanzada de la pasarela VoIP, consiste en la asignación de los parámetros correspondientes para las funcionalidades de enrutador y otras asociadas a la voz. Esta configuración se realiza por medio de un navegador web. Dentro de los aspectos más relevantes de la configuración, destacan la **utilización de SIP como protocolo de señalización, la configuración de NAT (Network Address Translation) y demás funcionalidades de enrutamiento. Por otro lado, en la configuración de audio se puede seleccionar diferentes codecs**, por ejemplo G729, la cantidad de muestras por paquete y la supresión de silencio.

<div class="row mt-3" style="text-align: center">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="assets/img/TICs/what-is-voip/2.png" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Figura #2: Ejemplo de configuración de audio.
</div>
