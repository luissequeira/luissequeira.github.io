---
layout: post
title:  How to modify files with SED?
date:   2014-05-12 05:00:00
description: Sed is a stream editor which is used to perform basic text transformations on an input stream (a file or input from a pipeline) or filter strings. It permits to modify the contents of different lines in a file, based on some parameters.
tags: linux console
categories: Tutorials
---
<h1>
<span style="font-family: arial, helvetica, sans-serif; font-size: 14px;">What is sed?</span></h1>
<p>
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;">Sed is a stream editor which is used to perform basic text transformations on an input stream (a file or input from a pipeline) or filter strings. It permits to <strong>modify the contents of different lines in a file</strong>, based on some parameters.</span></span></p>
<p>
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;">For the examples shown in this article, you used the 4.2.1 version of sed as shown below:</span></span></p>
<pre><span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;">sed --version</span></span>

<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;">GNU sed version 4.2.1</span></span>
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;">Copyright (C) 2009 Free Software Foundation, Inc.</span></span>
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;">This is free software; see the source for copying conditions. There is NO</span></span>
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;">warranty; not even for MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE,</span></span>
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;">to the extent permitted by law.</span></span></pre>
<p>
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;">Sed has a syntax as follows:</span></span></p>
<pre><span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;">sed [-options] [command] [&lt;file(s)&gt;]</span></span></pre>
<p>
&nbsp;</p>
<h1>
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;">Visualization</span></span></h1>
<p>
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;">For the cases where you need to display the contents of a file or part of it, we can use any of the following commands:</span></span></p>
<pre><span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;">sed 5q file1                              # see the firsts 5 lines of file1</span></span>
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;">cat -n file1 | sed -n '5,6 p'        # see lines 5 and 6 of file1</span></span>
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;">sed -n '1p' file1 &gt; file2             # copy the first line of file1 to file2</span></span>
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;">sed -n '$p' file1                        # show the last line of file1</span></span></pre>
<p>
&nbsp;</p>
<h1>
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;">Replacing strings and characters</span></span></h1>
<p>
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;">In these cases, it is always advisable storing in another file, the results of a substitution, leaving the original file unchanged. Some examples are:</span></span></p>
<pre><span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;"># replace strings in all lines that satisfied the string of file1 and store the result in file2</span></span>
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;">sed 's/old_string/new_string/g' file1 &gt; file2</span></span>
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;"># replace strings only in lines 200 y 201</span></span>
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;">sed '200,201 s/old_string/new_string/g' file1 &gt; file2</span></span>
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;"># replace several strings by new one</span></span>
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;">sed 's/old_string_1\|old_string_2/new_string/g' file1 &gt; file2</span></span>
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;"># replace all lowercase to uppercase</span></span>
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;">sed 'y/abcdefghijklmnopqrstuvwxyz/ABCDEFGHIJKLMNOPQRSTUVWXYZ/' file1 &gt; file2</span></span></pre>
<p>
&nbsp;</p>
<h1>
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;">Insert strings</span></span></h1>
<p>
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;">As in the previous case, the original file is left unchanged while the second will contain the changes.</span></span></p>
<pre><span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;"># insert a string at the beginning of each line</span></span>
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;">sed 's/^/string_at_the_beginning/' file1 &gt;file2</span></span>
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;"># insert a string at the end of the file</span></span>
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;">sed -e '$ string_at_the_end' file &gt; file2</span></span>
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;"># insert a blank line before each line that matches with string</span></span>
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;">sed '/string/{x;p;x;}' file1 &gt; file2</span></span>
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;"># insert a blank line after each line that matches with string</span></span>
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;">sed '/string/G' file1 &gt; file2</span></span>
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;"># insert a blank line before and other after each line that matches with string</span></span>
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;">sed '/string/{x;p;x;G;}' file1 &gt; file2</span></span>
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;"># insert a blank line every 2 lines</span></span>
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;">sed 'n;G;' file1 &gt; file2</span></span></pre>
<p>
&nbsp;</p>
<h1>
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;">Delete lines and strings</span></span></h1>
<p>
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;">If we want to delete characters or entire lines, either because they are empty or commented, we can use the following commands:</span></span></p>
<pre><span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;">sed '2,4 d' file1 &gt; file2                    # remove lines 100 and 105 of file1</span></span>
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;">sed '5,20 !d' file1 &gt; file2                 # delete all lines except the 5 and 20</span></span>
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;">sed '$d' file1 &gt; file2                        # delete the last line of file1</span></span>
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;">sed -i '$d' file1                               # delete the last line of file1 in the same file</span></span>
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;">sed '/string/ d' file1 &gt; file2              # remove lines that satisfied a string</span></span>
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;">sed '/^$/d' file1 &gt; file2                    # remove blank lines</span></span>
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;">sed '/^$/d; / *#/d' file1 &gt; file2          # remove blank lines and bash comments</span></span></pre>
<p>
&nbsp;</p>
