---
title: AutoMark | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
ms.assetid: c4de965e-0364-4f78-9936-1f509e85df74
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: f63ee0e28a432e43f30377b9f876004b69cd13dc
ms.sourcegitcommit: 37144589d9f850ff81ec7bfb884429989925a43d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/19/2018
ms.locfileid: "34335732"
---
# <a name="automark"></a>AutoMark
Die Option **AutoMark** gibt die Zeit in Millisekunden an, die für die Erfassung von Leistungsindikatorereignissen für Windows-Software beansprucht wird. Windows-Leistungsindikatoren werden in der Option **WinCounter** angegeben.  
  
 In der Befehlszeile kann nur eine **AutoMark**-Option angegeben werden. Bitte beachten Sie, dass das von **AutoMark** angegebene Samplingintervall **WinCounter** unabhängig vom Hauptsamplingintervall ist.  
  
## <a name="syntax"></a>Syntax  
  
```cmd  
VSPerfCmd.exe /Start:Method /WinCounter:Path /AutoMark:Milliseconds  
```  
  
#### <a name="parameters"></a>Parameter  
 `Milliseconds`  
 Gibt die Zeit in Millisekunden an, die für die Erfassungen von Windows-Leistungsindikatorereignissen beansprucht wird.  
  
## <a name="required-options"></a>Erforderliche Optionen  
 **WinCounter:** `Path`  
 Gibt den Windows-Leistungsindikator an, der erfasst werden soll. Wenn Sie die Instrumentierungsmethode verwenden, können Sie mehrere Windows-Indikatoren angeben. Wenn Sie die Samplingmethode verwenden, können Sie nur einen Software-Indikator angeben. Die Option **WinCounter** muss in einer Befehlszeile angegeben sein, die die Option **Start** enthält.  
  
## <a name="example"></a>Beispiel  
 In diesem Beispiel ist ein Samplingintervall von 1000 ms für zwei Windows-Leistungsindikatoren festgelegt.  
  
```cmd  
VSPerfCmd.exe /Start:Trace /Output:TestApp.exe.vsp /WinCounter:"\Process(*)\% Processor Time" /WinCounter:"\ASP.NET\Pages/sec" /AutoMark:1000  
VSPerfCmd.exe /Launch:TestApp.exe  
```  
  
## <a name="see-also"></a>Siehe auch  
 [VSPerfCmd](../profiling/vsperfcmd.md)   
 [Profilerstellung für eigenständige Anwendungen](../profiling/command-line-profiling-of-stand-alone-applications.md)   
 [Profilerstellung für ASP.NET-Webanwendungen](../profiling/command-line-profiling-of-aspnet-web-applications.md)   
 [Profilerstellung für Dienste](../profiling/command-line-profiling-of-services.md)