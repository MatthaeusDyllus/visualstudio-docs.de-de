---
title: 'Workflow-Designer - Vorgehensweise: Verwenden des Variablen-Designers'
ms.date: 11/04/2016
ms.topic: conceptual
ms.prod: visual-studio-dev15
ms.technology: vs-workflow-designer
f1_keywords:
- System.Activities.Presentation.View.DesignTimeVariable.UI
ms.assetid: 0318dfb0-bf8f-4f92-9b86-ae4c1b2161ad
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: dc180df4a9be83c0f0b755bffd7ed40009b41497
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/26/2018
---
# <a name="how-to-use-the-variable-designer"></a>Vorgehensweise: Verwenden des Variablen-Designers

Der Variablen-Designer dient zum Erstellen von Variablen in Datenbindungsszenarien und bedingten Anweisungen. Der Designer zugegriffen wird, indem Sie auf die **Variablen** Schaltfläche in der unteren linken Ecke des Zeichenbereichs. Der Designer enthält eine Liste von Variablen, die in einer Tabelle angezeigt und können nach jedem Spaltenkopf, sortiert werden, mit Ausnahme von der **Standard** Spalte. Jede Variable verfügt über einen Namen, einen Variablentyp, einen Gültigkeitsbereich und ggf. über einen Standardwert. Der Name und der Standardwert sind bearbeitbare Textfelder, der Typ und der Gültigkeitsbereich sind Dropdownlisten. Der Gültigkeitsbereich entspricht der Aktivität, die beim Aufrufen des Variablen-Designers ausgewählt wurde. Wenn eine Variable nicht innerhalb des Gültigkeitsbereichs der Auswahl erstellt werden kann, wird standardmäßig der Gültigkeitsbereich der nächsten Vorgängeraktivität der Auswahl verwendet, in dem die Variable erstellt werden kann. Weitere Informationen finden Sie unter [Variablen und Argumente (.NET)](/dotnet/framework/windows-workflow-foundation/variables-and-arguments).

 Die Sortierreihenfolge wird erst übernommen, wenn der Benutzer eines der Sortiersteuerelemente explizit verwendet, den Variablen-Designer schließt und erneut öffnet oder eine andere Variable erstellt.

## <a name="to-create-a-new-variable"></a>So erstellen Sie eine neue Variable

1.  Öffnen Sie in Visual Studio eine Projektmappe Workflow- oder aktivitätsprojektmappe.

2.  Wählen Sie im Zeichenbereich eine Aktivität im Workflow aus.

3.  Öffnen Sie den Variablen-Designer, indem Sie auf die **Variablen** Schaltfläche in der unteren linken Ecke des Zeichenbereichs. Der Variablen-Designer wird angezeigt.

4.  Klicken Sie auf die leere Zeile, die mit der Bezeichnung **Variable erstellen**. Dadurch wird eine neue Zeile mit einer neuen Variablen, die mit den folgenden Standardwerten hinzugefügt: Bereichsgrenzen für die **Namen** , wobei x eine ganze Zahl mit einem Anfangswert von 1 ist, die zum Erstellen von eindeutiger Variablennamen automatisch erhöht  **Zeichenfolge** für die **Variablentyp**, und **Sequenz** für die **Bereich**. Wird kein Wert für hinzugefügt **Standard**. Sie können diese Werte jederzeit während des Workflowentwurfs ändern.

    > [!NOTE]
    > Um eine Variable zu löschen, wählen Sie die Variable, indem Sie darauf klicken, und drücken Sie dann die **löschen** Schlüssel.

## <a name="see-also"></a>Siehe auch

- [Verwenden des Workflow-Designers](../workflow-designer/using-the-workflow-designer.md)
- [Variablen und Argumente](/dotnet/framework/windows-workflow-foundation/variables-and-arguments)
- [Vorgehensweise: Verwenden des Argument-Designers](../workflow-designer/how-to-use-the-argument-designer.md)