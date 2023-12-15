---
layout: post
title:  How to manage groups, users and permissions?
date:   2014-03-17 06:00:00
description: Groups are useful for grouping a number of special permissions on the system to a group of users, each user must belong to at least one group. In any system there must be a superuser (root), which will have all the permits and maximum privileges allowing to do any work on the system.
tags: linux system-management manage-groups
categories: Tutorials
---
<p>
<span style="font-family: arial, helvetica, sans-serif; font-size: 14px;">Linux is a multiuser and multitasking operating system, ie, multiple users can work on the system simultaneously running several tasks at once. It is therefore, <strong>very important that the operating system allows the management and control of users</strong>.</span></p>
<p>
<span style="font-family: arial, helvetica, sans-serif; font-size: 14px;"><strong>Unix based systems organize all this by users and groups</strong>, where each user must be identified with a user name and password. During login, the password entered by each user, is encrypted and compared to the encrypted passwords that were previously stored in the system.</span></p>

<p>
<span style="font-family: arial, helvetica, sans-serif; font-size: 14px;"><strong>Groups are useful for grouping a number of special permissions on the system to a group of users, each user must belong to at least one group</strong>. In any system there must be a superuser (root), which will have all the permits and maximum privileges allowing to do any work on the system.</span></p>
<p>
<span style="font-family: arial, helvetica, sans-serif; font-size: 14px;">Here are some examples of the most common commands for managing groups, users and their respective permissions.</span></p>
<p>
&nbsp;</p>
<h1>
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;">Users and Groups</span></span></h1>
<pre>groupadd group_name               # create a new group
groupdel group_name               # delete a group
groupmod -n new_group_name old_group_name          # rename a group
useradd user1                     # create new user
useradd -c full_name -g admin -d /home/user1 -s /bin/bash user1        # create a user user1 belonging to the admin group
userdel -r user1                  # delete a user and delete the home directory
usermod -c “User FTP” -g system -d /ftp/user1 -s /bin/nologin user1    # change user attributes
usermod -aG grupo1,grupo2 user1   # add the user1 user to existing groups
passwd                            # change password
passwd user1                      # change password for user1
chage -E 2011-12-31 user1         # change the date in which a user password expires
pwck                              # check the correct syntax format file /etc/passwd and the existence of users
grpck                             # check the correct syntax format file /etc/group and the existence of groups</pre>
<p>
&nbsp;</p>
<h1>
<span style="font-size:14px;"><span style="font-family:arial,helvetica,sans-serif;">Permissions on files</span></span></h1>
<pre>ls -lh                          # show Permissions
ls /tmp | pr -T5 -W$COLUMNS     # terminal split into 5 columns
chmod ugo+rwx dir1              # set permissions of read (r), write (w) and execute (x) to the owner (u), group (g) and other (o) on the directory dir1
chmod go-rwx dir1               # remove read permission (r), write (w) and execute (x) to the group (g) and others (o) on the directory dir1
chown user1 file1               # change the owner of a file
chown -R user1 dir1             # change the owner of a directory and all files and directories contained within
chgrp grupo1 file1              # change file group
chown user1:grupo1 file1        # change user and group ownership of a file
find / -perm -u+s               # display all system files with SUID configured
chmod u+s /bin/file1            # set the SUID bit on a binary file. The user running this file takes the same privileges as owner
chmod u-s /bin/file1            # disable SUID bit on a binary file
chmod g+s /home/public          # set SGID bit on a directory, similar to SUID but for directory
chmod g-s /home/public          # disable SGID bit on a directory
chmod o+t /home/public          # set STIKY bit in a directory. Allows deletion of files only rightful owners
chmod o-t /home/public          # disable STIKY bit in a directory</pre>
<p>
&nbsp;</p>