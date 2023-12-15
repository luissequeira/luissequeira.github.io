---
layout: post
title:  Características de la arquitectura LTE/SAE
date:   2013-12-19 06:00:00
description: La cuarta generación de telefonía móvil (4G), es muy común que los que nos gusta estar actualizados, nos interesemos por aspectos generales de la arquitectura de esta nueva tecnología. Pues bien, “System Architecture Evolution” (SAE) o también conocida como EPC (“Evolved Packed Core”) tiene su desarrollo a partir del año 2004 y hasta el 2009, durante ese tiempo se han desarrollado estudios que han permitido realizar los estándares que definen la arquitectura del núcleo de la red.
tags: LTE 4G wireless red red-de-acceso arquitectura
categories: LTE (4G)
---
<p>
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;">Con tanta información que surge día a día entorno a la <a href="index.php/es/tecnologias-de-la-informacion/lte-4g/item/31-que-es-4g-y-cuales-son-las-caracteristicas-tecnicas-mas-importantes.html"><strong>cuarta generación de telefonía móvil (4G)</strong></a>, es muy común que los que nos gusta estar actualizados, nos interesemos por aspectos generales de la <strong>arquitectura de esta nueva tecnología</strong>. Pues bien, “System Architecture Evolution” (SAE) o también conocida como EPC (“Evolved Packed Core”) tiene su desarrollo a partir del año 2004 y hasta el 2009, durante ese tiempo se han desarrollado estudios que han permitido realizar los estándares que definen la arquitectura del núcleo de la red. Las especificaciones pueden verse de manera cronológica en la siguiente figura:</span></span></p>
<p>
&nbsp;</p>
<p style="text-align: center;">
<img alt="" src="images/TICs/caracteristicas-de-la-arquetectura-LTE/1.jpg" /></p>
<p style="text-align: center;">
<span style="font-family: arial, helvetica, sans-serif; font-size: 14px; color: rgb(0, 0, 255);"><strong>Figura # 1</strong></span><span style="font-family: arial, helvetica, sans-serif; font-size: 14px;">: Evolución de SAE </span><strong style="font-family: arial, helvetica, sans-serif; font-size: 14px;"><span style="color:#ff8c00;">[1]</span></strong><span style="font-family: arial, helvetica, sans-serif; font-size: 14px;">.</span></p>

