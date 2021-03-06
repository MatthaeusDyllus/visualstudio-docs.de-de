---
title: IDebugMemoryContext2 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
f1_keywords:
- IDebugMemoryContext2
helpviewer_keywords:
- IDebugMemoryContext2 interface
ms.assetid: 3a544c8b-11dc-46bb-8549-261e4ac5bbc4
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 26ae199d1fee210559f599cdfe1393aeae5dd169
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/16/2018
---
# <a name="idebugmemorycontext2"></a>IDebugMemoryContext2
Diese Schnittstelle stellt eine Position im Adressraum des Computers, das derzeit debuggte Programm ausgeführt wird.  
  
## <a name="syntax"></a>Syntax  
  
```  
IDebugMemoryContext2 : IUnknown  
```  
  
## <a name="notes-for-implementers"></a>Hinweise für Implementierer  
 Die Debugging-Modul (DE) implementiert diese Schnittstelle, um eine Adresse im Speicher darzustellen.  
  
## <a name="notes-for-callers"></a>Hinweise für Aufrufer  
 Ein Aufruf von [GetMemoryContext](../../../extensibility/debugger/reference/idebugproperty2-getmemorycontext.md) oder [GetMemoryContext](../../../extensibility/debugger/reference/idebugreference2-getmemorycontext.md) gibt diese Schnittstelle. Darüber hinaus Aufrufe von [hinzufügen](../../../extensibility/debugger/reference/idebugmemorycontext2-add.md) und [Subtract](../../../extensibility/debugger/reference/idebugmemorycontext2-subtract.md) neue Kopien dieser Schnittstelle zurück, nachdem die entsprechende arithmetische Operation angewendet wurde.  
  
## <a name="methods-in-vtable-order"></a>Methoden in Vtable-Reihenfolge  
 Die folgende Tabelle zeigt die Methoden der `IDebugMemoryContext2`.  
  
|Methode|Beschreibung|  
|------------|-----------------|  
|[getName](../../../extensibility/debugger/reference/idebugmemorycontext2-getname.md)|Ruft den Benutzer angezeigten Namen für diesen Kontext ab.|  
|[GetInfo](../../../extensibility/debugger/reference/idebugmemorycontext2-getinfo.md)|Ruft die Informationen, die diesem Kontext zu beschreiben.|  
|[Add](../../../extensibility/debugger/reference/idebugmemorycontext2-add.md)|Fügt einen angegebenen Wert auf den aktuellen Kontext Adresse, die ein neuer Kontext erstellt.|  
|[Subtrahieren](../../../extensibility/debugger/reference/idebugmemorycontext2-subtract.md)|Subtrahiert einen angegebenen Wert des aktuellen Kontexts Absenderadresse einen neuen Kontext erstellt.|  
|[Compare](../../../extensibility/debugger/reference/idebugmemorycontext2-compare.md)|Vergleicht zwei Kontexten auf die Weise ersichtlich Vergleichsflags.|  
  
## <a name="remarks"></a>Hinweise  
 Visual Studio **Arbeitsspeicher** Fenster Aufrufe [GetMemoryContext](../../../extensibility/debugger/reference/idebugproperty2-getmemorycontext.md) zum Abrufen der `IDebugMemoryContext2` -Schnittstelle, den ausgewerteten Ausdruck verwendet, für die Speicheradresse enthält. Dieser Kontext dann an übergeben wird [ReadAt](../../../extensibility/debugger/reference/idebugmemorybytes2-readat.md) und [WriteAt](../../../extensibility/debugger/reference/idebugmemorybytes2-writeat.md) an die Adresse zum Lesen oder schreiben.  
  
## <a name="requirements"></a>Anforderungen  
 Header: msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Assembly: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>Siehe auch  
 [Core-Schnittstellen](../../../extensibility/debugger/reference/core-interfaces.md)   
 [GetMemoryContext](../../../extensibility/debugger/reference/idebugproperty2-getmemorycontext.md)   
 [GetMemoryContext](../../../extensibility/debugger/reference/idebugreference2-getmemorycontext.md)   
 [ReadAt](../../../extensibility/debugger/reference/idebugmemorybytes2-readat.md)   
 [WriteAt](../../../extensibility/debugger/reference/idebugmemorybytes2-writeat.md)