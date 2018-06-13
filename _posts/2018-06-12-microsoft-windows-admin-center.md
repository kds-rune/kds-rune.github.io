---
layout: post
title: Microsoft | Windows Admin Center (WAC)
---

# Description
...only a draft..

Tested with:
-[ ] Microsoft Server 2019 (Core)
-[ ] Microsoft Server 2019
-[x] Microsoft Server 2016 (Core)
-[ ] Microsoft Server 2016

# Instructions
1) Download [installer](http://aka.ms/WACDownload)
2) Copy installer to server (or make available)
3) Start [https://docs.microsoft.com/en-us/windows-server/manage/windows-admin-center/deploy/install](installation):
```
PS> msiexec /i <NameOfInstallationFile>.msi /qn /L*v log.txt SME_PORT=443 SSL_CERTIFICATE_OPTION=generate
```
4) Access server from https://<ServerNameOrAddress>
5) Login as a user with access to WAC server/service
