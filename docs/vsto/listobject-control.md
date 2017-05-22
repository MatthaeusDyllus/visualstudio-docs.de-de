---
title: "ListObject-Steuerelement"
ms.custom: ""
ms.date: "02/02/2017"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "office-development"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "VST.Toolbox.List"
dev_langs: 
  - "VB"
  - "CSharp"
helpviewer_keywords: 
  - "Listen, Ereignisse"
  - "ListObject-Steuerelement"
  - "ListObject-Steuerelement, Ereignisse"
  - "ListObject-Steuerelement, Datenbindung"
  - "ListObject-Steuerelement, Verbessern der Leistung bei der Datenbindung"
ms.assetid: 2bdecbf0-2a0f-48de-a544-dca12bb4a9a3
caps.latest.revision: 70
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
caps.handback.revision: 69
---
# ListObject-Steuerelement
  Das <xref:Microsoft.Office.Tools.Excel.ListObject>\-Steuerelement ist eine Liste, die Ereignisse verfügbar macht und an Daten gebunden werden kann. Beim Hinzufügen einer Liste zu einem Arbeitsblatt erstellt Visual Studio ein <xref:Microsoft.Office.Tools.Excel.ListObject>\-Steuerelement, für das Sie direkt programmieren können, ohne das Objektmodell von Microsoft Office Excel zu durchlaufen.  
  
 [!INCLUDE[appliesto_xlalldocapp](../vsto/includes/appliesto-xlalldocapp-md.md)]  
  
## Erstellen des Steuerelements  
 In Projekten auf Dokumentebene können Sie einem Arbeitsblatt zur Entwurfszeit oder Laufzeit <xref:Microsoft.Office.Tools.Excel.ListObject>\-Steuerelemente hinzufügen. In VSTO\-Add\-in\-Projekten können Sie Arbeitsblättern <xref:Microsoft.Office.Tools.Excel.ListObject>\-Steuerelemente nur zur Laufzeit hinzufügen. Weitere Informationen finden Sie unter [Gewusst wie: Hinzufügen von ListObject-Steuerelementen zu Arbeitsblättern](../vsto/how-to-add-listobject-controls-to-worksheets.md).  
  
> [!NOTE]  
>  Standardmäßig werden dynamisch erstellte Listenobjekte im Arbeitsblatt nicht dauerhaft als Hoststeuerelemente gespeichert, wenn das Arbeitsblatt geschlossen wird. Weitere Informationen finden Sie unter [Hinzufügen von Steuerelementen zu Office-Dokumenten zur Laufzeit](../vsto/adding-controls-to-office-documents-at-run-time.md).  
  
## Binden von Daten an das Steuerelement  
 Ein <xref:Microsoft.Office.Tools.Excel.ListObject>\-Steuerelement unterstützt die einfache und komplexe Datenbindung. Das <xref:Microsoft.Office.Tools.Excel.ListObject>\-Steuerelement kann zur Entwurfszeit mit der <xref:Microsoft.Office.Tools.Excel.ListObject.DataSource%2A>\-Eigenschaft und der <xref:Microsoft.Office.Tools.Excel.ListObject.DataMember%2A>\-Eigenschaft oder zur Laufzeit mit der <xref:Microsoft.Office.Tools.Excel.ListObject.SetDataBinding%2A>\-Methode an eine Datenquelle gebunden werden.  
  
