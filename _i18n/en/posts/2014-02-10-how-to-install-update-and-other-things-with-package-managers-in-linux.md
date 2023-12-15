---
layout: post
title:  How to install, update and other things with package managers in Linux?
date:   2014-02-10 06:00:00
description: Package managers are tools to automate the process of installing, upgrading, uninstalling or configuring software on Linux. 
tags: linux console terminal GNU
categories: Tutorials
---
<p>
<span style="font-family: arial, helvetica, sans-serif; font-size: 14px;"><strong>Package managers are tools to automate the process of installing, upgrading, uninstalling or configuring software</strong> on Linux. Package managers are <strong>part of the operating system</strong> and they use a single database for installation and a single packet format, for example: rpm or deb. They are also responsible for checking the digital signature, and dependency resolution for updates.</span></p>

<p>
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;"><!--StartFragment-->Currently, the vast majority of Linux operating systems have a intuitive and easy to use graphics interface for package managers. <!--StartFragment-->For this reason, we discuss some basic features of the best-known command-line packet managers, which commonly generate <!--StartFragment-->doubts.</span></span></p>
<p>
&nbsp;</p>
<h1>
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;">YUM (Yellow dog Updater, Modified) package <!--EndFragment--><!--StartFragment-->manager</span></span></h1>
<p>
<span style="font-family: arial, helvetica, sans-serif; font-size: 14px;">This is the <strong>package manager for RPM-based</strong> Linux systems as Fedora, Redhat, CentOS and its derivatives e.g. BlueCat. Some of the most common uses are:</span></p>
<pre>yum install package                     # <!--StartFragment-->download and install a package and its dependencies<!--EndFragment-->
yum localinstall package.rpm            # <!--StartFragment-->install a previously downloaded package and its dependencies<!--EndFragment-->
yum update                              # <!--StartFragment-->update all installed packages<!--EndFragment-->
yum update package                      # <!--StartFragment-->update a package<!--EndFragment-->
yum remove package                      # <!--StartFragment-->remove a package<!--EndFragment-->
yum list                                # <!--StartFragment-->list all installed packages<!--EndFragment-->
yum search package                      # <!--StartFragment-->find a package in the repository<!--EndFragment-->
yum clean all                           # <!--StartFragment-->remove cache packages, headers and other<!--EndFragment-->s</pre>
<p>
&nbsp;</p>
<h1>
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;"><!--StartFragment-->Dpkg package manager</span></span><!--EndFragment--></h1>
<p>
<span style="font-family: arial, helvetica, sans-serif; font-size: 14px;">This is the basis of <strong>Debian's package management system, and therefore, it is also used by distributions like Ubuntu and its derivatives</strong>. Some examples are:</span></p>
<pre>dpkg -i package.deb           # install a package
dpkg -r package               # <!--StartFragment-->remove a package
dpkg -l                       # <!--StartFragment-->list all installed packages
dpkg -l | grep httpd          # <!--StartFragment-->show all packages with the name "httpd"<!--EndFragment-->
dpkg -s package               # obtain <!--StartFragment-->information of installed package<!--EndFragment-->
dpkg -L package               # file list of an installed package<!--EndFragment-->
dpkg -S /bin/ping             # <!--StartFragment-->verify which file a package belongs to<!--EndFragment--></pre>
<p>
&nbsp;</p>
<h1>
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;">APT and APTITUDE package managers</span></span></h1>
<p>
<span style="font-family: arial, helvetica, sans-serif; font-size: 14px;">APT (Advanced Packaging Tool) is not really a program, but a C++ library that is used by several programs, e.g. apt-get or apt-cache. </span><span style="font-family: arial, helvetica, sans-serif; font-size: 14px;">On the other hand, aptitude is an interface for apt that facilitate search systems and dependence resolutions to users. <strong>These package managers have commands and options similar to those already described</strong>, as we can see below:</span></p>
<pre>apt-get install package                # install a package
apt-cdrom install package              # install a package from cdrom
apt-get update                         # <!--StartFragment-->update the list of packages<!--EndFragment-->
apt-get upgrade                        # <!--StartFragment-->update all installed packages<!--EndFragment-->
apt-get remove package                 # <!--StartFragment-->remove a package
apt-get check                          # <!--StartFragment-->verify dependencies<!--EndFragment-->
apt-get clean                          # <!--StartFragment-->clean cache<!--EndFragment-->
apt-cache search package               # list packages that corresponds to "package"
aptitude search paquete                # <!--StartFragment-->looking for a package by its name<!--EndFragment-->
aptitude show paquete | less           # <!--StartFragment-->display information about a package<!--EndFragment-->
aptitude install paquete1 paquete2 …   # <!--StartFragment-->install multiple packages and their dependencies<!--EndFragment-->
aptitude remove paquete                # <!--StartFragment-->remove a package
aptitude purge paquete                 # <!--StartFragment-->remove a package and <!--StartFragment-->clean cache
aptitude clean                         # <!--StartFragment-->clean cache</pre>
<p>
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;"><!--StartFragment-->PD: Do you like cows? writes in a terminal: apt-get moo</span></span><!--EndFragment--></p>
<p>
&nbsp;</p>
<h1>
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;">References</span></span></h1>
<ol>
<li>
<a href="http://yum.baseurl.org/" style="font-family: arial, helvetica, sans-serif; font-size: 14px;">http://yum.baseurl.org/</a></li>
<li>
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;">http://www.debian.org/doc/manuals/debian-faq/ch-pkgtools.en.html</span></span></li>
<li>
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;"><a href="http://www.debian.org/doc/manuals/apt-howto/index.es.html">http://www.debian.org/doc/manuals/apt-howto/index.es.html</a></span></span></li>
<li>
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;"><a href="http://algebraicthunk.net/~dburrows/projects/aptitude/">http://algebraicthunk.net/~dburrows/projects/aptitude/</a></span></span></li>
</ol>