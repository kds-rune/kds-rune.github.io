---
layout: post
title: Microsoft | RemoteApp Infrastructure
categories: ['microsoft','software']
published: false
---
# Details
Tested with:
- [x] Microsoft Server 2016 (Core)
- [x] Microsoft Server 2016

## Planning your insfrastructure
We will be using the following servers:

| name         | server   | role(s)           |
| :----------- | :------- | :---------------- |
| rds-broker1  | core     | licensing, broker |
| rds-gateway1 | standard | gateway           |
| rds-web1     | standard | web access        |
| rds-host1    | standard | session host      |
