---
layout: post
title:  RaspberryPi | VPN Server (pivpn)
categories: ['raspberry','software']
published: true
---
# Details
Tested with:
- [x] Hardware: [https://www.raspberrypi.org/products/raspberry-pi-zero-w/](RaspberryPi Zero W)
- [x] Operating System: [hypriot](https://blog.hypriot.com/)

# Installation
- OpenVPN with PiVPN | [Github](https://github.com/pivpn/pivpn) | [Home](http://www.pivpn.io/)

Download & run installer:
```
$ curl -L https://install.pivpn.io | bash
```

Generate client certificate(s):
```
$ pivpn --add
```

List available options:
```
$ pivpn --help
```

Import the generated certificates on your clients, and you are ready to
connect.

# Troubleshooting
If you are unable to access the internet, please configure
iptables/firewall settings ont the pivpn server (see below)

## Firewall/iptables
Add persistent firewall-rules:
- OpenVPN (1194/udp)
- Masquerading

```
# systemctl status firewalld
# firewall-cmd --permanent --list-all --zone=public
# firewall-cmd --permanent --add-service openvpn --zone=public
# firewall-cmd --permanent --add-masquerading --zone=public
# firewall-cmd --reload
# firewall-cmd --permanent --list-all --zone=public
# journalctl -f -u firewalld
```

## SELinux
Set to "permissive" (logging only), unless you are an advanced user
