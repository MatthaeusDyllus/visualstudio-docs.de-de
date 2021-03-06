---
title: 'Exemplarische Vorgehensweise: Binden an Daten aus einem Dienst in einem VSTO Add-In-Projekt | Microsoft Docs'
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- databases [Office development in Visual Studio], scrolling records
- records [Office development in Visual Studio], scrolling
- data [Office development in Visual Studio], scrolling database records
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: a89b9455051031b3faa0a44102f2fe97dca97d89
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/16/2018
---
# <a name="walkthrough-binding-to-data-from-a-service-in-a-vsto-add-in-project"></a>Exemplarische Vorgehensweise: Binden an Daten aus einem Dienst in einem VSTO-Add-In-Projekt
  Sie können Daten in VSTO-Add-In-Projekten an Hoststeuerelemente binden. In dieser exemplarischen Vorgehensweise wird veranschaulicht, wie Steuerelemente zu einem Microsoft Office Word-Dokument hinzugefügt werden, wie die Steuerelemente an Daten gebunden werden, die aus dem MSDN Content Service abgerufen werden, und wie auf Ereignisse zur Laufzeit reagiert wird.  
  
 **Betrifft:** Die Informationen in diesem Thema betreffen Projekte auf Anwendungsebene für Word 2010. Weitere Informationen finden Sie unter [Verfügbare Funktionen nach Office-Anwendung und Projekttyp](../vsto/features-available-by-office-application-and-project-type.md).  
  
 In dieser exemplarischen Vorgehensweise werden die folgenden Aufgaben veranschaulicht:  
  
-   Hinzufügen eines <xref:Microsoft.Office.Tools.Word.RichTextContentControl> -Steuerelements zu einem Dokument zur Laufzeit  
  
-   Binden des <xref:Microsoft.Office.Tools.Word.RichTextContentControl> -Steuerelements an Daten aus einem Webdienst  
  
-   Reagieren auf das <xref:Microsoft.Office.Tools.Word.ContentControlBase.Entering> -Ereignis eines <xref:Microsoft.Office.Tools.Word.RichTextContentControl> Steuerelements  
  
 [!INCLUDE[note_settings_general](../sharepoint/includes/note-settings-general-md.md)]  
  
## <a name="prerequisites"></a>Erforderliche Komponenten  
 Zum Durchführen dieser exemplarischen Vorgehensweise benötigen Sie die folgenden Komponenten:  
  
-   [!INCLUDE[vsto_vsprereq](../vsto/includes/vsto-vsprereq-md.md)]  
  
-   [!INCLUDE[Word_15_short](../vsto/includes/word-15-short-md.md)] oder [!INCLUDE[Word_14_short](../vsto/includes/word-14-short-md.md)].  
  
## <a name="creating-a-new-project"></a>Erstellen eines neuen Projekts  
 Der erste Schritt besteht im Erstellen eines VSTO-Add-In-Projekts für Word.  
  
#### <a name="to-create-a-new-project"></a>So erstellen Sie ein neues Projekt  
  
1.  Erstellen Sie in Visual Basic oder C# ein Word-VSTO-Add-In-Projekt namens **MTPS Content Service**.  
  
     Weitere Informationen finden Sie unter [How to: Create Office Projects in Visual Studio](../vsto/how-to-create-office-projects-in-visual-studio.md).  
  
     Visual Studio öffnet die Datei `ThisAddIn.vb` oder `ThisAddIn.cs` und fügt das Projekt dem **Projektmappen-Explorer**hinzu.  
  
## <a name="adding-a-web-service"></a>Hinzufügen eines Webdiensts  
 Für diese exemplarische Vorgehensweise verwenden Sie einen Webdienst, der den Namen „MTPS Content Service“ hat. Dieser Webdienst gibt Informationen aus einem angegebenen MSDN-Artikel in Form einer XML-Zeichenfolge oder als Nur-Text zurück. In einem späteren Schritt wird gezeigt, wie die zurückgegebenen Informationen in einem Inhaltssteuerelement angezeigt werden.  
  
#### <a name="to-add-the-mtps-content-service-to-the-project"></a>So fügen Sie dem Projekt den „MTPS Content Service“ hinzu  
  
1.  Klicken Sie im Menü **Daten** auf **Neue Datenquelle hinzufügen**.  
  
2.  Klicken Sie im **Assistent zum Konfigurieren von Datenquellen**auf **Dienst**und dann auf **Weiter**.  
  
3.  Geben Sie die folgende URL in das Feld **Adresse** ein:  
  
     **http://services.msdn.microsoft.com/ContentServices/ContentService.asmx**  
  
4.  Klicken Sie auf **Go**.  
  
5.  Geben Sie in das Feld **Namespace** die Zeichenfolge **ContentService**ein, und klicken Sie auf **OK**.  
  
6.  Klicken Sie im Dialogfeld **Assistent zum Hinzufügen von Verweisen** auf **Fertig stellen**.  
  
