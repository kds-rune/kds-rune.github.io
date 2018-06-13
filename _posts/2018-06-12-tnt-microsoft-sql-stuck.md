---
layout: post
title: Tips and Tricks | Microsoft SQL database stuck
---
#
..only a draft..

Tested with:
-[x] Microsoft SQL Studio 2014
-[x] Microsoft SQL Server 2014 (Standard)

# Database stuck (when taking offline)
Open SQL Management Studio and execute the following
query to find any processes (b)locking your database:
```
EXEC sp_who2
```
..then user the corresponding SPID to kill the processes:
```
KILL <SPID>
```
