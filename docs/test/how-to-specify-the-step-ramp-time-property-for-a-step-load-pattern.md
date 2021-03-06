---
title: Schrittverlaufszeit für ein Schrittauslastungsmuster für Auslastungstests in Visual Studio
ms.date: 10/19/2016
ms.topic: conceptual
helpviewer_keywords:
- load tests, load patterns
ms.assetid: 4a69e857-f93b-4907-9a01-fd1b66291205
author: gewarren
ms.author: gewarren
manager: douge
ms.prod: visual-studio-dev15
ms.technology: vs-ide-test
ms.openlocfilehash: 20eb70b6c3c6308e41599e65a4b00a3e4043e8d1
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/26/2018
---
# <a name="how-to-specify-the-step-ramp-time-property-for-a-step-load-pattern"></a>How to: Specify the Step Ramp Time Property for a Step Load Pattern

Nachdem Sie den Auslastungstest mithilfe des **Assistenten für neuen Auslastungstest** erstellt haben, können Sie die Szenarioeigenschaften mit dem **Auslastungstest-Editor** entsprechend Ihren Testanforderungen und -zielen ändern. Weitere Informationen finden Sie unter [ Vorgehensweise: Erstellen und Ausführen eines Auslastungstests](../test/walkthrough-create-and-run-a-load-test.md).

> [!NOTE]
> Eine vollständige Liste der Eigenschaften von Auslastungstestszenarios und deren Beschreibungen finden Sie unter [Load Test Scenario Properties (Auslastungstestszenario-Eigenschaften)](../test/load-test-scenario-properties.md).

Die Eigenschaft **Schrittverlaufszeit** wird im Eigenschaftenfenster festgelegt. Sie bearbeiten Eigenschaften von Auslastungstestszenarien im Auslastungstest-Editor.

Die Eigenschaft **Schrittverlaufszeit** wird nur mit einem Schrittauslastungsmuster verwendet. Weitere Informationen finden Sie unter [Editing Load Patterns to Model Virtual User Activities (Bearbeiten von Auslastungsmustern zur Modellierung virtueller Benutzeraktivitäten)](../test/edit-load-patterns-to-model-virtual-user-activities.md).

Ein schrittweises Auslastungsmuster wird zum Erhöhen der Auslastung auf den Servern während der Ausführung des Auslastungstests verwendet, um zu verdeutlichen, wie sich die Leistung bei Erhöhen der Benutzerauslastung ändert. Wenn Sie z. B. die Leistung der Server beim Erhöhen der Benutzerauslastung auf 2.000 Benutzer anzeigen möchten, können Sie einen 10-stündigen Auslastungstest mit einem schrittweisen Auslastungsmuster mit den folgenden Eigenschaften ausführen:

-   Benutzeranzahl (ursprünglich): 100

-   Maximale Benutzeranzahl: 2.000

-   Schrittdauer (Sekunden): 1.800

-   Schrittverlaufszeit (Sekunden): 20

-   Benutzeranzahl pro Schritt: 100

Mit diesen Einstellungen wird der Auslastungstest 30 Minuten (1.800 Sekunden) mit einer Benutzerauslastung von 100, 200, 300 und bis zu 2.000 Benutzern ausgeführt.

> [!NOTE]
> Die Eigenschaft **Schrittverlaufszeit** ist die einzige dieser Eigenschaften, die im Assistenten für neuen Auslastungstest nicht ausgewählt werden kann.

Die Eigenschaft **Schrittverlaufszeit** ermöglicht es, dass die Steigerung von einer Stufe zur nächsten (z.B. von 100 auf 200 Benutzer) schrittweise statt plötzlich vonstatten geht. In dem Beispiel würde die Benutzerauslastung von 100 auf 200 Benutzer in einem Zeitraum von 20 Sekunden (Zunahme von fünf Benutzern pro Sekunde) gesteigert werden.

## <a name="to-edit-the-step-ramp-time-property-for-a-step-load-pattern"></a>So bearbeiten Sie die Eigenschaft "Schrittverlaufszeit" für ein schrittweises Auslastungsmuster

1.  Öffnen Sie einen Auslastungstest.

     Der **Auslastungstest-Editor** wird angezeigt. Die Auslastungsteststruktur wird angezeigt.

2.  Öffnen Sie im Ordner **Szenarios** der Auslastungsteststruktur den Szenarioknoten, für den die Schrittverlaufszeit angegeben werden soll.

3.  Klicken Sie auf den Knoten **Schrittweises Auslastungsmuster**.

    > [!NOTE]
    > Das Auslastungsmuster für das Szenario muss ein schrittweises Auslastungsmuster sein. Falls dies nicht der Fall ist, zeigt das Auslastungsmuster den Auslastungsmustertyp an, der dem Szenario derzeit zugeordnet ist. Weitere Informationen finden Sie unter [Editing Load Patterns to Model Virtual User Activities (Bearbeiten von Auslastungsmustern zur Modellierung virtueller Benutzeraktivitäten)](../test/edit-load-patterns-to-model-virtual-user-activities.md).

4.  Klicken Sie im Menü **Ansicht** auf **Eigenschaftenfenster**.

     Die Szenariokategorien und -eigenschaften werden im Eigenschaftenfenster angezeigt.

5.  Legen Sie den Wert für die Eigenschaft **Schrittverlaufszeit** fest, indem Sie eine Zahl für die Sekunden der einzelnen Schritte eingeben, um die von der Eigenschaft **Benutzeranzahl pro Schritt** angegebenen Benutzer allmählich hinzuzufügen.

6.  Nachdem die Änderungen der Eigenschaft abgeschlossen sind, klicken Sie im Menü **Datei** auf **Speichern**. Sie können anschließend den Auslastungstest mit dem neuen Wert für die **Schrittverlaufszeit** ausführen.

## <a name="see-also"></a>Siehe auch

- [Editing Load Test Scenarios (Szenarios zum Bearbeiten von Auslastungstests)](../test/edit-load-test-scenarios.md)
- [Testcontroller und Test-Agents](configure-test-agents-and-controllers-for-load-tests.md)
- [Auslastungstestszenario-Eigenschaften](../test/load-test-scenario-properties.md)
- [Bearbeiten von Auslastungsmustern zur Modellierung virtueller Benutzeraktivitäten](../test/edit-load-patterns-to-model-virtual-user-activities.md)