## <a name="adding-a-content-control-and-binding-to-data-at-run-time"></a>Hinzufügen eines Inhaltssteuerelements und Binden an Daten zur Laufzeit  
 In VSTO-Add-In-Projekten nehmen Sie das Hinzufügen und Binden von Steuerelementen zur Laufzeit vor. In dieser exemplarischen Vorgehensweise konfigurieren Sie das Inhaltssteuerelement so, dass es Daten aus dem Webdienst abruft, wenn ein Benutzer auf das Steuerelement klickt.  
  
#### <a name="to-add-a-content-control-and-bind-to-data"></a>So fügen Sie ein Inhaltssteuerelement hinzu und binden es an Daten  
  
1.  Deklarieren Sie in der `ThisAddIn` -Klasse die Variablen für „MTPS Content Service“, das Inhaltssteuerelement und die Datenbindung.  
  
     [!code-csharp[Trin_WordAddIn_BindingDataToContentControl#2](../vsto/codesnippet/CSharp/trin_wordaddin_bindingdatatocontentcontrol/ThisAddIn.cs#2)]
     [!code-vb[Trin_WordAddIn_BindingDataToContentControl#2](../vsto/codesnippet/VisualBasic/trin_wordaddin_bindingdatatocontentcontrol/ThisAddIn.vb#2)]  
  
2.  Fügen Sie der `ThisAddIn` -Klasse die folgende Methode hinzu. Diese Methode erstellt ein Inhaltssteuerelement am Anfang des aktiven Dokuments.  
  
     [!code-csharp[Trin_WordAddIn_BindingDataToContentControl#4](../vsto/codesnippet/CSharp/trin_wordaddin_bindingdatatocontentcontrol/ThisAddIn.cs#4)]
     [!code-vb[Trin_WordAddIn_BindingDataToContentControl#4](../vsto/codesnippet/VisualBasic/trin_wordaddin_bindingdatatocontentcontrol/ThisAddIn.vb#4)]  
  
3.  Fügen Sie der `ThisAddIn` -Klasse die folgende Methode hinzu. Diese Methode initialisiert die Objekte, die zum Erstellen und Senden einer Anforderung an den Webdienst erforderlich sind.  
  
     [!code-csharp[Trin_WordAddIn_BindingDataToContentControl#6](../vsto/codesnippet/CSharp/trin_wordaddin_bindingdatatocontentcontrol/ThisAddIn.cs#6)]
     [!code-vb[Trin_WordAddIn_BindingDataToContentControl#6](../vsto/codesnippet/VisualBasic/trin_wordaddin_bindingdatatocontentcontrol/ThisAddIn.vb#6)]  
  
4.  Erstellen Sie einen Ereignishandler, um das MSDN Library-Dokument über Inhaltssteuerelemente abzurufen, wenn ein Benutzer auf das Inhaltssteuerelement klickt, und die Daten an das Inhaltssteuerelement zu binden.  
  
     [!code-csharp[Trin_WordAddIn_BindingDataToContentControl#5](../vsto/codesnippet/CSharp/trin_wordaddin_bindingdatatocontentcontrol/ThisAddIn.cs#5)]
     [!code-vb[Trin_WordAddIn_BindingDataToContentControl#5](../vsto/codesnippet/VisualBasic/trin_wordaddin_bindingdatatocontentcontrol/ThisAddIn.vb#5)]  
  
5.  Rufen Sie die Methoden `AddRichTextControlAtRange` und `InitializeServiceObjects` aus der `ThisAddIn_Startup` -Methode auf. C#-Programmierer müssen einen Ereignishandler hinzufügen.  
  
     [!code-csharp[Trin_WordAddIn_BindingDataToContentControl#3](../vsto/codesnippet/CSharp/trin_wordaddin_bindingdatatocontentcontrol/ThisAddIn.cs#3)]
     [!code-vb[Trin_WordAddIn_BindingDataToContentControl#3](../vsto/codesnippet/VisualBasic/trin_wordaddin_bindingdatatocontentcontrol/ThisAddIn.vb#3)]  
  
## <a name="testing-the-add-in"></a>Testen des Add-Ins  
 Wenn Sie Word öffnen, wird das <xref:Microsoft.Office.Tools.Word.RichTextContentControl> -Steuerelement angezeigt. Der Text im Steuerelement ändert sich, wenn Sie auf das Steuerelement klicken.  
  
#### <a name="to-test-the-vsto-add-in"></a>So testen Sie das VSTO-Add-In  
  
1.  Drücken Sie **F5**.  
  
2.  Klicken Sie auf das Inhaltssteuerelement.  
  
     Es werden Informationen aus dem „MTPS Content Service“ heruntergeladen und im Inhaltssteuerelement angezeigt.  
  
## <a name="see-also"></a>Siehe auch  
 [Binden von Daten an Steuerelemente in Office-Projektmappen](../vsto/binding-data-to-controls-in-office-solutions.md)  
  
  