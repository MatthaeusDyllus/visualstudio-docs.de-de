---
title: Auslastungstest-API in Visual Studio
ms.date: 10/19/2016
ms.topic: conceptual
helpviewer_keywords:
- code, load tests
- plug-ins, load test
- APIs, load tests
ms.assetid: e15567bc-1f21-4feb-b81d-f17ba35cfde5
author: gewarren
ms.author: gewarren
manager: douge
ms.prod: visual-studio-dev15
ms.technology: vs-ide-test
ms.openlocfilehash: 3a5204848c24a25514fc8eb30a81dbca704a77a3
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/26/2018
---
# <a name="how-to-use-the-load-test-api"></a>Gewusst wie: Verwenden der Auslastungstest-API

Visual Studio unterstützt Auslastungstest-Plug-Ins zum Steuern oder Erweitern der Funktionen eines Auslastungstests. Auslastungstest-Plug-Ins sind benutzerdefinierte Klassen, die die <xref:Microsoft.VisualStudio.TestTools.LoadTesting.ILoadTestPlugin>-Schnittstelle des <xref:Microsoft.VisualStudio.TestTools.LoadTesting>-Namespace implementieren. Auslastungstest-Plug-Ins ermöglichen die benutzerdefinierte Steuerung von Auslastungstests, z. B. das Abbrechen eines Auslastungstests beim Erreichen eines bestimmten Indikator- oder Fehlerschwellenwerts. Verwenden Sie die Eigenschaften der <xref:Microsoft.VisualStudio.TestTools.LoadTesting.LoadTest>-Klasse zum Abrufen oder Festlegen von Auslastungstestparametern im benutzerdefinierten Code. Verwenden Sie die Ereignisse der <xref:Microsoft.VisualStudio.TestTools.LoadTesting.LoadTest>-Klasse, um Delegate für Benachrichtigungen anzufügen, die während der Ausführung des Auslastungstests ausgegeben werden.

> [!TIP]
> Verwenden Sie den Objektkatalog, um den <xref:Microsoft.VisualStudio.TestTools.LoadTesting>-Namespace zu durchsuchen. Sowohl der Visual C#- als auch der Visual Basic-Editor bieten IntelliSense-Unterstützung für das Schreiben von Code mit den Klassen im Namespace.

Sie können auch Plug-Ins für Webleistungstests erstellen. Weitere Informationen finden Sie unter [How to: Create a Web Performance Test Plug-In (Vorgehensweise: Erstellen eines Webleistungstest-Plug-Ins)](../test/how-to-create-a-web-performance-test-plug-in.md) und [How to: Create a Request-Level Plug-In (Vorgehensweise: Erstellen eines Anforderungsebenen-Plug-Ins)](../test/how-to-create-a-request-level-plug-in.md).

## <a name="to-use-the-loadtesting-namespace"></a>So verwenden Sie den LoadTesting-Namespace

1.  Öffnen Sie ein Webleistungs- und Auslastungstestprojekt, das einen Auslastungstest enthält.

2.  Fügen Sie Ihrer Testprojektmappe ein Projekt für eine Visual C#- oder Visual Basic-Klassenbibliothek hinzu.

3.  Fügen Sie dem Webleistungs- und Auslastungstestprojekt einen Verweis auf das Klassenbibliotheksprojekt hinzu.

4.  Fügen Sie dem Klassenbibliotheksprojekt einen Verweis auf die Microsoft.VisualStudio.QualityTools.LoadTestFramework-DLL hinzu.

5.  Fügen Sie der Klassendatei im Klassenbibliotheksprojekt eine `using`-Anweisung für den <xref:Microsoft.VisualStudio.TestTools.LoadTesting>-Namespace hinzu.

6.  Erstellen Sie eine öffentliche Klasse, die die <xref:Microsoft.VisualStudio.TestTools.LoadTesting.ILoadTestPlugin>-Schnittstelle implementiert.

7.  Erstellen Sie das Projekt.

8.  Fügen Sie das neue Auslastungstest-Plug-In mithilfe des Auslastungstest-Editors hinzu:

    1.  Klicken Sie mit der rechten Maustaste auf den Stammknoten des Auslastungstests, und klicken Sie anschließend auf **Auslastungstest-Plug-In hinzufügen**.

    2.  Das Dialogfeld **Auslastungstest-Plug-In hinzufügen** wird angezeigt.

    3.  Legen Sie im Bereich "Eigenschaften für das ausgewählte Plug-In" die Anfangswerte fest, die das Plug-In zur Laufzeit verwenden soll.

        > [!NOTE]
        > Sie können beliebig viele Plug-In-Eigenschaften verfügbar machen. Die Eigenschaften müssen dazu lediglich öffentlich, festlegbar und von einem Basistyp (z. B. "Integer", "Boolean" oder "String") sein. Sie können die Eigenschaften des Auslastungstest-Plug-Ins auch zu einem späteren Zeitpunkt im Eigenschaftenfenster bearbeiten.

9. Führen Sie den Auslastungstest aus.

     Eine Implementierung von <xref:Microsoft.VisualStudio.TestTools.LoadTesting.ILoadTestPlugin> finden Sie unter [How to: Create a Load Test Plug-In (Vorgehensweise: Erstellen eines Auslastungstest-Plug-Ins)](../test/how-to-create-a-load-test-plug-in.md).

## <a name="see-also"></a>Siehe auch

- <xref:Microsoft.VisualStudio.TestTools.LoadTesting>
- [Erstellen von benutzerdefiniertem Code und benutzerdefinierten Plug-Ins für Auslastungstests](../test/create-custom-code-and-plug-ins-for-load-tests.md)
- [Gewusst wie: Verwenden der Webleistungstest-API](../test/how-to-use-the-web-performance-test-api.md)
- [Gewusst wie: Erstellen eines Auslastungstest-Plug-Ins](../test/how-to-create-a-load-test-plug-in.md)