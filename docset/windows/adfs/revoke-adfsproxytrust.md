---
author: brianlic-msft-msft
description: 
external help file: Microsoft.IdentityServer.Management.dll-Help.xml
keywords: powershell, cmdlet
manager: alanth
ms.date: 2016-12-20
ms.prod: powershell
ms.technology: powershell
ms.topic: reference
online version: 
schema: 2.0.0
title: Revoke-AdfsProxyTrust
ms.assetid: AE02463D-DF40-4E7F-A92C-E641A8CCB47D
---

# Revoke-AdfsProxyTrust

## SYNOPSIS
Revokes trust for all federation server proxies configured for the Federation Service.

## SYNTAX

```
Revoke-AdfsProxyTrust [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Revoke-AdfsProxyTrust** cmdlet revokes trust for all federation server proxies by resetting the trust ID for the Federation Service.
Use this cmdlet for lockdown purposes in the event of an attack or confirmed possible threat to your deployment.
The cmdlet effectively revokes trust to all configured proxies immediately.

## EXAMPLES

### Example 1: Revoke trust
```
PS C:\> Revoke-AdfsProxyTrust
```

This command revokes all trust between the current federation server and any of its configured federation server proxies.

## PARAMETERS

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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### None

## OUTPUTS

### None

## NOTES
* Use this cmdlet only in the event of a security breach in a live deployment. We recommend that, if you want to practice using this cmdlet, you use a test lab environment.

## RELATED LINKS
