---
layout: post
title: Tips & Tricks - SQL Problems
---

# Database stuck
Open SQL Management Studio and execute queries below:

First:
```
EXEC sp_who2
```

Then kill the process SPID locking your database:
```
KILL <SPID>
```
