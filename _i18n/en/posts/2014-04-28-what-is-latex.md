---
layout: post
title:  What is LaTeX?
date:   2014-04-28 05:00:00
description: Latex is a language for high quality editing documents, especially oriented to book composition, scientific and technical documents, that include formulas and high quality images. It consists on a set of Tex macros (one low-level language) and has become almost a standard for scientific publications in areas such as mathematics, physics and engineering, since we can have finer control over any typographical appearance of the document.
tags: Latex tools
categories: Tools
---
<p>
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;"><strong>Latex is a language for high quality editing documents, especially oriented to book composition, scientific and technical documents, that include formulas and high quality images</strong>. It consists on a set of Tex macros (one low-level language) and has become almost a standard for scientific publications in areas such as mathematics, physics and engineering, since we can have finer control over any typographical appearance of the document.</span></span></p>

<p>
<span style="font-family: arial, helvetica, sans-serif; font-size: 14px;"><strong>Latex is not a text editor</strong>, is a language for preparing documents and therefore its appearance is not equal. The latex editors differ of the WYSIWYG editor (what you see is what you get) because latex allows users to write a paper, focusing exclusively on the content <strong>without having to worry about the format details</strong>.</span></p>
<p>
&nbsp;</p>
<h1>
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;">Advantages of Latex</span></span></h1>
<ul>
<li>
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;">Stable and multi-platform: <strong>the file format is more stable than the one in text editors</strong>, also there exist implementations for different platforms, and in all of them, the result is exactly the same.</span></span></li>
<li>
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;"><strong>High-quality equation editing</strong>: it can set the size of the parentheses, integrals, subscript and superscript, align elements in a matrices, constructed boxes, etc.</span></span></li>
<li>
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;"><strong>Ease-writing structured documents</strong>: it is possible to write texts dividing them into chapters, sections, subsections, controlling at all times numbering and cross-referencing. Automatic indexing of contents, tables or figures.</span></span></li>
<li>
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;"><strong>It's free</strong>.</span></span></li>
</ul>
<p>
&nbsp;</p>
<h1>
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;">Disadvantages of Latex</span></span></h1>
<ul>
<li>
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;"><strong>Slow learning curve</strong>: it requires a learning period before getting the first results. Even medium or advanced user always have a manual nearby.</span></span></li>
<li>
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;"><strong>The results are not seen until the file is compiled</strong>: no preview available until it is compiled. During this process, it is usual the appearing of compilation errors and it can be frustrating for beginners. The only solution is to be patient.</span></span></li>
</ul>
<p>
&nbsp;</p>
<h1>
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;">Using Latex</span></span></h1>
<p>
<span style="font-family: arial, helvetica, sans-serif; font-size: 14px;">The document preparation normally requires <strong>two stages</strong>: the first is to <strong>create a source file</strong> using a text editor, which includes the appropriate commands and the text to be printed. The second is to <strong>compile the source file</strong>; this process consists on interpreting the written orders on the source file, leaving it ready to be sent to the corresponding output, either the screen or the pdf printer. Now, if you want to add or change something in the document, you must make the appropriate changes in the source file and compile it again.</span></p>
<p>
&nbsp;</p>
<h1>
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;">Latex distributions</span></span></h1>
<p>
<span style="font-family: arial, helvetica, sans-serif; font-size: 14px;">There are several latex distributions, e.g., TeXLive can be used on Linux, Mac and Windows, MacTex for OS X and MiKTeX is used in Windows. Another advantage of LaTeX is that the output is always the same, regardless of the device (printer, screen, etc..) or the operating system, and it can be exported to a variety of formats (Postscript, PDF, SGML, HTML, RTF, etc.).</span></p>
<p>
&nbsp;</p>
<h1>
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;">Latex Editors</span></span></h1>
<p>
<span style="font-family: arial, helvetica, sans-serif; font-size: 14px;">There are several applications that helps a person to write a document in a more visual way: Texmaker, LyX, TeXmacs, Texstudio, WinShell, Kile and others. Another easy way to edit and to produce the corresponding equations in latex code, is to use a Google Chrome browser extension called Daum Equation Editor.</span></p>
<p>
&nbsp;</p>
<h1>
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;">Example of a Latex document</span></span></h1>
<p>
&nbsp;</p>
<pre><span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;">\documentclass[12pt]{article}</span></span>
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;">\usepackage[spanish]{babel}</span></span>
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;">\usepackage{amsmath}</span></span>
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;">\usepackage[latin1]{inputenc}</span></span>
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;">\title{\LaTeX}</span></span>
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;">\date{}</span></span>
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;">% This is a comment, not be displayed in the final document.</span></span>
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;">\begin{document}</span></span>
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;">\maketitle</span></span>
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;">\LaTeX es un programa para preparar documentos con el sistema de tipograf\'ias \footnote{Seg\'un Wikipedia, la tipograf\'ia es el arte y t\'ecnica del manejo y selecci\'on de tipos, originalmente de plomo, para crear trabajos de impresi\'ion} \TeX. \LaTeX fue desarrollado originalmente por Leslie Lamport en $1984$ y se convirti\'o en el m\'etodo dominante para la manipulaci\'on de \TeX. La versi\'on utilizada para generar este documento es \LaTeXe.</span></span>
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;">\newline</span></span>
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;">% The following code shows the quality of LaTeX typesetting</span></span>
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;">$$E=mc^2$$</span></span>
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;">$$\oint F(x)dx$$</span></span>
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;">$$\iint \Phi(x, y)dxdy$$</span></span>
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;">$$\begin{matrix}A\xrightarrow{\;\;\;f\;\;\;}B\\\pi\downarrow{\;\;\;\;\;}\;\;\;\uparrow{} \phi\\C\xrightarrow{\;\;\;g\;\;\;}D\end{matrix}$$</span></span>
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;">\end{document}</span></span></pre>
<p>
&nbsp;</p>
<p>
<span style="font-family: arial, helvetica, sans-serif; font-size: 14px;">This code will produce a document as in <span style="color:#0000ff;"><strong>Figure # 1</strong></span>.</span></p>
<p>
&nbsp;</p>
<p style="text-align: center;">
<img alt="" src="images/Research/que-es-latex/2.png" style="height: 707px; width: 500px;" /></p>
<p style="text-align: center;">
<span style="font-family: arial, helvetica, sans-serif; font-size: 14px; color: rgb(0, 0, 255);"><strong>Figure # 1</strong></span><span style="font-family: arial, helvetica, sans-serif; font-size: 14px;">: Example of a Latex document.</span></p>
<p style="text-align: center;">
&nbsp;</p>