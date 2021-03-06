---
title: Verwalten von Auslastungstestergebnissen in Visual Studio
ms.date: 10/19/2016
ms.topic: conceptual
helpviewer_keywords:
- load tests, results repository
- results, load test
- load test results, repository
- Load Test Results Repository
ms.assetid: 1cd63c4b-4f74-4133-b675-5e8fbeab25f3
author: gewarren
ms.author: gewarren
manager: douge
ms.prod: visual-studio-dev15
ms.technology: vs-ide-test
ms.openlocfilehash: e1eb6a5218f9d9ea7c853733690922846443ed4c
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/26/2018
---
# <a name="manage-load-test-results-in-the-load-test-results-repository"></a>Verwalten von Auslastungstestergebnissen im Ergebnisrepository für Auslastungstests

Informationen, die während eines Auslastungstests erfasst wurden, können im *Ergebnisrepository für Auslastungstests*, einer SQL-Datenbank, gespeichert werden. Das Ergebnisrepository für Auslastungstests enthält Leistungsindikatordaten und Informationen zu aufgezeichneten Fehlern. Die Ergebnisrepository-Datenbank wird für Controller vom Setup erstellt, oder sie wird bei der ersten lokalen Ausführung eines Auslastungstests automatisch erstellt. Wenn das Auslastungstestschema nicht vorhanden ist, wird die Datenbank bei lokaler Ausführung automatisch erstellt.

 Wenn Sie die Ergebnisrepository-Verbindungszeichenfolge des Controllers ändern, um einen anderen Server zu verwenden, muss auf dem neuen Server das loadtestresultsrepository.sql-Skript ausgeführt werden, um das Schema zu erstellen.

 Visual Studio Enterprise stellt Indikatorensätze mit Namen zur Verfügung, die häufige Leistungsindikatoren erfassen, deren Grundlage eine bestimmte Technologie ist. Diese Sätze sind bei der Analyse von IIS-Servern, ASP.NET-Servern oder SQL-Servern hilfreich. Alle mit Indikatorensätzen erfassten Daten werden im Ergebnisrepository für Auslastungstests gespeichert.

> [!IMPORTANT]
> Es wird zwischen einem Indikatorensatz und den Leistungsindikatordaten unterschieden. Indikatorensätze sind Metadaten. Sie definieren eine Gruppe von Leistungsindikatoren, die von einem Computer erfasst werden, der eine bestimmte Aufgabe erfüllt, beispielsweise ein IIS- oder SQL-Server. Der Indikatorensatz ist ein Teil der Auslastungstestdefinition. Leistungsindikatordaten werden basierend auf den Indikatorensätzen, der Zuordnung der Indikatorensätze zu einem bestimmten Computer und der Samplingrate erfasst.

## <a name="sql-server-versions"></a>SQL Server-Versionen

 Für das Verwenden von Auslastungstests können Sie SQL Server Express LocalDB verwenden. Die Installation erfolgt zusammen mit Visual Studio. Dabei handelt es sich um einen Standarddatenbankserver für Auslastungstests (einschließlich der Integration in Microsoft Excel). SQL Server Express LocalDB ist ein Ausführungsmodus von SQL Server Express, der speziell für Programmentwickler vorgesehen ist. Bei der Installation von SQL Server Express LocalDB wird eine Mindestzahl an Dateien kopiert, die für den Start des SQL Server-Datenbankmoduls erforderlich sind.

 Wenn das Team hohe Datenbankanforderungen erwartet oder die Projekte zu groß für SQL Server Express LocalDB werden, sollten Sie ein Upgrade auf SQL Express oder auf die Vollversion von SQL Server in Erwägung ziehen, um Raum für weitere Skalierungen bereitzustellen. Wenn Sie SQL Server aktualisieren, werden die MDF- und LDF-Dateien für SQL Server Express LocalDB im Benutzerprofilordner gespeichert. Mit diesen Dateien können Sie die Auslastungstestdatenbank in SQL Server Express oder SQL Server importieren.

