---
layout: post
title:  How to install, update and other things with package managers in Linux?
date:   2014-02-10 06:00:00
description: Package managers are tools to automate the process of installing, upgrading, uninstalling or configuring software on Linux. 
tags: linux console terminal commandline
categories: Linux
thumbnail: assets/img/Linux/como-instalar-actualizar-gestores-paquetes-linux/1.jpg
---

<div class="row mt-3" style="text-align: center">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="assets/img/Linux/como-instalar-actualizar-gestores-paquetes-linux/1.jpg" class="img-fluid rounded z-depth-1" %}
    </div>
</div>

**Package managers are tools to automate the process of installing, upgrading, uninstalling or configuring software** on Linux. Package managers are **part of the operating system** and they use a single database for installation and a single packet format, for example: `rpm` or `deb`. They are also responsible for checking the digital signature, and dependency resolution for updates.

Currently, the vast majority of Linux operating systems have a intuitive and easy to use graphics interface for package managers. For this reason, we discuss some basic features of the best-known command-line packet managers, which commonly generate doubts.

## YUM (Yellow dog Updater, Modified) package manager

This is the **package manager for RPM-based** Linux systems as Fedora, Redhat, CentOS and its derivatives e.g. BlueCat. Some of the most common uses are:

```sh
yum install package                     # download and install a package and its dependencies
yum localinstall package.rpm            # install a previously downloaded package and its dependencies
yum update                              # update all installed packages
yum update package                      # update a package
yum remove package                      # remove a package
yum list                                # list all installed packages
yum search package                      # find a package in the repository
yum clean all                           # remove cache packages, headers and others
```

## Dpkg package manager

This is the basis of **Debian's package management system, and therefore, it is also used by distributions like Ubuntu and its derivatives**. Some examples are:

```sh
dpkg -i package.deb           # install a package
dpkg -r package               # remove a package
dpkg -l                       # list all installed packages
dpkg -l | grep httpd          # show all packages with the name "httpd"
dpkg -s package               # obtain information of installed package
dpkg -L package               # file list of an installed package
dpkg -S /bin/ping             # verify which file a package belongs to
```

## APT and APTITUDE package managers

APT (Advanced Packaging Tool) is not really a program, but a C++ library that is used by several programs, e.g. apt-get or apt-cache. On the other hand, aptitude is an interface for apt that facilitate search systems and dependence resolutions to users. **These package managers have commands and options similar to those already described**, as we can see below:

```sh
apt-get install package                # install a package
apt-cdrom install package              # install a package from cdrom
apt-get update                         # update the list of packages
apt-get upgrade                        # update all installed packages
apt-get remove package                 # remove a package
apt-get check                          # verify dependencies
apt-get clean                          # clean cache
apt-cache search package               # list packages that corresponds to "package"
aptitude search paquete                # looking for a package by its name
aptitude show paquete | less           # display information about a package
aptitude install paquete1 paquete2 …   # install multiple packages and their dependencies
aptitude remove paquete                # remove a package
aptitude purge paquete                 # remove a package and clean cache
aptitude clean                         # clean cache
```

> PD: Do you like cows? writes in a terminal: `apt-get moo`

## References

1. [http://yum.baseurl.org/](http://yum.baseurl.org/)
2. [http://www.debian.org/doc/manuals/debian-faq/ch-pkgtools.en.html](http://www.debian.org/doc/manuals/debian-faq/ch-pkgtools.en.html)
3. [http://www.debian.org/doc/manuals/apt-howto/index.es.html](http://www.debian.org/doc/manuals/apt-howto/index.es.html)
4. [http://algebraicthunk.net/~dburrows/projects/aptitude/](http://algebraicthunk.net/~dburrows/projects/aptitude/)