<p>
<span style="font-family: arial, helvetica, sans-serif; font-size: 14px;">La arquitectura SAE presenta varias <strong>ventajas</strong> con respecto a las tecnologías que se han desarrollado anteriormente para redes celulares, <strong>mejorando la latencia, el throughput y la capacidad de la red</strong>, además, el núcleo de la red presenta simplicidad en la arquitectura, optimiza el tráfico de los servicios, los cuales son <strong>totalmente basados en IP</strong>. De una manera muy simplificada se puede describir la arquitectura LTE como se puede apreciar en la </span><strong style="font-family: arial, helvetica, sans-serif; font-size: 14px;"><span style="color:#0000ff;">Figura # 2</span></strong><span style="font-family: arial, helvetica, sans-serif; font-size: 14px;">, donde se observa la interacción de los eNodosB, a través de una red IP, con los gateway's que proporcionan comunicación y accesos a diversos servicios o redes, permitiendo una interacción entre la parte móvil y las otras redes con las que cuenta el ISP o incluso externas.</span></p>
<p>
&nbsp;</p>
<p style="text-align: center;">
<img alt="" src="images/TICs/caracteristicas-de-la-arquetectura-LTE/2.jpg" /></p>
<p style="text-align: center;">
<strong style="font-family: arial, helvetica, sans-serif; font-size: 14px;"><span style="color:#0000ff;">Figura # 2</span></strong><span style="font-family: arial, helvetica, sans-serif; font-size: 14px;">: Arquitectura LTE </span><strong style="font-family: arial, helvetica, sans-serif; font-size: 14px;"><span style="color:#ff8c00;">[2]</span></strong><span style="font-family: arial, helvetica, sans-serif; font-size: 14px;">.</span></p>
<p style="text-align: center;">
&nbsp;</p>
<p>
<span style="font-family: arial, helvetica, sans-serif; font-size: 14px;">La arquitectura LTE consta de <strong>dos partes</strong> (ver </span><strong style="font-family: arial, helvetica, sans-serif; font-size: 14px;"><span style="color:#0000ff;">Figura # 3</span></strong><span style="font-family: arial, helvetica, sans-serif; font-size: 14px;">) la EPC y la EUTRAN (Envolved UTRAN). La EUTRAN es la parte de la red que se encarga de todas la funciones relacionadas a la <strong>interfaz de radio y el control de los móviles</strong>, por otro lado, la EPC brinda <strong>acceso a otras redes de paquetes IP</strong>, además, es aquí donde se gestiona los aspectos relacionados a la seguridad, calidad de servicio, gestión de recursos y movilidad </span><strong style="font-family: arial, helvetica, sans-serif; font-size: 14px;"><span style="color:#ff8c00;">[1]</span></strong><span style="font-family: arial, helvetica, sans-serif; font-size: 14px;">.</span></p>
<p>
&nbsp;</p>
<p style="text-align: center;">
<img alt="" src="images/TICs/caracteristicas-de-la-arquetectura-LTE/3.jpg" /></p>
<p style="text-align: center;">
<strong style="font-family: arial, helvetica, sans-serif; font-size: 14px;"><span style="color:#0000ff;">Figura # 3</span></strong><span style="font-family: arial, helvetica, sans-serif; font-size: 14px;">: Arquitectura LTE simplificada </span><strong style="font-family: arial, helvetica, sans-serif; font-size: 14px;"><span style="color:#ff8c00;">[1]</span></strong><span style="font-family: arial, helvetica, sans-serif; font-size: 14px;">.</span></p>
<p style="text-align: center;">
&nbsp;</p>
<p>
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;">La EUTRAN está compuesta por los eNodosB (ver <strong><span style="color:#0000ff;">Figura # 4</span></strong>) <strong>brindando aspectos de control de móviles y el manejo del medio</strong>, estos elementos de red se interconectan entre ellos por medio de interfaces X2, los eNodeB interactúan con la EPC por medio de los MME (“Mobility Management Entity”) con interfaces S1 para el <strong>control de la movilidad</strong>, gestión y otros aspectos. Ambas son interfaces IP que además usan el protocolo SCTP (“Stream Control Transmission Protocol”) <span style="color:#ff8c00;"><strong>[5]</strong></span>. Por otro lado, algunas de las funciones del eNodeB son <strong><span style="color:#ff8c00;">[6]</span></strong>:</span></span></p>
<ul>
<li>
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;"><strong>Funciones de gestión de recursos de radio</strong> como conexión, control de admisión de radio, control de movilidad en el plano de usuario.</span></span></li>
<li>
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;"><strong>Compresión de encabezados IP</strong> y encripción de datos de usuario.</span></span></li>
<li>
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;"><strong>Enrutamiento</strong> en el plano de usuario.</span></span></li>
<li>
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;"><strong>Transmisión</strong> de información broadcast.</span></span></li>
<li>
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;"><strong>Reportes de configuración</strong> para movilidad.</span></span></li>
</ul>
<p>
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;">Las funciones de la MME son las siguientes <strong><span style="color:#ff8c00;">[6]</span></strong>:</span></span></p>
<ul>
<li>
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;"><strong>Proveer señalización</strong>, seguridad y control de la seguridad.</span></span></li>
<li>
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;">Proveer señalización entre los nodos para <strong>gestionar la movilidad</strong> entre nodos.</span></span></li>
<li>
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;">Es el encargado de <strong>administrar tarifas</strong> para cobros.</span></span></li>
<li>
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;">Gestiona la <strong>movilidad entre otras redes</strong> como 2G y 3G.</span></span></li>
</ul>
<p>
&nbsp;</p>
<p style="text-align: center;">
<img alt="" src="images/TICs/caracteristicas-de-la-arquetectura-LTE/4.jpg" /></p>
<p style="text-align: center;">
<strong style="font-family: arial, helvetica, sans-serif; font-size: 14px;"><span style="color:#0000ff;">Figura # 4</span></strong><span style="font-family: arial, helvetica, sans-serif; font-size: 14px;">: Interfaces entre eNodeB y MME </span><strong style="font-family: arial, helvetica, sans-serif; font-size: 14px;"><span style="color:#ff8c00;">[1]</span></strong><span style="font-family: arial, helvetica, sans-serif; font-size: 14px;">.</span></p>
<p style="text-align: center;">
&nbsp;</p>
<p>
<span style="font-family: arial, helvetica, sans-serif; font-size: 14px;">Una visión más amplia de la arquitectura planteada por LTE se muestra en la </span><strong style="font-family: arial, helvetica, sans-serif; font-size: 14px;"><span style="color:#0000ff;">Figura # 5</span></strong><span style="font-family: arial, helvetica, sans-serif; font-size: 14px;">, donde se aprecia la interacción de LTE con <strong>diversos tipos de redes</strong> como GSM, UMTS, IP y otras. En color naranja se presenta los bloques funcionales que representan los elementos que conforman la SAE, los cuales son: los eNodosB, MME y SAE GW (también denominado SWG, “Serving Gateway”), en este último bloque se han incluido el PGW (PDN Gateway, “Public Data Network Gateway”). El dicha figura las líneas continuas representan el <strong>flujo de datos</strong> por medio de las interfaces correspondientes y con líneas discontinuas se representa la <strong>señalización</strong> entre los diferentes bloques funcionales o equipos.</span></p>
<p>
&nbsp;</p>
<p style="text-align: center;">
<img alt="" src="images/TICs/caracteristicas-de-la-arquetectura-LTE/5.jpg" /></p>
<p style="text-align: center;">
<strong style="font-family: arial, helvetica, sans-serif; font-size: 14px;"><span style="color:#0000ff;">Figura # 5</span></strong><span style="font-family: arial, helvetica, sans-serif; font-size: 14px;">: Arquitectura LTE interconectada con otras redes </span><strong style="font-family: arial, helvetica, sans-serif; font-size: 14px;"><span style="color:#ff8c00;">[1]</span></strong><span style="font-family: arial, helvetica, sans-serif; font-size: 14px;">.</span></p>
<p style="text-align: center;">
&nbsp;</p>
<p>
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;">El MME obtiene información del abonado a través de la información almacenada en el HSS para autorizar al usuario a los servicios a los que tiene acceso. <strong>El MME autentica, autoriza y selecciona el PDN (“Public Data Network”)</strong> apropiado para establecer el enlace entre el EUTRAN a las redes o servicios externos, al mismo tiempo <strong>gestiona la movilidad y obtiene información de cobro</strong>. El MME proporciona conectividad entre el eNodoB y una red GSM o UMTS a través del SGSN (“Serving GPRS Support Node”). En general se puede decir que MME tiene toda la responsabilidad por las operaciones concernientes al <strong>plano de control</strong>, además, es el primer contacto de LTE con GSM o UMTS</span></span></p>
<p>
<span style="font-family: arial, helvetica, sans-serif; font-size: 14px;">El SGW es controlado por el MME, es un punto donde se monitorizan las políticas de conexión y servicio establecidas en el PCRF (“Policy and Charging Rules Function”) para poder <strong>administrar QoS</strong>, además, es responsable de la organización del tráfico y los buffers para almacenamiento de paquetes. <strong>El PGW gestiona la asignación de direcciones IP</strong> a los UE (“User Equipment”), tiene que ver con todo lo relacionada a la inspección de paquete IP y realiza las funciones que en GSM realizaba el GGSN (“Gateway GPRS Support Node”) pero además tiene la función de <strong>control de la movilidad</strong>. Por otro lado, el <strong>HSS almacena y administra</strong> todo lo relativo a los datos de suscripciones de los usuarios.</span></p>
<p>
&nbsp;</p>
<h2>
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;">Referencias</span></span></h2>
<ol>
<li>
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;">Ericsson , Gerhard, Fritze, SAE - The Core Network for LTE , 2008</span></span></li>
<li>
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;">Nortel, Long-Term Evolution (LTE): The vision beyond 3G, 2008</span></span></li>
<li>
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;">Motorola, long Term Evolution (LTE): A Technical Overview, 2010</span></span></li>
<li>
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;">3GPP 25.913, Requirements for Evolved UTRA (E-UTRA) and Evolved UTRAN (E-UTRAN) (Release 8), 2008</span></span></li>
<li>
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;">Santosh KD, LTE Whitepaper, 2009</span></span></li>
<li>
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;">3GPP 36.300, EUTRA and EUTRAN overall description, Stage 2, 2009</span></span></li>
<li>
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;">3GPP 25.892, Multiplexing (OFDM) for UTRAN enhancement (Release 6), 2004</span></span></li>
<li>
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;">Rohde &amp; Schwarz, UMTS Long Term Evolution (LTE) Tecnologi Introduccion, 2007</span></span></li>
<li>
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;">Telefónica I+D, ¿Qué podemos esperar de LTE? Ventajas y prestaciones, 2010</span></span></li>
<li>
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;"><a href="http://www.3gpp.org/LTE">http://www.3gpp.org/LTE</a></span></span></li>
<li>
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;"><a href="http://sociedadinformacion.fundacion.telefonica.com/DYC/SHI/seccion=1188&amp;idioma=es_ES&amp;id=2009100116310140&amp;activo=4.do?elem=7096">http://sociedadinformacion.fundacion.telefonica.com/DYC/SHI/seccion=1188&amp;idioma=es_ES&amp;id=2009100116310140&amp;activo=4.do?elem=7096</a></span></span></li>
<li>
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;"><a href="http://www.gradiant.org/index.php?option=com_content&amp;view=article&amp;id=289:mimo-en-wimax-y-lte&amp;catid=1:noticias&amp;Itemid=7&amp;lang=es">http://www.gradiant.org/index.php?option=com_content&amp;view=article&amp;id=289:mimo-en-wimax-y-lte&amp;catid=1:noticias&amp;Itemid=7&amp;lang=es</a></span></span></li>
</ol>