> [!NOTE]  
>  <xref:Microsoft.Office.Tools.Excel.ListObject> wird bei der Bindung an eine Datenquelle wie <xref:System.Data.DataTable>, die Ereignisse auslöst, wenn die Daten geändert werden, automatisch aktualisiert. Wenn Sie <xref:Microsoft.Office.Tools.Excel.ListObject> an eine Datenquelle binden, die bei einer Datenänderung keine Ereignisse auslöst, müssen Sie die <xref:Microsoft.Office.Tools.Excel.ListObject.RefreshDataRow%2A>\-Methode oder <xref:Microsoft.Office.Tools.Excel.ListObject.RefreshDataRows%2A>\-Methode aufrufen, um <xref:Microsoft.Office.Tools.Excel.ListObject> zu aktualisieren.  
  
 Wenn Sie <xref:Microsoft.Office.Tools.Excel.ListObject> einer Arbeitsblattzelle hinzufügen, indem Sie der Zelle ein sich wiederholendes Schemaelement zuordnen, ordnet Visual Studio <xref:Microsoft.Office.Tools.Excel.ListObject> automatisch dem generierten DataSet zu. Allerdings wird <xref:Microsoft.Office.Tools.Excel.ListObject> nicht automatisch an die Daten gebunden. Sie können dafür sorgen, dass <xref:Microsoft.Office.Tools.Excel.ListObject> in einem Projekt auf Dokumentebene zur Entwurfszeit oder zur Laufzeit an das DataSet gebunden wird. Sie können <xref:Microsoft.Office.Tools.Excel.ListObject> zur Laufzeit in einem VSTO\-Add\-In programmgesteuert an das DataSet binden.  
  
 Da die Daten von <xref:Microsoft.Office.Tools.Excel.ListObject> getrennt sind, sollten Sie Daten über das gebundene DataSet und nicht direkt über <xref:Microsoft.Office.Tools.Excel.ListObject> hinzufügen und entfernen. Wenn die Daten im gebundenen DataSet auf beliebige Weise aktualisiert werden, spiegelt das <xref:Microsoft.Office.Tools.Excel.ListObject>\-Steuerelement automatisch die Änderungen wider. Weitere Informationen finden Sie unter [Binden von Daten an Steuerelemente in Office-Projektmappen](../vsto/binding-data-to-controls-in-office-solutions.md).  
  
 Sie können ein <xref:Microsoft.Office.Tools.Excel.ListObject>\-Steuerelement schnell füllen, indem Sie <xref:Microsoft.Office.Tools.Excel.ListObject> an eine Datenquelle binden. Wenn Sie die Daten in einem datengebundenen <xref:Microsoft.Office.Tools.Excel.ListObject> bearbeiten, werden die Änderungen auch automatisch in der Datenquelle vorgenommen. Wenn Sie <xref:Microsoft.Office.Tools.Excel.ListObject> füllen und dann dem Benutzer das Ändern der Daten in <xref:Microsoft.Office.Tools.Excel.ListObject> ermöglichen möchten, ohne die Datenquelle zu ändern, können Sie die <xref:Microsoft.Office.Tools.Excel.ListObject.Disconnect%2A>\-Methode verwenden, um <xref:Microsoft.Office.Tools.Excel.ListObject> von der Datenquelle zu trennen. Weitere Informationen finden Sie unter [Gewusst wie: Füllen eines ListObject-Steuerelements mit Daten](../vsto/how-to-fill-listobject-controls-with-data.md).  
  
> [!NOTE]  
>  Die Datenbindung wird bei überlappenden <xref:Microsoft.Office.Tools.Excel.ListObject>\-Steuerelementen nicht unterstützt.  
  
### Verbessern der Leistung von ListObject\-Steuerelementen  
 Das Einlesen einer XML\-Datei in ein datengebundenes <xref:Microsoft.Office.Tools.Excel.ListObject>\-Steuerelement ist normalerweise langsamer, wenn Sie das Steuerelement zuerst binden und dann <xref:System.Data.DataSet.ReadXml%2A> zum Füllen des DataSets aufrufen. Rufen Sie für eine bessere Leistung <xref:System.Data.DataSet.ReadXml%2A> auf, bevor Sie das Steuerelement binden.  
  
### Trennen von ListObject\-Steuerelementen von der Datenquelle  
 Nachdem Sie ein <xref:Microsoft.Office.Tools.Excel.ListObject>\-Steuerelement mit Daten gefüllt haben, indem es an eine Datenquelle gebunden wurde, können sie es trennen, damit Änderungen an den Daten im Listenobjekt keine Auswirkungen auf die Datenquelle haben. Weitere Informationen finden Sie unter [Gewusst wie: Füllen eines ListObject-Steuerelements mit Daten](../vsto/how-to-fill-listobject-controls-with-data.md).  
  
