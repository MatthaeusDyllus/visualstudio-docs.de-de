---
title: 'Exemplarische Vorgehensweise: Aktualisieren eines Diagramms in einem Dokument mithilfe von Optionsfeldern | Microsoft Docs'
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- documents [Office development in Visual Studio], updating using controls
- controls [Office development in Visual Studio], updating documents
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: 60daf98d02c358e3a288a7dbb6a8a02df3a1258f
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/16/2018
---
# <a name="walkthrough-updating-a-chart-in-a-document-using-radio-buttons"></a>Exemplarische Vorgehensweise: Aktualisieren eines Diagramms in einem Dokument mithilfe von Optionsfeldern
  Diese Vorgehensweise zeigt Ihnen, wie Sie Optionsfelder in einer Anpassung auf Dokumentebene für Microsoft Office Word verwenden, um Benutzern die Möglichkeit zu geben, Diagrammformatvorlagen im Dokument auszuwählen.  
  
 [!INCLUDE[appliesto_wdalldoc](../vsto/includes/appliesto-wdalldoc-md.md)]  
  
 In dieser exemplarischen Vorgehensweise werden die folgenden Aufgaben veranschaulicht:  
  
-   Hinzufügen eines Diagramms zum Dokument in einem Projekt auf Dokumentebene zur Entwurfszeit.  
  
-   Gruppieren von Optionsfeldern durch Hinzufügen zu einem Benutzersteuerelement.  
  
-   Ändern der Diagrammformatvorlage, wenn eine Option ausgewählt ist.  
  
 Das Ergebnis als vollständiges Beispiel finden Sie unter dem Beispiel der Word-Steuerelemente unter [Office Development Samples and Walkthroughs](../vsto/office-development-samples-and-walkthroughs.md).  
  
 [!INCLUDE[note_settings_general](../sharepoint/includes/note-settings-general-md.md)]  
  
## <a name="prerequisites"></a>Erforderliche Komponenten  
 Zum Durchführen dieser exemplarischen Vorgehensweise benötigen Sie die folgenden Komponenten:  
  
-   [!INCLUDE[vsto_vsprereq](../vsto/includes/vsto-vsprereq-md.md)]  
  
-   [!INCLUDE[Word_15_short](../vsto/includes/word-15-short-md.md)] oder [!INCLUDE[Word_14_short](../vsto/includes/word-14-short-md.md)].  
  
## <a name="creating-the-project"></a>Erstellen des Projekts  
 Im ersten Schritt wird ein Word-Dokumentprojekt erstellt.  
  
#### <a name="to-create-a-new-project"></a>So erstellen Sie ein neues Projekt  
  
1.  Erstellen Sie ein Word-Dokumentprojekt mit dem Namen **Meine Diagrammoptionen**. Wählen Sie im Assistenten **erstellen Sie ein neues Dokument**. Weitere Informationen finden Sie unter [How to: Create Office Projects in Visual Studio](../vsto/how-to-create-office-projects-in-visual-studio.md).  
  
     Visual Studio öffnet das neue Word-Dokument im Designer und fügt die **Meine Diagrammoptionen** Projekt **Projektmappen-Explorer**.  
  
## <a name="adding-a-chart-to-the-document"></a>Hinzufügen eines Diagramm zum Dokument  
  
#### <a name="to-add-a-chart"></a>So fügen Sie ein Diagramm hinzu  
  
1.  Klicken Sie im Word-Dokument, das in Visual Studio-Designer, auf dem Menüband gehostet wird auf die **einfügen** Registerkarte.  
  
2.  In der **Text** zu gruppieren, klicken Sie auf die **Objekt einfügen** Dropdown-Schaltfläche, und klicken Sie auf **Objekt**.  
  
     Die **Objekt** Dialogfeld wird geöffnet.  
  
3.  In der **Objekttyp** auf in der Liste der **neu erstellen** Registerkarte **Microsoft Graph-Diagramm** , und klicken Sie dann auf **OK**.  
  
     Das Dokument an der Einfügemarke ein Diagramm hinzugefügt wird und die **Datenblatt** Fenster wird mit einigen Standarddaten angezeigt.  
  
4.  Schließen der **Datenblatt** Fenster übernehmen die Standardwerte im Diagramm, und klicken in das Dokument den Fokus des Diagramms aufzuheben.  
  
