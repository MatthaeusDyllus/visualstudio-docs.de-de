---
title: 'Exemplarische Vorgehensweise: Erstellen einer DataTable im Dataset-Designer'
ms.date: 10/19/2016
ms.topic: conceptual
helpviewer_keywords:
- DataTable objects, creating
- Dataset Designer, creating data tables
- tables [Visual Studio], creating
- data [Visual Studio], Dataset Designer
author: gewarren
ms.author: gewarren
manager: douge
ms.prod: visual-studio-dev15
ms.technology: vs-data-tools
ms.workload:
- data-storage
ms.openlocfilehash: baf4fca6c45bb81473b5b4fa0169c7958105803f
ms.sourcegitcommit: 58052c29fc61c9a1ca55a64a63a7fdcde34668a4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2018
ms.locfileid: "34747442"
---
# <a name="walkthrough-creating-a-datatable-in-the-dataset-designer"></a>Exemplarische Vorgehensweise: Erstellen einer DataTable im Dataset-Designer

In dieser exemplarischen Vorgehensweise wird erläutert, wie zum Erstellen einer <xref:System.Data.DataTable> (ohne einen TableAdapter) mithilfe der **Dataset-Designer**. Informationen zum Erstellen von Datentabellen, die TableAdapters enthalten, finden Sie unter [erstellen und Konfigurieren von TableAdapters](../data-tools/create-and-configure-tableadapters.md).

In dieser exemplarischen Vorgehensweise werden u. a. folgende Aufgaben veranschaulicht:

-   Erstellen ein neues Windows Forms-Anwendungsprojekt

-   Hinzufügen eines neuen Datasets zur Anwendung

-   Das Dataset hinzugefügt eine neue Datentabelle

-   Hinzufügen von Spalten zur Datentabelle

-   Festlegen des Primärschlüssels für die Tabelle

## <a name="creating-a-new-windows-forms-application"></a>Erstellen einer neuen Windows Forms-Anwendung

### <a name="to-create-a-new-windows-forms-application-project"></a>So erstellen Sie ein neues Windows Forms-Anwendungsprojekt

1. In Visual Studio auf die **Datei** klicken Sie im Menü **neu**, **Projekt...** .

2. Erweitern Sie entweder **Visual C#-** oder **Visual Basic** im linken Bereich, und wählen Sie dann **Windows Desktop**.

3. Wählen Sie im mittleren Bereich die **Windows Forms-App** Projekttyp.

4. Nennen Sie das Projekt **DataTableWalkthrough**, und wählen Sie dann **OK**.

     Die **DataTableWalkthrough** Projekt wird erstellt und hinzugefügt **Projektmappen-Explorer**.

## <a name="adding-a-new-dataset-to-the-application"></a>Hinzufügen eines neuen Datasets zur Anwendung

### <a name="to-add-a-new-dataset-item-to-the-project"></a>So fügen Sie dem Projekt ein neues Dataset-Element hinzu

1.  Auf der **Projekt** klicken Sie im Menü **neues Element hinzufügen...** .

     Das Dialogfeld "Neues Element hinzufügen" angezeigt wird.

2.  Wählen Sie im linken Bereich **Daten**, und wählen Sie dann **DataSet** im mittleren Bereich.

3.  Wählen Sie **Hinzufügen** aus.

     Visual Studio fügt eine Datei namens **DataSet1.xsd** auf das Projekt und öffnet sie in der **Dataset-Designer**.

## <a name="adding-a-new-datatable-to-the-dataset"></a>Hinzufügen einer neuen "DataTable" zum Dataset

### <a name="to-add-a-new-data-table-to-the-dataset"></a>Das Dataset eine neue Datentabelle hinzu

1.  Ziehen Sie eine **DataTable** aus der **DataSet** auf der Registerkarte die **Toolbox** auf die **Dataset-Designer**.

     Eine Tabelle namens **DataTable1** zum Dataset hinzugefügt wird.

2.  Klicken Sie auf die Titelleiste des **DataTable1** und benennen Sie sie `Music`.

## <a name="adding-columns-to-the-datatable"></a>Hinzufügen von Spalten zu der "DataTable"

### <a name="to-add-columns-to-the-datatable"></a>Um Spalten hinzuzufügen, zu der "DataTable"

1.  Mit der rechten Maustaste die **Musik** Tabelle. Zeigen Sie auf **hinzufügen**, und klicken Sie dann auf **Spalte**.

2.  Den Namen der Spalte `SongID`.

3.  In der **Eigenschaften** legen die <xref:System.Data.DataColumn.DataType%2A> Eigenschaft <xref:System.Int16?displayProperty=fullName>.

4.  Wiederholen Sie diesen Vorgang, und fügen Sie die folgenden Spalten:

     `SongTitle`: <xref:System.String?displayProperty=fullName>

     `Artist`: <xref:System.String?displayProperty=fullName>

     `Genre`: <xref:System.String?displayProperty=fullName>

## <a name="setting-the-primary-key-for-the-table"></a>Festlegen der Primärschlüssel für die Tabelle

Alle Datentabellen sollten über einen Primärschlüssel verfügen. Ein Primärschlüssel identifiziert eindeutig einen bestimmten Datensatz in einer Datentabelle.

### <a name="to-set-the-primary-key-of-the-data-table"></a>Den Primärschlüssel der Datentabelle festgelegt.

-   Mit der rechten Maustaste die **SongID** Spalte, und klicken Sie dann auf **Primärschlüssel festlegen**.

     Ein Schlüsselsymbol wird neben der **SongID** Spalte.

## <a name="saving-your-project"></a>Beim Speichern des Projekts

### <a name="to-save-the-datatablewalkthrough-project"></a>Zum Speichern des Projekts DataTableWalkthrough

-   Auf der **Datei** Menü klicken Sie auf **alle speichern**.

## <a name="see-also"></a>Siehe auch

- [Erstellen und Konfigurieren von Datasets in Visual Studio](../data-tools/create-and-configure-datasets-in-visual-studio.md)
- [Binden von Steuerelementen an Daten in Visual Studio](../data-tools/bind-controls-to-data-in-visual-studio.md)
- [Überprüfen von Daten](../data-tools/validate-data-in-datasets.md)
- [Speichern von Daten](../data-tools/saving-data.md)