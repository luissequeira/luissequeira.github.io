---
layout: post
title:  ¿Cómo modificar ficheros con SED?
date:   2014-05-15 05:00:00
description: Sed es un editor de flujo que se utiliza para realizar transformaciones básicas de texto en un flujo de entrada (un fichero o la entrada de una tubería) o filtrar cadenas de caracteres. Permite modificar el contenido de diferentes líneas de un fichero basándose en una serie de parámetros.
tags: linux consola
categories: Tutorials
---
<h1>
<span style="font-family: arial, helvetica, sans-serif; font-size: 14px;">¿Qué es sed?</span></h1>
<p>
<span style="font-family: arial, helvetica, sans-serif; font-size: 14px;">Sed es un editor de flujo que se utiliza para realizar transformaciones básicas de texto en un flujo de entrada (un fichero o la entrada de una tubería) o filtrar cadenas de caracteres. Permite <strong>modificar el contenido de diferentes líneas de un fichero</strong> basándose en una serie de parámetros.</span></p>

<p>
<span style="font-family: arial, helvetica, sans-serif; font-size: 14px;">Para los ejemplos que se muestran en este artículo, se ha utilizado la versión 4.2.1 de sed como se muestra a continuación:</span></p>
<pre><span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;">sed --version</span></span>

<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;">GNU sed version 4.2.1</span></span>
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;">Copyright (C) 2009 Free Software Foundation, Inc.</span></span>
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;">This is free software; see the source for copying conditions. There is NO</span></span>
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;">warranty; not even for MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE,</span></span>
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;">to the extent permitted by law.</span></span></pre>
<p>
<span style="font-family: arial, helvetica, sans-serif; font-size: 14px;">Sed tiene una sintaxis de la siguiente manera:</span></p>
<pre><span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;">sed [-opciones] [comando] [&lt;fichero(s)&gt;]</span></span></pre>
<p>
&nbsp;</p>
<h1>
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;">Visualización</span></span></h1>
<p>
<span style="font-family: arial, helvetica, sans-serif; font-size: 14px;">Para los casos en los que se necesita visualizar el contenido de un fichero o parte de éste, podemos utilizar alguno de los siguientes comandos:</span></p>
<pre><span style="font-family: arial, helvetica, sans-serif; font-size: 14px;">sed 5q fichero1                                   # ver las primeras 5 líneas del fichero1</span>
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;">cat -n fichero1 | sed -n '5,6 p'             # ver las líneas 5 y 6 del fichero1</span></span>
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;">sed -n '1p' fichero1 &gt; fichero2            # copiar la primera linea de fichero1 a fichero2</span></span>
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;">sed -n '$p' fichero1                             # mostrar la última línea de fichero1</span></span></pre>
<p>
&nbsp;</p>
<h1>
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;">Sustitución de cadenas y caracteres</span></span></h1>
<p>
<span style="font-family: arial, helvetica, sans-serif; font-size: 14px;">En estos casos siempre es recomendable almacenar el resultado de una sustitución en otro fichero, dejando el fichero original sin modificar. Algunos ejemplos son los siguientes:</span></p>
<pre><span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;"># reemplazar cadenas en todas las lineas que contentan dicha cadena del fichero1 y almacenar el resultado en fichero2</span></span>
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;">sed 's/cadena_vieja/cadena_nueva/g' fichero1 &gt; fichero2</span></span>
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;"># reemplazar cadenas sólo en las líneas 200 y 201</span></span>
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;">sed '200,201 s/cadena_vieja/cadena_nueva/g' fichero1 &gt; fichero2</span></span>
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;"># reemplazar multiples cadenas por una nueva</span></span>
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;">sed 's/cadena_vieja_1\|cadena_vieja_2/cadena_nueva/g' fichero1 &gt; fichero2</span></span>
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;"># remplazar todas las minúsculas por mayúsculas</span></span>
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;">sed 'y/abcdefghijklmnopqrstuvwxyz/ABCDEFGHIJKLMNOPQRSTUVWXYZ/' fichero1 &gt; fichero2</span></span><span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;">
</span></span></pre>
<h1>
&nbsp;</h1>
<h1>
<span style="font-size:14px;"><span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;">Insertar cadenas</span></span></span></h1>
<p>
<span style="font-size:14px;"><span style="font-family: arial, helvetica, sans-serif; font-size: 14px;">Al igual que en el caso anterior, se dejará el fichero inicial sin modificar mientras que el segundo contendrá los cambios realizados.</span></span></p>
<pre><span style="font-size:14px;"><span style="font-family: arial, helvetica, sans-serif; font-size: 14px;"># insertar una cadena al principio de cada línea
</span><span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;">sed 's/^/cadena_al_inicio/' fichero1 &gt;fichero2 </span></span>
<span style="font-family: arial, helvetica, sans-serif; font-size: 14px;"># añadir una línea al final de un fichero
</span><span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;">sed -e '$ cadena_al_final' fichero &gt; fichero2 </span></span>
<span style="font-family: arial, helvetica, sans-serif; font-size: 14px;"># insertar una linea en blanco antes de cada linea que cumpla con una cadena
</span><span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;">sed '/cadena/{x;p;x;}' fichero1 &gt; fichero2 </span></span>
<span style="font-family: arial, helvetica, sans-serif; font-size: 14px;"># insertar una linea en blanco detrás de cada linea que cumpla con una cadena
</span><span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;">sed '/cadena/G' fichero1 &gt; fichero2 </span></span>
<span style="font-family: arial, helvetica, sans-serif; font-size: 14px;"># insertar una linea en blanco antes y después de cada linea que cumpla con una cadena
</span><span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;">sed '/cadena/{x;p;x;G;}' fichero1 &gt; fichero2 </span></span>
<span style="font-family: arial, helvetica, sans-serif; font-size: 14px;"># insertar una línea en blanco cada 2 líneas
</span><span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;">sed 'n;G;' fichero1 &gt; fichero2 </span></span></span></pre>
<h1>
&nbsp;</h1>
<h1>
<span style="font-size:14px;"><span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;">Eliminar líneas y cadenas</span></span></span></h1>
<p>
<span style="font-size:14px;"><span style="font-family: arial, helvetica, sans-serif; font-size: 14px;">Para eliminar caracteres o líneas completas, ya sea porque están vacías o bien por ser comentario, podemos utilizar los siguientes comandos:</span></span></p>
<pre><span style="font-size:14px;"><span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;">sed '2,4 d' fichero1 &gt; fichero2              # eliminar las líneas 100 y 105 del fichero1</span></span>
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;">sed '5,20 !d' fichero1 &gt; fichero2           # eliminar todas las líneas excepto las 5 y 20</span></span>
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;">sed '$d' fichero1 &gt; fichero2                  # eliminar la última línea del fichero1</span></span>
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;">sed -i '$d' fichero1                                # eliminar la última línea del fichero1 en el mismo fichero</span></span>
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;">sed '/cadena/ d' fichero1 &gt; fichero2      # eliminar las líneas que contentan una cadena</span></span>
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;">sed '/^$/d' fichero1 &gt; fichero2               # eliminar líneas en blanco</span></span>
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;">sed '/^$/d; / *#/d' fichero1 &gt; fichero2     # eliminar líneas en blanco y comentarios bash</span></span></span></pre>
<p>
<span style="font-size:14px;">&nbsp;</span></p>