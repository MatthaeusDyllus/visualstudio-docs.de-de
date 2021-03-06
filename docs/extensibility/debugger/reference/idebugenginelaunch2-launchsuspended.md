---
title: IDebugEngineLaunch2::LaunchSuspended | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
f1_keywords:
- IDebugEngineLaunch2::LaunchSuspended
helpviewer_keywords:
- IDebugEngineLaunch2::LaunchSuspended
ms.assetid: 5dd2643e-c20a-470e-9024-2a423eb39856
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: a05e8f034ec30f0f387675759cb7601f7b3fc3e7
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/16/2018
---
# <a name="idebugenginelaunch2launchsuspended"></a>IDebugEngineLaunch2::LaunchSuspended
Diese Methode startet einen Prozess mithilfe von Debugging-Modul (DE).  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT LaunchSuspended (   
   LPCOLESTR             pszMachine,  
   IDebugPort2*          pPort,  
   LPCOLESTR             pszExe,  
   LPCOLESTR             pszArgs,  
   LPCOLESTR             pszDir,  
   BSTR                  bstrEnv,  
   LPCOLESTR             pszOptions,  
   LAUNCH_FLAGS          dwLaunchFlags,  
   DWORD                 hStdInput,  
   DWORD                 hStdOutput,  
   DWORD                 hStdError,  
   IDebugEventCallback2* pCallback,  
   IDebugProcess2**      ppDebugProcess  
);  
```  
  
```csharp  
int LaunchSuspended(  
   string               pszServer,   
   IDebugPort2          pPort,   
   string               pszExe,   
   string               pszArgs,   
   string               pszDir,   
   string               bstrEnv,   
   string               pszOptions,   
   enum_LAUNCH_FLAGS    dwLaunchFlags,   
   uint                 hStdInput,   
   uint                 hStdOutput,   
   uint                 hStdError,  
   IDebugEventCallback2 pCallback,   
   out IDebugProcess2   ppProcess  
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `pszMachine`  
 [in] Der Name des Computers, den Prozess zu starten. Verwenden Sie einen null-Wert, um den lokalen Computer anzugeben.  
  
 `pPort`  
 [in] Die [IDebugPort2](../../../extensibility/debugger/reference/idebugport2.md) Schnittstelle, die den Port, der das Programm, in ausgeführt wird darstellt.  
  
 `pszExe`  
 [in] Der Name der ausführbaren Datei gestartet werden.  
  
 `pszArgs`  
 [in] Die Argumente, die an die ausführbare Datei übergeben werden soll. Möglicherweise ein null-Wert, wenn keine Argumente.  
  
 `pszDir`  
 [in] Der Name des Arbeitsverzeichnisses, das durch die ausführbare Datei verwendet werden soll. Möglicherweise ein null-Wert, wenn kein Arbeitsverzeichnis erforderlich ist.  
  
 `bstrEnv`  
 [in] Umgebungsblock mit NULL endende Zeichenfolgen, gefolgt von einer zusätzlichen NULL-Terminator.  
  
 `pszOptions`  
 [in] Die Optionen für die ausführbare Datei.  
  
 `dwLaunchFlags`  
 [in] Gibt an, die [LAUNCH_FLAGS](../../../extensibility/debugger/reference/launch-flags.md) für eine Sitzung.  
  
 `hStdInput`  
 [in] Handle für einen anderen Eingabedatenstrom. Möglicherweise 0, wenn keine Umleitung erforderlich ist.  
  
 `hStdOutput`  
 [in] Handle für einen anderen Ausgabestream. Möglicherweise 0, wenn keine Umleitung erforderlich ist.  
  
 `hStdError`  
 [in] In einen Ausgabestream alternativen Fehler zu behandeln. Möglicherweise 0, wenn keine Umleitung erforderlich ist.  
  
 `pCallback`  
 [in] Die [IDebugEventCallback2](../../../extensibility/debugger/reference/idebugeventcallback2.md) Objekt, das Debugger-Ereignisse empfängt.  
  
 `ppDebugProcess`  
 [out] Gibt die resultierende [IDebugProcess2](../../../extensibility/debugger/reference/idebugprocess2.md) -Objekt, das die gestarteten Prozess darstellt.  
  
## <a name="return-value"></a>Rückgabewert  
 Im Erfolgsfall gibt `S_OK`ist, andernfalls wird ein Fehlercode zurückgegeben.  
  
## <a name="remarks"></a>Hinweise  
 In der Regel [!INCLUDE[vsprvs](../../../code-quality/includes/vsprvs_md.md)] startet eine Anwendung mithilfe der [LaunchSuspended](../../../extensibility/debugger/reference/idebugportex2-launchsuspended.md) Methode und fügt dann den Debugger an das Programm angehalten. Es gibt jedoch Situationen, in dem die Debugging-Modul möglicherweise ein Programm (z. B., wenn die Debugging-Modul ist Bestandteil des ein Interpreter und das derzeit debuggte Programm ist eine interpretierte Sprache), in diesem Fall starten [!INCLUDE[vsprvs](../../../code-quality/includes/vsprvs_md.md)] verwendet die `IDebugEngineLaunch2::LaunchSuspended` Methode .  
  
 Die [ResumeProcess](../../../extensibility/debugger/reference/idebugenginelaunch2-resumeprocess.md) Methode wird aufgerufen, um den Prozess zu starten, nachdem der Prozess in einem angehaltenen Zustand erfolgreich gestartet wurde.  
  
## <a name="see-also"></a>Siehe auch  
 [IDebugEngineLaunch2](../../../extensibility/debugger/reference/idebugenginelaunch2.md)   
 [IDebugPort2](../../../extensibility/debugger/reference/idebugport2.md)   
 [LAUNCH_FLAGS](../../../extensibility/debugger/reference/launch-flags.md)   
 [IDebugEventCallback2](../../../extensibility/debugger/reference/idebugeventcallback2.md)   
 [IDebugProcess2](../../../extensibility/debugger/reference/idebugprocess2.md)   
 [LaunchSuspended](../../../extensibility/debugger/reference/idebugportex2-launchsuspended.md)   
 [ResumeProcess](../../../extensibility/debugger/reference/idebugenginelaunch2-resumeprocess.md)