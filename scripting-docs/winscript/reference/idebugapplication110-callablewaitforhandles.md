---
title: IDebugApplication110::CallableWaitForHandles | Microsoft Docs
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
helpviewer_keywords:
- IDebugApplication110::CallableWaitForHandles
ms.assetid: 02e79b60-0d67-47f9-bf78-b65a02c9c014
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: b259f5296f8e0b32def793a81e4c2e1069643306
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/27/2017
---
# <a name="idebugapplication110callablewaitforhandles"></a>IDebugApplication110::CallableWaitForHandles
Wartet, bis eines der angegebenen Handles signalisiert wird, während gleichzeitig threadübergreifende Aufrufe an diesen Thread bereitgestellt werden. Diese Methode muss von dem Debuggerthread aufgerufen werden.  
  
> [!IMPORTANT]
>  [IDebugApplication110-Schnittstelle](../../winscript/reference/idebugapplication110-interface.md) wird implementiert von PDM V11. 0 und höher. Gefunden in activdbg100.h.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT CallableWaitForHandles([in] DWORD handleCount, [in, size_is(handleCount)] const HANDLE* pHandles, [out] DWORD* pIndex);  
```  
  
#### <a name="parameters"></a>Parameter  
 `handleCount`  
 Die Anzahl der Handles zu warten.  
  
 `pHandles`  
 Der Satz von Handles zu warten.  
  
 `pIndex`  
 Wenn der HRESULT-Wert S_OK zurück, der Index ist `pHandles` für das Handle, das signalisiert wurde.  
  
## <a name="see-also"></a>Siehe auch  
 [IDebugApplication110-Schnittstelle](../../winscript/reference/idebugapplication110-interface.md)