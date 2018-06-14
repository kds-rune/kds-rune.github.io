---
layout: post
title: RemoteApp Infrastructure
categories: ['microsoft','software','powershell']
published: false
---
# Index

* [Information]()
* [Planning Your Infrastructure]()
* [Server Roles Explained]()

# Information
Estimated time:
- ???

Operating Systems:
- [x] Microsoft Server 2016 (Core)
- [x] Microsoft Server 2016

Remote Desktop Services options:
- [ ] Remote Desktops (shared machine for desktops)
- [ ] Virtual Desktops (separate machine per desktop)
- [x] Remote Applications (applications as a service; no desktop)

## Links
- [One]()

# Planning your infrastructure
We will be using the following servers for testing:

Name    | Server   | CPU   | RAM      | Role(s)             | Zone
------: | :------- | :---: | :------: | :------------------ | :-------
rds-br1 | core     | 1     | 512 MiB  | licensing, broker   | internal
rds-gw1 | standard | 1     | 1024 MiB | gateway, web-access | dmz
rds-sh1 | standard | 1     | 1024 MiB | session host        | internal

# Server Roles explained

## Licensing Server
Manages your user/device licenses (CAL)

## Connection Broker
Manages the communication between clients and remote resources

Performs the following tasks:
- Check user credentials
- Assigns clients to hosts
- Load balancing for hosts
- Manages images (?)
- Redirects multimedia processing

## Gateway Server
Allows secure TLS/SSL connection to your RDS environment. Example is connecting
from the internet ('home-office'). Should be in dmz

## Web Access Server
Allows you to view and connect to published resources via the browser

## Session Host
This is the computer doing the heavy lifting. Published applications are
installed and run on the session hosts. Users get assigned to the hosts by
the connection broker(s)

## Example scenarios
Office, via browser (RemoteApp):
[Client]-->[Web Access]-->[Broker]-->[Session]

Home-office, via browser (RemoteApp):
[Client]-->[Internet]-->[Web Access]-->[Gateway]-->[Broker]-->[Session]

Office via remote desktop:
[Client]-->[Broker]-->[Session Host]

Home-office via remote desktop:
[Client]-->[Internet]-->[Gateway]-->[Broker]-->[Session Host]

# Installation | Licensing Server  
```

```
