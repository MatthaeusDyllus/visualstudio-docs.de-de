---
title: Übersicht der Auslastungstestergebnisse in Visual Studio
ms.date: 10/19/2016
ms.topic: conceptual
f1_keywords:
- vs.test.load.monitor.summary.view
helpviewer_keywords:
- load test results, summary
- load tests, summary in analyzer
- load tests, results summary
- Load Test Viewer, summary
- load tests, summary in Load Test Viewer
ms.assetid: 326b6c3c-5378-452b-8ca3-ba5a06ab3d41
author: gewarren
ms.author: gewarren
manager: douge
ms.prod: visual-studio-dev15
ms.technology: vs-ide-test
ms.openlocfilehash: 41849b5ac9b55ff97735dbbda4df909d54f8a346
ms.sourcegitcommit: 58052c29fc61c9a1ca55a64a63a7fdcde34668a4
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2018
ms.locfileid: "34751857"
---
# <a name="load-test-results-summary-overview"></a>Load Test Results Summary Overview

Nachdem Sie einen Auslastungstest ausgeführt haben, können Sie die Zusammenfassung des Auslastungstests anzeigen, um einen schnellen Überblick über die Ergebnisse zu erhalten. In der Zusammenfassung des Auslastungstests werden die wichtigsten Ergebnisse in einem kompakten und leicht lesbaren Format dargestellt. Sie können die Zusammenfassung des Auslastungstests auch ausdrucken. Dies ist hilfreich, wenn Sie Ergebnisse an Projektbeteiligte weitergeben möchten. Die Zusammenfassung des Auslastungstests ist auch die Standardansicht, wenn Sie das Auslastungstestergebnis eines zuvor ausgeführten Auslastungstest öffnen. Weitere Informationen finden Sie unter [How to: Access Load Test Results for Analysis (Vorgehensweise: Zugreifen auf Auslastungstestergebnisse für die Analyse)](../test/how-to-access-load-test-results-for-analysis.md).

 ![Zusammenfassungsansicht](../test/media/ltest_summaryview.png)

## <a name="the-load-test-summary"></a>Zusammenfassung des Auslastungstests

Die Zusammenfassung des Auslastungstests ist in Abschnitte unterteilt. Die ersten Abschnitte oben in der Zusammenfassung sind immer sichtbar. Wenn Sie die Zusammenfassung des Auslastungstests anzeigen, werden die folgenden Elemente zuerst angezeigt:

- Testlaufinformationen

- Gesamtergebnisse

- Schlüsselstatistik: 5 langsamste Seiten

- Schlüsselstatistik: 5 langsamste Tests

- Schlüsselstatistik: 5 langsamste SQL-Vorgänge

    > [!NOTE]
    > Der Abschnitt über SQL-Vorgänge wird nur angezeigt, wenn die SQL-Ablaufverfolgung im Auslastungstest aktiviert wurde.

Die abschließenden Abschnitte werden am Ende der Zusammenfassung angezeigt und können reduziert werden, um Platz zu sparen. Die folgenden Elemente werden am Ende der Zusammenfassung des Auslastungstests angezeigt:

- Testergebnisse

- Seitenergebnisse

- Transaktionsergebnisse

- Ressourcen des getesteten Systems

- Ressourcen für Controller und Agents

- Fehler

## <a name="test-run-information"></a>Testlaufinformationen

Der Abschnitt mit Testlaufinformationen enthält allgemeine Informationen zur Ausführung, einschließlich Testnamen, Start- und Endzeit des Tests sowie ausführender Controller. Dieser Abschnitt enthält außerdem die optionale Beschreibung des Laufs, die beim Ausführen des Auslastungstests hinzugefügt wird.

## <a name="overall-results"></a>Gesamtergebnisse

Der Abschnitt über Gesamtergebnisse enthält Zusammenfassungsergebnisse des Tests, einschließlich der Anzahl der Anforderungen pro Sekunde, der Gesamtanzahl der fehlgeschlagenen Anforderungen, der durchschnittlichen Antwortzeit sowie der durchschnittlichen Seitenzeit.

## <a name="key-statistic-top-5-slowest-pages"></a>Schlüsselstatistik: 5 langsamste Seiten

Der Abschnitt zu den langsamsten Seiten enthält die fünf langsamsten Seiten im Auslastungstest. Die URL und die durchschnittliche Seitenladezeit werden pro Seite angezeigt. Die Seiten werden in absteigender Reihenfolge aufgelistet. Sie können die URL einer Seite auswählen, um die Tabelle **Seiten** zu öffnen und weitere Details dieser Seite zu überprüfen. Weitere Informationen finden Sie unter [How to: View Web Page Response (Vorgehensweise: Anzeigen der Antwortzeit einer Webseite)](../test/how-to-view-web-page-response-time-in-a-load-test.md).

