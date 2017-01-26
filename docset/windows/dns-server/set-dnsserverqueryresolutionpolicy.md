---
author: brianlic-msft
description: 
external help file: PS_DnsServerQueryResolutionPolicy_v1.0.0.cdxml-help.xml
keywords: powershell, cmdlet
manager: alanth
ms.date: 2016-12-20
ms.prod: powershell
ms.technology: powershell
ms.topic: reference
online version: 
schema: 2.0.0
title: Set-DnsServerQueryResolutionPolicy
ms.assetid: 0D7A6874-0BFD-4A01-B6CE-C2F6A8C287AA
---

# Set-DnsServerQueryResolutionPolicy

## SYNOPSIS
Updates settings of a query resolution policy on a DNS server.

## SYNTAX

### Server (Default)
```
Set-DnsServerQueryResolutionPolicy [-PassThru] [-ComputerName <String>] -Name <String>
 [-TransportProtocol <String>] [-TimeOfDay <String>] [-RecursionScope <String>] [-ServerInterfaceIP <String>]
 [-QType <String>] [-ProcessingOrder <UInt32>] [-ClientSubnet <String>] [-Condition <String>]
 [-InternetProtocol <String>] [-Fqdn <String>] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

### Zone
```
Set-DnsServerQueryResolutionPolicy [-PassThru] [-ComputerName <String>] [-ZoneName] <String> -Name <String>
 [-TransportProtocol <String>] [-TimeOfDay <String>] [-ServerInterfaceIP <String>] [-QType <String>]
 [-ProcessingOrder <UInt32>] [-ClientSubnet <String>] [-Condition <String>] [-InternetProtocol <String>]
 [-Fqdn <String>] [-ZoneScope <String>] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

### InputObject
```
Set-DnsServerQueryResolutionPolicy [-PassThru] [-ComputerName <String>] [-InputObject] <CimInstance>
 [[-ZoneName] <String>] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## DESCRIPTION
The **Set-DnsServerQueryResolutionPolicy** cmdlet updates the settings of a policy for query resolution on a Domain Name System (DNS) server.

## EXAMPLES

### Example 1: Add a criterion to a policy
```
PS C:\>Set-DnsServerQueryResolutionPolicy -Name "PolicyMalicious" -InternetProtocol "eq,IPv4" -PassThru | Format-List *
Action                : Ignore
AppliesOn             : QueryProcessing
Condition             : And
Content               : 
Criteria              : {DnsServerPolicyCriteria, DnsServerPolicyCriteria}
IsEnabled             : True
Level                 : Server
Name                  : PolicyMalicious
ProcessingOrder       : 2
ZoneName              : 
PSComputerName        : 
CimClass              : root/Microsoft/Windows/DNS:DnsServerPolicy
CimInstanceProperties : {Action, AppliesOn, Condition, Content...} 
CimSystemProperties   : Microsoft.Management.Infrastructure.CimSystemProperties
```

This command adds a value for Internet protocol for the policy named PolicyMalicious.
The command uses the **Format-List** cmdlet to control the appearance of the output.
For more information, type `Get-Help Format-List`.

## PARAMETERS

### -AsJob
{{Fill AsJob Description}}

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -CimSession
Runs the cmdlet in a remote session or on a remote computer.
Enter a computer name or a session object, such as the output of a New-CimSessionhttp://go.microsoft.com/fwlink/p/?LinkId=227967 or Get-CimSessionhttp://go.microsoft.com/fwlink/p/?LinkId=227966 cmdlet.
The default is the current session on the local computer.

```yaml
Type: CimSession[]
Parameter Sets: (All)
Aliases: Session

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ClientSubnet
Specifies the client subnet criterion.
Specify a criterion in the following format: 

operator, value01, value02, .
. .
, operator, value03, value04, .
. .

The operator is either EQ or NE.
You can specify no more than one of each operator in a criterion.

