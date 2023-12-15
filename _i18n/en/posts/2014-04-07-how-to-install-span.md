---
layout: post
title:  How to install SPAN?
date:   2014-04-07 05:00:00
description: Installation is very simple, for Linux and Mac users only need to have installed Tcl/Tk 8.5, then download SPAN software from here and unzip it. Finally, we define two environment variables SPAN and AVISPA_PACKAGE.
tags: tools security criptography
categories: Tools
---
<p>
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;">Security Protocol Animator (SPAN) is a free tool to check cryptographic protocols that helps in searching and characterization of attacks. <strong>The main advantage of this application is that allows different verification techniques using a same protocol</strong>. We can say, it is a graphical interface for managing HLPSL (High-Level Protocol Specification Language) and CAS + (an implementation of the Protocol Central Authentication), which allows the translation between these languages ​​and also provides a friendly graphical user interface. <strong>SPAN helps to produce interactively sequences messages</strong> or MSC (Message Sequence Charts).</span></span></p>
<p>
<span style="font-family: arial, helvetica, sans-serif; font-size: 14px;">This <strong>tool is used for simulating cryptographic protocol</strong>, allows active or passive intruder simulation, the automatic attack&#39;s construction of the designed protocols. The protocol can be edited by means of HLPSL or CAS+, having the ability to convert between these languages. Some features of the graphical user interface are shown in <span style="color:#0000ff;"><strong>Figure # 1</strong></span>.</span></p>
<p style="text-align: center;">
<img alt="" src="images/Research/como-instalar-span/1.png" style="height: 462px; width: 500px;" /></p>
<p style="text-align: center;">
<span style="font-family: arial, helvetica, sans-serif; font-size: 14px; color: rgb(0, 0, 255);"><strong>Figure # 1</strong></span><span style="font-family: arial, helvetica, sans-serif; font-size: 14px;">: SPAN GUI description.</span></p>

<p>
<span style="font-family: arial, helvetica, sans-serif; font-size: 14px;">SPAN can be used in three different modes:</span></p>
<ol>
<li>
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;"><strong>Protocol simulator</strong>: it can simulate by MSC from a HLPSL code.</span></span></li>
<li>
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;"><strong>Intrusion simulator</strong>: simulates a protocol with a passive or active attacker.</span></span></li>
<li>
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;"><strong>Attack simulator</strong>: from outputs of OFMC or CL-ATSE (other tools from <a href="http://www.avispa-project.org/">AVISPA project</a>).</span></span></li>
</ol>
<p>
&nbsp;</p>
<h1>
<span style="font-family: arial, helvetica, sans-serif; font-size: 14px;">Installation</span></h1>
<p>
<span style="font-family: arial, helvetica, sans-serif; font-size: 14px;"><strong>Installation is very simple, for Linux and Mac users only need to have installed Tcl/Tk 8.5</strong>, then download SPAN software from <a href="http://www.irisa.fr/celtique/genet/span/">here</a> and unzip it (for example: <em>/usr/bob/span</em>). <strong>Finally, we define two environment variables</strong>: <em>SPAN</em> and <em>AVISPA_PACKAGE</em>, for this, open a terminal and type:</span></p>
<pre><span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;">export SPAN=/usr/bob/span</span></span>
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;">export AVISPA_PACKAGE=/usr/bob/span</span></span></pre>
<p>
<span style="font-family: arial, helvetica, sans-serif; font-size: 14px;">Taking into account that <em>/usr/bob/span</em> is the path where you unzipped SPAN. The program runs as any other script, we should write in a terminal:</span></p>
<pre><span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;">./span</span></span></pre>
<p>
<span style="font-family: arial, helvetica, sans-serif; font-size: 14px;">If we unzipped SPAN in a folder in your user directory, for example <em>/home/myuser/span/</em>, so, every time you start your machine will have to perform the above procedure. To avoid this, we can make a simple little bash script, for this, create a text file called <em>&quot;start&quot;</em>, we can do it with any text editor like <em>gedit</em> or <em>kate</em>, or via command line with <em>vi</em> or <em>nano</em>. On the command line, open a terminal and headed to the path where you have unpacked SPAN (<em>/home/myuser/span/</em>), and write:</span></p>
<pre><span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;">cd /home/myuser/span/ # go to the folder</span></span>
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;">nano start # it creates a file called start</span></span></pre>
<p>
<span style="font-family: arial, helvetica, sans-serif; font-size: 14px;">Then, we write into the file the following:</span></p>
<pre><span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;">#! /bin/bash</span></span>
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;">export SPAN=/home/myuser/span/</span></span>
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;">export AVISPA_PACKAGE=/home/myuser/span/</span></span>
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;">./span</span></span>
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;">exit</span></span></pre>
<p>
<span style="font-family: arial, helvetica, sans-serif; font-size: 14px;">To exit from the text editor press <em>CTRL+X</em> and the editor will ask if you want to save the changes, we answer yes. Now all that remains is to give execute permission to the file, then we write:</span></p>
<pre><span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;">chmod +x start</span></span></pre>
<p>
<span style="font-family: arial, helvetica, sans-serif; font-size: 14px;">Tested by typing:</span></p>
<pre><span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;">./start</span></span></pre>
<p>
<span style="font-family: arial, helvetica, sans-serif; font-size: 14px;">And ready!</span></p>
<p>
&nbsp;</p>
<h1>
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;">References</span></span></h1>
<ol>
<li>
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;">Y. Glouche, T. Genet, O. Heen and O. Courtay A Security Protocol Animator Tool for AVISPA. In ARTIST2 Workshop on Security Specification and Verification of Embedded Systems , pp. 15, Pisa, May 2006.</span></span></li>
<li>
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;">http://www.irisa.fr/celtique/genet/span/</span></span></li>
</ol>