---
title: MESSAGETYPE | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
f1_keywords:
- MESSAGETYPE
helpviewer_keywords:
- MESSAGETYPE enumeration
ms.assetid: 800cc77d-3c27-4763-a9df-552a9384bd49
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 3fa09d938e0e7c3853431369c7e0634242df2ee0
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/16/2018
---
# <a name="messagetype"></a>MESSAGETYPE
Gibt den Nachrichtentyp und dem Grund.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
enum enum_MESSAGETYPE {   
   MT_OUTPUTSTRING      = 0x0000001,  
   MT_MESSAGEBOX        = 0x00000002,  
   MT_TYPE_MASK         = 0x000000FF,  
   MT_REASON_EXCEPTION  = 0x00000100,  
   MT_REASON_TRACEPOINT = 0x00000200,  
   MT_REASON_MASK       = 0x0000FF00  
};  
typedef DWORD MESSAGETYPE;  
```  
  
```csharp  
public enum enum_MESSAGETYPE {   
   MT_OUTPUTSTRING      = 0x0000001,  
   MT_MESSAGEBOX        = 0x00000002,  
   MT_TYPE_MASK         = 0x000000FF,  
   MT_REASON_EXCEPTION  = 0x00000100,  
   MT_REASON_TRACEPOINT = 0x00000200,  
   MT_REASON_MASK       = 0x0000FF00  
};  
```  
  
## <a name="members"></a>Member  
 MT_OUTPUTSTRING  
 Gibt an, dass die Nachricht in das Ausgabefenster gesendet werden soll. Dies ist aus sich gegenseitig ausschließende `MT_MESSAGEBOX`.  
  
 MT_MESSAGEBOX  
 Gibt an, dass die Nachricht in einem Meldungsfeld angezeigt werden sollen. Dies ist aus sich gegenseitig ausschließende `MT_OUTPUTSTRING`.  
  
 MT_TYPE_MASK  
 Ein Wert vom Ziel der Nachricht zu isolieren.  
  
 MT_REASON_EXCEPTION  
 Gibt an, dass aufgrund einer Ausnahme ein Meldungsfeld angezeigt wird. Dies ist aus sich gegenseitig ausschließende `MT_REASON_TRACEPOINT`.  
  
 MT_REASON_TRACEPOINT  
 Gibt an, dass als Ergebnis erreichen eines Ablaufverfolgungspunkts ein Meldungsfeld angezeigt wird. Dies ist an sich gegenseitig ausschließende `MT_REASON_EXCEPTION`.  
  
 MT_REASON_MASK  
 Ein Wert zum Isolieren von des Grund für die Meldung angezeigt wird.  
  
## <a name="remarks"></a>Hinweise  
 Diese Werte werden zurückgegeben, aus der [GetMessage](../../../extensibility/debugger/reference/idebugmessageevent2-getmessage.md) und [GetErrorMessage](../../../extensibility/debugger/reference/idebugerrorevent2-geterrormessage.md) Methoden.  
  
 Einer der Werte Ursache kann kombiniert werden, mit einem der Ziel-Ausgabewerte, die mit einem bitweisen `OR`.  
  
## <a name="requirements"></a>Anforderungen  
 Header: msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Assembly: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>Siehe auch  
 [Enumerationen](../../../extensibility/debugger/reference/enumerations-visual-studio-debugging.md)   
 [getMessage](../../../extensibility/debugger/reference/idebugmessageevent2-getmessage.md)   
 [GetErrorMessage](../../../extensibility/debugger/reference/idebugerrorevent2-geterrormessage.md)