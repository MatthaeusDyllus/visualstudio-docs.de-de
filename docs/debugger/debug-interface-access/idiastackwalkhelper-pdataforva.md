---
title: IDiaStackWalkHelper::pdataForVA | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaStackWalkHelper2::pdataByVA method
ms.assetid: fafc38fe-74dc-4726-9a51-eebf3a673d7f
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 9eb500539184d6ac5e7e3cb00e753a00f3585057
ms.sourcegitcommit: 3d10b93eb5b326639f3e5c19b9e6a8d1ba078de1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2018
---
# <a name="idiastackwalkhelperpdataforva"></a>IDiaStackWalkHelper::pdataForVA
Gibt zurück, der PDATA-Datenblock, die der virtuellen Adresse zugeordnet.  
  
## <a name="syntax"></a>Syntax  
  
```C++  
HRESULT pdataForVA(   
   ULONGLONG  va,  
   DWORD      cbData,  
   DWORD*     pcbData,  
   BYTE*      pbData  
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `va`  
 [in] Gibt die virtuelle Adresse der Daten zu erhalten.  
  
 `cbData`  
 [in] Die Größe der Daten in Bytes zu erhalten.  
  
 `pcbData`  
 [out] Gibt die tatsächliche Größe der Daten in Byte, das abgerufen wurde.  
  
 `pbData`  
 [in, out] Ein Puffer, der mit der angeforderten Daten ausgefüllt ist. Nicht mit `NULL`.  
  
## <a name="return-value"></a>Rückgabewert  
 Im Erfolgsfall gibt `S_OK`. Gibt `S_FALSE` Wenn keine PDATA für die angegebene Adresse vorhanden ist. Andernfalls wird ein Fehlercode zurückgegeben.  
  
## <a name="remarks"></a>Hinweise  
 PDATA (im Abschnitt mit dem Namen ".pdata") eine Kompiliereinheit enthält Informationen zur Ausnahmebehandlung für Funktionen.  
  
 Der Aufrufer weiß, wie viele Daten zurückgegeben werden, damit der Aufrufer nicht erforderlich verfügt, um Unterstützung bitten für wie viele Daten zur Verfügung steht. Daher ist es zulässig, eine Implementierung dieser Methode einen Fehler wird zurückgegeben, wenn die `pbData` Parameter ist `NULL`.  
  
## <a name="see-also"></a>Siehe auch  
 [IDiaStackWalkHelper](../../debugger/debug-interface-access/idiastackwalkhelper.md)