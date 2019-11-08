---
layout: post
title: "Accessing Windows File From Linux Subshell"
date: 2019-11-06 01:25:06 -0700
comments: true
tags: Geekout
---

If you are using Ubuntu subshell in Windows (I use the one available in Microsoft Store), this is for you. There are times, where you may need to access the files saved on your windows in the Linux subshell. 
All you need to do is mount your drive. You may need to access the subshell via administrative privileges. For example, if you have the file in C: Drive, use the following:

```
cd /mnt/c
ls
```

The same can be used to access data from external hard disk too. If the external disk is in D: Drive, the command would simply change to:

```
cd /mnt/d
ls
```
