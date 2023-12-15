---
layout: post
title:  El funcionamiento del protocolo Kerberos
date:   2014-06-16 05:00:00
description: El protocolo de autenticación Kerberos permite a una serie de ordenadores demostrar su identidad entre ellos de una manera segura en una red insegura. El funcionamiento de dicho protocolo está basado en el protocolo Needham-Schroeder, el cual define un 'tercero de confianza.
tags: seguridad kerberos
categories: Security
---
<p>
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;"><strong>El protocolo de autenticaci&oacute;n Kerberos permite a una serie de ordenadores demostrar su identidad entre ellos</strong> de una manera segura en una red insegura. El funcionamiento de dicho protocolo est&aacute; basado en el protocolo Needham-Schroeder, el cual define un &#39;&#39;tercero de confianza&#39;&#39; denominado Centro de Distribuci&oacute;n de Claves (KDC). William Stallings en su libro Fundamentos de Seguridad de Redes: Aplicaciones y Est&aacute;ndares, Segunda Edici&oacute;n (pag. 394), define un KDC de la siguiente manera:</span></span></p>
<div class="demo-typo-col1">
<blockquote>
Sistema autorizado para transmitir claves de sesi&oacute;n temporales a usuarios. Cada clave de sesi&oacute;n se transmite cifrada, usando una clave maestra que el centro de distribuci&oacute;n de claves comparte con el usuario destino.<small>William Stallings</small></blockquote>
</div>
<p>
<span style="font-family: arial, helvetica, sans-serif; font-size: 14px;">El KDC se puede ver como el conjunto de <strong>dos etapas l&oacute;gicas compuesta por un servidor de autenticaci&oacute;n (AS) y un servidor emisor de &#39;&#39;tickets&#39;&#39; (TGS)</strong>. El AS tiene como funci&oacute;n identificar a cada usuario, validar su identidad y entregar al cliente una clave que le permite comunicarse con el TGS. Por otro lado, el TGS es el servidor encargado de comprobar que el cliente posea el &#39;&#39;ticket&#39;&#39; de autenticaci&oacute;n y entrega una clave al usuario que le permite acceder a los servicios que ha solicitado. Este escenario se muestra en la <span style="color:#0000ff;"><strong>Figura # 1</strong></span>.</span></p>
<p>
&nbsp;</p>
<p style="text-align: center;">
<img alt="" src="images/TICs/funcionamiento-protocolo-kerberos/1.png" style="height: 470px; width: 500px;" /></p>
<p style="text-align: center;">
<span style="font-family: arial, helvetica, sans-serif; font-size: 14px; color: rgb(0, 0, 255);"><strong>Figura # 1:</strong></span><span style="font-family: arial, helvetica, sans-serif; font-size: 14px;"> Componentes y flujo de comunicaci&oacute;n del protocolo Kerberos.</span></p>

<p>
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;">Kerberos realiza una gesti&oacute;n de &#39;&#39;tickets&#39;&#39; que le permite a los usuarios demostrar su identidad y obtener las claves se sesi&oacute;n para un determinado servicio, estas claves le permite a dos entidades interaccionar de manera segura. Para ello es necesario que dicho protocolo realice una gesti&oacute;n adecuada de diferentes bases de datos con el fin de identificar a los usuarios, y a la vez, mantener otra base de datos de claves secretas para poder asignar a cada entidad, ya sea cliente o servidor.</span></span></p>
<p>
<span style="font-family: arial, helvetica, sans-serif; font-size: 14px;">La <span style="color:#0000ff;"><strong>Figura # 2</strong></span> muestra el flujo de mensajes producidos por el protocolo Kerberos, donde claramente se ve la informaci&oacute;n que contiene cada uno de los mensajes enviados entre las diferente entidades que participan en el intercambio de claves. Se debe aclarar que no se muestra la comunicaci&oacute;n previa que debe establecer el cliente con el AS, donde le brinda el nombre de usuario y contrase&ntilde;a que ha introducido el usuario en el cliente. Sin embargo, la gesti&oacute;n de los &#39;&#39;tickets&#39;&#39; es bastante claro.</span></p>
<p>
<span style="font-family: arial, helvetica, sans-serif; font-size: 14px;">Cuando el cliente realiza una solicitud al AS, el AS contesta con dos mensajes: <strong>en el primero env&iacute;a la clave cifrada que va a compartir el cliente con el TGS, y en el segundo paquete debe ser reenviado al TGS</strong>, dicho paquete no puede ser descifrado por el cliente y contiene informaci&oacute;n acerca de la validaci&oacute;n hecha por el AS.</span></p>
<p>
<span style="font-family: arial, helvetica, sans-serif; font-size: 14px;">Luego, el cliente env&iacute;a dos mensajes al TGS: <strong>en el primer mensaje reenv&iacute;a el paquete que le di&oacute; el AS agregando el tipo de servicio solicitado y el segundo mensaje es un autenticador</strong> cifrado con la clave generada por el AS para la comunicaci&oacute;n entre cliente y TGS.</span></p>
<p>
<span style="font-family: arial, helvetica, sans-serif; font-size: 14px;">Ahora el TGS responde al cliente con la clave que va a compartir con el servidor del servicio solicitado y un &#39;&#39;ticket&#39;&#39; que solamente el servidor de servicio puede descifrar y que el cliente debe reenviar. <strong>El cliente reenv&iacute;a el &#39;&#39;ticket&#39;&#39; hacia el servidor del servicio y adem&aacute;s un autenticador</strong> cifrado con la clave entregada por el TGS para dicha comunicaci&oacute;n, de modo que la comunicaci&oacute;n entre cliente y servicio ya puede ser realizada de manera cifrada con dicha clave.</span></p>
<p>
&nbsp;</p>
<p style="text-align: center;">
<img alt="" src="images/TICs/funcionamiento-protocolo-kerberos/2.png" style="height: 400px; width: 500px;" /></p>
<p style="text-align: center;">
<span style="font-family: arial, helvetica, sans-serif; font-size: 14px; color: rgb(0, 0, 255);"><strong>Figura # 2:</strong></span><span style="font-family: arial, helvetica, sans-serif; font-size: 14px;"> Intercambio de mensajes del protocolo Kerberos.</span></p>
<p style="text-align: center;">
&nbsp;</p>
<h1>
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;">Referencias</span></span></h1>
<ol>
<li>
<span style="font-family: arial, helvetica, sans-serif; font-size: 14px;">William Stallings. Fundamentos de Seguridad de Redes: Aplicaciones y Est&aacute;ndares, Segunda Edici&oacute;n. Pearson Education. 2004.</span></li>
</ol>
<p>
&nbsp;</p>