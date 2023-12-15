---
layout: post
title:  ¿Cómo obtener un modelo de tráfico para VoIP?
date:   2014-03-06 06:00:00
description: En este artículo se describe como obtener un modelo de tráfico para voip, el cual es bastante sencillo de interpretar y facilitará algunas de las cosas que se deben hacer.
tags: modelado-de-tráfico voip multimedia
categories: Research
---
<p>
<span style="font-family: arial, helvetica, sans-serif; font-size: 14px;">Para realizar las estimaciones del modelo de tr&aacute;fico para flujos multimedia, es necesario que el investigador tenga un control preciso del entorno de pruebas, minimizando los posibles errores e interferencia que puedan presentarse, dejando un escenario de pruebas que permita un desarrollo fluido a la aplicaci&oacute;n que se dese modelar. <strong>A modo de ejemplo se ha seleccionado un tr&aacute;fico de <a href="es/biblioteca/servicios/item/65-que-es-voip">VoIP</a></strong>, el cual es bastante sencillo de interpretar y facilitar&aacute; algunas de las cosas que se deben hacer.</span></p>
<p>
&nbsp;</p>
<h1>
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;">Escenario para las pruebas</span></span></h1>
<p>
<span style="font-family: arial, helvetica, sans-serif; font-size: 14px;"><strong>En la <span style="color:#0000ff;">Figura # 1</span> se muestra el diagrama utilizado para realizar las pruebas con la finalidad de obtener el modelo del tr&aacute;fico en la transmisi&oacute;n de voz sobre IP</strong>. En este caso, utilizaremos un <em>gateway</em> de voz sobre IP <em>Linksys SPA 3102</em>, con el fin de conectar un sistema telef&oacute;nico convencional con una red IP y viceversa. Un sniffer permite la captura del tr&aacute;fico que circula por la red para su posterior an&aacute;lisis.</span></p>
<p style="text-align: center;">
&nbsp;</p>
<p style="text-align: center;">
<img alt="" src="images/Research/como-obtener-modelo-trafico-voip/1.png" style="height: 332px; width: 500px;" /></p>
<p style="text-align: center;">
<span style="font-family: arial, helvetica, sans-serif; font-size: 14px; color: rgb(0, 0, 255);"><strong>Figura # 1</strong></span><span style="font-family: arial, helvetica, sans-serif; font-size: 14px;">: Escenario utilizado para determinar el tr&aacute;fico de voz.</span></p>

