---
title: 'Gewusst wie: Starten einer eigenständigen .NET Framework-Anwendung mit dem Profiler zum Sammeln paralleler Daten über die Befehlszeile | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
ms.assetid: 17a48848-bd3e-44ef-9971-e39836ff1df2
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- dotnet
ms.openlocfilehash: 5cece8a5b97f3a9c78bdda8c5e841661d2b4d58d
ms.sourcegitcommit: 37144589d9f850ff81ec7bfb884429989925a43d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/19/2018
ms.locfileid: "34335579"
---
# <a name="how-to-launch-a-stand-alone-net-framework-application-with-the-profiler-to-collect-concurrency-data-by-using-the-command-line"></a>Vorgehensweise: Starten einer eigenständigen .NET Framework-Anwendung mit dem Profiler zum Sammeln paralleler Daten über die Befehlszeile
In diesem Thema wird beschrieben, wie mit den Befehlszeilentools der [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]-Profilerstellungstools eigenständige .NET Framework-(Client-)Anwendungen gestartet und Parallelitätsdaten zu Prozessen und Threads erfasst werden.  
  
> [!NOTE]
>  Die Befehlszeilentools der Profilerstellungstools befinden sich im Unterverzeichnis "\Team Tools\Performance Tools" des [!INCLUDE[vs_current_short](../code-quality/includes/vs_current_short_md.md)]-Installationsverzeichnisses. Auf 64-Bit-Computern sind 64-Bit- und 32-Bit-Versionen der Tools verfügbar. Damit Sie die Profilerbefehlszeilentools verwenden können, müssen Sie den Pfad des Tools der PATH-Umgebungsvariable des Eingabeaufforderungsfensters oder dem Befehl selbst hinzufügen. Weitere Informationen finden Sie unter [Angeben des Pfads für Befehlszeilentools](../profiling/specifying-the-path-to-profiling-tools-command-line-tools.md).  
  
 Während der Profiler an die Anwendung angefügt ist, können Sie die Datensammlung anhalten und fortsetzen. Um eine Profilerstellungssitzung zu beenden, darf der Profiler nicht mehr an die Anwendung angefügt sein und muss explizit beendet werden.  
  
## <a name="start-the-application-with-the-profiler"></a>Starten der Anwendung mit dem Profiler  
 Um eine .NET Framework-Zielanwendung mit dem Profiler zu starten, legen Sie die .NET Framework-Profilerstellungsvariablen mithilfe von VSPerfClrEnv.exe fest. Verwenden Sie anschließend die VSPerfCmd-Optionen **/start** und **/launch**, um den Profiler zu initialisieren und die Anwendung zu starten. Sie können **/start** und **/launch** sowie die zugehörigen Optionen in einer einzigen Befehlszeile angeben. Außerdem können Sie der Befehlszeile die Option **/globaloff** hinzufügen, um die Datensammlung anzuhalten, wenn die Zielanwendung gestartet wird. Verwenden Sie dann den Befehl **/globalon** in einer separaten Befehlszeile, um die Datensammlung zu starten.  
  
#### <a name="to-start-an-application-with-the-profiler"></a>Starten einer Anwendung mit dem Profiler  
  
1.  Öffnen Sie ein Eingabeaufforderungsfenster.  
  
