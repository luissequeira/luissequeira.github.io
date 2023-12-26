---
layout: post
title:  LTE data transmission techniques
date:   2014-01-20 06:00:00
description: Duplex Systems transmission LTE-FDD and LTE-TDD. FDD (Frequency Division Duplex) is a scheme of transmitting and receiving signals, this system allows full duplex communication using two different frequencies. TDD (Time Division Duplex) is another multiplexing technique for communication that uses a single channel or frequency, for information transmission. The modulation technique and channel coding is one of the important points of the LTE speed ranges. This new model of mobile network uses AMC (Adaptive Modulation and Coding)
tags: LTE 4G FDD TDD wireless propagation modulation coding transmission
categories: Networks Innovation
thumbnail: assets/img/TICs/tecnicas-para-la-transmision-de-datos-en-LTE/1.jpg
---
## Duplex Systems transmission: LTE-FDD and LTE-TDD

FDD (Frequency Division Duplex) is a **scheme of transmitting and receiving signals**, this system allows **full duplex communication** using two different frequencies, one for the downlink and one for uplink, maintaining a [separation band between said frequencies]({% post_url 2014-01-06-the-spectrum-and-multiplexing-in-lte %}) in order **not overlap of channels**<, it makes that the FDD spectral efficiency is not very good. However, one advantage of this multiplexing scheme is that it does **not introduce additional delays or latency**.

On the other hand, TDD (Time Division Duplex) is another multiplexing technique for communication that uses a **single channel or frequency**, for information transmission. In this case, the transmission and reception is performed by the same frequency but with differences in time and **a temporal separation between the two directions of communication**, making more efficient use of spectrum. The TDD multiplexing takes a temporary assignment to the communication directions, and the guard time, which **makes it more sensitive to delays and latency**.

Some comparisons:

- **Regarding FDD distance** has better characteristics at longer distances than TDD, so TDD has more acceptation in scenarios where distances are shorter.
- **The signal propagation also has different characteristics**, since TDD uses a single frequency, this makes the channel as such, presents the same characteristics in transmission and reception.
- In FDD each **channel has different propagation characteristics** depending on the frequency used.
- The frequency difference of the FDD channels, causes that **the capacity of each channel depends on the frequency** allocated by regulatory authorities.
- In TDD is **easier to make a dynamic distribution** of the uplink and downlink capacity in order to meet the demand characteristics of resources.

Figure #1 shows the frequency assignments set by 3GPP for the use of TDD and FDD:

<div class="row mt-3" style="text-align: center">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="assets/img/TICs/tecnicas-para-la-transmision-de-datos-en-LTE/1.jpg" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Figure #1: Frequency bands for LTE FDD and TDD [1].
</div>

## Modulation and Coding

The modulation technique and channel coding is one of the **important points of the [LTE]({% post_url 2013-11-04-what-is-4g-and-what-are-the-most-important-technical-characteristics %}) speed ranges**. This new model of mobile network uses AMC (Adaptive Modulation and Coding) [9], this technique **consist in to assess the conditions of the radio channel** and using different channel coding and modulation schemes. The process for selecting the **optimal modulation and coding scheme** is carried out in coordination with the "fast scheduling". Modulation schemes are $$QPSK$$, $$16QAM$$ and $$64QAM$$.

<div class="row mt-3" style="text-align: center">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="assets/img/TICs/tecnicas-para-la-transmision-de-datos-en-LTE/2.jpg" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Figure #2: Constellation diagrams for 16QAM and 64QAM.
</div>

In [LTE]({% post_url 2013-11-04-what-is-4g-and-what-are-the-most-important-technical-characteristics %}), the channel coding is called HARQ ("Fast Hybrid ARQ, Fast Hybrid Automatic Repeat Request"), it is a combination of FEC + ARQ, if a frame can not be corrected, then a re-transmission is requested. For the case the damaged frames that have been corrected by the FEC **are not discarded**, but they are kept to be combined with other successive damaged frames to produce a correct one, this is based on the principle that for two successive frames, containing the same information, **the probability of having the same error bit is very low, so that the probability of reconstructing a packet without error from the previous two is high**. The error correction mechanisms are implemented in the eNodeB.

## References

1. Ericsson , Gerhard, Fritze, SAE - The Core Network for LTE , 2008
2. Nortel, Long-Term Evolution (LTE): The vision beyond 3G, 2008
3. Motorola, long Term Evolution (LTE): A Technical Overview, 2010
4. 3GPP 25.913, Requirements for Evolved UTRA (E-UTRA) and Evolved UTRAN (E-UTRAN) (Release 8), 2008
5. Santosh KD, LTE Whitepaper, 2009
6. 3GPP 36.300, EUTRA and EUTRAN overall description, Stage 2, 2009
7. 3GPP 25.892, Multiplexing (OFDM) for UTRAN enhancement (Release 6), 2004
8. Rohde & Schwarz, UMTS Long Term Evolution (LTE) Tecnologi Introduccion, 2007
9. Telefónica I+D, ¿Qué podemos esperar de LTE? Ventajas y prestaciones, 2010
10. [http://www.3gpp.org/LTE](http://www.3gpp.org/LTE)
11. [http://sociedadinformacion.fundacion.telefonica.com/DYC/SHI/seccion=1188&amp;idioma=es_ES&amp;id=2009100116310140&amp;activo=4.do?elem=7096](http://sociedadinformacion.fundacion.telefonica.com/DYC/SHI/seccion=1188&amp;idioma=es_ES&amp;id=2009100116310140&amp;activo=4.do?elem=7096)
12. [http://www.gradiant.org/index.php?option=com_content&amp;view=article&amp;id=289:mimo-en-wimax-y-lte&amp;catid=1:noticias&amp;Itemid=7&amp;lang=es](http://www.gradiant.org/index.php?option=com_content&amp;view=article&amp;id=289:mimo-en-wimax-y-lte&amp;catid=1:noticias&amp;Itemid=7&amp;lang=es)
