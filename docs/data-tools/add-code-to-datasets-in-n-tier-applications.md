---
title: Fügen Sie Code hinzu, um Datasets in n-Tier-Anwendungen
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- n-tier applications, extending datasets
ms.assetid: d43c2ccd-4902-43d8-b1a8-d10ca5d3210c
author: gewarren
ms.author: gewarren
manager: douge
ms.prod: visual-studio-dev15
ms.technology: vs-data-tools
ms.workload:
- data-storage
ms.openlocfilehash: 6de192b07552b4516aa8289e2a68fa90830b7fe8
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/26/2018
---
# <a name="add-code-to-datasets-in-n-tier-applications"></a>Fügen Sie Code hinzu, um Datasets in n-Tier-Anwendungen
Sie können die Funktionen eines Datasets erweitern, indem Sie die Datei eine partielle Klasse für das Dataset zu erstellen und Code hinzufügen (anstatt zum Hinzufügen von Code, um die *DatasetName*. Dataset.Designer-Datei). Partielle Klassen können Sie Code für eine bestimmte Klasse auf mehrere physische Dateien unterteilt werden. Weitere Informationen finden Sie unter [partielle](/dotnet/visual-basic/language-reference/modifiers/partial) oder [partielle Klassen und Methoden](/dotnet/csharp/programming-guide/classes-and-structs/partial-classes-and-methods).

Der Code, der ein Dataset definiert wird generiert, jedes Mal, wenn die Definition des Datasets (in das typisierte Dataset) geändert werden. Dieser Code wird auch generiert, wenn Sie während der Ausführung des Assistenten für alle Änderungen vornehmen, die die Konfiguration eines Datasets ändert. Um zu verhindern, dass Ihr Code während der erneuten Generierung eines Datasets gelöscht wird, fügen Sie Code partiellen Klassendatei für das Dataset ein.

Standardmäßig ist bei einer Trennung von Dataset und TableAdapter-Code wird eine separate Klassendatei in jedem Projekt angelegt. Das ursprüngliche Projekt enthält eine Datei namens *DatasetName*. Designer.vb (oder *DatasetName*. Designer.cs), die den TableAdapter-Code enthält. Das Projekt, das in festgelegten der **Dataset-Projekt** Eigenschaft verfügt über eine Datei mit dem Namen *DatasetName*. DataSet.Designer.vb (oder *DatasetName*. (DataSet.Designer.cs). Diese Datei enthält den Dataset-Code.

> [!NOTE]
>  Beim Trennen von Datasets und TableAdaptern (durch Festlegen der **DataSet-Projekt** Eigenschaft), vorhandene partielle Dataset-Klassen im Projekt wird nicht automatisch verschoben werden. Vorhandene partielle DataSet-Klassen müssen manuell in das DataSet-Projekt verschoben werden.

> [!NOTE]
>  Wenn Validierungscode hinzugefügt werden muss, enthält das typisierte Dataset Funktionen zum Generieren von <xref:System.Data.DataTable.ColumnChanging> und <xref:System.Data.DataTable.RowChanging> -Ereignishandler. Weitere Informationen finden Sie unter [Hinzufügen von Validierungen zu einem n-Tier-Dataset](../data-tools/add-validation-to-an-n-tier-dataset.md).

## <a name="to-add-code-to-datasets-in-n-tier-applications"></a>Hinzufügen von Code zu Datasets in n-Tier-Anwendungen

1.  Suchen Sie das Projekt, das die XSD-Datei enthält.

2.  Wählen Sie die **XSD** Datei, um das Dataset zu öffnen.

3.  Mit der rechten Maustaste in der Datentabelle, Sie fügen Code (der Tabellenname in der Titelleiste), und wählen Sie dann möchten **Code anzeigen**.

     Eine partielle Klasse wird erstellt und im Code-Editor geöffnet.

4.  Fügen Sie Code innerhalb der Deklaration der partiellen Klasse hinzu.

     Das folgende Beispiel zeigt, wo der CustomersDataTable im NorthwindDataSet Code hinzufügen:

    ```vb
    Partial Public Class CustomersDataTable
        ' Add code here to add functionality
        ' to the CustomersDataTable.
    End Class
    ```
    ```csharp
    partial class CustomersDataTable
    {
        // Add code here to add functionality
        // to the CustomersDataTable.
    }
    ```

## <a name="see-also"></a>Siehe auch

- [Übersicht über N-Tier-Datenanwendungen](../data-tools/n-tier-data-applications-overview.md)
- [Gewusst wie: Hinzufügen von Code zu TableAdapters in N-Tier-Anwendungen](../data-tools/add-code-to-tableadapters-in-n-tier-applications.md)
- [Erstellen und Konfigurieren von TableAdapters](create-and-configure-tableadapters.md)
- [Übersicht über die hierarchische Aktualisierung](hierarchical-update.md)
- [Datasettools in Visual Studio](../data-tools/dataset-tools-in-visual-studio.md)