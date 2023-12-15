---
layout: post
title:  ¿Cómo instalar SPAN?
date:   2014-04-10 05:00:00
description: La instalación es muy sencilla, para usuarios de Linux y Mac solo es necesario tener instalado Tcl/Tk 8.5, luego descargar el programa SPAN aqui y descomprimir. Por último, definir dos variables de entorno SPAN y AVISPA_PACKAGE.
tags: seguridad criptografía herramientas
categories: Tools
---
<p>
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;"><strong>Security Protocol Animator (SPAN) es una herramienta libre de verificaci&oacute;n para protocolos criptogr&aacute;ficos que ayuda en la b&uacute;squeda y caracterizaci&oacute;n de ataques</strong>. La principal ventaja de esta aplicaci&oacute;n es que permite usar diferentes t&eacute;cnicas de verificaci&oacute;n a un mismo protocolo. Se puede decir que es una interfaz gr&aacute;fica para el manejo de HLPSL (High-Level Protocol Specification Language) y CAS+ (una implementaci&oacute;n del Protocolo de Autenticaci&oacute;n Central), que permite la traducci&oacute;n entre estos lenguajes y adem&aacute;s brinda una interfaz gr&aacute;fica m&aacute;s amigable al usuario. <strong>SPAN ayuda a producir de manera interactiva secuencias de mensajes</strong> o MSC (Message Sequence Charts).</span></span></p>
<p>
<span style="font-family: arial, helvetica, sans-serif; font-size: 14px;">Esta herramienta se utiliza para la simulaci&oacute;n de protocolo criptogr&aacute;ficos, <strong>permite la simulaci&oacute;n de intrusos de manera activa o pasiva, la construcci&oacute;n autom&aacute;tica de ataques a los protocolos dise&ntilde;ados</strong>. La edici&oacute;n del protocolo se puede realiza mediante HLPSL o CAS+, teniendo la posibilidad de realizar conversiones entre dichos lenguajes. Algunas caracter&iacute;sticas de la interfaz gr&aacute;fica se muestran en la <span style="color:#0000ff;"><strong>Figura # 1</strong></span>.</span></p>
<p>
&nbsp;</p>
<p style="text-align: center;">
<img alt="" src="images/Research/como-instalar-span/1.png" style="height: 462px; width: 500px;" /></p>
<p style="text-align: center;">
<span style="font-family: arial, helvetica, sans-serif; font-size: 14px; color: rgb(0, 0, 255);"><strong>Figura # 1</strong></span><span style="font-family: arial, helvetica, sans-serif; font-size: 14px;">: Descripci&oacute;n de la interfaz gr&aacute;fica de SPAN.</span></p>

<p>
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;">SPAN puede ser utilizado en tres modos diferentes:</span></span></p>
<ol>
<li>
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;"><strong>Simulador de protocolos</strong>: puede simular protocolos mediante MSC a partir de un c&oacute;digo HLPSL.</span></span></li>
<li>
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;"><strong>Simulador de intrusos</strong>: permite simular un protocolo con un intruso pasivo o activo.</span></span></li>
<li>
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;"><strong>Simulador de ataques</strong>: a partir de las salidas de OFMC o CL-ATSE (otras herramientas del proyecto <a href="http://www.avispa-project.org/">AVISPA</a>).</span></span></li>
</ol>
<p>
&nbsp;</p>
<h1>
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;">Instalaci&oacute;n</span></span></h1>
<p>
<span style="font-family: arial, helvetica, sans-serif; font-size: 14px;"><strong>La instalaci&oacute;n es muy sencilla, para usuarios de Linux y Mac solo es necesario tener instalado Tcl/Tk 8.5</strong>, luego descargar el programa SPAN <a href="http://www.irisa.fr/celtique/genet/span/">aqui</a> y descomprimir (por ejemplo en: <em>/usr/bob/span</em>). <strong>Por &uacute;ltimo, definir dos variables de entorno</strong>: <em>SPAN</em> y <em>AVISPA_PACKAGE</em>, para esto abrimos un terminal y escribimos:</span></p>
<pre><span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;">export SPAN=/usr/bob/span</span></span>
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;">export AVISPA_PACKAGE=/usr/bob/span</span></span></pre>
<p>
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;">Teniendo en cuenta que <em>/usr/bob/span</em> es la ruta donde se descomprimi&oacute; SPAN. El programa se ejecuta como cualquier otro script, solamente se debe escribir en un terminal:</span></span></p>
<pre><span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;">./span</span></span></pre>
<p>
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;">Si has descomprimido SPAN en una carpeta en el directorio de tu usuario, por ejemplo en <em>/home/mi_usuario/span/</em>, lo que suceder&aacute; es que cada vez que inicies tu m&aacute;quina tendr&aacute;s que realizar el procedimiento anterior. Para evitar esto, se puede hacer un peque&ntilde;o y sencillo script en bash, para ello, creamos un fichero de texto llamado <em>&ldquo;iniciar&rdquo;</em>, lo podemos hacer con alg&uacute;n editor de texto como <em>gedit</em> o <em>kate</em>, o bien por medio de l&iacute;nea de comando con <em>vi </em>o <em>nano</em>. Por l&iacute;nea de comandos, se abre un terminal y nos dirigimos a la ruta donde hemos descomprimido SPAN (<em>/home/mi_usuario/span/</em>), escribimos:</span></span></p>
<pre><span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;">cd /home/mi_usuario/span/                # ir a la carpeta</span></span>
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;">nano iniciar                                        # se crea un fichero de nombre iniciar</span></span></pre>
<p>
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;">Luego, escribimos dentro del fichero lo siguiente:</span></span></p>
<pre><span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;">#! /bin/bash</span></span>
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;">export SPAN=/home/mi_usuario/span/</span></span>
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;">export AVISPA_PACKAGE=/home/mi_usuario/span/</span></span>
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;">./span</span></span>
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;">exit</span></span></pre>
<p>
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;">Para salir del editor se presiona <em>CTRL+X</em> y el editor preguntar&aacute; si se desea guardar los cambio, a lo que se responde que si. Ahora, lo &uacute;nico que falta es darle permisos de ejecuci&oacute;n al fichero, entonces escribimos:</span></span></p>
<pre><span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;">chmod +x iniciar</span></span></pre>
<p>
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;">Se prueba escribiendo:</span></span></p>
<pre><span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;">./iniciar</span></span></pre>
<p>
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;">Y listo!</span></span></p>
<p>
&nbsp;</p>
<h1>
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;">Referencias</span></span></h1>
<ol>
<li>
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;">Y. Glouche, T. Genet, O. Heen and O. Courtay A Security Protocol Animator Tool for AVISPA. In ARTIST2 Workshop on Security Specification and Verification of Embedded Systems , pp. 15, Pisa, May 2006.</span></span></li>
<li>
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;">http://www.irisa.fr/celtique/genet/span/</span></span></li>
</ol>