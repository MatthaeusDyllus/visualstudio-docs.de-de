---
title: 'Vorgehensweise: Hinzufügen von XMLNodes-Steuerelementen zu Word-Dokumenten | Microsoft Docs'
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- XMLNodes control, adding to documents
- controls [Office development in Visual Studio], adding to documents
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: 1ff96af4078883bf77d3632d08b6417ff1c34e2f
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/16/2018
---
# <a name="how-to-add-xmlnodes-controls-to-word-documents"></a>Gewusst wie: Hinzufügen von XMLNodes-Steuerelementen zu Word-Dokumenten
  **Wichtige** die Informationen in diesem Thema nach Microsoft Word wird dargestellten ausschließlich für die Vorteile und die Verwendung von Einzelpersonen und Organisationen, die außerhalb der Vereinigten Staaten und seine Gebiete befinden, oder verwenden, oder entwickeln Programme, die unter ausgeführt, im Zusammenhang mit benutzerdefinierten XML-Code von Microsoft Word Microsoft Word-Produkte, die von Microsoft vor Januar 2010 lizenziert wurden, wenn eine Implementierung der einzelnen Funktionen von Microsoft entfernt. Diese Informationen bezüglich Microsoft Word kann nicht gelesen oder von Einzelpersonen oder Organisationen aus, in den Vereinigten Staaten oder die Vertriebsgebiete, denen der verwenden, oder entwickeln Programme, die auf Microsoft Word-Produkte ausgeführt, die von Microsoft nach dem 10. Januar 2010 lizenziert wurden verwendet werden ; Diese Produkte verhält sich nicht wie Produkte, die vor diesem Datum lizenziert oder erworben und lizenziert für die Verwendung außerhalb der Vereinigten Staaten.  
  
 [!INCLUDE[appliesto_wdalldoc](../vsto/includes/appliesto-wdalldoc-md.md)]  
  
 Wenn Sie Microsoft Office Word-Dokument ein sich wiederholendes XML-Schemaelement zuordnen, fügt Visual Studio automatisch eine <xref:Microsoft.Office.Tools.Word.XMLNodes> -Steuerelement zum Dokument.  
  
 Informationen zum Zuordnen von XML-Schemaelemente nicht wiederholten finden Sie unter [wie: Hinzufügen von XMLNode-Steuerelementen zu Word-Dokumenten](../vsto/how-to-add-xmlnode-controls-to-word-documents.md).  
  
> [!NOTE]  
>  Die <xref:Microsoft.Office.Tools.Word.XMLNodes> Steuerelement ist nicht verfügbar, von der **Toolbox** oder **Datenquellen** Fenster noch programmgesteuert erstellt werden kann.  
  
 [!INCLUDE[note_settings_general](../sharepoint/includes/note-settings-general-md.md)]  
  
### <a name="to-add-an-xmlnodes-control-to-a-document"></a>Hinzufügen von XMLNodes-Steuerelement zu einem Dokument  
  
1.  Klicken Sie in das Dokument im Designer von Visual Studio, klicken Sie im Menüband auf die **Developer** Registerkarte.  
  
    > [!NOTE]  
    >  Wenn die Registerkarte **Entwickler** nicht sichtbar ist, müssen Sie diese zuerst anzeigen. Weitere Informationen finden Sie unter [Gewusst wie: Anzeigen der Registerkarte "Entwickler" auf der Multifunktionsleiste](../vsto/how-to-show-the-developer-tab-on-the-ribbon.md).  
  
2.  In der **XML** zu gruppieren, klicken Sie auf **Schema**.  
  
     Die **Vorlagen und Add-Ins** Dialogfeld wird geöffnet.  
  
3.  Klicken Sie auf die **XML-Schema** Registerkarte.  
  
4.  Klicken Sie auf **Schema hinzufügen**.  
  
     Die **Schema hinzufügen** Dialogfeld wird geöffnet.  
  
5.  Wählen Sie ein XML-Schema, das sich wiederholende Schemaelemente und klicken Sie auf enthält **öffnen**.  
  
     Die **Schemaeinstellungen** Dialogfeld wird angezeigt.  
  
6.  Weisen Sie einen Alias ein, oder klicken Sie auf **OK** das Schema ohne Alias hinzufügen.  
  
     Das Schema wird hinzugefügt, um die **Schema hinzufügen** (Dialogfeld).  
  
7.  In der **Schema hinzufügen** (Dialogfeld), klicken Sie auf **OK**.  
  
     Die **XML-Struktur** Aufgabe wird geöffnet.  
  
8.  Klicken Sie auf der sich wiederholendes Schemaelement auf die **XML-Struktur** Aufgabenbereich, um sie dem Dokument hinzuzufügen.  
  
     Ein <xref:Microsoft.Office.Tools.Word.XMLNodes> Steuerelement erstellt und dem Projekt hinzugefügt.  
  
## <a name="see-also"></a>Siehe auch  
 [XMLNodes-Steuerelement](../vsto/xmlnodes-control.md)   
 [Automatisieren von Word mithilfe von erweiterten Objekten](../vsto/automating-word-by-using-extended-objects.md)   
 [Übersicht über Hostelemente und Hoststeuerelemente](../vsto/host-items-and-host-controls-overview.md)   
 [Programmgesteuerte Einschränkungen von Hostelementen und Hoststeuerelementen](../vsto/programmatic-limitations-of-host-items-and-host-controls.md)  
  
  