---
title: Verwenden von Profilerstellungsmethoden zum Sammeln von Leistungsdaten über die Befehlszeile | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
ms.assetid: 5613fafc-f298-4e7a-9a2d-a853b61cdf9c
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 6a9c87de9f5815496d29bfa212fbc5ee204b2c10
ms.sourcegitcommit: 046a9adc5fa6d6d05157204f5fd1a291d89760b7
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2018
---
# <a name="using-profiling-methods-to-collect-performance-data-from-the-command-line"></a>Verwenden von Profilerstellungsmethoden zum Sammeln von Leistungsdaten über die Befehlszeile
Die zur Verfügung stehenden Befehlszeilentools und Optionen der [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]-Profilerstellungstools hängen von verschiedenen Faktoren ab, beispielsweise von der Art der Anwendung, für die ein Profil erstellt werden soll, von der Profilerstellungsmethode, die Sie verwenden möchten, sowie davon, ob die Zielanwendung in nativem Code oder in [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)]-Code geschrieben ist.  
  
 In diesem Thema sind die Themen über Verfahren mittels Befehlszeile gemäß der ausgewählten Profilerstellungsmethode aufgeführt.  
  
## <a name="in-this-topic"></a>In diesem Thema  
 [Sammeln von Leistungsstatistiken mit der Samplingmethode](#BKMK_Using_the_sampling_method_to_collect_performance_statistics)  
  
 [Sammeln von ausführlichen Zeitsteuerungsdaten mit der Instrumentierungsmethode](#BKMK_Using_the_instrumentation_method_to_collect_detailed_timing_data)  
  
 [Verwenden von .NET-Arbeitsspeichermethoden zur Sammlung von Daten zur Speicherbelegung und Objektlebensdauer](#BKMK_Using__NET_memory_methods_to_collect_memory_allocation_and_object_lifetime_data)  
  
 [Erfassen von Daten zu Ressourcenkonflikten und Threadaktivitäten mit der Nebenläufigkeitsmethode](#BKMK_Using_the_concurrency_method_to_collect_resource_contention_and_thread_activity_data)  
  
 [Hinzufügen von Ebeneninteraktionsdaten zu einer Profilerstellung](#BKMK_Adding_tier_interaction_data_to_a_profiling_run)  
  
##  <a name="BKMK_Using_the_sampling_method_to_collect_performance_statistics"></a> Sammeln von Leistungsstatistiken mit der Samplingmethode  
 Mit der Samplingmethode der Profilerstellungstools werden während einer Profilerstellung Leistungsdaten in angegebenen Intervallen gesammelt. Samplingdaten ermöglichen Einblicke in Leistungsprobleme im Zusammenhang mit der CPU, und sie ermöglichen eine Basis für die Untersuchung der Leistung einer Anwendung.  
  
 Sie können gleichzeitig den Profiler und die Anwendung starten oder den Profiler an eine Instanz einer Anwendung anfügen, die gerade ausgeführt wird.  
  
|Aufgabe|Art der Zielanwendung|  
|----------|-----------------------------|  
|**Starten einer Anwendung**|-   [Eigenständige Anwendungen](../profiling/how-to-launch-a-stand-alone-application-with-the-profiler-and-collect-application-statistics-by-using-the-command-line.md)|  
|**Anfügen an einen laufenden Prozess**|-   [Eigenständige .NET Framework-Anwendungen](../profiling/how-to-attach-the-profiler-to-a-dotnet-app-and-collect-application-statistics.md)<br />-   [Native, eigenständige Anwendungen](../profiling/how-to-attach-the-profiler-to-a-native-stand-alone-application-and-collect-application-statistics-by-using-the-command-line.md)<br />-   [ASP.NET-Webanwendungen](../profiling/how-to-attach-the-profiler-to-an-aspnet-web-application-to-collect-application-statistics-by-using-the-command-line.md)<br />-   [.NET-Dienste](../profiling/how-to-attach-the-profiler-to-a-dotnet-service-to-collect-application-statistics-by-using-the-command-line.md)<br />-   [Native Dienste](../profiling/how-to-attach-the-profiler-to-a-native-service-to-collect-application-statistics-by-using-the-command-line.md)|  
  
##  <a name="BKMK_Using_the_instrumentation_method_to_collect_detailed_timing_data"></a> Sammeln von ausführlichen Zeitsteuerungsdaten mit der Instrumentierungsmethode  
 Mit der Instrumentierungsmethode der Profilerstellungstools werden Leistungsdaten aus Kopien von Anwendungsbinärdateien gesammelt, die Softwaretests zum Erfassen von Leistungsinformationen enthalten. Instrumentierungsdaten werden am Anfang und Ende jeder instrumentierten Funktion und jedes Aufrufs von anderen Funktionen durch die instrumentierte Funktion gesammelt. Die Instrumentierungsmethode ist nützlich für das Ermitteln von Leistungsbeeinträchtigungen aufgrund von E/A-Problemen, z.B. bei der Datenträgerverwendung.  
  
 Die instrumentierte Binärdatei wird mit dem Tool [VInstr.exe](../profiling/vsinstr.md) erstellt. Nachdem Sie den Profiler initialisiert haben, werden die Daten automatisch von den instrumentierten Binärdateien gesammelt, wenn Sie die Zielanwendung ausführen.  
  
 **Art der Zielanwendung**  
  
-   [Eigenständige .NET Framework-Komponenten](../profiling/how-to-instrument-a-stand-alone-dotnet-framework-component-and-collect-timing-data-with-the-profiler-from-the-command-line.md)  
  
-   [Native, eigenständige Komponenten](../profiling/how-to-instrument-a-native-stand-alone-component-and-collect-timing-data-with-the-profiler-from-the-command-line.md)  
  
-   [Statisch kompilierte ASP.NET-Webanwendungen](../profiling/how-to-instrument-statically-compiled-aspnet-and-collect-detailed-timing-data.md)  
  
-   [Dynamisch kompilierte ASP.NET-Webanwendungen](../profiling/how-to-instrument-a-dynamically-compiled-aspnet-app-and-collect-timing-data.md)  
  
-   [.NET-Dienste](../profiling/how-to-instrument-a-dotnet-service-and-collect-detailed-timing-data-by-using-the-profiler-command-line.md)  
  
-   [Native Dienste](../profiling/how-to-instrument-a-native-service-and-collect-detailed-timing-data-by-using-the-profiler-command-line.md)  
  
##  <a name="BKMK_Using__NET_memory_methods_to_collect_memory_allocation_and_object_lifetime_data"></a> Verwenden von .NET-Arbeitsspeichermethoden zur Sammlung von Daten zur Speicherbelegung und Objektlebensdauer  
 Die .NET Arbeitsspeichermethode der Profilerstellungstools ermöglicht das Sammeln von Speicherbelegungsdaten für [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)] sowie von Informationen zur Lebensdauer von Objekten in [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)].  
  
 Sie können die Zielanwendung mit dem Profiler starten, den Profiler an eine aktive Instanz einer Anwendung anfügen und instrumentierte Versionen der Anwendung erstellen, um ausführliche Zeitsteuerungsinformationen sowie [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)]-Speicherdaten zu sammeln.  
  
|Aufgabe|Art der Zielanwendung|  
|----------|-----------------------------|  
|**Starten einer Anwendung**|-   [Eigenständige .NET Framework-Anwendungen](../profiling/how-to-launch-a-stand-alone-dotnet-framework-application-with-the-profiler-to-collect-memory-data-by-using-the-command-line.md)|  
|**Anfügen an einen laufenden Prozess**|-   [Eigenständige .NET Framework-Anwendungen](../profiling/how-to-attach-the-profiler-to-a-dotnet-framework-stand-alone-application-to-collect-memory-data-by-using-the-command-line.md)<br />-   [ASP.NET-Webanwendungen](../profiling/how-to-attach-the-profiler-to-an-aspnet-web-application-to-collect-memory-data-by-using-the-command-line.md)<br />-   [.NET-Dienste](../profiling/how-to-attach-the-profiler-to-a-dotnet-service-to-collect-memory-data-by-using-the-command-line.md)|  
|**Instrumentieren von Modulen**|-   [Eigenständige .NET Framework-Komponenten](../profiling/how-to-instrument-a-dotnet-framework-component-and-collect-memory-data.md)<br />-   [Statisch kompilierte ASP.NET-Webanwendungen](../profiling/how-to-instrument-a-statically-compiled-aspnet-web-application-and-collect-memory-data-by-using-the-profiler-command-line.md)<br />-   [Dynamisch kompilierte ASP.NET-Webanwendungen](../profiling/how-to-instrument-a-dynamically-compiled-aspnet-web-application-and-collect-memory-data.md)<br />-   [.NET-Dienste](../profiling/how-to-instrument-a-dotnet-framework-service-and-collect-memory-data-by-using-the-profiler-command-line.md)|  
  
##  <a name="BKMK_Using_the_concurrency_method_to_collect_resource_contention_and_thread_activity_data"></a> Erfassen von Daten zu Ressourcenkonflikten und Threadaktivitäten mit der Nebenläufigkeitsmethode  
 Mit der Nebenläufigkeitsmethode der Profilerstellungstools können Sie Daten zu Ressourcenkonflikten sowie zu Thread- und Prozessaktivitäten aus Anwendungen mit mehreren Threads sammeln.  
  
 Sie können die Anwendung mit dem Profiler starten oder den Profiler an eine Instanz einer Anwendung anfügen, die gerade ausgeführt wird.  
  
|Aufgabe|Art der Zielanwendung|  
|----------|-----------------------------|  
|**Starten einer Anwendung**|-   [Eigenständige .NET Framework-Anwendung](../profiling/how-to-launch-a-stand-alone-dotnet-framework-app-to-collect-concurrency-data.md)<br />-   [Native eigenständige Anwendung](../profiling/how-to-launch-a-stand-alone-native-application-with-the-profiler-to-collect-concurrency-data-by-using-the-command-line.md)|  
|**Anfügen an einen laufenden Prozess**|-   [Eigenständige .NET Framework-Anwendung](../profiling/how-to-attach-the-profiler-to-a-dotnet-app-and-collect-concurrency-data.md)<br />-   [Native, eigenständige Anwendung](../profiling/how-to-attach-the-profiler-to-a-native-stand-alone-application-and-collect-concurrency-data-by-using-the-command-line.md)<br />-   [ASP.NET-Webanwendung](../profiling/how-to-attach-the-profiler-to-an-aspnet-web-application-to-collect-concurrency-data-by-using-the-command-line.md)<br />-   [.NET-Dienst](../profiling/how-to-attach-the-profiler-to-a-dotnet-service-to-collect-concurrency-data-by-using-the-command-line.md)<br />-   [Nativer Dienst](../profiling/how-to-attach-the-profiler-to-a-native-service-to-collect-concurrency-data-by-using-the-command-line.md)|  
  
##  <a name="BKMK_Adding_tier_interaction_data_to_a_profiling_run"></a> Hinzufügen von Ebeneninteraktionsdaten zu einer Profilerstellung  
 Das Hinzufügen von Ebeneninteraktionsdaten zu einer Profilerstellung erfordert bestimmte Verfahren der Befehlszeilenprofilerstellungstools. Informationen hierzu finden Sie unter [Collecting tier interaction data (Hinzufügen von Ebeneninteraktionsdaten über die Befehlszeile)](../profiling/adding-tier-interaction-data-from-the-command-line.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Profiling Stand-Alone Applications (Profilerstellung für eigenständige Anwendungen)](../profiling/command-line-profiling-of-stand-alone-applications.md)   
 [Profilerstellung für ASP.NET-Webanwendungen](../profiling/command-line-profiling-of-aspnet-web-applications.md)   
 [Erstellen von Dienstprofilen](../profiling/command-line-profiling-of-services.md)