5.  Mit der rechten Maustaste in des Diagramms, und klicken Sie dann auf **Formatobjekt**.  
  
6.  Auf der **Layout** auf der Registerkarte die **Formatobjekt** wählen Sie im Dialogfeld **Quadrat** , und klicken Sie auf **OK**.  
  
## <a name="adding-a-user-control-to-the-project"></a>Hinzufügen eines Benutzersteuerelements zum Projekt  
 Optionsfelder in einem Dokument schließen sich standardmäßig nicht gegenseitig aus. Sie können dafür sorgen, dass sie ordnungsgemäß funktionieren, indem Sie sie einem Benutzersteuerelement hinzufügen und dann Code schreiben, um die Auswahl zu steuern.  
  
#### <a name="to-add-a-user-control"></a>So fügen Sie ein Benutzersteuerelement hinzu  
  
1.  Wählen Sie die **Meine Diagrammoptionen** Projekt **Projektmappen-Explorer**.  
  
2.  Klicken Sie im Menü **Projekt** auf **Neues Element hinzufügen**.  
  
3.  In der **neues Element hinzufügen** (Dialogfeld), klicken Sie auf **Benutzersteuerelement**, benennen Sie das Steuerelement **ChartOptions** , und klicken Sie auf **hinzufügen**.  
  
#### <a name="to-add-windows-form-controls-to-the-user-control"></a>So fügen Sie dem Benutzersteuerelement Windows Forms-Steuerelemente hinzu  
  
1.  Wenn das Benutzersteuerelement nicht im Designer sichtbar ist, doppelklicken Sie auf **ChartOptions** in **Projektmappen-Explorer**.  
  
2.  Aus der **Standardsteuerelementen** auf der Registerkarte die **Toolbox**, ziehen Sie das erste **Optionsfeld** -Steuerelement auf das Benutzersteuerelement, und ändern Sie die folgenden Eigenschaften.  
  
    |Eigenschaft|Wert|  
    |--------------|-----------|  
    |**Name**|**columnChart**|  
    |**Text**|**Säulendiagramm**|  
  
3.  Fügen Sie eine zweite **Optionsfeld** für den Benutzer zu steuern, und ändern Sie die folgenden Eigenschaften.  
  
    |Eigenschaft|Wert|  
    |--------------|-----------|  
    |**Name**|**barChart**|  
    |**Text**|**Balkendiagramm**|  
  
4.  Fügen Sie ein drittes **Optionsfeld** für den Benutzer zu steuern, und ändern Sie die folgenden Eigenschaften.  
  
    |Eigenschaft|Wert|  
    |--------------|-----------|  
    |**Name**|**lineChart**|  
    |**Text**|**Liniendiagramm**|  
  
5.  Fügen Sie ein viertes **Optionsfeld** für den Benutzer zu steuern, und ändern Sie die folgenden Eigenschaften.  
  
    |Eigenschaft|Wert|  
    |--------------|-----------|  
    |**Name**|**areaBlockChart**|  
    |**Text**|**Flächendiagramm**|  
  
## <a name="adding-references"></a>Hinzufügen von Verweisen  
 Zum Zugriff auf das Diagramm über das Benutzersteuerelement in einem Dokument, müssen Sie einen Verweis auf die Microsoft.Office.Interop.Graph-Assembly in Ihrem Projekt haben.  
  
#### <a name="to-add-a-reference-to-the-microsoftofficeinteropgraph-assembly"></a>So fügen Sie einen Verweis auf die Microsoft.Office.Interop.Graph-Assembly hinzu  
  
1.  Klicken Sie im Menü **Projekt** auf **Verweis hinzufügen** .  
  
     Das Dialogfeld **Verweis hinzufügen** wird angezeigt.  
  
2.  Auf der **.NET** Registerkarte **Microsoft.Office.Interop.Graph** , und klicken Sie auf **OK**. Verwenden Sie die 14.0.0.0-Version der Assembly.  
  
## <a name="changing-the-chart-style-when-a-radio-button-is-selected"></a>Ändern der Diagrammformatvorlage bei ausgewähltem Optionsfeld  
 Damit die Schaltflächen ordnungsgemäß funktionieren, erstellen Sie ein öffentliches Ereignis auf dem Benutzersteuerelement, fügen Sie eine Eigenschaft hinzu, um den Auswahltyp festzulegen, und erstellen Sie eine Prozedur für das `CheckedChanged`-Ereignis der einzelnen Optionsfelder.  
  
