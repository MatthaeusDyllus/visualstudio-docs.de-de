---
title: 'Vorgehensweise: Ändern der Größe von NamedRange-Steuerelementen | Microsoft Docs'
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- controls [Office development in Visual Studio], resizing
- NamedRange control, resizing
- ranges, resizing in Excel
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: 6d475f9140607ba0ae7415a60a9589aef11a44a1
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/16/2018
---
# <a name="how-to-resize-namedrange-controls"></a>Gewusst wie: Ändern der Größe von NamedRange-Steuerelementen
  Sie können die Größe eines <xref:Microsoft.Office.Tools.Excel.NamedRange> -Steuerelements festlegen, wenn Sie es zu einem Microsoft Office Excel-Dokument hinzufügen. Möglicherweise möchten Sie jedoch zu einem späteren Zeitpunkt die Größe ändern.  
  
 [!INCLUDE[appliesto_xlalldocapp](../vsto/includes/appliesto-xlalldocapp-md.md)]  
  
 Sie können einen benannten Bereich in Projekten auf Dokumentebene zur Entwurfszeit oder zur Laufzeit ändern. Sie können benannte Bereiche in VSTO-Add-Ins auf Anwendungsebene auch zur Laufzeit ändern.  
  
 In diesem Thema werden die folgenden Aufgaben beschrieben:  
  
