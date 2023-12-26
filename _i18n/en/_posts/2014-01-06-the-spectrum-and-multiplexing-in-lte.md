---
layout: post
title:  The spectrum and multiplexing in LTE
date:   2014-01-06 06:00:00
description: Regarding the spectrum, LTE becomes quite flexible, allowing bandwidths of 1.25MHz, 1.6MHz, 2.5MHz, 5MHz, 10MHz, 15MHz and 20MHz in the downlink and uplink. Furthermore, it supports broadcast transmission in downlink and uplink-downlink modes, on the other hand, radio resources for broadcast transmissions can be modified according to the operator needs. Orthogonal Frequency Division Multiplexing (OFDM) is a frequency multiplexing scheme characterized by sending a certain amount of carrier frequencies in a specified bandwidth, each of these carriers, transports information using modulation schemes such as QAM or PSK (QPSK, 16QAM and 64QAM). One of the main advantages of this type of multiplexing is about the fading of signals, delays and in general against interference, also has excellent characteristics against multipath. Furthermore, with QAM and PSK modulations is possible to transmit more amount symbols per cycle.
tags: LTE 4G wireless multiplexing OFDM QAM PSK spectrum
categories: Networks
thumbnail: assets/img/TICs/el-espectro-y-la-multiplexion-en-LTE/2.jpg
---
## The spectrum

Regarding the spectrum, LTE becomes quite flexible, allowing **bandwidths** of $$1.25MHz$$, $$1.6MHz$$, $$2.5MHz$$, $$5MHz$$, $$10MHz$$, $$15MHz$$ and $$20MHz$$ in the downlink and uplink [4]. Furthermore, it supports broadcast transmission in downlink and uplink-downlink modes, on the other hand, **radio resources for broadcast transmissions can be modified** according to the operator needs.

The various scenarios which may present between the interaction of different service providers and other networks that they have, are not largely affected because manufacturers have planned **coexistence**, within the same geographic area, of the [EUTRAN with other networks such as 3G and coexistence between adjacent operators]({% post_url 2013-12-16-architecture-features-lte-sae %}), so too, is the case of the overlapping in **countries boundaries** [4].

The LTE spectral efficiency exceeds largely to HSPA +, these are the results of Telefónica [9], the study provides a scenario of urban centers with **high density of buildings**, $$2x2$$ MIMO antenna configuration for both cases and using $$64QAM$$ as modulation scheme, with this, the study says that **LTE spectral efficiency exceeds to HSPA +** by $$20%$$ at full load. It is apparent from Figure #1 than for rural or suburban centers LTE benefits will outweigh, furthermore along the chart, the LTE superiority is denoted.

<div class="row mt-3" style="text-align: center">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="assets/img/TICs/el-espectro-y-la-multiplexion-en-LTE/1.jpg" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Figure #1: Spectral efficiency in terms of resource use [9].
</div>

## Orthogonal Frequency Division Multiplexing (OFDM)

Orthogonal Frequency Division Multiplexing (OFDM) is a **frequency multiplexing scheme** characterized by sending a certain amount of carrier frequencies in a specified bandwidth [7-8], each of these carriers, transports information using **modulation schemes such as $$QAM$$ or $$PSK$$ ($$QPSK$$, $$16QAM$$ and $$64QAM$$)** [10]. One of the **main advantages** of this type of multiplexing is about the **fading of signals, delays and in general against interference**, [also has excellent characteristics against multipath]({% post_url 2013-11-25-general-aspects-of-propagation-on-lte %}). Furthermore, with $$QAM$$ and $$PSK$$ modulations is possible to transmit more amount symbols per cycle.

<div class="row mt-3" style="text-align: center">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="assets/img/TICs/el-espectro-y-la-multiplexion-en-LTE/2.jpg" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Figure #2: Representation of frequency and time for an OFDM signal [7].
</div>

The different frequencies ($$n-th$$) called **sub-carriers**, in Figure #2, must have equal spacing between them, and should remain constant in order to avoid the signal overlapping which cause interference between them. This separation between sub-carriers is given by the following expression [7]:

$$
\frac{\vert \omega_{n} - \omega_{n-1} \vert}{2\pi} = \Delta f, n \in [1, N-1]
$$

Where $$w$$ is the frequency, $$n$$ the number of subcarriers and $$f$$ the separation between them.

For this, the 3GPP has defined a separation between OFDM channels, it is known as a **guard band or guard interval** and aims to create a distance between adjacent frequency channels **to avoid interference between them**. In the practice, we cancel the transmission of a number of sub-carriers in the spectrum section where the channel ends and the next begins, repeating at the top and bottom of the channel, thus reducing the usable bandwidth per channel, seen Figure #3.

<div class="row mt-3" style="text-align: center">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="assets/img/TICs/el-espectro-y-la-multiplexion-en-LTE/3.jpg" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Figure #3: Inactive sub-carriers for an OFDM channel [7].
</div>

Overall, the study by the 3GPP [7] discussed the feasibility of using OFDM for downlink UTRAN and validates their inclusion, it says that **OFDM improves performance compared to HSDPA** Realease 5, however, the introduction of a more advanced and more complex system, such as OFDM, does not generate a significant difference in performance at the receiver side, and therefore, **only recommended for the downlink**.

## References

1. Ericsson , Gerhard, Fritze, SAE - The Core Network for LTE , 2008
2. Nortel, Long-Term Evolution (LTE): The vision beyond 3G, 2008
3. Motorola, long Term Evolution (LTE): A Technical Overview, 2010
4. 3GPP 25.913, Requirements for Evolved UTRA (E-UTRA) and Evolved UTRAN (E-UTRAN) (Release 8), 2008
5. Santosh KD, LTE Whitepaper, 2009
6. 3GPP 36.300, EUTRA and EUTRAN overall description, Stage 2, 2009
7. 3GPP 25.892, Multiplexing (OFDM) for UTRAN enhancement (Release 6), 2004
8. Rohde &amp; Schwarz, UMTS Long Term Evolution (LTE) Tecnologi Introduccion, 2007
9. Telefónica I+D, ¿Qué podemos esperar de LTE? Ventajas y prestaciones, 2010
10. [http://www.3gpp.org/LTE](http://www.3gpp.org/LTE)
11. [http://sociedadinformacion.fundacion.telefonica.com/DYC/SHI/seccion=1188&amp;idioma=es_ES&amp;id=2009100116310140&amp;activo=4.do?elem=7096](http://sociedadinformacion.fundacion.telefonica.com/DYC/SHI/seccion=1188&amp;idioma=es_ES&amp;id=2009100116310140&amp;activo=4.do?elem=7096)
12. [http://www.gradiant.org/index.php?option=com_content&amp;view=article&amp;id=289:mimo-en-wimax-y-lte&amp;catid=1:noticias&amp;Itemid=7&amp;lang=es](http://www.gradiant.org/index.php?option=com_content&amp;view=article&amp;id=289:mimo-en-wimax-y-lte&amp;catid=1:noticias&amp;Itemid=7&amp;lang=es)
