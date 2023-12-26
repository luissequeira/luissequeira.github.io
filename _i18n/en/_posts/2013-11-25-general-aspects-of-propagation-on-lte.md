---
layout: post
title:  General aspects of propagation on LTE
date:   2013-11-25 06:00:00
description: The Propagation of radio signals has a number of inherent problems of electromagnetic waves, of which LTE or 4G is not exempt. Aspects such as absorption, refraction, diffraction, fading, and other properties can cause serious problems of coverage, interference, and general degradation of the transmitted signal. Some of these parameters are largely unpredictable, mainly those arising from meteorological phenomena or the ground, and therefore, fewer steps may be taken in such cases.
tags: LTE 4G wireless propagation multipath
categories: Networks
thumbnail: assets/img/TICs/aspectos-generales-de-propagacion-en-LTE/1.jpg
---
The propagation of radio signals has a number of inherent problems of electromagnetic waves, of which [LTE or 4G]({% post_url 2013-11-04-what-is-4g-and-what-are-the-most-important-technical-characteristics %}) is not exempt. Aspects such as **absorption, refraction, diffraction, fading**, and other properties can cause serious problems of coverage, interference, and general degradation of the transmitted signal. Some of these parameters are largely **unpredictable**, mainly those arising from **meteorological phenomena or the ground**, and therefore, fewer steps may be taken in such cases.

Moreover, the **free space loss** (FSL) is directly related to the **system operating frequency and the distance between transmitter and receiver**. The case of [frequency is a parameter already defined for this type of technology]({% post_url 2014-01-06-the-spectrum-and-multiplexing-in-lte %}) by the International Telecommunication Union [1], also depends on the frequency assignments of each country, and therefore it is not something that operators can easily handle to increase the coverage of their mobile systems.

The case of **multipath is a problem** that is associated with the spread of radio beam by several pathways, supported by the phenomena of **reflection, diffraction and scattering**. This type of phenomenon produces a difference in the distance that a beam that travels with sight line over another who has suffered the effect of reflection (to name one example) and consequently there is a difference between the arrival times of the signals and the receiver, which may **cause the overlap of the signals at the receiving** antenna causing **inter-symbol interference (ISI)**, or too low power to be demodulated, it is also possible that even a given beam incident on the receiving antenna as shown in the following Figure #1.

<div class="row mt-3" style="text-align: center">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="assets/img/TICs/aspectos-generales-de-propagacion-en-LTE/1.jpg" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Figure #1: Multipath example.
</div>

Another problems that cause degradation of the transmitted signal are the effects of **penetration** in any type of building, every time the signal is refracted within the walls of a building or house will lose power, which translates into low signal received by the mobile or base station, depending on the direction of the link. Penetration has a significant impact in terms of mobile networks, because cells in LTE can have a typical coverage of $$30Km$$ [2] and [3] (even among $$5Km$$ to $$100km$$), this causes the power decreases while furthest from the EU ("User Equipment") from the eNodeB, this can be seen in Figure #2, where different micro-cells provide coverage for a given area, each of these micro-cell has its point of lower power signal near limits with other micro-cells. If we combine the scattering effects cited above and penetration in buildings or homes, it easily follows that the more far locations from the **transmitter power will have more problems** and therefore coverage within buildings.

<div class="row mt-3" style="text-align: center">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="assets/img/TICs/aspectos-generales-de-propagacion-en-LTE/2.jpg" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Figure #2: Set of micro-cells [4].
</div>

We might think that the only solution is to **increase the transmission power** to counter penetration losses, and in turn, would be used for a greater coverage, however, the power levels that a power station can radiate are **standardized** within of spectrum management policies for each country, in addition, increasing the transmit power would **cause an increase on the coverage area**, as mentioned previously, generating interference in the adjacent eNodeB and a degradation in the signal perceived by the user.

## Referencias

1. UIT, Disposiciones de frecuencias para la implementación de la componente terrenal de las telecomunicaciones móviles internacionales-2000 (IMT-2000), 2007.
2. Motorola, long Term Evolution (LTE): A Technical Overview, 2010
3. 3GPP 25.913, Requirements for Evolved UTRA (E-UTRA) and Evolved UTRAN (E-UTRAN) (Release 8), 2008
4. Vikram Chandrasekhar, Jeffrey G. Andrews, Alan Gatherer. Femtocell Networks: A Survey. Communications Magazine, IEEE, vol. 46, no. 9, pp. 59-67, 2008.