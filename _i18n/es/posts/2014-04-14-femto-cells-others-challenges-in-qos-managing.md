---
layout: post
title:  Femtoceldas otros desafíos en la gestión de la QoS
date:   2014-04-17 05:00:00
description: La transmisión de un paquete de información por una red IP es susceptible a retardos, de este modo las femto-celdas podrían experimentarán problemas para obtener una base de tiempo que sea inmune al jitter. Los operadores deberían de garantizar el concepto de QoS en femto-celdas, los parámetros establecidos en estos escenarios debe ser comparables a los ofrecidos por las macro-celdas.
tags: femtoceldas LTE 4G
categories: QoS
---
<h1>
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;">Gestión de la calidad de servicio</span></span></h1>
<p>
<span style="font-family: arial, helvetica, sans-serif; font-size: 14px;">Un punto importante en cuanto a brindar <strong>QoS es reducir la señalización y las interferencias</strong>. Con esto, los operadores puedan gestionar adecuadamente los recursos sin este tipo de problemas, con la finalidad de mejorar los servicios que dan a los usuarios.</span></p>
<p>
<span style="font-family: arial, helvetica, sans-serif; font-size: 14px;">En este nuevo escenario, el tráfico que se genera del UE hacia el eNodeB es desviado por una red IP antes de llegar a la red móvil. <strong>La transmisión de un paquete de información por una red IP es susceptible a retardos, de este modo las femto-celdas podrían experimentarán problemas para obtener una base de tiempo que sea inmune al jitter</strong>. <strong>Los operadores deberían de garantizar el concepto de QoS en femto-celdas</strong>, los parámetros establecidos en estos escenarios debe ser comparables a los ofrecidos por las macro-celdas.</span></p>

<p>
<span style="font-family: arial, helvetica, sans-serif; font-size: 14px;">Otro de los aspectos que destacan en la implementación de femto-celdas, es como asegurar ciertos parámetros de calidad de servicio que son necesarios para el tráfico sensible al retardo. Sin olvidar, que las soluciones que se brinden deben proveer suficiente capacidad para no provocar un cuello de botella en ciertos puntos críticos de la red, ya que la línea de banda ancha que utilizan las femto-celdas es compartida con otros servicios propios del usuario. Además, los problemas encontrados por Telefónica (mencionados anteriormente) pueden provocar una degradación de la calidad del servicio brindado a los usuarios en entornos donde se encuentran redes Wi-Fi cercanas, en este aspecto los operadores deben tener mucho cuidado al brindar soluciones de este tipo, ya que lo más usual es que los suscriptores implementen redes inalámbricas dentro de las viviendas para el acceso a Internet.</span></p>
<p>
&nbsp;</p>
<h1>
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;">Sincronización, temporización y otros aspectos</span></span></h1>
<p>
<span style="font-family: arial, helvetica, sans-serif; font-size: 14px;">Las femto-celdas necesitan sincronización para poder alinear las señales recibidas y así minimizar las interferencias, además, de garantizar una portadora aceptable. Por otro lado, <strong>las macro-celdas y femto-celdas deben estar debidamente sincronizadas para poder realizar handoff ya que sin una coordinación centralizada</strong> este trabajo se dificulta más. Además, sin una temporización adecuada las transmisiones de las diversas celdas pueden presentar solapamientos, ya que la falta de una referencia entre las femto-celdas generarían variaciones en los instantes de transmisión y recepción, de tal manera, que el enlace ascendente de una de las celdas pueda superponerse con el enlace descendente de la otra y viceversa.</span></p>
<p>
<span style="font-family: arial, helvetica, sans-serif; font-size: 14px;">La movilidad es uno de los aspectos que deben ser gestionados con mucho cuidado, ya que <strong>el usuario no debería percibir la complejidad de la infraestructura de acceso, ni de los procedimientos necesarios para llevar a cabo la movilidad y mucho menos tener alguna intervención</strong>. Sin embargo, los crecientes despliegues de femto-celdas y en particular las técnicas de acceso y de gestión de la movilidad pueden provocar un incremento en la señalización necesaria para realizar un traspaso.</span></p>
<p>
<span style="font-family: arial, helvetica, sans-serif; font-size: 14px;">Otro de los aspectos que no queda claro hasta el momento son aspectos referentes a la portabilidad. El caso de las redes WiFi es más claro, ya que operan en una banda de frecuencias no licenciadas y por lo tanto los usuarios pueden trasladarla fácilmente, pero el caso de las femto-celdas no parece ser tan sencillo. Por un lado, operan en bandas de frecuencias licenciadas, de tal manera hacen uso de un espacio de frecuencias que ha sido asignado a un operador en específico. Por otro lado, si un usuario tiene contratado un servicio con un operador y traslada la femto-celda a cierta localidad donde dicho operador no tiene cobertura, y la cobertura en dicha zona la provee un segundo proveedor de servicios de telecomunicaciones, <strong>este escenario tiende a tener aspecto todavía no definidos con certeza</strong>.</span></p>
<p>
&nbsp;</p>
<h1>
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;">Referencias</span></span></h1>
<ol>
<li>
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;">Assen G, Mona M &amp; Leo BP. Femtocell Access Control Strategy in UMTS and LTE. IEEE Comunication Magazine (2009) 47: pp. 117-123.</span></span></li>
<li>
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;">G DLR, A V, D L &amp; Jie Z. Access control Mechanisms for Femtocells. IEEE Communications Magazine (2010) 48: pp. 33-39.</span></span></li>
</ol>