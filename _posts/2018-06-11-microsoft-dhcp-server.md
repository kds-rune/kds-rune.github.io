---
layout: post
title: Microsoft | Install DHCP role (powershell)
categories: ['microsoft','software']
published: true
---
# Details
Tested with:
- [x] Microsoft Server 2016 (Core)

This guide assumes you already have a server with operating system installed,
and a static ip address configured. You should also have access to the server,
or be able to manage it remotely (prefered)

# Installation
Install the DHCP role:
```
PS> Install-WindowsFeature DHCP -IncludeManagementTools
```

Add scope to manage:
```
PS> Add-DhcpServerv4Scope -Name "NameOfScope" -StartRange x.x.x.x -EndRange x.x.x.x -SubnetMask x.x.x.x -Description "ScopeDescription"
```

Set scope options:
```
PS> Set-DhcpServerv4OptionValue -ScopeID "NameOfScope" -DNSServer x.x.x.x -DNSDomain domain.name -Router x.x.x.x
```

Set server options (omit 'scope-id'):
```
PS> Set-DhcpServerv4OptionValue -DNSServer x.x.x.x -DNSDomain domain.name -Router x.x.x.x
```

Authorize server in AD:
```
Add-DhcpServerInDC -DNSName domain.name
```

Configure failover:
```
Add-DhcpServerv4Failover -Name "FailoverName" -PartnerServer partnerserver.domain.name -ScopeId x..x.x -LoadBalancePercent 50 -SharedSecret "SomeSecretCode" -MaxClientLeadTime 2:00:00 -AutoStateTransition $true -StateSwitchInterval 2:00:00
```
