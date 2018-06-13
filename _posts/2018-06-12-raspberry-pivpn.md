---
layout: post
title:  RaspberryPi | VPN Server (pivpn)
---
# Description
...only a draft..

Tested with:
- [x] Hardware: [https://www.raspberrypi.org/products/raspberry-pi-zero-w/](RaspberryPi Zero W)
- [x] Operating System: [hypriot](https://blog.hypriot.com/)

## RaspberryPi
- OpenVPN with PiVPN | [Github](https://github.com/pivpn/pivpn) | [Home](http://www.pivpn.io/)

# Firewall/iptables
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

# SELinux
Set to "permissive" (logging only), unless you are an advanced user
