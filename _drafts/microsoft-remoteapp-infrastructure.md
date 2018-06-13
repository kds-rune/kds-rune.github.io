---
layout: post
title: Microsoft | RemoteApp Infrastructure
categories: ['microsoft','software','powershell']
published: false
---
## Details
Operating Systems:
- [x] Microsoft Server 2016 (Core)
- [x] Microsoft Server 2016

Remote Desktop Services options:
- [] Remote Desktops (shared machine for desktops)
- [] Virtual Desktops (separate machine per desktop)
- [x] Remote Applications (applications as a service; no desktop)

links:
- [One]()

## Planning the infrastructure
We will be using the following servers:

Name         | Server   | CPU   | RAM      | Role(s)
:----------- | :------- | :---: | :------: | :----------------
rds-broker1  | core     | 1     | 1024 Mib | licensing, broker
rds-gateway1 | standard | 1     | 1024 Mib | gateway
rds-web1     | standard | 1     | 1024 Mib | web-access
rds-host1    | standard | 2     | 4096 Mib | session host
client1      | -        | -     | -        | user client

## Roles explained

#### Licensing Server
...

#### Cnnection Broker
...

#### Gateway Server
...

#### Web Access Server
...

#### Session Host
...
