---
layout: post
title:  How to install SPAN?
date:   2014-04-07 05:00:00
description: Installation is very simple, for Linux and Mac users only need to have installed Tcl/Tk 8.5, then download SPAN software from here and unzip it. Finally, we define two environment variables SPAN and AVISPA_PACKAGE.
tags: security criptography
categories: Innovation
thumbnail: assets/img/Research/como-instalar-span/1.png
---
Security Protocol Animator (SPAN) is a free tool to check cryptographic protocols that helps in searching and characterization of attacks. **The main advantage of this application is that allows different verification techniques using a same protocol**. We can say, it is a graphical interface for managing HLPSL (High-Level Protocol Specification Language) and CAS+ (an implementation of the Protocol Central Authentication), which allows the translation between these languages ​​and also provides a friendly graphical user interface. **SPAN helps to produce interactively sequences messages** or MSC (Message Sequence Charts).

**This tool is used for simulating cryptographic protocol**, allows active or passive intruder simulation, the automatic attack's construction of the designed protocols. The protocol can be edited by means of HLPSL or CAS+, having the ability to convert between these languages. Some features of the graphical user interface are shown in Figure #1.

<div class="row mt-3" style="text-align: center">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="assets/img/Research/como-instalar-span/1.png" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Figure #1: SPAN GUI description.
</div>

SPAN can be used in three different modes:

- **Protocol simulator**: it can simulate by MSC from a HLPSL code.
- **Intrusion simulator**: simulates a protocol with a passive or active attacker.
- **Attack simulator**: from outputs of OFMC or CL-ATSE (other tools from [AVISPA project](http://www.avispa-project.org/)).

## Installation

**Installation is very simple, for Linux and Mac users only need to have installed Tcl/Tk 8.5**, then download SPAN software from [here](http://www.irisa.fr/celtique/genet/span/) and unzip it (for example in `/usr/bob/span`). **Finally, we define two environment variables**: `SPAN` and `AVISPA_PACKAGE`, for this, open a terminal and type:

```sh
export SPAN=/usr/bob/span
export AVISPA_PACKAGE=/usr/bob/span
```

Taking into account that `/usr/bob/span` is the path where you unzipped SPAN. The program runs as any other script, we should write in a terminal:

```sh
./span
```

If we unzipped SPAN in a folder in your user directory, for example `/home/myuser/span/`, so, every time you start your machine will have to perform the above procedure. To avoid this, we can make a simple little bash script, for this, create a text file called `start`, we can do it with any text editor like `gedit` or `kate`, or via command line with `vi` or `nano`. On the command line, open a terminal and headed to the path where you have unpacked SPAN (`/home/myuser/span/`), and write:

```sh
cd /home/myuser/span/ # go to the folder
nano start # it creates a file called start
```

Then, we write into the file the following:

```sh
#! /bin/bash
export SPAN=/home/myuser/span/
export AVISPA_PACKAGE=/home/myuser/span/
./span
exit
```

To exit from the text editor press `CTRL+X` and the editor will ask if you want to save the changes, we answer yes. Now all that remains is to give execute permission to the file, then we write:

```sh
chmod +x start
```

Tested by typing:

```sh
./start
```

And ready!

## References

1. Y. Glouche, T. Genet, O. Heen and O. Courtay A Security Protocol Animator Tool for AVISPA. In ARTIST2 Workshop on Security Specification and Verification of Embedded Systems , pp. 15, Pisa, May 2006.
2. [http://www.irisa.fr/celtique/genet/span/](http://www.irisa.fr/celtique/genet/span/)
