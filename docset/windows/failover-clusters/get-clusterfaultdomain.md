---
author: brianlic-msft
description: 
external help file: ClusterFaultDomain.cdxml-help.xml
keywords: powershell, cmdlet
manager: alanth
ms.date: 2016-12-20
ms.prod: powershell
ms.technology: powershell
ms.topic: reference
online version: 
schema: 2.0.0
title: Get-ClusterFaultDomain
ms.assetid: 731AC930-E887-47E7-89AA-066D790DD8B6
---

# Get-ClusterFaultDomain

## SYNOPSIS
Gets the cluster fault domains in a cluster.

## SYNTAX

```
Get-ClusterFaultDomain [[-Name] <String[]>] [-Type <FaultDomainType[]>] [-Id <String[]>]
 [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

## DESCRIPTION
The **Get-ClusterFaultDomain** cmdlet gets the cluster fault domains in a cluster.

## EXAMPLES

### Example 1: Get all fault domains in the cluster
```
PS C:\>Get-ClusterFaultDomain
Name            Type ParentName ChildrenNames
----            ---- ---------- -------------
CONTOSO-VM-1101 Node
```

This command gets all the fault domains in the cluster.

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

### -Id
Specifies the ID of the fault domain that this cmdlet gets as an array.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Name
Specifies the name of the fault domain that this cmdlet gets as an array.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases: 

Required: False
Position: 0
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

### -Type
Specifies the type of the fault domains that this cmdlet gets from the cluster.

```yaml
Type: FaultDomainType[]
Parameter Sets: (All)
Aliases: FaultDomainType
Accepted values: Unknown, Site, Rack, Chassis, Node

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[New-ClusterFaultDomain](./New-ClusterFaultDomain.md)

[Remove-ClusterFaultDomain](./Remove-ClusterFaultDomain.md)

[Set-ClusterFaultDomain](./Set-ClusterFaultDomain.md)