2.  Starten Sie den Profiler. Typ:  
  
     [VSPerfCmd](../profiling/vsperfcmd.md) **/start:concurrency**[**,**{**ResourceOnly**&#124;**ThreadOnly**}] **/output:**`OutputFile` [`Options`]  
  
    -   Mit der Option [/start](../profiling/start.md) wird der Profiler initialisiert.  
  
        |||  
        |-|-|  
        |**/start:concurrency**|Aktiviert das Sammeln von Ressourcenkonflikt- und Threadausführungsdaten.|  
        |**/start:concurrency,resourceonly**|Aktiviert nur das Sammeln von Ressourcenkonfliktdaten.|  
        |**/start:concurrency,threadonly**|Aktiviert nur das Sammeln von Threadausführungsdaten.|  
  
    -   Die Option [/output](../profiling/output.md)**:**`OutputFile` ist zusammen mit **/start** erforderlich. Mit dem `OutputFile`-Objekt werden Name und Speicherort der Profilerstellungs-Datendatei (VSP-Datei) angegeben.  
  
     Sie können jede der folgenden Optionen zusammen mit der Option **/start:concurrency** verwenden.  
  
    |Option|description|  
    |------------|-----------------|  
    |[/user](../profiling/user-vsperfcmd.md) **:**[`domain\`]`username`|Gibt den optionalen Domänen- und Benutzernamen des Kontos an, dem Zugriff auf den Profiler gewährt werden soll.|  
    |[/crosssession](../profiling/crosssession.md)|Aktiviert die Profilerstellung für Prozesse in anderen Anmeldesitzungen.|  
    |[/wincounter](../profiling/wincounter.md) **:** `WinCounterPath`|Gibt einen Windows-Leistungsindikator an, dessen Daten während der Profilerstellung gesammelt werden sollen.|  
    |[/automark](../profiling/automark.md) **:** `Interval`|Verwenden Sie nur **/wincounter**. Gibt die Anzahl von Millisekunden zwischen Ereignissen bei der Datensammlung mit Windows-Leistungsindikatoren an. Der Standardwert ist 500 ms.|  
    |[/events](../profiling/events-vsperfcmd.md) **:** `Config`|Gibt ein ETW-Ereignis (Ereignisablaufverfolgung für Windows) an, dessen Daten während der Profilerstellung gesammelt werden sollen. ETW-Ereignisse werden in einer separaten Datei (.etl) gesammelt.|  
  
3.  Starten Sie die Zielanwendung. Typ:  
  
     **VSPerfCmd**  [/launch](../profiling/launch.md) **:** `AppName` [`Options`] [`Sample Event`]  
  
     Sie können jede der folgenden Optionen zusammen mit der Option **/launch** verwenden.  
  
    |Option|description|  
    |------------|-----------------|  
    |[/args](../profiling/args.md) **:** `Arguments`|Gibt eine Zeichenfolge mit den Befehlszeilenargumenten an, die an die Zielanwendung übergeben werden sollen.|  
    |[/console](../profiling/console.md)|Startet die Ziel-Befehlszeilenanwendung in einem separaten Fenster.|  
    |[/targetclr](../profiling/targetclr.md) **:** `Version`|Gibt die Version der CLR (Common Language Runtime) für die Profilerstellung an, wenn mehr als eine Laufzeitversion in eine Anwendung geladen wird.|  
  
## <a name="control-data-collection"></a>Steuerung der Datensammlung  
 Während die Zielanwendung ausgeführt wird, können Sie die Datensammlung steuern, indem Sie das Schreiben von Daten in die Datei mit VSPerfCmd.exe-Optionen starten und beenden. Durch die Steuerung der Datensammlung können Sie Daten zu einem bestimmten Teil der Programmausführung sammeln, z. B. zum Starten oder Schließen der Anwendung.  
  
#### <a name="to-start-and-stop-data-collection"></a>So starten und beenden Sie die Datensammlung  
  
1.  Mit den folgenden VSPerfCmd.exe-Optionspaaren wird die Datensammlung gestartet und beendet. Geben Sie jede Option in einer eigenen Befehlszeile an. Sie können die Datensammlung mehrmals aktivieren und deaktivieren.  
  
    |Option|description|  
    |------------|-----------------|  
    |[/globalon /globaloff](../profiling/globalon-and-globaloff.md)|Die Datensammlung wird für alle Prozesse gestartet (**/globalon**) oder beendet (**/globaloff**).|  
    |[/processon](../profiling/processon-and-processoff.md) **:** `PID` [/processoff](../profiling/processon-and-processoff.md) **:** `PID`|Die Datensammlung wird für den mit der Prozess-ID (`PID`) angegebenen Prozess gestartet (**/processon**) oder beendet (**/processoff**).|  
    |[/attach](../profiling/attach.md) **:**{`PID`&#124;`ProcName`} [/detach](../profiling/detach.md)[**:**{`PID`&#124;`ProcName`}]|Mit **/attach** wird die Datensammlung für den Prozess gestartet, der anhand der Prozess-ID (`PID`) oder des Prozessnamens („ProcName“) angegeben ist. Mit **/detach** wird die Datensammlung für den angegebenen Prozess (oder für alle Prozesse, wenn kein bestimmter Prozess angegeben ist) beendet.|  
  
## <a name="end-the-profiling-session"></a>Beenden der Profilerstellungssitzung  
 Um eine Profilerstellungssitzung beenden zu können, darf der Profiler keine Daten erfassen. Sie können die Erfassung von Parallelitätsdaten beenden, indem Sie die profilierte Anwendung schließen oder indem Sie die Option **VSPerfCmd /detach** aufrufen. Rufen Sie anschließend die Option **VSPerfCmd /shutdown** auf, um den Profiler zu deaktivieren und die Profilerstellungs-Datendatei zu schließen. Mit dem Befehl **VSPerfClrEnv /off** werden die Umgebungsvariablen für die Profilerstellung gelöscht.  
  
#### <a name="to-end-a-profiling-session"></a>So beenden Sie eine Profilerstellungssitzung  
  
1.  Führen Sie einen der folgenden Schritte aus, um den Profiler von der Zielanwendung zu trennen:  
  
    -   Schließen Sie die Zielanwendung.  
  
         - oder -   
  
    -   Geben Sie **VSPerfCmd /detach** ein.  
  
2.  Schließen Sie den Profiler.  
  
     **VSPerfCmd**  [/shutdown](../profiling/shutdown.md)  
  
## <a name="see-also"></a>Siehe auch  
 [Sammeln von Parallelitätsdaten](../profiling/collecting-concurrency-data-for-stand-alone-applications.md)