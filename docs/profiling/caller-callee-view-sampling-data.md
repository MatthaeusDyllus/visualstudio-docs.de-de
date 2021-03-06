---
title: Aufrufer-/Aufgerufener-Ansicht – Samplingdaten | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
helpviewer_keywords:
- sampling profiling method,Caller/Callee view
- Caller/Callee view
ms.assetid: 28e85ed5-1512-4b59-bb84-138a2abca7dd
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 8e964ec877b791fc3058068e2f89706cc5826e0f
ms.sourcegitcommit: 37144589d9f850ff81ec7bfb884429989925a43d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/19/2018
ms.locfileid: "34335969"
---
# <a name="caller--callee-view---sampling-data"></a>Aufrufer-/Aufgerufener-Ansicht – Samplingdaten
In der Aufrufer-/Aufgerufener-Ansicht werden Profilerstellungsinformationen für eine ausgewählte Funktion und ihre übergeordneten und untergeordneten Funktionen angezeigt. Die Aufrufer-/Aufgerufener-Ansicht enthält drei Raster.  
  
 **Aktuelle Funktion** wird im mittleren Raster angezeigt und gibt Profilerstellungsinformationen für die ausgewählte Funktion an. Die Werte umfassen alle Samplingaufrufe der Funktion.  
  
 **Funktionen, die die aktuelle Funktion aufgerufen haben** wird im obersten Raster angezeigt und gibt die einzelnen Beiträge der (übergeordneten) Aufruferfunktion zu den Werten der ausgewählten (aktuellen) Funktion an.  
  
 **Funktionen, die von der aktuellen Funktion aufgerufen wurden** wird im untersten Raster angezeigt und gibt Profilerstellungsinformationen für die aufgerufenen (untergeordneten) Funktionen der ausgewählten Funktion an, wenn die untergeordnete Funktion von der aktuellen Funktion aufgerufen wurde.  
  
> [!NOTE]
>  Verbesserte Sicherheitsfunktionen in Windows 8 und Windows Server 2012 erforderten tiefgreifende Änderungen bei der Datenerfassung des Visual Studio-Profilers auf diesen Plattformen. Außerdem benötigen UWP-Apps neue Erfassungsmethoden. Weitere Informationen finden Sie unter [Profilerstellung für Windows 8- und Windows Server 2012-Anwendungen](../profiling/performance-tools-on-windows-8-and-windows-server-2012-applications.md).  
  
|Spalte|description|  
|------------|-----------------|  
|**Prozess-ID**|Die Prozess-ID (PID) der Profilerstellung.|  
|**Prozessname**|Der Prozessname.|  
|**Modulname**|Der Name des Moduls, das die Funktion enthält.|  
|**Modulpfad**|Der Pfad des Moduls, das die Funktion enthält.|  
|**Quelldatei**|Die Quelldatei, die die Definition der Funktion enthält.|  
|**Funktionsname**|Der vollqualifizierte Name der Funktion.|  
|**Funktionszeilennummer**|Die Zeilennummer des Anfangs dieser Funktion in der Quelldatei.|  
|**Funktionsadresse**|Die Adresse der Funktion.|  
|**Type**|Der Kontext der Funktion:<br /><br /> -   **0** – die aktuelle Funktion<br />-   **1** – eine Funktion, die die aktuelle Funktion aufruft<br />-   **2** – eine Funktionen, die von der aktuellen Funktion aufgerufen wird|  
|**Name der Stammfunktion**|Der Name der aktuellen Funktion.|  
|**Inklusive Samplings**|- Bei der aktuellen Funktion die Anzahl von Samplings, die gesammelt wurden, obwohl diese Funktion oder eine ihrer untergeordneten Funktionen ausgeführt wurde.<br />- Bei einer Aufruferfunktion die Anzahl von inklusiven Samplings der aktuellen Funktion, die gesammelt wurden, als diese Funktion die aktuelle Funktion aufgerufen hat.<br />- Bei einer aufgerufenen Funktion die Anzahl von inklusiven Samplings dieser Funktion, die gesammelt wurden, als die aktuelle Funktion diese Funktion aufgerufen hat.|  
|**Inklusive Samplings in %**|Der Prozentsatz aller Samplings während der Profilerstellung, die inklusive Samplings dieser Funktion waren.|  
|**Exclusive Samplings**|- Bei der aktuellen Funktion die Anzahl der Samplings während der Profilerstellung, die gesammelt wurden, als diese Funktion direkt ausgeführt wurde (d.h., während sich diese Funktion an erster Stelle der Aufrufliste befunden hat). Samplings, die beim Ausführen von untergeordneten Funktionen dieser Funktion gesammelt wurden, sind nicht in den exklusiven Werten enthalten.<br />- Bei einer Aufruferfunktion die Anzahl von exklusiven Samplings der aktuellen Funktion, die gesammelt wurden, als diese Funktion die aktuelle Funktion aufgerufen hat.<br />- Bei einer aufgerufenen Funktion die Anzahl von exklusiven Samplings dieser Funktion, die gesammelt wurden, als die aktuelle Funktion diese Funktion aufgerufen hat.|  
|**Exklusive Samplings %**|Der Prozentsatz aller Samplings während der Profilerstellung, die exklusive Samplings dieser Funktion waren.|  
  
## <a name="see-also"></a>Siehe auch  
 [Aufrufer-/Aufgerufener-Ansicht – .NET-Speichersamplingdaten](../profiling/caller-callee-view-dotnet-memory-sampling-data.md)   
 [Aufrufer-/Aufgerufener-Ansicht – .NET-Speicherinstrumentierungsdaten](../profiling/caller-callee-view-net-memory-instrumentation-data.md)   
 [Aufrufer-/Aufgerufener-Ansicht – Instrumentierungsdaten](../profiling/caller-callee-view-instrumentation-data.md)