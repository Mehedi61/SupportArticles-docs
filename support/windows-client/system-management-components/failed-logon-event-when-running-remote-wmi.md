---
title: Failed logon event when running remote WMI
description: Provides a solution to a failed logon event when you run remote WMI command.
ms.date: 09/16/2020
author: Deland-Han 
ms.author: delhan
manager: dscontentpm
audience: itpro
ms.topic: troubleshooting
ms.prod: windows-client
localization_priority: medium
ms.reviewer: kaushika
ms.prod-support-area-path: WMI
ms.technology: SysManagementComponents
---
# Failed logon event generated when running remote WMI command

This article provides a solution to a failed logon event when you run remote WMI command.

_Original product version:_ &nbsp; Windows 7 Service Pack 1, Windows Server 2012 R2  
_Original KB number:_ &nbsp; 2816192

## Symptoms

Consider the following scenario:

- You've two or more computers running Windows.
- The computers are set up in a workgroup or domain environment.
- You run a remote WMI query using an application that makes WMI calls from one computer to another computer.
In this scenario, if you review the Security log on the remote computer you'll notice an Event ID 4625 with regards to failure audit events for failed logon with bad username or password. You'll also note that subsequently there is a successful logon with the credentials specified on the remote WMI query.

## Cause

This is due to the fact that pass-through authentication is always attempted first even if specific credentials are specified in the tool being used.

## Resolution

You can safely ignore the error message.