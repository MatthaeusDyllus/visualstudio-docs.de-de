---
title: IDebugBinder3 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
f1_keywords:
- IDebugBinder3
helpviewer_keywords:
- IDebugBinder3 interface
ms.assetid: 92353a74-dc74-4f93-8762-61d6b220478c
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 6924cfb321ade3955c8e039e32a0374158ea43b6
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/16/2018
---
# <a name="idebugbinder3"></a>IDebugBinder3
> [!IMPORTANT]
>  In Visual Studio 2015 wird diese Möglichkeit zum Implementieren von ausdruckauswertung veraltet. Informationen zu CLR-ausdrucksauswertungen implementieren, finden Sie unter [CLR-Ausdrucksauswertungen](https://github.com/Microsoft/ConcordExtensibilitySamples/wiki/CLR-Expression-Evaluators) und [Managed Expression Evaluator Sample](https://github.com/Microsoft/ConcordExtensibilitySamples/wiki/Managed-Expression-Evaluator-Sample).  
  
 Diese Schnittstelle bietet Zugriff auf Typen, Aliase und benutzerdefinierte Schnellansicht-Dienste.  
  
## <a name="syntax"></a>Syntax  
  
```  
IDebugBinder3 : IDebugBinder  
```  
  
## <a name="notes-for-implementers"></a>Hinweise für Implementierer  
 Ein Debugmodul implementiert diese Schnittstelle, um Aliase, benutzerdefinierte Schnellansicht-Dienste und den Zugriff auf objekttypdaten unterstützen.  
  
## <a name="notes-for-callers"></a>Hinweise für Aufrufer  
 Ein [IDebugBinder](../../../extensibility/debugger/reference/idebugbinder.md) Schnittstelle erhält diese Schnittstelle mit [QueryInterface](/cpp/atl/queryinterface).  
  
## <a name="methods-in-vtable-order"></a>Methoden in Vtable-Reihenfolge  
 Zusätzlich zu den bereitgestellten Methoden die [IDebugBinder](../../../extensibility/debugger/reference/idebugbinder.md) diese Schnittstelle implementiert, die folgenden:  
  
|Methode|Beschreibung|  
|------------|-----------------|  
|[GetMemoryObject](../../../extensibility/debugger/reference/idebugbinder3-getmemoryobject.md)|Ruft ein Speicherobjekt, das den Arbeitsspeicher, zu dem dieses Objekt gebunden ist, darstellt.|  
|[GetExceptionObjectAndType](../../../extensibility/debugger/reference/idebugbinder3-getexceptionobjectandtype.md)|Ruft die Ausnahme, die diesem Objekt (sofern vorhanden) zugeordnet,|  
|[FindAlias](../../../extensibility/debugger/reference/idebugbinder3-findalias.md)|Ruft einen Alias mit dem angegebenen Namen ab,|  
|[GetAllAliases](../../../extensibility/debugger/reference/idebugbinder3-getallaliases.md)|Ruft ein Array aller Aliase für dieses Objekt ab,|  
|[GetTypeArgumentCount](../../../extensibility/debugger/reference/idebugbinder3-gettypeargumentcount.md)|Ruft die Anzahl von Argumenttypen, die diesem Objekt zugeordneten ab,|  
|[GetTypeArguments](../../../extensibility/debugger/reference/idebugbinder3-gettypearguments.md)|Ruft eine Liste von Argumenttypen, die diesem Objekt zugeordneten ab,|  
|[GetEEService](../../../extensibility/debugger/reference/idebugbinder3-geteeservice.md)|Ruft eine Schnittstelle zu einem schnellansichtsdienst,|  
|[GetMemoryContext64](../../../extensibility/debugger/reference/idebugbinder3-getmemorycontext64.md)|Konvertiert ein Ort des Objekts oder eine 64-Bit-Speicheradresse an einen Speicherkontext.|  
  
## <a name="requirements"></a>Anforderungen  
 Header: ee.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Assembly: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>Siehe auch  
 [Ausdruck Auswertung Schnittstellen](../../../extensibility/debugger/reference/expression-evaluation-interfaces.md)   
 [IDebugBinder](../../../extensibility/debugger/reference/idebugbinder.md)