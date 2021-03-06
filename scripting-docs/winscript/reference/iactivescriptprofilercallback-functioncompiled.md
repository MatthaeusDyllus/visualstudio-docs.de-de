---
title: IActiveScriptProfilerCallback::FunctionCompiled | Microsoft Docs
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
apiname: IActiveScriptProfilerCallback.FunctionCompiled
apilocation: scrobj.dll
ms.assetid: a7e9ef17-3891-4731-9d08-c37bc489be61
caps.latest.revision: "8"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 797476d4892224ad0b27c9caf579c0704693c835
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/27/2017
---
# <a name="iactivescriptprofilercallbackfunctioncompiled"></a>IActiveScriptProfilerCallback::FunctionCompiled
Benachrichtigt den Profiler, Objekt, das das Skript-engine-Funktion gefunden, beim Kompilieren eines Skripts.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT FunctionCompiled(  
    [in] PROFILER_TOKEN functionId,  
    [in] PROFILER_TOKEN scriptId,  
    [in] [string] const WCHAR *pwszFunctionName,  
    [in] [string] const WCHAR *pwszFunctionNameHint,  
    [in] IUnknown *pIDebugDocumentContext);  
```  
  
#### <a name="parameters"></a>Parameter  
 `functionId`  
 [in] Die eindeutige ID der Funktion. Diese ID wird vom Skriptmodul zugewiesen.  
  
 `scriptId`  
 [in] Die eindeutige ID des Skripts, die die Funktion gehört.  
  
 `pwszFunctionName`  
 [in] Der Name der Funktion oder Null für einer anonymen Funktion.  
  
 `pwszFunctionNameHint`  
 [in] Der abgeleitete Name der Funktion, oder Null, wenn das Skriptmodul nicht über einen beliebigen Namen ableitet.  
  
 `pIDebugDocumentContext`  
 [in] Falls verfügbar, die Zeiger auf ein `IUnknown` -Schnittstelle, die der Profiler für die Abfrage ausführen muss ein [IDebugDocumentContext-Schnittstelle](../../winscript/reference/idebugdocumentcontext-interface.md) Zeiger. Andernfalls NULL.  
  
## <a name="return-value"></a>Rückgabewert  
 Der Rückgabewert dieser Methode wird vom Skriptmodul ignoriert.  
  
## <a name="remarks"></a>Hinweise  
 Das Skriptmodul bieten den Dokumentenkontext, nur, wenn dies vom Host unterstützt wird.  
  
## <a name="see-also"></a>Siehe auch  
 [IActiveScriptProfilerCallback-Schnittstelle](../../winscript/reference/iactivescriptprofilercallback-interface.md)