---
layout: post
title:  How to manage files and directories on GNU/Linux?
date:   2013-11-18 06:30:00
description: Once inside a directory, you might want to see the content, hidden files, permissions or details of each files or subdirectories, even delete and find files.
tags: console terminal commandline
categories: Linux
thumbnail: assets/img/Linux/como-gestionar-archivos-y-directorios-en-gnu-linux/snapshot18.png
---
Before starting with the use of **some Linux commands**, I want to remind the importance of reviewing the **reference manual** for each command, because this is the place where you can find all the possible options. The reference manual can be displayed on a terminal using the `man` command, for example, if we see the manual of the `man` command in a terminal, we should write `man man` and we would see something like this:

<div class="row mt-3" style="text-align: center">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="assets/img/Linux/como-gestionar-archivos-y-directorios-en-gnu-linux/snapshot18.png" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Figure #1: Linux terminal displaying the manual of the `man` command.
</div>

One of the most used command is `cd`, it is used to access a directory, here are some examples:

```sh
cd                  # go to the personal directory
cd ..               # back one level
cd ../..            # back two levels
cd -                # go to previous directory
cd /home            # go to /home directory
cd ~user1           # go to the directory user1
```

If you want to know the current route:

```sh
pwd                 # display the current directory path
```

Once inside a directory, you might want to see the content, hidden files, permissions or details of each files or subdirectories, in this case `ls` is the solution:

```sh
ls                  # list the contents of a directory
ls -F               # distinguishing the directories with a slash
ls -l               # showing the details
ls -lh              # showing the details(in a size format of K, M)
ls -a               # including hidden files
ls *[0-9]           # list the files and folders that contain numbers
tree                # show files and folders in a tree starting by the root
```

To create directories we use `mkdir` like this:

```sh
mkdir dir1                    # create a directory called dir1
mkdir dir1 dir2               # create two directories at once
mkdir -p /dir1/dir2/dir3      # create a directory structure, if not there
```

To delete files and directories:

```sh
rm file1                      # delete the file file1
rm -f file1                   # remove file1 in forced mode
rm -r dir1                    # recursively delete the directory dir1 with all contents
rm -rf dir1 dir2              # remove two directories with their contents recursively and forced
```

To move (rename), copy files and folders we need two different commands:

```sh
mv old_dir new_dir                 # rename or move a file or directory
cp file1 /path/to/destiny/         # copy a file to destiny
cp file1 file2 destiny/            # copy two files simultaneously
cp file1 file2                     # copy file1 in file2
cp -r dir1 destiny/                # copy a directory
```

To create symbolic links (shortcuts):

```sh
ln -s file link                    # create a symbolic link to the file or directory
```

To find files there are several options one of the most common is using the command `find`, though some users find it annoying as it may wait too much time in large systems, so they prefer to use `locate`, for this command to work properly, the database must be updated by means of `updatedb` command.

```sh
find / -name file1                              # search file and directory from the system root
find / -user user1                              # belonging to user1
find /home/user1 -name \*.bin                   # with .bin extention in the directory / home/user1
find /usr/bin -type f -atime +100               # unused binary files in the last 100 days
find /usr/bin -type f -mtime -10                # files created or changed within the last 10 days
locate \*.ps                                    # find files with .ps extentions
whereis file                                    # show the location of a binary file, help, or source
which command                                   # show the full path to a command
```

## References

1. Red Hat Enterprise Linux: Reference Manual