<h1>
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;">Procedimiento</span></span></h1>
<p>
<span style="font-family: arial, helvetica, sans-serif; font-size: 14px;"><strong>En primer lugar, se debe configurar el <em>gateway</em></strong>, esto se hace con relativa facilidad por medio de un men&uacute; IVR (<em>Interative Voice Response</em>) o mediante cualquier navegador de Internet. Los aspectos m&aacute;s relevantes de la configuraci&oacute;n son: la utilizaci&oacute;n de SIP (<em>Session Initiation Protocol</em>) como protocolo de se&ntilde;alizaci&oacute;n, asignaci&oacute;n de direcciones IP a cada pasarela y la desactivaci&oacute;n de NAT (<em>Network Address Translation</em>). Para la configuraci&oacute;n de audio: uso del codec G.729, una paquetizaci&oacute;n de dos muestras por paquete y no se realiza supresi&oacute;n de silencio.</span></p>
<p>
<strong style="font-family: arial, helvetica, sans-serif; font-size: 14px;">Despu&eacute;s de la configuraci&oacute;n de los equipos se lanza el sniffer</strong><span style="font-family: arial, helvetica, sans-serif; font-size: 14px;"> para poder realizar la captura del tr&aacute;fico, </span><strong style="font-family: arial, helvetica, sans-serif; font-size: 14px;">posteriormente, se realiza una llamada entre los terminales</strong><span style="font-family: arial, helvetica, sans-serif; font-size: 14px;">. Mediante el sniffer se realiza la captura de paquetes mientras la llamada est&aacute; en curso y se almacenan los datos para su posterior an&aacute;lisis.</span></p>
<p>
&nbsp;</p>
<h1>
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;">Modelo de VoIP</span></span></h1>
<p>
<span style="font-family: arial, helvetica, sans-serif; font-size: 14px;">Analizando la captura realizada, con alguna de las herramientas recomendadas <a href="es/laboratorio/herramientas/item/30-las-2-mejores-herramientas-para-la-captura-y-la-interpretacion-de-datos-de-red">para la captura e interpretaci&oacute;n de datos de red</a>, <strong>se puede reconstruir la distribuci&oacute;n de los encabezados de cada uno de los paquetes capturados</strong> y de esta manera deducir la <span style="color:#0000ff;"><strong>Figura # 2</strong></span>.</span></p>
<p style="text-align: center;">
&nbsp;</p>
<p style="text-align: center;">
<img alt="" src="images/Research/como-obtener-modelo-trafico-voip/2_es.png" /></p>
<p style="text-align: center;">
<span style="font-family: arial, helvetica, sans-serif; font-size: 14px; color: rgb(0, 0, 255);"><strong>Figura # 2</strong></span><span style="font-family: arial, helvetica, sans-serif; font-size: 14px;">: Descripci&oacute;n de los encabezados de cada paquete para el tr&aacute;fico de voz.</span></p>
<p style="text-align: center;">
&nbsp;</p>
<p>
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;">Como se puede observar, <strong>VoIP utiliza el protocolo RTP (Real-Time TRansport Protocol) para la transmisi&oacute;n de datos en tiempo real y este se transporta por medio de UDP</strong>, la <span style="color:#0000ff;"><strong>Figura # 2</strong></span> permite comprobar la utilizaci&oacute;n de los protocolos mencionados. <strong>Se destaca en el an&aacute;lisis de la captura de paquetes realizada, que la transmisi&oacute;n de cada uno de los paquetes tiene una distribuci&oacute;n constante (no se presentan r&aacute;fagas de paquetes)</strong>. Adem&aacute;s, se confirma que cada terminal realiza el env&iacute;o de paquetes cada 20 ms y que el contenido de datos de dichos paquetes corresponde con el tipo de codec utilizado (G.729) y la cantidad de muestras que se definieron en la configuraci&oacute;n de cada gateway (dos muestras por paquete).</span></span></p>
<p>
<span style="font-family: arial, helvetica, sans-serif; font-size: 14px;">Un aspecto importante de tener en cuenta para un modelo de tr&aacute;fico es el tiempo, o la variaci&oacute;n de &eacute;ste, en el cual cada paquete es enviado. Para ello es necesario extraer del fichero de traza, el tiempo entre los inicios (o llegadas) de cada paquete. En la <span style="color:#0000ff;"><strong>Figura # 3</strong></span> se puede observar la variaci&oacute;n de la duraci&oacute;n de cada paquete, para el tr&aacute;fico enviado y recibido de voz en funci&oacute;n del tiempo de transmisi&oacute;n. <strong>Para las muestras tomadas en este caso, se obtiene un tiempo medio de env&iacute;o de paquetes de 20 ms con una desviaci&oacute;n est&aacute;ndar de 0.62 ms. Cada conexi&oacute;n de este flujo tiene un consumo de ancho de banda a nivel IP BW=(60X8)/20X10<sup>-3</sup>, lo que equivale a 24 Kbps</strong>.</span></p>
<p>
&nbsp;</p>
<p style="text-align: center;">
<img alt="" src="images/Research/como-obtener-modelo-trafico-voip/3_es.png" style="font-size: 13px; height: 542px; width: 500px;" /></p>
<p style="text-align: center;">
<span style="font-family: arial, helvetica, sans-serif; font-size: 14px; color: rgb(0, 0, 255);"><strong>Figura # 3</strong></span><span style="font-family: arial, helvetica, sans-serif; font-size: 14px;">: Detalle del tiempo entre los inicios de cada paquete para el tr&aacute;fico de voz.</span></p>
<p style="text-align: center;">
&nbsp;</p>
<h1>
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;">Conclusi&oacute;n</span></span></h1>
<p>
<span style="font-family: arial, helvetica, sans-serif; font-size: 14px;">El modelo de la transmisi&oacute;n de voz es relativamente sencillo y estable en cuanto a tiempos y tama&ntilde;os ya que <strong>no presenta un comportamiento de r&aacute;fagas, o bien, puede verse como una sola. Generar un flujo IP de este tipo consiste en el env&iacute;o de paquetes de 60 bytes (incluyendo las cabeceras) cada 20 ms con una desviaci&oacute;n est&aacute;ndar de 0.62 ms, esto si, se utiliza el codec G.729 y una paquetizaci&oacute;n de dos muestras por paquete</strong>. En el caso de que sea necesario cambiar el codec o la cantidad de muestras por paquete, los cambios son sencillos de hacer. Para este caso, se debe tener en cuenta la frecuencia de muestreo definida por el nuevo codec utilizado y la cantidad de muestras que se quieren empaquetar, las cuales se incluir&iacute;an despu&eacute;s del encabezado RTP.</span></p>
<p>
&nbsp;</p>