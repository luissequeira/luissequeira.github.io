---
layout: post
title:  ¿Qué es LaTeX?
date:   2014-05-01 05:00:00
description: Latex es un lenguaje de edición de documentos de alta calidad, especialmente orientado a la composición de libros, documentos científicos y técnicos que incluyen fórmulas o imágenes de alta calidad. Está compuesto por un conjunto de macros Tex (un lenguaje de bajo nivel) y se ha convertido casi en un estándar para publicaciones científicas en áreas como la matemática, física e ingeniería ya que se puede tener un control más fino sobre cualquier aspecto tipográfico del documento.
tags: Latex herramientas
categories: Tools
---
<p>
<span style="font-family: arial, helvetica, sans-serif; font-size: 14px;"><strong>Latex es un lenguaje de edición de documentos de alta calidad, especialmente orientado a la composición de libros, documentos científicos y técnicos que incluyen fórmulas o imágenes de alta calidad</strong>. Está compuesto por un conjunto de macros Tex (un lenguaje de bajo nivel) y se ha convertido casi en un estándar para publicaciones científicas en áreas como la matemática, física e ingeniería ya que se puede tener un control más fino sobre cualquier aspecto tipográfico del documento.</span></p>

<p>
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;">Latex <strong>no es un editor de textos</strong>, es un lenguaje para prepara documentos y por lo tanto su apariencia no es no es igual. Los editores latex difieren a los conocidos como&nbsp;WYSIWYG (lo que ves es lo que obtienes), ya que latex permite a los usuarios escribir un documento centrándose exclusivamente en el contenido, <strong>sin tener que preocuparse de los detalles del formato</strong>.</span></span></p>
<p>
&nbsp;</p>
<h1>
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;">Ventajas de Latex</span></span></h1>
<ul>
<li>
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;">Estable y multiplataforma: el formato de los archivos <strong>es más estable que en editores de texto</strong>, además, existen implementaciones <strong>para distintas plataformas y en todas el resultado es exactamente el mismo</strong>.</span></span></li>
<li>
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;"><strong>Alta calidad en la edición de ecuaciones</strong>: ajusta los tamaños de paréntesis, integrales, subíndices y superíndices, alinea los elementos de las matrices, construye cajas, etc.</span></span></li>
<li>
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;"><strong>Facilidad en la redacción de documentos estructurados</strong>: posibilita escribir textos dividiéndolos en capítulos, secciones, subsecciones, controlando en todo momento la numeración y las referencias cruzadas. Construye automáticamente índices de contenidos, tablas o figuras.</span></span></li>
<li>
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;"><strong>Es gratis</strong>.</span></span></li>
</ul>
<p>
&nbsp;</p>
<h1>
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;">Desventajas de Latex</span></span></h1>
<ul>
<li>
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;"><strong>Curva de aprendizaje lenta</strong>: requiere un periodo de aprendizaje antes de conseguir los primeros resultados. Incluso cuando ya se es un usuario medio o avanzado, siempre es conveniente tener cerca un manual cerca.</span></span></li>
<li>
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;"><strong>No se ven los resultados hasta que se compila el archivo</strong>: no hay una visualización previa del trabajo hasta que se compila. Durante este proceso suelen aparecer errores de compilación, y puede llegar a ser frustrante para los principiantes. La única solución es armarse de paciencia.</span></span></li>
</ul>
<p>
&nbsp;</p>
<h1>
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;">Uso de Latex</span></span></h1>
<p>
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;">La elaboración de un documento requiere normalmente se divide en <strong>dos etapas</strong>: la primera consiste en <strong>crear un fichero fuente mediante un editor de texto</strong>, el cual incluye los comandos adecuados y el texto que se quiere imprimir. La segunda consiste en <strong>compilar el fichero fuente</strong>; este proceso consiste en interpretar las órdenes escritas en fichero fuente, dejándolo preparado para que pueda ser enviado a la salida correspondiente, ya sea la pantalla o la impresora pdf. Ahora bien, si se quiere añadir o cambiar algo en el documento, se deberá hacer los cambios correspondiente en el fichero fuente y compilarlo de nuevo.</span></span></p>
<p>
&nbsp;</p>
<h1>
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;">Distribuciones Latex</span></span></h1>
<p>
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;">Existen diversas distribuciones latex, por ejemplo: TeXLive que se puede utilizar en Linux, Mac y Windows, MacTex para OS X y MikTex que se utiliza en Windows. Otra de las ventajas de LaTeX es que la salida es siempre la misma, sin importar el dispositivo (impresora, pantalla, etc.) o el sistema operativo y puede ser exportado a una gran cantidad de formatos (Postscript, PDF, SGML, HTML, RTF, etc.).</span></span></p>
<p>
&nbsp;</p>
<h1>
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;">Editores Latex</span></span></h1>
<p>
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;">Existen varias aplicaciones que ayudan a una persona a escribir un documento de una manera más visual como: Texmaker, LyX, TeXmacs, Texstudio, Winshell, Kile y otros. Otra manera fácil de editar ecuaciones y producir el correspondiente código en latex, es utilizar una extensión del navegador Google Chrome llamada Daum Equation Editor.</span></span></p>
<p>
&nbsp;</p>
<h1>
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;">Ejemplo de documento en Latex</span></span></h1>
<p>
&nbsp;</p>
<pre><span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;">\documentclass[12pt]{article}</span></span>
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;">\usepackage[spanish]{babel}</span></span>
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;">\usepackage{amsmath}</span></span>
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;">\usepackage[latin1]{inputenc}</span></span>
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;">\title{\LaTeX}</span></span>
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;">\date{}</span></span>
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;">% Este es un comentario, no será mostrado en el documento final.</span></span>
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;">\begin{document}</span></span>
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;">\maketitle</span></span>
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;">\LaTeX es un programa para preparar documentos con el sistema de tipograf\'ias \footnote{Seg\'un Wikipedia, la tipograf\'ia es el arte y t\'ecnica del manejo y selecci\'on de tipos, originalmente de plomo, para crear trabajos de impresi\'ion} \TeX. \LaTeX fue desarrollado originalmente por Leslie Lamport en $1984$ y se convirti\'o en el m\'etodo dominante para la manipulaci\'on de \TeX. La versi\'on utilizada para generar este documento es \LaTeXe.</span></span>
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;">\newline</span></span>
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;">% El siguiente código muestra la calidad de la tipografía de LaTeX</span></span>
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;">$$E=mc^2$$</span></span>
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;">$$\oint F(x)dx$$</span></span>
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;">$$\iint \Phi(x, y)dxdy$$</span></span>
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;">$$\begin{matrix}A\xrightarrow{\;\;\;f\;\;\;}B\\\pi\downarrow{\;\;\;\;\;}\;\;\;\uparrow{} \phi\\C\xrightarrow{\;\;\;g\;\;\;}D\end{matrix}$$</span></span>
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;">\end{document}</span></span></pre>
<p>
&nbsp;</p>
<p>
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;">Este código producirá un documento como en la <span style="color:#0000ff;"><strong>Figura # 1</strong></span>.</span></span></p>
<p>
&nbsp;</p>
<p style="text-align: center;">
<img alt="" src="images/Research/que-es-latex/2.png" style="height: 707px; width: 500px;" /></p>
<p style="text-align: center;">
<span style="font-family: arial, helvetica, sans-serif; font-size: 14px;"><span style="color:#0000ff;"><strong>Figura # 1</strong></span>: Ejemplo de documento en Latex.</span></p>
<p style="text-align: center;">
&nbsp;</p>