#### <a name="to-create-an-event-and-property-on-a-user-control"></a>So erstellen Sie ein Ereignis und eine Eigenschaft auf einem Benutzersteuerelement  
  
1.  In **Projektmappen-Explorer**mit der rechten Maustaste auf das Benutzersteuerelement, und klicken Sie dann auf **Code anzeigen**.  
  
2.  Fügen Sie Code hinzu, um ein `SelectionChanged`-Ereignis und die `Selection`-Eigenschaft der `ChartOptions`-Klasse zu erstellen.  
  
     [!code-csharp[Trin_VstcoreProgrammingControlsWord#9](../vsto/codesnippet/CSharp/Trin_VstcoreProgrammingControlsWordCS/ChartOptions.cs#9)]
     [!code-vb[Trin_VstcoreProgrammingControlsWord#9](../vsto/codesnippet/VisualBasic/my chart options/ChartOptions.vb#9)]  
  
#### <a name="to-handle-the-checkedchange-event-of-the-radio-buttons"></a>So behandeln Sie das CheckedChange-Ereignis der Optionsfelder  
  
1.  Legen Sie den Diagrammtyp im `CheckedChanged`-Ereignishandler des `areaBlockChart`-Optionsfelds fest, und erhöhen Sie dann das Ereignis.  
  
     [!code-csharp[Trin_VstcoreProgrammingControlsWord#10](../vsto/codesnippet/CSharp/Trin_VstcoreProgrammingControlsWordCS/ChartOptions.cs#10)]
     [!code-vb[Trin_VstcoreProgrammingControlsWord#10](../vsto/codesnippet/VisualBasic/my chart options/ChartOptions.vb#10)]  
  
2.  Legen Sie den Diagrammtyp im `CheckedChanged`-Ereignishandler des `barChart`-Optionsfelds fest.  
  
     [!code-csharp[Trin_VstcoreProgrammingControlsWord#11](../vsto/codesnippet/CSharp/Trin_VstcoreProgrammingControlsWordCS/ChartOptions.cs#11)]
     [!code-vb[Trin_VstcoreProgrammingControlsWord#11](../vsto/codesnippet/VisualBasic/my chart options/ChartOptions.vb#11)]  
  
3.  Legen Sie den Diagrammtyp im `CheckedChanged`-Ereignishandler des `columnChart`-Optionsfelds fest.  
  
     [!code-csharp[Trin_VstcoreProgrammingControlsWord#12](../vsto/codesnippet/CSharp/Trin_VstcoreProgrammingControlsWordCS/ChartOptions.cs#12)]
     [!code-vb[Trin_VstcoreProgrammingControlsWord#12](../vsto/codesnippet/VisualBasic/my chart options/ChartOptions.vb#12)]  
  
4.  Legen Sie den Diagrammtyp im `CheckedChanged`-Ereignishandler des `lineChart`-Optionsfelds fest.  
  
     [!code-csharp[Trin_VstcoreProgrammingControlsWord#13](../vsto/codesnippet/CSharp/Trin_VstcoreProgrammingControlsWordCS/ChartOptions.cs#13)]
     [!code-vb[Trin_VstcoreProgrammingControlsWord#13](../vsto/codesnippet/VisualBasic/my chart options/ChartOptions.vb#13)]  
  
5.  In C# müssen Sie Ereignishandler für die Optionsfelder hinzufügen. Sie können den Code dem `ChartOptions`-Konstruktor hinzufügen, unterhalb des Aufrufs von `InitializeComponent`. Informationen zum Erstellen von Ereignishandlern finden Sie unter [Vorgehensweise: Erstellen von Ereignishandlern in Office-Projekten](../vsto/how-to-create-event-handlers-in-office-projects.md).  
  
     [!code-csharp[Trin_VstcoreProgrammingControlsWord#14](../vsto/codesnippet/CSharp/Trin_VstcoreProgrammingControlsWordCS/ChartOptions.cs#14)]  
  
## <a name="adding-the-user-control-to-the-document"></a>Hinzufügen des Benutzersteuerelements zum Dokument  
 Wenn Sie die Projektmappe zu erstellen, wird das neue Benutzersteuerelement automatisch um hinzugefügt der **Toolbox**. Anschließend können Sie das Steuerelement aus ziehen die **Toolbox** in Ihr Dokument.  
  
#### <a name="to-add-the-user-control-your-document"></a>So fügen Sie dem Dokument das Benutzersteuerelement hinzu  
  
1.  Klicken Sie im Menü **Erstellen** auf **Projektmappe erstellen**.  
  
     Die **ChartOptions** Benutzersteuerelement wird hinzugefügt, um die **Toolbox**.  
  
2.  In **Projektmappen-Explorer**, mit der rechten Maustaste **ThisDocument.vb** oder **ThisDocument.cs**, und klicken Sie dann auf **Sicht-Designer**.  
  
3.  Ziehen Sie die `ChartOptions` -Steuerelement aus der **Toolbox** auf das Dokument.  
  
     In der **Eigenschaften** Fenster, Name, die das Steuerelement, das Sie gerade dem Dokument hinzugefügt `ChartOptions1`.  
  
## <a name="changing-the-chart-type"></a>Ändern des Diagrammtyps  
 Erstellen Sie einen Ereignishandler, um den Diagrammtyp gemäß der im Benutzersteuerelement ausgewählten Option zu ändern.  
  
#### <a name="to-change-the-type-of-chart-that-is-displayed-in-the-document"></a>So ändern Sie den Diagrammtyp, der im Dokument angezeigt wird  
  
1.  Fügen Sie der `ThisDocument`-Klasse den folgenden Ereignishandler hinzu.  
  
     [!code-vb[Trin_VstcoreProgrammingControlsWord#15](../vsto/codesnippet/VisualBasic/my chart options/ThisDocument.vb#15)]
     [!code-csharp[Trin_VstcoreProgrammingControlsWord#15](../vsto/codesnippet/CSharp/Trin_VstcoreProgrammingControlsWordCS/ThisDocument.cs#15)]  
  
2.  In C# müssen Sie dem <xref:Microsoft.Office.Tools.Word.Document.Startup>-Ereignis einen Ereignishandler für das Benutzersteuerelement hinzufügen.  
  
     [!code-csharp[Trin_VstcoreProgrammingControlsWord#16](../vsto/codesnippet/CSharp/Trin_VstcoreProgrammingControlsWordCS/ThisDocument.cs#16)]  
  
## <a name="testing-the-application"></a>Testen der Anwendung  
 Sie können jetzt Ihr Dokument testen, um sicherzustellen, dass die Diagrammformatvorlage ordnungsgemäß aktualisiert wird, wenn Sie ein Optionsfeld auswählen.  
  
#### <a name="to-test-your-document"></a>So testen Sie das Dokument  
  
1.  Drücken Sie F5, um das Projekt auszuführen.  
  
2.  Wählen Sie verschiedene Optionsfelder aus.  
  
3.  Stellen Sie sicher, dass sich die Diagrammformatvorlage ändert, um der Auswahl zu entsprechen.  
  
## <a name="next-steps"></a>Nächste Schritte  
 Die folgenden Aufgaben könnten sich daran anschließen:  
  
-   Verwenden einer Schaltfläche zum Ausfüllen eines Textfeldes. Weitere Informationen finden Sie unter [Exemplarische Vorgehensweise: Anzeigen von Text in einem Textfeld in einem Dokument mithilfe einer Schaltfläche](../vsto/walkthrough-displaying-text-in-a-text-box-in-a-document-using-a-button.md).  
  
-   Ändern der Formatierung durch Auswahl eines Formats aus einem Kombinationsfeld. Weitere Informationen finden Sie unter [Exemplarische Vorgehensweise: Ändern von Dokument Formatierung mithilfe von CheckBox-Steuerelementen](../vsto/walkthrough-changing-document-formatting-using-checkbox-controls.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Exemplarische Vorgehensweisen in Word](../vsto/walkthroughs-using-word.md)   
 [Office-Entwicklungsbeispiele und exemplarische Vorgehensweisen](../vsto/office-development-samples-and-walkthroughs.md)   
 [Einschränkungen für Windows Forms-Steuerelemente in Office-Dokumenten](../vsto/limitations-of-windows-forms-controls-on-office-documents.md)  
  
  