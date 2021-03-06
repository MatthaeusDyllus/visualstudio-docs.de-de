---
title: Bookmark-Steuerelement
ms.date: 02/02/2017
ms.technology: office-development
ms.prod: visual-studio-dev15
ms.topic: conceptual
f1_keywords:
- VST.Toolbox.Bookmark
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- bookmarks, controlling
- Bookmark control, data binding
- Bookmark control, events
- Bookmark control
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: 60ab9db37f3ed41de4afcdecbf2c9e83ffb5c2f6
ms.sourcegitcommit: 209c2c068ff0975994ed892b62aa9b834a7f6077
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/17/2018
---
# <a name="bookmark-control"></a>Bookmark-Steuerelement
  Das <xref:Microsoft.Office.Tools.Word.Bookmark> -Steuerelement ist eine Textmarke, die über einen eindeutigen Namen verfügt, Ereignisse verfügbar macht und an Daten gebunden werden kann. Die Textmarke kann als Platzhalter verwendet werden, um ein Element oder eine Position in einem Microsoft Office Word-Dokument zu markieren. Das <xref:Microsoft.Office.Tools.Word.Bookmark> -Steuerelement ist eine Kombination aus einem <xref:Microsoft.Office.Interop.Word.Bookmark> - und einem <xref:Microsoft.Office.Interop.Word.Range> -Objekt.

 [!INCLUDE[appliesto_wdalldocapp](../vsto/includes/appliesto-wdalldocapp-md.md)]

 Sie können in Projekten auf Dokumentebene hinzufügen <xref:Microsoft.Office.Tools.Word.Bookmark> Steuerelemente im Dokument zur Entwurfszeit oder zur Laufzeit. Sie können in VSTO-Add-in-Projekten hinzufügen <xref:Microsoft.Office.Tools.Word.Bookmark> Steuerelementen zu einem beliebigen geöffneten Dokument zur Laufzeit. Weitere Informationen finden Sie unter [wie: Hinzufügen von Lesezeichen-Steuerelementen an Word-Dokumenten](../vsto/how-to-add-bookmark-controls-to-word-documents.md).

## <a name="bind-data-to-the-control"></a>Binden von Daten an das Steuerelement
 Ein <xref:Microsoft.Office.Tools.Word.Bookmark> -Steuerelement unterstützt die einfache Datenbindung. Die Textmarke sollte mithilfe der <xref:System.Windows.Forms.IBindableComponent.DataBindings%2A> -Eigenschaft an eine Datenquelle gebunden werden. Die Standardeigenschaft für die Datenbindung der Textmarke ist die <xref:Microsoft.Office.Tools.Word.Bookmark.Text%2A> -Eigenschaft.

 Wenn die Daten im gebundenen Dataset aktualisiert werden, die <xref:Microsoft.Office.Tools.Word.Bookmark> Steuerelement zeigt die Änderungen an.

 In Projekten auf Dokumentebene können Sie Daten auch an Textmarken binden, indem Sie das Fenster **Datenquellen** verwenden. Weitere Informationen finden Sie unter [wie: Auffüllen von Dokumenten mit Daten aus Objekten](../vsto/how-to-populate-documents-with-data-from-objects.md).

## <a name="formatting"></a>Formatierung
 Die auf <xref:Microsoft.Office.Interop.Word.Bookmark> anwendbare Formatierung kann auf ein <xref:Microsoft.Office.Tools.Word.Bookmark> -Steuerelement angewendet werden. Diese Formatierung schließt Schriftarten, Einzüge, Abstände, Nummerierung und Stile.

## <a name="assign-text-to-the-bookmark"></a>Weisen Sie diesem Text zur Textmarke
 Ein weiterer Unterschied zwischen einem <xref:Microsoft.Office.Interop.Word.Bookmark?displayProperty=nameWithType> Objekt und ein <xref:Microsoft.Office.Tools.Word.Bookmark?displayProperty=nameWithType> -Steuerelement ist das Verhalten beim Zuweisen von Text zur Textmarke. Wenn Sie eine leere Text zuweisen <xref:Microsoft.Office.Interop.Word.Bookmark?displayProperty=nameWithType>, wird der Text rechts neben der Textmarke angefügt und die Textmarke behält die Länge 0 (null). Jedoch, wenn Sie eine leere Text zuweisen <xref:Microsoft.Office.Tools.Word.Bookmark?displayProperty=nameWithType>, wird der Text in die Textmarke eingefügt und die Länge der Textmarke wird auf die Gesamtanzahl der eingefügten Zeichen erweitert.

 Die <xref:Microsoft.Office.Tools.Word.Bookmark?displayProperty=nameWithType> -Steuerelement verfügt über die <xref:Microsoft.Office.Tools.Word.Bookmark.Text?displayProperty=nameWithType> Eigenschaft. Diese Eigenschaft unterscheidet sich von der <xref:Microsoft.Office.Interop.Word.Range.Text?displayProperty=nameWithType> -Eigenschaft, die verfügbar ist die <xref:Microsoft.Office.Tools.Word.Bookmark.Range?displayProperty=nameWithType> Eigenschaft eine <xref:Microsoft.Office.Tools.Word.Bookmark?displayProperty=nameWithType> -Steuerelement, oder die <xref:Microsoft.Office.Interop.Word.Bookmark.Range?displayProperty=nameWithType> Eigenschaft ein <xref:Microsoft.Office.Interop.Word.Bookmark?displayProperty=nameWithType> Objekt.

