---
title: TaskScheduler-Verwaltungsklasse - interne Member | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- TaskScheduler class [.NET Framework debug engines]
- debug engines, TaskScheduler class [.NET Framework]
ms.assetid: 87f1c969-0217-4464-8907-7609c1bf61d3
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 18cd3ec809df921d6baefbf8018fefc77db238d3
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/16/2018
---
# <a name="taskscheduler-class---internal-members"></a>TaskScheduler-Verwaltungsklasse - interne Member
In diesem Thema wird beschrieben, die internen Member des der <xref:System.Threading.Tasks.TaskScheduler?displayProperty=fullName> Klasse, mit denen Sie einen benutzerdefinierten Debugger zu implementieren. Allgemeine Informationen zu dieser Klasse finden Sie unter der <xref:System.Threading.Tasks.TaskScheduler> Referenzthema.  
  
 **Namespace:** <xref:System.Threading.Tasks?displayProperty=fullName>  
  
 **Assembly:** "mscorlib" (in "mscorlib.dll")  
  
 Da diese internen Member von .NET Framework zugegriffen werden kann, wird die folgende Syntax gemeinsame Intermediate Language (CIL) bereitgestellt.  
  
## <a name="syntax"></a>Syntax  
  
```  
.class public abstract auto ansi beforefieldinit System.Threading.Tasks.TaskScheduler  
       extends System.Object  
```  
  
## <a name="members"></a>Member  
  
### <a name="methods"></a>Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[GetScheduledTasksForDebugger](../../extensibility/debugger/getscheduledtasksfordebugger-method.md)|Ruft ein Array aller geplanten Aufgaben ab.|  
|[GetTaskSchedulersForDebugger](../../extensibility/debugger/gettaskschedulersfordebugger-method.md)|Ruft ein Array aller <xref:System.Threading.Tasks.TaskScheduler> Objekte, die derzeit aktiv sind.|  
  
## <a name="remarks"></a>Hinweise  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Threading.Tasks.TaskScheduler?displayProperty=fullName>   
 [Interne Elemente der parallelen Erweiterung für das .NET-Framework](../../extensibility/debugger/parallel-extension-internals-for-the-dotnet-framework.md)