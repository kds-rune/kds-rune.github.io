---
layout: post
title: Tips andTricks | Microsoft SQL database stuck
---
#
..only a draft..

Tested with:
-[x] Microsoft SQL Studio 2014
-[x] Microsoft SQL Server 2014 (Standard)

# Database stuck
Open SQL Management Studio and execute queries below:

First, find any and all processes locking your database:
```
EXEC sp_who2
```
..then user the corresponding SPID to kill the processes:
```
KILL <SPID>
```
