---
layout: post
title:  ¿Cómo modificar ficheros con SED?
date:   2014-05-15 05:00:00
description: Sed es un editor de flujo que se utiliza para realizar transformaciones básicas de texto en un flujo de entrada (un fichero o la entrada de una tubería) o filtrar cadenas de caracteres. Permite modificar el contenido de diferentes líneas de un fichero basándose en una serie de parámetros.
tags: linux consola comandos terminal
categories: Linux
thumbnail: assets/img/Linux/como-modificar-ficheros-con-sed/1.jpg
---

<div class="row mt-3" style="text-align: center">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="assets/img/Linux/como-modificar-ficheros-con-sed/1.jpg" class="img-fluid rounded z-depth-1" %}
    </div>
</div>

## ¿Qué es sed?

`sed` es un editor de flujo que se utiliza para realizar transformaciones básicas de texto en un flujo de entrada (un fichero o la entrada de una tubería) o filtrar cadenas de caracteres. Permite **modificar el contenido de diferentes líneas de un fichero basándose en una serie de parámetros**.

Para los ejemplos que se muestran en este artículo, se ha utilizado la versión 4.2.1 de `sed` como se muestra a continuación:

```sh
sed --version

GNU sed version 4.2.1
Copyright (C) 2009 Free Software Foundation, Inc.
This is free software; see the source for copying conditions. There is NO
warranty; not even for MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE,
to the extent permitted by law.
```

`sed` tiene una sintaxis de la siguiente manera:

```sh
sed [-opciones] [comando] [<fichero(s)>]
```

## Visualización

Para los casos en los que se necesita visualizar el contenido de un fichero o parte de éste, podemos utilizar alguno de los siguientes comandos:

```sh
sed 5q fichero1                                  # ver las primeras 5 líneas del fichero1
cat -n fichero1 | sed -n '5,6 p'                 # ver las líneas 5 y 6 del fichero1
sed -n '1p' fichero1 > fichero2                  # copiar la primera linea de fichero1 a fichero2
sed -n '$p' fichero1                             # mostrar la última línea de fichero1
```

## Sustitución de cadenas y caracteres

En estos casos siempre es recomendable almacenar el resultado de una sustitución en otro fichero, dejando el fichero original sin modificar. Algunos ejemplos son los siguientes:

```sh
# reemplazar cadenas en todas las lineas que contentan dicha cadena del fichero1 y almacenar el resultado en fichero2
sed 's/cadena_vieja/cadena_nueva/g' fichero1 > fichero2

# reemplazar cadenas sólo en las líneas 200 y 201
sed '200,201 s/cadena_vieja/cadena_nueva/g' fichero1 > fichero2

# reemplazar multiples cadenas por una nueva
sed 's/cadena_vieja_1\|cadena_vieja_2/cadena_nueva/g' fichero1 > fichero2

# remplazar todas las minúsculas por mayúsculas
sed 'y/abcdefghijklmnopqrstuvwxyz/ABCDEFGHIJKLMNOPQRSTUVWXYZ/' fichero1 > fichero2
```

## Insertar cadenas

Al igual que en el caso anterior, se dejará el fichero inicial sin modificar mientras que el segundo contendrá los cambios realizados.

```sh
# insertar una cadena al principio de cada línea
sed 's/^/cadena_al_inicio/' fichero1 > fichero2 

# añadir una línea al final de un fichero
sed -e '$ cadena_al_final' fichero > fichero2

# insertar una linea en blanco antes de cada linea que cumpla con una cadena
sed '/cadena/{x;p;x;}' fichero1 > fichero2

# insertar una linea en blanco detrás de cada linea que cumpla con una cadena
sed '/cadena/G' fichero1 > fichero2 

# insertar una linea en blanco antes y después de cada linea que cumpla con una cadena
sed '/cadena/{x;p;x;G;}' fichero1 > fichero2

# insertar una línea en blanco cada 2 líneas
sed 'n;G;' fichero1 > fichero2
```

## Eliminar líneas y cadenas

Para eliminar caracteres o líneas completas, ya sea porque están vacías o bien por ser comentario, podemos utilizar los siguientes comandos:

```sh
sed '2,4 d' fichero1 > fichero2             # eliminar las líneas 100 y 105 del fichero1
sed '5,20 !d' fichero1 > fichero2           # eliminar todas las líneas excepto las 5 y 20
sed '$d' fichero1 > fichero2                # eliminar la última línea del fichero1
sed -i '$d' fichero1                        # eliminar la última línea del fichero1 en el mismo fichero
sed '/cadena/ d' fichero1 > fichero2        # eliminar las líneas que contentan una cadena
sed '/^$/d' fichero1 > fichero2             # eliminar líneas en blanco
sed '/^$/d; / *#/d' fichero1 > fichero2     # eliminar líneas en blanco y comentarios bash
```
