---
layout: post
title:  ¿Qué es LaTeX?
date:   2014-05-01 05:00:00
description: Latex es un lenguaje de edición de documentos de alta calidad, especialmente orientado a la composición de libros, documentos científicos y técnicos que incluyen fórmulas o imágenes de alta calidad. Está compuesto por un conjunto de macros Tex (un lenguaje de bajo nivel) y se ha convertido casi en un estándar para publicaciones científicas en áreas como la matemática, física e ingeniería ya que se puede tener un control más fino sobre cualquier aspecto tipográfico del documento.
tags: latex herramientas
categories: Innovation
thumbnail: assets/img/Research/que-es-latex/1.png
---

<div class="row mt-3" style="text-align: center">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="assets/img/Research/que-es-latex/1.png" class="img-fluid rounded z-depth-1" %}
    </div>
</div>

**Latex es un lenguaje de edición de documentos de alta calidad, especialmente orientado a la composición de libros, documentos científicos y técnicos que incluyen fórmulas o imágenes de alta calidad**. Está compuesto por un conjunto de macros Tex (un lenguaje de bajo nivel) y se ha convertido casi en un estándar para publicaciones científicas en áreas como la matemática, física e ingeniería ya que se puede tener un control más fino sobre cualquier aspecto tipográfico del documento.

**Latex no es un editor de textos**, es un lenguaje para prepara documentos y por lo tanto su apariencia no es no es igual. Los editores latex difieren a los conocidos como WYSIWYG (lo que ves es lo que obtienes), ya que latex permite a los usuarios escribir un documento centrándose exclusivamente en el contenido, **sin tener que preocuparse de los detalles del formato**.

## Ventajas de Latex

- Estable y multiplataforma: el formato de los archivos **es más estable que en editores de texto, además, existen implementaciones** para distintas plataformas y en todas el resultado es exactamente el mismo.
- **Alta calidad en la edición de ecuaciones**: ajusta los tamaños de paréntesis, integrales, subíndices y superíndices, alinea los elementos de las matrices, construye cajas, etc.
- **Facilidad en la redacción de documentos estructurados**: posibilita escribir textos dividiéndolos en capítulos, secciones, subsecciones, controlando en todo momento la numeración y las referencias cruzadas. Construye automáticamente índices de contenidos, tablas o figuras.
- **Es gratis**.

## Desventajas de Latex

- **Curva de aprendizaje lenta**: requiere un periodo de aprendizaje antes de conseguir los primeros resultados. Incluso cuando ya se es un usuario medio o avanzado, siempre es conveniente tener cerca un manual cerca.
- **No se ven los resultados hasta que se compila el archivo**: no hay una visualización previa del trabajo hasta que se compila. Durante este proceso suelen aparecer errores de compilación, y puede llegar a ser frustrante para los principiantes. La única solución es armarse de paciencia.

## Uso de Latex

La elaboración de un documento requiere normalmente se divide en **dos etapas**: la primera consiste en **crear un fichero fuente mediante un editor de texto**, el cual incluye los comandos adecuados y el texto que se quiere imprimir. La segunda consiste en **compilar el fichero fuente**; este proceso consiste en interpretar las órdenes escritas en fichero fuente, dejándolo preparado para que pueda ser enviado a la salida correspondiente, ya sea la pantalla o la impresora pdf. Ahora bien, si se quiere añadir o cambiar algo en el documento, se deberá hacer los cambios correspondiente en el fichero fuente y compilarlo de nuevo.

## Distribuciones Latex

Existen diversas distribuciones latex, por ejemplo: TeXLive que se puede utilizar en Linux, Mac y Windows, MacTex para OS X y MikTex que se utiliza en Windows. Otra de las ventajas de LaTeX es que la salida es siempre la misma, sin importar el dispositivo (impresora, pantalla, etc.) o el sistema operativo y puede ser exportado a una gran cantidad de formatos (Postscript, PDF, SGML, HTML, RTF, etc.).

## Editores Latex

Existen varias aplicaciones que ayudan a una persona a escribir un documento de una manera más visual como: Texmaker, LyX, TeXmacs, Texstudio, Winshell, Kile y otros. Otra manera fácil de editar ecuaciones y producir el correspondiente código en latex, es utilizar una extensión del navegador Google Chrome llamada Daum Equation Editor.

## Ejemplo de documento en Latex

```latex
\documentclass[12pt]{article}
\usepackage[spanish]{babel}
\usepackage{amsmath}
\usepackage[latin1]{inputenc}

\title{\LaTeX}
\date{}

% This is a comment, not be displayed in the final document.

\begin{document}
\maketitle

\LaTeX es un programa para preparar documentos con el sistema de tipograf\'ias \footnote{Seg\'un Wikipedia, la tipograf\'ia es el arte y t\'ecnica del manejo y selecci\'on de tipos, originalmente de plomo, para crear trabajos de impresi\'ion} \TeX. \LaTeX fue desarrollado originalmente por Leslie Lamport en $1984$ y se convirti\'o en el m\'etodo dominante para la manipulaci\'on de \TeX. La versi\'on utilizada para generar este documento es \LaTeXe.

\newline

% The following code shows the quality of LaTeX typesetting
$$E=mc^2$$
$$\oint F(x)dx$$
$$\iint \Phi(x, y)dxdy$$
$$\begin{matrix}A\xrightarrow{\;\;\;f\;\;\;}B\\\pi\downarrow{\;\;\;\;\;}\;\;\;\uparrow{} \phi\\C\xrightarrow{\;\;\;g\;\;\;}D\end{matrix}$$

\end{document}
```

Este código producirá un documento como en la Figura #1.

<div class="row mt-3" style="text-align: center">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="assets/img/Research/que-es-latex/2.png" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Figure #1: Ejemplo de documento en Latex.
</div>