## <a name="load-test-results-store-considerations"></a>Überlegungen zum Auslastungstest-Ergebnisspeicher

 Wenn Visual Studio Enterprise installiert ist, wird der Auslastungstest-Ergebnisspeicher zur Verwendung einer Instanz der SQL Express-Anwendung eingerichtet, die auf dem Computer installiert ist. SQL Express ist auf die Nutzung von maximal 4 GB Speicherplatz beschränkt. Wenn Sie über einen langen Zeitraum viele Auslastungstests ausführen, sollten Sie erwägen, den Auslastungstest-Ergebnisspeicher ggf. zur Verwendung einer Instanz des vollständigen SQL Server-Produkts zu konfigurieren.

## <a name="load-test-analyzer-tasks"></a>Aufgaben des Auslastungstest-Analyzers

|Aufgaben|Verwandte Themen|
|-----------|-----------------------|
|**Einrichten eines Repositorys für Auslastungstestergebnisse:** Sie können ein Repository für Auslastungstestergebnisse in einer SQL-Datenbank einrichten. **Hinweis:** Ein Auslastungstestrepository kann auch erstellt werden, wenn Sie einen Testcontroller installieren. Weitere Informationen finden Sie unter [Installieren und Konfigurieren von Test-Agents](../test/lab-management/install-configure-test-agents.md).||
|**Auswählen und Anzeigen eines Ergebnisrepositorys:** Sie können ein bestimmtes Ergebnisrepository auswählen. Sie sind nicht auf einen lokalen Ergebnisspeicher beschränkt. Häufig werden Auslastungstests auf einem Remotesatz von Agent-Computern ausgeführt. Testergebnisse von den Agents oder den lokalen Computern können auf einem beliebigen SQL-Server gespeichert werden, auf dem Sie einen Auslastungstest-Ergebnisspeicher erstellt haben. In jedem Fall müssen Sie mithilfe des Fensters **Testcontroller verwalten** angeben, wo die Ergebnisse des Auslastungstests gespeichert werden sollen.|-   [How to: Select a Load Test Results Repository (Vorgehensweise: Auswählen eines Ergebnisrepositorys für Auslastungstests)](../test/how-to-select-a-load-test-results-repository.md)<br />-   [How to: Access Load Test Results for Analysis (Vorgehensweise: Zugreifen auf Auslastungstestergebnisse für die Analyse)](../test/how-to-access-load-test-results-for-analysis.md)|
|**Löschen eines Auslastungstestergebnisses aus dem Repository:** Sie können ein Auslastungstestergebnis aus dem **Auslastungstest-Editor** mithilfe des Dialogfelds **Auslastungstestergebnisse öffnen und verwalten** entfernen.|-   [How to: Delete Load Test Results from a Repository (Vorgehensweise: Löschen von Auslastungstestergebnissen aus einem Repository)](../test/how-to-delete-load-test-results-from-a-repository.md)|
|**Importieren und Exportieren von Ergebnissen in ein Repository:** Sie können Auslastungstestergebnisse aus dem **Auslastungstest-Editor** entfernen.|-   [How to: Import Load Test Results into a Repository (Vorgehensweise: Importieren von Auslastungstestergebnissen in ein Repository)](../test/how-to-import-load-test-results-into-a-repository.md)<br />-   [How to: Export Load Test Results from a Repository (Vorgehensweise: Exportieren von Auslastungstestergebnissen aus einem Repository)](../test/how-to-export-load-test-results-from-a-repository.md)|

## <a name="related-tasks"></a>Verwandte Aufgaben

 [Analyze Load Test Results (Analysieren von Auslastungstestergebnissen)](../test/analyze-load-test-results-using-the-load-test-analyzer.md)

 Sie können mit dem Auslastungstest-Analyzer die Ergebnisse sowohl eines derzeit ausgeführten Auslastungstests als auch eines abgeschlossenen Auslastungstests anzeigen.

## <a name="see-also"></a>Siehe auch

- [Analyze Load Test Results (Analysieren von Auslastungstestergebnissen)](../test/analyze-load-test-results-using-the-load-test-analyzer.md)
- [Gewusst wie: Zugreifen auf Auslastungstestergebnisse für die Analyse](../test/how-to-access-load-test-results-for-analysis.md)