The policy treats values that follow the EQ operator as multiple assertions which are logically combined (OR'd).
The policy treats values that follow the NE operator as multiple assertions which are logically differenced (AND'd).
The criterion is satisfied if the subnet of the request matches one of the EQ values and does not match any of the NE values.

```yaml
Type: String
Parameter Sets: Server, Zone
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ComputerName
Specifies a remote DNS server.
You can specify an IP address or any value that resolves to an IP address, such as an FQDN, host name, or NETBIOS name.

```yaml
Type: String
Parameter Sets: (All)
Aliases: Cn

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Condition
Specifies how the policy treats multiple criteria.
The acceptable values for this parameter are:

- OR.
The policy evaluates criteria as multiple assertions which are logically combined (OR'd). 
- AND.
The policy evaluates criteria as multiple assertions which are logically differenced (AND'd). 

The default value is AND.

```yaml
Type: String
Parameter Sets: Server, Zone
Aliases: 
Accepted values: AND, OR

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Confirm
Prompts you for confirmation before running the cmdlet.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -Fqdn
Specifies the FQDN criterion.
Specify a criterion in the following format: 

operator, value01, value02, .
. .
, operator, value03, value04, .
. .

The operator is either EQ or NE.
You can specify no more than one of each operator a criterion.

The policy treats values that follow the EQ operator as multiple assertions which are logically combined (OR'd).
The policy treats values that follow the NE operator as multiple assertions which are logically differenced (AND'd).
The criterion is satisfied if the FQDN of the request matches one of the EQ values and does not match any of the NE values.
You can include the asterisk (*) as the wildcard character.
For example, `EQ,*.contoso.com,NE,*.fabricam.com`.

```yaml
Type: String
Parameter Sets: Server, Zone
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -InputObject
{{Fill InputObject Description}}

```yaml
Type: CimInstance
Parameter Sets: InputObject
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -InternetProtocol
Specifies the Internet Protocol criterion.
Specify a criterion in the following format: 

operator, value01, value02, .
. .
, operator, value03, value04, .
. .

The operator is either EQ or NE.
You can specify no more than one of each operator in a criterion.

The policy treats values that follow the EQ operator as multiple assertions which are logically combined (OR'd).
The policy treats values that follow the NE operator as multiple assertions which are logically differenced (AND'd).
The criterion is satisfied if the IP address of the request matches one of the EQ values and does not match any of the NE values.

```yaml
Type: String
Parameter Sets: Server, Zone
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Name
Specifies the name of the policy to modify.

```yaml
Type: String
Parameter Sets: Server, Zone
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -PassThru
Returns an object representing the item with which you are working.
By default, this cmdlet does not generate any output.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ProcessingOrder
Specifies the precedence of the policy.
Higher integer values have lower precedence.
By default, this cmdlet adds a new policy as the lowest precedence.

If this cmdlet changes the processing order to be equal to the processing order of an existing policy, then the DNS server updates the processing order of the existing policies.

```yaml
Type: UInt32
Parameter Sets: Server, Zone
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -QType
Specifies the query type criterion.
Specify a criterion in the following format: 

operator, value01, value02, .
. .
, operator, value03, value04, .
. .

The operator is either EQ or NE.
You can specify no more than one of each operator in a criterion.

The policy treats values the follow the EQ operator as multiple assertions which are logically combined (OR'd).
The policy treats values that follow the NE operator as multiple assertions which are logically differenced (AND'd).
The criterion is satisfied if the type of query of the request matches one of the EQ values and does not match any of the NE values.

```yaml
Type: String
Parameter Sets: Server, Zone
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -RecursionScope
Specifies the scope of recursion.
If the policy is a recursion policy, and if a query matches it, the DNS server uses settings from this scope to perform recursion for the query.

```yaml
Type: String
Parameter Sets: Server
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ServerInterfaceIP
Specifies the IP address of the server interface on which the DNS server listens.
Specify a criterion in the following format: 

operator, value01, value02, .
. .
, operator, value03, value04, .
. .

The operator is either EQ or NE.
You can specify no more than one of each operator in the criterion.

The policy treats values the follow the EQ operator as multiple assertions which are logically combined (OR'd).
The policy treats values that follow the NE operator as multiple assertions which are logically differenced (AND'd).
The criterion is satisfied if the IP address of the interface matches one of the EQ values and does not match any of the NE values.

```yaml
Type: String
Parameter Sets: Server, Zone
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ThrottleLimit
Specifies the maximum number of concurrent operations that can be established to run the cmdlet.
If this parameter is omitted or a value of `0` is entered, then Windows PowerShell® calculates an optimum throttle limit for the cmdlet based on the number of CIM cmdlets that are running on the computer.
The throttle limit applies only to the current cmdlet, not to the session or to the computer.

```yaml
Type: Int32
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -TimeOfDay
Specifies the time of day criterion.
Specify a criterion in the following format: 

operator, value01, value02, .
. .
, operator, value03, value04, .
. .

The operator is either EQ or NE.
You can specify no more than one of each operator in the criterion.

The policy treats values the follow the EQ operator as multiple assertions which are logically combined (OR'd).
The policy treats values that follow the NE operator as multiple assertions which are logically differenced (AND'd).
The criterion is satisfied if the time of day of the request matches one of the EQ values and does not match any of the NE values.

```yaml
Type: String
Parameter Sets: Server, Zone
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -TransportProtocol
Specifies the transport protocol criterion.
Specify a criterion in the following format: 

operator, value01, value02, .
. .
, operator, value03, value04, .
. .

The operator is either EQ or NE.
You can specify no more than one of each operator in the string.

The policy treats values the follow the EQ operator as multiple assertions which are logically combined (OR'd).
The policy treats values that follow the NE operator as multiple assertions which are logically differenced (AND'd).
The criterion is satisfied if the transport protocol of the request matches one of the EQ values and does not match any of the NE values.

```yaml
Type: String
Parameter Sets: Server, Zone
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -WhatIf
Shows what would happen if the cmdlet runs.
The cmdlet is not run.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -ZoneName
Specifies the name of a DNS zone on which the zone level policy.
The zone must exist on the DNS server.

```yaml
Type: String
Parameter Sets: Zone
Aliases: 

Required: True
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

```yaml
Type: String
Parameter Sets: InputObject
Aliases: 

Required: False
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ZoneScope
Specifies a list of scopes and weights for the zone.
Specify the value as a string in this format: 

Scope01, Weight01; Scope02, Weight02; 

If you do not specify the weight, the default value is one (1).

```yaml
Type: String
Parameter Sets: Zone
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance#DnsServerPolicy

## NOTES

## RELATED LINKS

[Add-DnsServerQueryResolutionPolicy](./Add-DnsServerQueryResolutionPolicy.md)

[Get-DnsServerQueryResolutionPolicy](./Get-DnsServerQueryResolutionPolicy.md)

[Remove-DnsServerQueryResolutionPolicy](./Remove-DnsServerQueryResolutionPolicy.md)

[Add-DnsServerZoneTransferPolicy](./Add-DnsServerZoneTransferPolicy.md)