### Wiederherstellen der Spalten\- und Zeilenreihenfolge  
 Beim Binden von Daten an ein <xref:Microsoft.Office.Tools.Excel.ListObject>\-Steuerelement, das einem Dokument zur Entwurfszeit hinzugefügt wurde, protokolliert Visual Studio die Spalten\- und Zeilenreihenfolge bei jedem Speichern der Arbeitsmappe. Wenn ein Benutzer die <xref:Microsoft.Office.Tools.Excel.ListObject>\-Spalten oder \-Zeilen zur Laufzeit verschiebt, wird die neue Reihenfolge beim nächsten Öffnen der Arbeitsmappe beibehalten und das <xref:Microsoft.Office.Tools.Excel.ListObject>\-Steuerelement erneut an die Datenquelle gebunden.  
  
 Wenn Sie die ursprüngliche Spalten\- und Zeilenreihenfolge von <xref:Microsoft.Office.Tools.Excel.ListObject> wiederherstellen möchten, können Sie die <xref:Microsoft.Office.Tools.Excel.ListObject.ResetPersistedBindingInformation%2A>\-Methode aufrufen. Diese Methode entfernt die benutzerdefinierten Dokumenteigenschaften im Zusammenhang mit der Spalten\- und Zeilenreihenfolge des angegebenen <xref:Microsoft.Office.Tools.Excel.ListObject>. Rufen Sie diese Methode aus dem <xref:Microsoft.Office.Tools.Excel.Workbook.Shutdown>\-Ereignis der Arbeitsmappe auf, wenn Sie die Spalten\- und Zeilenreihenfolge von <xref:Microsoft.Office.Tools.Excel.ListObject> nicht beibehalten möchten.  
  
## Formatierung  
 Die auf <xref:Microsoft.Office.Interop.Excel.ListObject> anwendbare Formatierung kann auf ein <xref:Microsoft.Office.Tools.Excel.ListObject>\-Steuerelement angewendet werden. Dies umfasst, Rahmen, Schriftarten, Zahlenformate und Stile. Endbenutzer können Spalten in einem datengebundenen <xref:Microsoft.Office.Tools.Excel.ListObject> neu anordnen, und diese Änderungen werden mit dem Dokument beibehalten, vorausgesetzt, <xref:Microsoft.Office.Tools.Excel.ListObject> wurde dem Dokument zur Entwurfszeit hinzugefügt. Wenn das Dokument das nächste Mal geöffnet wird, das Listenobjekt an die gleiche Datenquelle gebunden, während die Spaltenreihenfolge jedoch die Benutzeränderungen widerspiegelt.  
  
## Hinzufügen und Entfernen von Spalten zur Laufzeit  
 Sie können Spalten in einem datengebundenen <xref:Microsoft.Office.Tools.Excel.ListObject>\-Steuerelement zur Laufzeit nicht manuell hinzufügen oder entfernen. Wenn ein Endbenutzer versucht, eine Spalte zu löschen, wird sie sofort wiederhergestellt, und alle hinzugefügten Spalten werden entfernt. Daher ist es wichtig, Code zu schreiben, der Benutzern erläutert, warum sie diese Aktionen nicht für ein <xref:Microsoft.Office.Tools.Excel.ListObject> ausführen können, das an Daten gebunden ist. Visual Studio bietet verschiedene Ereignisse für <xref:Microsoft.Office.Tools.Excel.ListObject>, die sich auf die Datenbindung beziehen. Beispielsweise können Sie das <xref:Microsoft.Office.Tools.Excel.ListObject.OriginalDataRestored>\-Ereignis verwenden, um Benutzer zu warnen, dass Daten, die sie löschen wollten, nicht gelöscht werden können und wiederhergestellt wurden.  
  
## Hinzufügen und Entfernen von Zeilen zur Laufzeit  
 Sie können Zeilen in einem datengebundenen <xref:Microsoft.Office.Tools.Excel.ListObject>\-Steuerelement manuell hinzufügen und entfernen, vorausgesetzt, die Datenquelle lässt das Hinzufügen neuer Zeilen zu und ist nicht schreibgeschützt. Sie können Code für Ereignisse wie <xref:Microsoft.Office.Tools.Excel.ListObject.BeforeAddDataBoundRow> schreiben, um die Daten zu überprüfen. Weitere Informationen finden Sie unter [Gewusst wie: Überprüfen der Daten, wenn einem ListObject-Steuerelement eine neue Zeile hinzugefügt wird](../vsto/how-to-validate-data-when-a-new-row-is-added-to-a-listobject-control.md).  
  
 Manchmal verursacht die Beziehung des Listenobjekts zur Datenquelle routinemäßige Fehler. Sie können z. B. die Spalten zuordnen, die in <xref:Microsoft.Office.Tools.Excel.ListObject> enthalten sein sollen. Wenn Sie Spalten auslassen, die eingeschränkt sind, z. B. ein Feld, das keine NULL\-Werte akzeptiert, wird bei jedem Erstellen einer Zeile ein Fehler ausgelöst. Sie können Code schreiben, um die fehlenden Werte in einem Ereignishandler für das <xref:Microsoft.Office.Tools.Excel.ListObject.ErrorAddDataBoundRow>\-Ereignis hinzuzufügen.  
  
