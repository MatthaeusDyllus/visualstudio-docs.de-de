---
title: IDebugProcessEx2 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
f1_keywords:
- IDebugProcessEx2
helpviewer_keywords:
- IDebugProcessEx2 interface
ms.assetid: 44e309ba-1d6f-499b-aa7e-9b34858a6d57
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 479206b75325c1b7e6bba0e4cc4e9b53944d73d3
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/16/2018
---
# <a name="idebugprocessex2"></a>IDebugProcessEx2
Dieser Schnittstelle können die Sitzung mit dem Debug-Manager (SDM) ein Prozesses, das zum Anfügen oder Trennen vom Prozess zu benachrichtigen.  
  
## <a name="syntax"></a>Syntax  
  
```  
IDebugProcessEx2 : IUnknown  
```  
  
## <a name="notes-for-implementers"></a>Hinweise für Implementierer  
 Ein benutzerdefinierten Port Lieferanten implementiert diese Schnittstelle auf das gleiche Objekt wie die [IDebugProcess2](../../../extensibility/debugger/reference/idebugprocess2.md) -Schnittstelle um:  
  
-   Unterstützung für Überwachung der Sitzungen verbunden an einen Prozess  
  
-   Unterstützung für das automatische Anhängen über mehrere Debugmodule  
  
 Der benutzerdefinierten Port Lieferanten kann diese Schnittstelle implementieren, wenn er entscheidet.  
  
## <a name="notes-for-callers"></a>Hinweise für Aufrufer  
  
-   Ruft die SDM [QueryInterface](/cpp/atl/queryinterface) auf eine `IDebugProcess2` Schnittstelle, um diese Schnittstelle zu erhalten.  
  
## <a name="methods-in-vtable-order"></a>Methoden in Vtable-Reihenfolge  
 Die folgende Tabelle zeigt die Methoden der `IDebugProcessEx2`.  
  
|Methode|Beschreibung|  
|------------|-----------------|  
|[Anfügen](../../../extensibility/debugger/reference/idebugprocessex2-attach.md)|Informiert, dass eine Sitzung jetzt den Prozess Debuggen wird dem Prozess.|  
|[Trennen](../../../extensibility/debugger/reference/idebugprocessex2-detach.md)|Informiert, dass eine Sitzung nicht mehr den Prozess Debuggen wird dem Prozess.|  
|[AddImplicitProgramNodes](../../../extensibility/debugger/reference/idebugprocessex2-addimplicitprogramnodes.md)|Programm-Knoten eine Liste der Debugmodule hinzugefügt.|  
  
## <a name="remarks"></a>Hinweise  
 Diese Schnittstelle ist privat zwischen den SDM und den Prozess.  
  
## <a name="requirements"></a>Anforderungen  
 Header: Portpriv.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Assembly: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>Siehe auch  
 [Core-Schnittstellen](../../../extensibility/debugger/reference/core-interfaces.md)   
 [IDebugProcess2](../../../extensibility/debugger/reference/idebugprocess2.md)