|Text-Eigenschaft|Beschreibung|
|-------------------|-----------------|
|<xref:Microsoft.Office.Tools.Word.Bookmark.Text?displayProperty=nameWithType>|Verwenden Sie diese Eigenschaft zum Anzeigen von Text in einer Textmarke, und belassen Sie die Textmarke im Dokument. Durch das Zuweisen von Text zur Textmarke wird der Textmarkenbereich erweitert und die Textmarke nicht gelöscht.<br /><br /> `Bookmark1.Text = "Hello world"` fügt z. B. den Text in die Textmarken ein, und die Textmarke bleibt intakt.|
|<xref:Microsoft.Office.Interop.Word.Range.Text?displayProperty=nameWithType>|Verwenden Sie diese Eigenschaft, um Text an der Position der Textmarke anzuzeigen und die Textmarke automatisch zu löschen. `Bookmark1.Range.Text = "Hello world"` fügt z. B. den Text in die Textmarke ein, und die Textmarke wird gelöscht.|

## <a name="rename-the-control-at-design-time"></a>Benennen Sie das Steuerelement zur Entwurfszeit
 Wenn Sie in Projekten auf Dokumentebene ein <xref:Microsoft.Office.Tools.Word.Bookmark> -Steuerelement aus der **Toolbox** in Ihr Dokument ziehen, generiert Visual Studio automatisch einen Namen für das Steuerelement. Sie können den Namen des Steuerelemente im Fenster **Eigenschaften** ändern.

## <a name="overlapping-controls"></a>Überlappende Steuerelemente
 Bookmark-Steuerelemente können einander überlappen. Derselbe Text kann von mehreren Textmarken gemeinsam genutzt werden. Wenn Sie eines der überlappenden Textmarken neuen Text zuweisen, sie nur den neuen Text enthält, und die Textmarken überlappen nicht mehr. Die andere Textmarke enthält jetzt nur den Text, der von der ursprünglich überlappenden Textmarke gemeinsam genutzt wurde nicht an.

 In der folgenden Tabelle wird gezeigt, wie der Satz „This is sample text.“ wird von zwei überlappenden Textmarken gemeinsam genutzt:

|Textmarke|Text|
|--------------|----------|
|Überlappende Textmarken|[this is {sample] text.}|
|Bookmark1|This is sample|
|Bookmark2|sample text.|

 Wenn Sie den neuen Text „This is replacement." zu Bookmark1 zuweisen, überlappen die Textmarken überlappen nicht, und Bookmark2 behält nur den Text, der ursprünglich Teil von Bookmark1 war nicht.

|Textmarke|Text|
|--------------|----------|
|Zwei separate Textmarken|[this is replacement]{ text.}|
|Bookmark1|This is replacement|
|Bookmark2|text.|

Die innere Textmarke wird nicht gelöscht, wenn Sie den Text eines Lesezeichens zu ändern, die einer anderen Textmarke enthält. Die innere Textmarke wird zu einer leeren Textmarke und an das Ende der äußeren Textmarke verschoben.

In der folgenden Tabelle wird gezeigt, wie der Satz „This is sample text.“ wird von einer Textmarke gemeinsam genutzt, die in einer anderen Textmarke enthalten ist:

|Textmarke|Text|
|--------------|----------|
|Überlappende Textmarken|[this is {sample} text.]|
|Bookmark1|This is sample text.|
|Bookmark2|Beispiel|

 Wenn Sie den neuen Text „This is replacement." zu Bookmark1 zuweisen, überlappen sich die Textmarken nicht mehr, und Bookmark2 wird zu einer leeren Textmarke, die sich am Ende von Bookmark1 befindet.

|Textmarke|Text|
|--------------|----------|
|Zwei separate Textmarken|[Dies ist ein Ersatz.]{}|
|Bookmark1|This is replacement.|
|Bookmark2|*\<leere >*|

## <a name="events"></a>Ereignisse

Die folgenden Ereignisse sind für das <xref:Microsoft.Office.Tools.Word.Bookmark> -Steuerelement verfügbar:

-   <xref:Microsoft.Office.Tools.Word.Bookmark.BeforeDoubleClick>

-   <xref:Microsoft.Office.Tools.Word.Bookmark.BeforeRightClick>

-   <xref:Microsoft.Office.Tools.Word.Bookmark.BindingContextChanged>

-   <xref:Microsoft.Office.Tools.Word.Bookmark.Deselected>

-   <xref:System.ComponentModel.IComponent.Disposed>

-   <xref:Microsoft.Office.Tools.Word.Bookmark.Selected>

-   <xref:Microsoft.Office.Tools.Word.Bookmark.SelectionChange>

## <a name="see-also"></a>Siehe auch

- [Automatisieren von Word mithilfe von erweiterten Objekten](../vsto/automating-word-by-using-extended-objects.md)
- [Vorgehensweise: Hinzufügen von Lesezeichen-Steuerelementen zu Word-Dokumenten](../vsto/how-to-add-bookmark-controls-to-word-documents.md)
- [Exemplarische Vorgehensweise: Erstellen von Kontextmenüs für Lesezeichen](../vsto/walkthrough-creating-shortcut-menus-for-bookmarks.md)
- [Binden von Daten an Steuerelemente in Office-Projektmappen](../vsto/binding-data-to-controls-in-office-solutions.md)
- [Programmgesteuerte Einschränkungen von Hostelementen und Hoststeuerelementen](../vsto/programmatic-limitations-of-host-items-and-host-controls.md)