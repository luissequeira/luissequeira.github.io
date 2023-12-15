---
layout: post
title:  Useful commands for system information and manage sesion
date:   2013-12-09 06:00:00
description: In this case, several commands are presented which allow us to collect certain system information and session managing.
tags: GNU console terminal linux
categories: Tutorials
---
<p>
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;">In a previous article, we showed the use of some <a href="index.php/en/linux-zone/tutorials/item/43-how-to-manage-files-and-directories-on-gnu-linux.html">useful commands for manipulating files and directories</a>, in this case, several commands are presented which allow us to <strong>collect certain system information</strong>. Also, we will see that displaying the <strong>content of certain files</strong>, can also be a way for giving useful information. Furthermore, the use of session managing commands will be described.</span></span></p>

<p>
<span style="font-family: arial, helvetica, sans-serif; font-size: 14px;">We begin with some commands to get system information: kernel features and architecture.</span></p>
<pre>arch                   # architecture
uname -m               # architecture
uname -r               # kernel version
uname -a               #complete information
cat /etc/issue         # distribution name</pre>
<p>
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;"><!--StartFragment-->Recall that in Linux, everything is stored in files, so if we want to see a detailed system information, "<em>/proc"</em> directory will be of much help, because it contains the <strong>files hierarchy that shows the current state of the kernel</strong>. Within this directory you can find a lot of information about the hardware and any processes running. If you enter to this directory, and you see that files have 0 bytes, do not worry it's normal, because the <em>"/proc"</em> directory contains another file type called <strong>virtual files</strong>, unlike the known types: text and binary files, that you will be more familiarized. Here are some examples:</span></span><!--EndFragment--></p>
<pre>cat /proc/cpuinfo             # CPU information
cat /proc/interrupts          # show interruptions
cat /proc/meminfo             # <!--StartFragment-->verify memory usage<!--EndFragment-->
cat /proc/mounts              # <!--StartFragment-->show mounted filesystem <!--EndFragment-->
cat /proc/swaps               # show swap
cat /proc/version             # kernel version
cat /proc/net/dev             # show <!--StartFragment-->network adapters and statistics<!--EndFragment-->
lspci -tv                     # show PCI devices
lsusb -tv                     # show USB devices</pre>
<p>
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;"><!--StartFragment-->On the other hand, if you want a real-time monitor system, the following command is the indicated. When you are using it you can type some options: <em>h - help, u – user, p - PID, q - exit</em>.</span></span><!--EndFragment--></p>
<pre>top                           # show Linux tasks</pre>
<p>
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;"><!--StartFragment-->For dates, schedules and time, also we have two useful commands:</span></span><!--EndFragment--></p>
<pre>date                          # show system date
date 041217002011.00          # set date and time
cal 2011                      # show 2011 schedule
cal 02 2009                   # show february 2009 schedule
clock -w                      # save date changes in BIOS</pre>
<p>
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;"><!--StartFragment-->To view the <strong>disk space consumption</strong>, directories or files, we can use different commands like <em>"ls"</em>, <em>"df"</em> and <em>"du"</em>. Below we combine them with other commands to optimize viewing:</span></span><!--EndFragment--></p>
<pre>ls -lSr | more                             # <!--StartFragment-->show file and directories sorted by size<!--EndFragment-->
df -h                                      # partitions list
du -sh dir1                                # used space by dir1
du -h --max-depth=1 | sort -nr             # <!--StartFragment-->show size of all subdirectories in the current location in descending order<!--EndFragment-->
du -sk * | sort -rn                        # <!--StartFragment-->show file and directories sorted by size</pre>
<p>
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;"><!--StartFragment-->Finally, shutdown, restart or log off:</span></span><!--EndFragment--></p>
<pre>shutdown -h 23:17                # scheduled <!--StartFragment-->shutdown at 23:17<!--EndFragment-->
shutdown -c                      # cancel a scheduled <!--StartFragment-->shutdown
shutdown -h now                  # shutdown
shutdown -r now                  # restart
halt                             # shutdown
poweroff                         # shutdown
reboot                           # restart
logout                           # log out</pre>
<p>
&nbsp;</p>
<h1>
<span style="font-family: arial, helvetica, sans-serif; font-size: 14px;">Refereces</span></h1>
<ol>
<li>
<span style="font-family: arial, helvetica, sans-serif; font-size: 14px;">Red Hat Enterprise Linux: Reference Manual</span></li>
</ol>