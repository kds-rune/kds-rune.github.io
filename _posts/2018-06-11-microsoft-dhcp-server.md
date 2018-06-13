---
layout: post
title: Microsoft | Install DHCP role
---

# Description
...only a draft..

Tested with:
- [x] Microsoft Server 2016 (Core)

# Instructions

1) Install the DHCP role
```
PS> Install-WindowsFeature DHCP -IncludeManagementTools
```
2) Add scope tom manage
```
PS> Add-DhcpServerv4Scope -Name "NameOfScope" -StartRange x.x.x.x -EndRange x.x.x.x -SubnetMask x.x.x.x -Description "ScopeDescription"
```
3) Set scope options
```
PS> Set-DhcpServerv4OptionValue -ScopeID "NameOfScope" -DNSServer x.x.x.x -DNSDomain domain.name -Router x.x.x.x
```
4) Set server options (omit 'scope-id'):
```
PS> Set-DhcpServerv4OptionValue -DNSServer x.x.x.x -DNSDomain domain.name -Router x.x.x.x
```
5) Authorize server in AD
```
Add-DhcpServerInDC -DNSName domain.name
```
6) Add failover
```
Add-DhcpServerv4Failover -Name "FailoverName" -PartnerServer partnerserver.domain.name -ScopeId x..x.x -LoadBalancePercent 50 -SharedSecret "SomeSecretCode" -MaxClientLeadTime 2:00:00 -AutoStateTransition $true -StateSwitchInterval 2:00:00
```