-   [Ändern der Größe von NamedRange-Steuerelementen zur Entwurfszeit](#designtime)  
  
-   [Ändern der Größe von NamedRange-Steuerelementen zur Laufzeit in einem Projekt auf Dokumentebene](#runtimedoclevel)  
  
-   [Ändern der Größe von NamedRange-Steuerelementen zur Laufzeit in einem VSTO-Add-In-Projekt](#runtimeaddin)  
  
##  <a name="designtime"></a> Resizing NamedRange Controls at Design Time  
 Sie können die Größe eines benannten Bereichs ändern, indem Sie die Größe im Dialogfeld **Namen definieren** neu definieren.  
  
#### <a name="to-resize-a-named-range-by-using-the-define-name-dialog-box"></a>So ändern Sie die Größe eines benannten Bereichs unter Verwendung des Dialogfelds „Namen definieren“  
  
1.  Klicken Sie mit der rechten Maustaste auf ein <xref:Microsoft.Office.Tools.Excel.NamedRange> -Steuerelement.  
  
2.  Klicken Sie im Kontextmenü auf **Benannte Bereiche verwalten** .  
  
     Das Dialogfeld **Namen definieren** wird geöffnet.  
  
3.  Wählen Sie den benannten Bereich aus, dessen Größe Sie ändern möchten.  
  
4.  Deaktivieren Sie das Feld **Bezieht sich auf** .  
  
5.  Wählen Sie die Zellen aus, anhand derer Sie die Größe des benannten Bereichs definieren möchten.  
  
6.  Klicken Sie auf **OK**.  
  
##  <a name="runtimedoclevel"></a> Resizing NamedRange Controls at Run Time in a Document-Level Project  
 Sie können die Größe eines benannten Bereichs programmgesteuert ändern, indem Sie die <xref:Microsoft.Office.Tools.Excel.NamedRange.RefersTo%2A> -Eigenschaft verwenden.  
  
> [!NOTE]  
>  Im Fenster **Eigenschaften** ist die <xref:Microsoft.Office.Tools.Excel.NamedRange.RefersTo%2A> -Eigenschaft als schreibgeschützt markiert.  
  
#### <a name="to-resize-a-named-range-programmatically"></a>So ändern Sie die Größe eines benannten Bereichs programmgesteuert  
  
1.  Erstellen Sie in der Zelle <xref:Microsoft.Office.Tools.Excel.NamedRange> A1 **von** ein `Sheet1`-Steuerelement.  
  
     [!code-csharp[Trin_VstcoreHostControlsExcel#4](../vsto/codesnippet/CSharp/Trin_VstcoreHostControlsExcelCS/Sheet1.cs#4)]
     [!code-vb[Trin_VstcoreHostControlsExcel#4](../vsto/codesnippet/VisualBasic/Trin_VstcoreHostControlsExcelVB/Sheet1.vb#4)]  
  
2.  Ändern Sie die Größe des benannten Bereichs, sodass er auch Zelle **B1**umfasst.  
  
     [!code-csharp[Trin_VstcoreHostControlsExcel#5](../vsto/codesnippet/CSharp/Trin_VstcoreHostControlsExcelCS/Sheet1.cs#5)]
     [!code-vb[Trin_VstcoreHostControlsExcel#5](../vsto/codesnippet/VisualBasic/Trin_VstcoreHostControlsExcelVB/Sheet1.vb#5)]  
  
##  <a name="runtimeaddin"></a> Resizing NamedRange Controls at Run Time in an VSTO Add-in project  
 Sie können die Größe eines <xref:Microsoft.Office.Tools.Excel.NamedRange> -Steuerelements in jedem beliebigen geöffneten Arbeitsblatt zur Laufzeit ändern. Weitere Informationen zum Hinzufügen eines <xref:Microsoft.Office.Tools.Excel.NamedRange> -Steuerelements zu einem Arbeitsblatt mit einem VSTO-Add-In finden Sie unter [How to: Add NamedRange Controls to Worksheets](../vsto/how-to-add-namedrange-controls-to-worksheets.md).  
  
#### <a name="to-resize-a-named-range-programmatically"></a>So ändern Sie die Größe eines benannten Bereichs programmgesteuert  
  
1.  Erstellen Sie in der Zelle <xref:Microsoft.Office.Tools.Excel.NamedRange> A1 **von** ein `Sheet1`-Steuerelement.  
  
     [!code-csharp[Trin_Excel_Dynamic_Controls#10](../vsto/codesnippet/CSharp/Trin_Excel_Dynamic_Controls/ThisAddIn.cs#10)]
     [!code-vb[Trin_Excel_Dynamic_Controls#10](../vsto/codesnippet/VisualBasic/Trin_Excel_Dynamic_Controls/ThisAddIn.vb#10)]  
  
2.  Ändern Sie die Größe des benannten Bereichs, sodass er auch Zelle **B1**umfasst.  
  
     [!code-csharp[Trin_Excel_Dynamic_Controls#11](../vsto/codesnippet/CSharp/Trin_Excel_Dynamic_Controls/ThisAddIn.cs#11)]
     [!code-vb[Trin_Excel_Dynamic_Controls#11](../vsto/codesnippet/VisualBasic/Trin_Excel_Dynamic_Controls/ThisAddIn.vb#11)]  
  
## <a name="see-also"></a>Siehe auch  
 [Erweitern von Word-Dokumenten und Excel-Arbeitsmappen in VSTO-Add-ins zur Laufzeit](../vsto/extending-word-documents-and-excel-workbooks-in-vsto-add-ins-at-run-time.md)   
 [Hinzufügen von Steuerelementen zu Office-Dokumenten zur Laufzeit](../vsto/adding-controls-to-office-documents-at-run-time.md)   
 [Steuerelemente für Office-Dokumente](../vsto/controls-on-office-documents.md)   
 [Übersicht über Hostelemente und Hoststeuerelemente](../vsto/host-items-and-host-controls-overview.md)   
 [Automatisieren von Excel mithilfe von erweiterten Objekten](../vsto/automating-excel-by-using-extended-objects.md)   
 [NamedRange-Steuerelement](../vsto/namedrange-control.md)   
 [Vorgehensweise: Hinzufügen von NamedRange-Steuerelementen zu Arbeitsblättern](../vsto/how-to-add-namedrange-controls-to-worksheets.md)   
 [Vorgehensweise: Ändern der Größe Lesezeichen-Steuerelementen](../vsto/how-to-resize-bookmark-controls.md)   
 [Vorgehensweise: Ändern der Größe von ListObject-Steuerelementen](../vsto/how-to-resize-listobject-controls.md)  
  
  