---
layout: post
title: ServerCore - Install DHCP Server Role
---

# Description
...

## Install the DHCP role
PS> Install-WindowsFeature DHCP -IncludeManagementTools

## Add scope tom manage
PS> Add-DhcpServerv4Scope -Name "NameOfScope" -StartRange x.x.x.x -EndRange x.x.x.x -SubnetMask x.x.x.x -Description "ScopeDescription"

## Set scope options
PS> Set-DhcpServerv4OptionValue -ScopeID "NameOfScope" -DNSServer x.x.x.x -DNSDomain domain.name -Router x.x.x.x

## Set server options (omit 'scope-id'):
PS> Set-DhcpServerv4OptionValue -DNSServer x.x.x.x -DNSDomain domain.name -Router x.x.x.x

## Authorize server in AD
Add-DhcpServerInDC -DNSName domain.name

## Add failover
Add-DhcpServerv4Failover -Name "FailoverName" -PartnerServer partnerserver.domain.name -ScopeId x..x.x -LoadBalancePercent 50 -SharedSecret "SomeSecretCode" -MaxClientLeadTime 2:00:00 -AutoStateTransition $true -StateSwitchInterval 2:00:00
