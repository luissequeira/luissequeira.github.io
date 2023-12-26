---
layout: post
title:  ¿Cómo instalar SPAN?
date:   2014-04-10 05:00:00
description: La instalación es muy sencilla, para usuarios de Linux y Mac solo es necesario tener instalado Tcl/Tk 8.5, luego descargar el programa SPAN aqui y descomprimir. Por último, definir dos variables de entorno SPAN y AVISPA_PACKAGE.
tags: seguridad criptografía
categories: Innovation
thumbnail: assets/img/Research/como-instalar-span/1.png
---
Security Protocol Animator (SPAN) es una herramienta libre de verificación para protocolos criptográficos que ayuda en la búsqueda y caracterización de ataques. **La principal ventaja de esta aplicación es que permite usar diferentes técnicas de verificación a un mismo protocolo**. Se puede decir que es una interfaz gráfica para el manejo de HLPSL (High-Level Protocol Specification Language) y CAS+ (una implementación del Protocolo de Autenticación Central), que permite la traducción entre estos lenguajes y además brinda una interfaz gráfica más amigable al usuario. **SPAN ayuda a producir de manera interactiva secuencias de mensajes** o MSC (Message Sequence Charts).

**Esta herramienta se utiliza para la simulación de protocolo criptográficos**, permite la simulación de intrusos de manera activa o pasiva, la construcción automática de ataques a los protocolos diseñados. La edición del protocolo se puede realiza mediante HLPSL o CAS+, teniendo la posibilidad de realizar conversiones entre dichos lenguajes. Algunas características de la interfaz gráfica se muestran en la Figura #1.

<div class="row mt-3" style="text-align: center">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="assets/img/Research/como-instalar-span/1.png" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Figura #1: Descripción de la interfaz gráfica de SPAN.
</div>

SPAN puede ser utilizado en tres modos diferentes:

- **Simulador de protocolos**: puede simular protocolos mediante MSC a partir de un código HLPSL.
- **Simulador de intrusos**: permite simular un protocolo con un intruso pasivo o activo.
- **Simulador de ataques**: a partir de las salidas de OFMC o CL-ATSE (otras herramientas del proyecto [AVISPA](http://www.avispa-project.org/)).

## Instalación

**La instalación es muy sencilla, para usuarios de Linux y Mac solo es necesario tener instalado Tcl/Tk 8.5**, luego descargar el programa SPAN [aqui](http://www.irisa.fr/celtique/genet/span/) y descomprimir (por ejemplo en: `/usr/bob/span`). **Por último, definir dos variables de entorno**: `SPAN` y `AVISPA_PACKAGE`, para esto abrimos un terminal y escribimos:

```sh
export SPAN=/usr/bob/span
export AVISPA_PACKAGE=/usr/bob/span
```

Teniendo en cuenta que `/usr/bob/span` es la ruta donde se descomprimió SPAN. El programa se ejecuta como cualquier otro script, solamente se debe escribir en un terminal:

```sh
./span
```

Si has descomprimido SPAN en una carpeta en el directorio de tu usuario, por ejemplo en `/home/mi_usuario/span/`, lo que sucederá es que cada vez que inicies tu máquina tendrás que realizar el procedimiento anterior. Para evitar esto, se puede hacer un pequeño y sencillo script en bash, para ello, creamos un fichero de texto llamado `iniciar`, lo podemos hacer con algún editor de texto como `gedit` o `kate`, o bien por medio de línea de comando con `vi` o `nano`. Por línea de comandos, se abre un terminal y nos dirigimos a la ruta donde hemos descomprimido SPAN (`/home/mi_usuario/span/`), escribimos:

```sh
cd /home/mi_usuario/span/                # ir a la carpeta
nano iniciar                             # se crea un fichero de nombre iniciar
```

Luego, escribimos dentro del fichero lo siguiente:

```sh
#! /bin/bash
export SPAN=/home/mi_usuario/span/
export AVISPA_PACKAGE=/home/mi_usuario/span/
./span
exit
```

Para salir del editor se presiona `CTRL+X` y el editor preguntará si se desea guardar los cambio, a lo que se responde que si. Ahora, lo único que falta es darle permisos de ejecución al fichero, entonces escribimos:

```sh
chmod +x iniciar
```

Se prueba escribiendo:

```sh
./iniciar
```

Y listo!

## References

1. Y. Glouche, T. Genet, O. Heen and O. Courtay A Security Protocol Animator Tool for AVISPA. In ARTIST2 Workshop on Security Specification and Verification of Embedded Systems , pp. 15, Pisa, May 2006.
2. [http://www.irisa.fr/celtique/genet/span/](http://www.irisa.fr/celtique/genet/span/)
