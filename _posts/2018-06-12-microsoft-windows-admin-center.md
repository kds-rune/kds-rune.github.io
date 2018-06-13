---
layout: post
title: Microsoft | Windows Admin Center (WAC)
categories: ['microsoft','software']
published: true
---
# Description
Tested with:
- [x] Microsoft Server 2016 (Core)

This guide assumes you already have a server with operating system installed.
You should also have access to the server, or be able to manage it remotely
(prefered). You will need internet access to download the installer (or you
will need to download the full installer from somewhere else)

# Instructions
1) Download [installer](http://aka.ms/WACDownload)
2) Copy installer to server (or make available)
3) Start [https://docs.microsoft.com/en-us/windows-server/manage/windows-admin-center/deploy/install](installation):
```
PS> msiexec /i <NameOfInstallationFile>.msi /qn /L*v log.txt SME_PORT=443 SSL_CERTIFICATE_OPTION=generate
```
4) Access server from https://<ServerNameOrAddress>
5) Login as a user with access to WAC server/service
