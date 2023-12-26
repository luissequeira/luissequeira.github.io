---
layout: post
title:  Useful commands for system information and manage sesion
date:   2013-12-09 06:00:00
description: In this case, several commands are presented which allow us to collect certain system information and session managing.
tags: console terminal commandline
categories: Linux
thumbnail: assets/img/Linux/como-obtener-informacion-sistema-gestionar-apagado-GNULinux/1.png
---

<div class="row mt-3" style="text-align: center">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="assets/img/Linux/como-obtener-informacion-sistema-gestionar-apagado-GNULinux/1.png" class="img-fluid rounded z-depth-1" %}
    </div>
</div>

In a previous article, we showed the use of some [useful commands for manipulating files and directories]({% post_url 2013-11-18-how-to-manage-files-and-directories-on-gnu-linux %}), in this case, several commands are presented which allow us to **collect certain system information**. Also, we will see that displaying the **content of certain files**, can also be a way for giving useful information. Furthermore, the use of session managing commands will be described.

We begin with some commands to get system information: kernel features and architecture.

```sh
arch                   # architecture
uname -m               # architecture
uname -r               # kernel version
uname -a               #complete information
cat /etc/issue         # distribution name
```

Recall that in Linux, everything is stored in files, so if we want to see a detailed system information, `/proc` directory will be of much help, because it contains the **files hierarchy that shows the current state of the kernel**. Within this directory you can find a lot of information about the hardware and any processes running. If you enter to this directory, and you see that files have 0 bytes, do not worry it's normal, because the `/proc` directory contains another file type called **virtual files**, unlike the known types: text and binary files, that you will be more familiarized with. Here are some examples:

```sh
cat /proc/cpuinfo             # CPU information
cat /proc/interrupts          # show interruptions
cat /proc/meminfo             # verify memory usage
cat /proc/mounts              # show mounted filesystem 
cat /proc/swaps               # show swap
cat /proc/version             # kernel version
cat /proc/net/dev             # show network adapters and statistics
lspci -tv                     # show PCI devices
lsusb -tv                     # show USB devices
```

On the other hand, if you want a **real-time monitor system**, the following command is the indicated. When you are using it you can type some options: `h - help`, `u – user`, `p - PID`, `q - exit`.

```sh
top                           # show Linux tasks</pre>
```

For dates, schedules and time, also we have two useful commands:<

```sh
date                          # show system date
date 041217002011.00          # set date and time
cal 2011                      # show 2011 schedule
cal 02 2009                   # show february 2009 schedule
clock -w                      # save date changes in BIOS
```

To view the **disk space consumption**, directories or files, we can use different commands like `ls`, `df` and `du`. Below we combine them with other commands to optimize viewing:

```sh
ls -lSr | more                             # show file and directories sorted by size
df -h                                      # partitions list
du -sh dir1                                # used space by dir1
du -h --max-depth=1 | sort -nr             # show size of all subdirectories in the current location in descending order
du -sk * | sort -rn                        # show file and directories sorted by size
```

Finally, shutdown, restart or log off:

```sh
shutdown -h 23:17                # scheduled shutdown at 23:17
shutdown -c                      # cancel a scheduled shutdown
shutdown -h now                  # shutdown
shutdown -r now                  # restart
halt                             # shutdown
poweroff                         # shutdown
reboot                           # restart
logout                           # log out
```

## Refereces

1. Red Hat Enterprise Linux: Reference Manual