## Umbenennen von ListObject\-Steuerelementen in Excel  
 Excel bietet Benutzern die Möglichkeit, den Namen von Excel\-Tabellen mithilfe der Registerkarte **Entwurf** zur Laufzeit zu ändern. Dieses Feature wird vom <xref:Microsoft.Office.Tools.Excel.ListObject>\-Steuerelement jedoch nicht unterstützt. Wenn ein Benutzer versucht, eine Excel\-Tabelle umzubenennen, die <xref:Microsoft.Office.Tools.Excel.ListObject> entspricht, wird der Name der Excel\-Tabelle beim Speichern der Arbeitsmappe automatisch auf den ursprünglichen Namen zurückgesetzt.  
  
## Ereignisse  
 Die folgenden Ereignisse sind für das <xref:Microsoft.Office.Tools.Excel.ListObject>\-Steuerelement verfügbar:  
  
-   <xref:Microsoft.Office.Tools.Excel.ListObject.BeforeAddDataBoundRow>  
  
-   <xref:Microsoft.Office.Tools.Excel.ListObject.BeforeDoubleClick>  
  
-   <xref:Microsoft.Office.Tools.Excel.ListObject.BeforeRightClick>  
  
-   <xref:Microsoft.Office.Tools.Excel.ListObject.BindingContextChanged>  
  
-   <xref:Microsoft.Office.Tools.Excel.ListObject.Change>  
  
-   <xref:Microsoft.Office.Tools.Excel.ListObject.DataBindingFailure>  
  
-   <xref:Microsoft.Office.Tools.Excel.ListObject.DataMemberChanged>  
  
-   <xref:Microsoft.Office.Tools.Excel.ListObject.DataSourceChanged>  
  
-   <xref:Microsoft.Office.Tools.Excel.ListObject.Deselected>  
  
-   <xref:Microsoft.Office.Tools.Excel.ListObject.ErrorAddDataBoundRow>  
  
-   <xref:Microsoft.Office.Tools.Excel.ListObject.OriginalDataRestored>  
  
-   <xref:Microsoft.Office.Tools.Excel.ListObject.Selected>  
  
-   <xref:Microsoft.Office.Tools.Excel.ListObject.SelectedIndexChanged>  
  
-   <xref:Microsoft.Office.Tools.Excel.ListObject.SelectionChange>  
  
## Siehe auch  
 [Automatisieren von Excel mithilfe von erweiterten Objekten](../vsto/automating-excel-by-using-extended-objects.md)   
 [Gewusst wie: Hinzufügen von ListObject-Steuerelementen zu Arbeitsblättern](../vsto/how-to-add-listobject-controls-to-worksheets.md)   
 [Gewusst wie: Ändern der Größe von ListObject-Steuerelementen](../vsto/how-to-resize-listobject-controls.md)   
 [Gewusst wie: Überprüfen der Daten, wenn einem ListObject-Steuerelement eine neue Zeile hinzugefügt wird](../vsto/how-to-validate-data-when-a-new-row-is-added-to-a-listobject-control.md)   
 [Gewusst wie: Zuordnung von ListObject-Spalten zu Daten](../vsto/how-to-map-listobject-columns-to-data.md)   
 [Gewusst wie: Füllen eines ListObject-Steuerelements mit Daten](../vsto/how-to-fill-listobject-controls-with-data.md)   
 [Beispiele und exemplarische Vorgehensweisen für die Programmierung mit Office](../vsto/office-development-samples-and-walkthroughs.md)   
 [Binden von Daten an Steuerelemente in Office-Projektmappen](../vsto/binding-data-to-controls-in-office-solutions.md)   
 [Erweitern von Word-Dokumenten und Excel-Arbeitsmappen in VSTO-Add-Ins zur Laufzeit](../vsto/extending-word-documents-and-excel-workbooks-in-vsto-add-ins-at-run-time.md)   
 [Steuerelemente für Office-Dokumente](../vsto/controls-on-office-documents.md)   
 [Hinzufügen von Steuerelementen zu Office-Dokumenten zur Laufzeit](../vsto/adding-controls-to-office-documents-at-run-time.md)   
 [Gewusst wie: Auffüllen von Arbeitsblättern mit Daten aus einer Datenbank](../vsto/how-to-populate-worksheets-with-data-from-a-database.md)   
 [Programmgesteuerte Einschränkungen von Hostelementen und Hoststeuerelementen](../vsto/programmatic-limitations-of-host-items-and-host-controls.md)  
  
  