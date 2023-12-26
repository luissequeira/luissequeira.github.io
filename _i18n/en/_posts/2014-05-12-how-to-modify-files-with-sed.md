---
layout: post
title:  How to modify files with SED?
date:   2014-05-12 05:00:00
description: Sed is a stream editor which is used to perform basic text transformations on an input stream (a file or input from a pipeline) or filter strings. It permits to modify the contents of different lines in a file, based on some parameters.
tags: linux console commandline
categories: Linux
thumbnail: assets/img/Linux/como-modificar-ficheros-con-sed/1.jpg
---

<div class="row mt-3" style="text-align: center">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="assets/img/Linux/como-modificar-ficheros-con-sed/1.jpg" class="img-fluid rounded z-depth-1" %}
    </div>
</div>

## What is sed?

`sed` is a stream editor which is used to perform basic text transformations on an input stream (a file or input from a pipeline) or filter strings. It permits to **modify the contents of different lines in a file**, based on some parameters.

For the examples shown in this article, you used the 4.2.1 version of `sed` as shown below:

```sh
sed --version</span></span>

GNU sed version 4.2.1
Copyright (C) 2009 Free Software Foundation, Inc.
This is free software; see the source for copying conditions. There is NO
warranty; not even for MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE,
to the extent permitted by law.
```

`sed` has a syntax as follows:

```sh
sed [-options] [command] [<file(s)>]
```

## Visualization

For the cases where you need to display the contents of a file or part of it, we can use any of the following commands:

```sh
sed 5q file1                            # see the firsts 5 lines of file1
cat -n file1 | sed -n '5,6 p'           # see lines 5 and 6 of file1
sed -n '1p' file1 > file2               # copy the first line of file1 to file2
sed -n '$p' file1                       # show the last line of file1
```

## Replacing strings and characters

In these cases, it is always advisable storing in another file, the results of a substitution, leaving the original file unchanged. Some examples are:

```sh
# replace strings in all lines that satisfied the string of file1 and store the result in file2
sed 's/old_string/new_string/g' file1 > file2

# replace strings only in lines 200 y 201
sed '200,201 s/old_string/new_string/g' file1 > file2

# replace several strings by new one
sed 's/old_string_1\|old_string_2/new_string/g' file1 > file2

# replace all lowercase to uppercase
sed 'y/abcdefghijklmnopqrstuvwxyz/ABCDEFGHIJKLMNOPQRSTUVWXYZ/' file1 > file2
```

## Insert strings

As in the previous case, the original file is left unchanged while the second will contain the changes.

```sh
# insert a string at the beginning of each line
sed 's/^/string_at_the_beginning/' file1 > file2

# insert a string at the end of the file
sed -e '$ string_at_the_end' file > file2

# insert a blank line before each line that matches with string
sed '/string/{x;p;x;}' file1 > file2

# insert a blank line after each line that matches with string
sed '/string/G' file1 > file2

# insert a blank line before and other after each line that matches with string
sed '/string/{x;p;x;G;}' file1 > file2

# insert a blank line every 2 lines
sed 'n;G;' file1 > file2
```

## Delete lines and strings

If we want to delete characters or entire lines, either because they are empty or commented, we can use the following commands:

```sh
sed '2,4 d' file1 > file2                   # remove lines 100 and 105 of file1
sed '5,20 !d' file1 > file2                 # delete all lines except the 5 and 20
sed '$d' file1 > file2                      # delete the last line of file1
sed -i '$d' file1                           # delete the last line of file1 in the same file
sed '/string/ d' file1 > file2              # remove lines that satisfied a string
sed '/^$/d' file1 > file2                   # remove blank lines
sed '/^$/d; / *#/d' file1 > file2           # remove blank lines and bash comments
```
