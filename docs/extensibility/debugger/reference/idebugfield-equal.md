---
title: IDebugField::Equal | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
f1_keywords:
- IDebugField::Equal
helpviewer_keywords:
- IDebugField::Equal method
ms.assetid: 75369fe6-ddd3-497d-80d1-2488e6100e9f
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: b2d195c28123cc786c9a5a97add98b7f67d499b7
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/16/2018
---
# <a name="idebugfieldequal"></a>IDebugField::Equal
Diese Methode vergleicht das Feld mit dem angegebenen Felds auf Gleichheit.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT Equal(   
   IDebugField* pField  
);  
```  
  
```csharp  
int Equal(  
   IDebugField pField  
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `pField`  
 [in] Das Feld, in dieses Objekt verglichen werden soll.  
  
## <a name="return-value"></a>Rückgabewert  
 Wenn die Felder identisch sind, gibt `S_OK`. Gibt zurück, wenn die Felder unterscheiden, `S_FALSE.` wird, andernfalls ein Fehlercode zurückgegeben.  
  
## <a name="see-also"></a>Siehe auch  
 [IDebugField](../../../extensibility/debugger/reference/idebugfield.md)