Der Prozentwert für **95% Seitenzeit (Sek.)** gibt an, das 95% der Seiten schneller als in dieser Zeit in Sekunden fertiggestellt wurden.

## <a name="key-statistic-top-5-slowest-tests"></a>Schlüsselstatistik: 5 langsamste Tests

Der Abschnitt zu den langsamsten Tests enthält die fünf langsamsten Tests im Auslastungstest. Testname und durchschnittliche Testzeit werden pro Test angezeigt. Die Tests werden in absteigender Reihenfolge aufgelistet. Sie können den Namen eines Tests auswählen, um die Tabelle **Tests** zu öffnen und weitere Details dieses Tests zu überprüfen. Weitere Informationen finden Sie unter [Analyze Load Test Results and Errors in the Tables View (Analysieren von Auslastungstestergebnissen und -fehlern in der Tabellenansicht)](../test/analyze-load-test-results-and-errors-in-the-tables-view.md).

Der Prozentwert für **95% Testzeit (Sek.)** gibt an, das 95% der Tests schneller als in dieser Zeit in Sekunden abgeschlossen wurden.

## <a name="key-statistic-top-5-slowest-sql-operations"></a>Schlüsselstatistik: 5 langsamste SQL-Vorgänge

Wenn die SQL-Ablaufverfolgung im Auslastungstest aktiviert ist, enthält der Abschnitt zu den langsamsten Abfragen die fünf langsamsten Abfragen im Auslastungstest. Der Name des Vorgangs und die Dauer werden pro Test angezeigt. Die Dauer wird in Mikrosekunden (SQL Server 2005) oder in Millisekunden (SQL Server 2000 und früher) angezeigt. Die Tests werden in absteigender Reihenfolge nach Dauer aufgelistet. Sie können den Namen eines Vorgangs auswählen, um die Tabelle **SQL-Ablaufverfolgung** zu öffnen und weitere Details dieses Vorgangs zu überprüfen. Weitere Informationen finden Sie unter [The SQL Trace Data Table (Die Tabelle der SQL-Ablaufverfolgungsdaten)](../test/analyze-load-test-results-and-errors-in-the-tables-view.md#the-sql-trace-data-table).

## <a name="test-results"></a>Testergebnisse

Der Abschnitt über Testergebnisse enthält eine Liste aller im Auslastungstests enthaltenen Tests und Szenarios. Es werden Testname, Szenario, Anzahl der Testausführungen, Anzahl der fehlgeschlagenen Ausführungen und die durchschnittliche Testlaufzeit angezeigt. Sie können den Namen eines Tests auswählen, um die Tabelle **Tests** zu öffnen und weitere Details dieses Tests zu überprüfen. Weitere Informationen finden Sie unter [Analyze Load Test Results and Errors in the Tables View (Analysieren von Auslastungstestergebnissen und -fehlern in der Tabellenansicht)](../test/analyze-load-test-results-and-errors-in-the-tables-view.md).

> [!NOTE]
> Sie können diesen Abschnitt reduzieren oder erweitern, indem Sie den Pfeil links neben dem Abschnittstitel auswählen.

## <a name="page-results"></a>Seitenergebnisse

Der Abschnitt über Seitenergebnisse enthält eine Liste aller im Auslastungstest enthaltenen Webseiten. URL, Szenario, Testname, durchschnittliche Seitenzeit und Anzahl werden angezeigt. Sie können die URL einer Seite auswählen, um die Tabelle **Seiten** zu öffnen und weitere Details dieser Seite zu überprüfen. Weitere Informationen finden Sie unter [How to: View Web Page Response (Vorgehensweise: Anzeigen der Antwortzeit einer Webseite)](../test/how-to-view-web-page-response-time-in-a-load-test.md).

> [!NOTE]
> Sie können diesen Abschnitt reduzieren oder erweitern, indem Sie den Pfeil links neben dem Abschnittstitel auswählen.

## <a name="transaction-results"></a>Transaktionsergebnisse

Der Abschnitt über Transaktionsergebnisse enthält einer Liste aller im Auslastungstest enthaltenen Transaktionen. Transaktionsname, Szenario, Test, Antwortzeit, verstrichene Zeit und Anzahl werden angezeigt. Sie können den Namen einer Transaktion auswählen, um die Tabelle **Transaktionen** zu öffnen und weitere Details dieser Transaktion zu überprüfen. Weitere Informationen finden Sie unter [Analyze Load Test Results and Errors in the Tables View (Analysieren von Auslastungstestergebnissen und -fehlern in der Tabellenansicht)](../test/analyze-load-test-results-and-errors-in-the-tables-view.md).

> [!NOTE]
> Sie können diesen Abschnitt reduzieren oder erweitern, indem Sie den Pfeil links neben dem Abschnittstitel auswählen.

Die Prozentwerte geben die folgenden Transaktionsinformationen an:

-   90 % der gesamten Transaktionen wurden in weniger als \<Zeit> Sekunden abgeschlossen.

-   95 % der gesamten Transaktionen wurden in weniger als \<Zeit> Sekunden abgeschlossen.

## <a name="system-under-test-resources"></a>Ressourcen des getesteten Systems

Der Abschnitt über Ressourcen des getesteten Systems enthält eine Liste der Computer, die zusammen die Zielcomputer ergeben, für die Auslastungsdaten erfasst werden. Dazu gehören mit Ausnahme von Agent oder Controller alle Computer, für die Indikatorensätze erfasst werden. Computername, Prozessorzeit (%) und verfügbarer Speicher werden angezeigt. Sie können einen Computernamen auswählen, um das Diagramm **Getestetes System** zu öffnen und die Ressourcennutzung über einen bestimmten Zeitraum anzuzeigen. Weitere Informationen finden Sie unter [Analyze Load Test Results in the Graphs View (Analysieren von Auslastungstestergebnissen in der Diagrammansicht)](../test/analyze-load-test-results-in-the-graphs-view.md).

> [!NOTE]
> Sie können diesen Abschnitt reduzieren oder erweitern, indem Sie den Pfeil links neben dem Abschnittstitel auswählen.

## <a name="controller-and-agent-resources"></a>Ressourcen für Controller und Agents

Der Abschnitt über Ressourcen für Controller und Agents enthält eine Liste der Computer, auf denen der Test ausgeführt wird. Computername, Prozessorzeit (%) und verfügbarer Speicher werden angezeigt. Sie können einen Computernamen auswählen, um das Diagramm **Controller und Agents** zu öffnen und die Ressourcennutzung über einen bestimmten Zeitraum anzuzeigen. Weitere Informationen finden Sie unter [Analyze Load Test Results in the Graphs View (Analysieren von Auslastungstestergebnissen in der Diagrammansicht)](../test/analyze-load-test-results-in-the-graphs-view.md).

> [!NOTE]
> Sie können diesen Abschnitt reduzieren oder erweitern, indem Sie den Pfeil links neben dem Abschnittstitel auswählen.

## <a name="errors"></a>Fehler

Der Abschnitt über Fehler enthält eine Liste aller Fehler, die während des Auslastungstests aufgetreten sind. Typ und Untertyp des Fehlers, Anzahl und die letzte Meldung werden angezeigt. Sie können einen Fehler auswählen, um die Tabelle **Fehler** zu öffnen und weitere Fehlerdetails zu überprüfen. Weitere Informationen finden Sie unter [Analyze Load Test Results and Errors in the Tables View (Analysieren von Auslastungstestergebnissen und -fehlern in der Tabellenansicht)](../test/analyze-load-test-results-and-errors-in-the-tables-view.md) und [How to: Analyze Errors Using the Counters Panel (Vorgehensweise: Analysieren von Fehlern mithilfe des Indikatorenfensters)](../test/how-to-analyze-errors-using-the-counters-panel.md).

> [!NOTE]
> Sie können diesen Abschnitt reduzieren oder erweitern, indem Sie den Pfeil links neben dem Abschnittstitel auswählen.

## <a name="printing-a-summary"></a>Ausdrucken einer Zusammenfassung

Sie können die Zusammenfassung des Auslastungstests ausdrucken, indem Sie im Kontextmenü der Zusammenfassung auf **Drucken** klicken. Sie können eine Vorschau des Druck anzeigen, indem Sie im Kontextmenü der Zusammenfassung auf **Seitenansicht** klicken. Sie können auch direkt aus der Seitenansicht drucken.

## <a name="see-also"></a>Siehe auch

- [Analyzing Threshold Rule Violations (Analysieren von Verstößen gegen die Schwellenwertregel)](../test/analyze-threshold-rule-violations-in-load-tests.md)
- [Analyze Load Test Results (Analysieren von Auslastungstestergebnissen)](../test/analyze-load-test-results-using-the-load-test-analyzer.md)