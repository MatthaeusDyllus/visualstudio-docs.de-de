---
title: IDE-Konstanten | Microsoft Docs
ms.date: 03/22/2018
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- IDE, errors
- logical views
- errors [Visual Studio], IDE
- UI context constants
- constants, Visual Studio IDE
- IDE, constants
- physical views
ms.assetid: 5030e70a-241d-474a-ba8c-e3b1cf947ff0
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: e9c7e870b02dbe5a903ca8195954ffd5a8f63549
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/16/2018
---
# <a name="ide-constants"></a>IDE-Konstanten

Die <xref:Microsoft.VisualStudio.VSConstants> -Klasse enthält Konstanten, die für die integrierte Entwicklungsumgebung (IDE) spezifisch sind und, die zuvor nur in den Headerdateien definiert wurden.

## <a name="logical-and-physical-views"></a>Logische und physische Ansichten

|Wert|Beschreibung|
|-----------|-----------------|
|<xref:Microsoft.VisualStudio.VSConstants.LOGVIEWID.Code_guid>|<xref:Microsoft.VisualStudio.VSConstants.GUID_VSStandardCommandSet97> `cmdidOpenWith` Handler sollte diesen Wert zum Übergeben der <xref:Microsoft.VisualStudio.Shell.Interop.IVsUIShellOpenDocument.OpenStandardEditor%2A> Methode zum Abrufen der **Öffnen mit** (Dialogfeld), in diesem Fall auf mögliche Code Ansichten.|
|<xref:Microsoft.VisualStudio.VSConstants.LOGVIEWID.Debugging_guid>|<xref:Microsoft.VisualStudio.VSConstants.GUID_VSStandardCommandSet97> `cmdidOpenWith` Handler übergeben Sie diesen Wert auf die <xref:Microsoft.VisualStudio.Shell.Interop.IVsUIShellOpenDocument.OpenStandardEditor%2A> Methode zum Abrufen der **Öffnen mit** (Dialogfeld), die in diesem Fall mit möglichen aufgefüllt <xref:Microsoft.VisualStudio.VSConstants.LOGVIEWID.Debugging_guid> Debuggen Ansichten, die die gleiche Ansicht als zuordnen <xref:Microsoft.VisualStudio.VSConstants.LOGVIEWID.Code_guid>.|
|<xref:Microsoft.VisualStudio.VSConstants.LOGVIEWID.Designer_guid>|<xref:Microsoft.VisualStudio.VSConstants.GUID_VSStandardCommandSet97> `cmdidOpenWith` Handler übergeben Sie diesen Wert auf die <xref:Microsoft.VisualStudio.Shell.Interop.IVsUIShellOpenDocument.OpenStandardEditor%2A> Methode zum Abrufen der **Öffnen mit** (Dialogfeld), in diesem Fall auf **Formular anzeigen** Designeransichten.|
|<xref:Microsoft.VisualStudio.VSConstants.LOGVIEWID.Primary_guid>|<xref:Microsoft.VisualStudio.VSConstants.GUID_VSStandardCommandSet97> `cmdidOpenWith` Handler übergeben Sie diesen Wert auf die <xref:Microsoft.VisualStudio.Shell.Interop.IVsUIShellOpenDocument.OpenStandardEditor%2A> Methode zum Abrufen der **Öffnen mit** (Dialogfeld), in diesem Fall die Standard/primäre Server Überblick über die Editor-Factory.|
|<xref:Microsoft.VisualStudio.VSConstants.LOGVIEWID.TextView_guid>|<xref:Microsoft.VisualStudio.VSConstants.GUID_VSStandardCommandSet97> `cmdidOpenWith` Handler übergeben Sie diesen Wert auf die <xref:Microsoft.VisualStudio.Shell.Interop.IVsUIShellOpenDocument.OpenStandardEditor%2A> Methode zum Abrufen der **Öffnen mit** im Dialogfeld, um ein Dokument oder -Text-Editor-Ansicht.|
|<xref:Microsoft.VisualStudio.VSConstants.LOGVIEWID.UserChooseView_guid>|<xref:Microsoft.VisualStudio.VSConstants.GUID_VSStandardCommandSet97> `cmdidOpenWith` Handler übergeben Sie diesen Wert auf die <xref:Microsoft.VisualStudio.Shell.Interop.IVsUIShellOpenDocument.OpenStandardEditor%2A> Methode, die den Benutzer auffordert, wählen die benutzerdefinierte Sicht zu verwenden.|

## <a name="editor-factory-flags"></a>Editor-Factory-Flags

|Wert|Beschreibung|
|-----------|-----------------|
|[CEF.CloneFile](<xref:Microsoft.VisualStudio.VSConstants.CEF#Microsoft_VisualStudio_VSConstants_CEF_CloneFile>)|Ein Flag veraltet kombiniert bitweiser als der erste Parameter der <xref:Microsoft.VisualStudio.Package.EditorFactory.CreateEditorInstance%2A> Methode.|
|[CEF.OpenAsNew](<xref:Microsoft.VisualStudio.VSConstants.CEF#Microsoft_VisualStudio_VSConstants_CEF_OpenAsNew>)|Bitweiser als erster Parameter des kombiniert die <xref:Microsoft.VisualStudio.Package.EditorFactory.CreateEditorInstance%2A>, Methode, hiermit die Editor-Factory sollten die erforderlichen Korrekturen ausführen.|
|[CEF.OpenFile](<xref:Microsoft.VisualStudio.VSConstants.CEF#Microsoft_VisualStudio_VSConstants_CEF_OpenFile>)|Bitweiser als erster Parameter des kombiniert die <xref:Microsoft.VisualStudio.Package.EditorFactory.CreateEditorInstance%2A> Methode dieses Flag schließen sich gegenseitig aus exclusive von [CEF. CloneFile](<xref:Microsoft.VisualStudio.VSConstants.CEF#Microsoft_VisualStudio_VSConstants_CEF_CloneFile>).|
|[CEF.Silent](<xref:Microsoft.VisualStudio.VSConstants.CEF#Microsoft_VisualStudio_VSConstants_CEF_Silent>)|Bitweiser als erster Parameter des kombiniert die <xref:Microsoft.VisualStudio.Package.EditorFactory.CreateEditorInstance%2A> -Methode, hiermit die Editor-Factory sollten Editor erstellen, ohne eine Benutzeroberfläche (UI) anzuzeigen.|

## <a name="visual-studio-errors"></a>Visual Studio-Fehler

|Wert|Beschreibung|
|-----------|-----------------|
|<xref:Microsoft.VisualStudio.VSConstants.VS_E_BUSY>|Eine Konstante, die von Schnittstellen zurückgegeben werden, um asynchrones Verhalten bei dem betreffenden Objekt bereits gebucht|
|<xref:Microsoft.VisualStudio.VSConstants.VS_E_INCOMPATIBLEDOCDATA>|Ein Fehler HRESULT, der für spezifischen [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] für "Dokumentdaten nicht kompatibel".|
|<xref:Microsoft.VisualStudio.VSConstants.VS_E_PACKAGENOTLOADED>|Ein Fehler HRESULT, der für spezifischen [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] und aufzeigenden "-Paket nicht geladen."|
|<xref:Microsoft.VisualStudio.VSConstants.VS_E_PROJECTALREADYEXISTS>|Ein Fehler HRESULT, das speziell für [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] und angibt, dass die "Projekt bereits vorhanden ist."|
|<xref:Microsoft.VisualStudio.VSConstants.VS_E_PROJECTMIGRATIONFAILED>|Ein Fehler HRESULT, der für spezifischen [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] und der Wert, der angibt, "Fehler bei Projektkonfiguration."|
|<xref:Microsoft.VisualStudio.VSConstants.VS_E_PROJECTNOTLOADED>|Ein Fehler HRESULT, der für spezifischen [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] und aufzeigenden "-Projekt nicht geladen."|
|<xref:Microsoft.VisualStudio.VSConstants.VS_E_SOLUTIONALREADYOPEN>|Ein Fehler HRESULT, der für spezifischen [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] und aufzeigenden "Projektmappe bereits geöffnet."|
|<xref:Microsoft.VisualStudio.VSConstants.VS_E_SOLUTIONNOTOPEN>|Ein Fehler HRESULT, der für spezifischen [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] und aufzeigenden "Lösung nicht öffnen."|
|<xref:Microsoft.VisualStudio.VSConstants.VS_E_SPECIFYING_OUTPUT_UNSUPPORTED>|Vom Build-Schnittstellen, die für die Angabe eines Arrays von Parametern zurückgegebenen der <xref:Microsoft.VisualStudio.Shell.Interop.IVsOutput> -Schnittstelle, aber die Implementierung der Methode nur auf alle Ausgaben anwenden kann.|
|<xref:Microsoft.VisualStudio.VSConstants.VS_E_UNSUPPORTEDFORMAT>|Die <xref:Microsoft.VisualStudio.Package.EditorFactory.CreateEditorInstance%2A> Methode gibt diesen Wert zurück, wenn das Dokument ein Format hat, die im Editor nicht geöffnet werden kann.|
|<xref:Microsoft.VisualStudio.VSConstants.VS_E_WIZARDBACKBUTTONPRESS>|Ein HRESULT-Wert, der angibt, dass der Benutzer die Schaltfläche "zurück", in erreicht eine [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] Assistenten.|

## <a name="visual-studio-constants"></a>Visual Studio-Konstanten

|Wert|Beschreibung|
|-----------|-----------------|
|<xref:Microsoft.VisualStudio.VSConstants.VS_S_PROJECTFORWARDED>|Ein Fehler HRESULT, der für spezifischen [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] und aufzeigenden "Weitergeleitet Project".|
|<xref:Microsoft.VisualStudio.VSConstants.VS_S_TBXMARKER>|Eine Konstante, die für spezifische [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] für ein "Toolbox"Marker.|
|<xref:Microsoft.VisualStudio.VSConstants.VSM_ENTERMODAL>|Eine Konstante, die speziell für [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] für das Senden einer Benachrichtigung über die <xref:Microsoft.VisualStudio.Shell.Interop.IVsBroadcastMessageEvents.OnBroadcastMessage%2A> Methode, die den Anfang des Modalität angibt.|
|<xref:Microsoft.VisualStudio.VSConstants.VSM_EXITMODAL>|Eine Konstante, die für spezifische [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] für das Senden einer Benachrichtigung über die <xref:Microsoft.VisualStudio.Shell.Interop.IVsBroadcastMessageEvents.OnBroadcastMessage%2A> Methode, die das Ende des Modalität angibt.|
|<xref:Microsoft.VisualStudio.VSConstants.VSM_TOOLBARMETRICSCHANGE>|Eine Konstante, die für spezifische [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] für das Senden einer Benachrichtigung über die <xref:Microsoft.VisualStudio.Shell.Interop.IVsBroadcastMessageEvents.OnBroadcastMessage%2A> Methode, der angibt, dass der Befehlsleiste Metriken geändert wurden.|
|<xref:Microsoft.VisualStudio.VSConstants.VSCOOKIE_NIL>|Eine Konstante, die für spezifischen [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] , der angibt, ob ein Cookie nicht festgelegt wurden.|
|[VSITEMID.Nil](<xref:Microsoft.VisualStudio.VSConstants.VSITEMID#Microsoft_VisualStudio_VSConstants_VSITEMID_Nil>)|Ein [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] Element-ID, die die Abwesenheit eines Projektelements darstellt. Dieser Wert wird verwendet, wenn keine aktuelle Auswahl vorhanden ist.|
|[VSITEMID.Root](<xref:Microsoft.VisualStudio.VSConstants.VSITEMID#Microsoft_VisualStudio_VSConstants_VSITEMID_Root>)|Ein [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] Element-ID, die der Stamm einer Projekthierarchie darstellt, abgerufen und wird verwendet, um die gesamte Hierarchie, im Gegensatz zu einem einzelnen Element identifizieren.|
|[VSITEMID. Auswahl](<xref:Microsoft.VisualStudio.VSConstants.VSITEMID#Microsoft_VisualStudio_VSConstants_VSITEMID_Selection>)|Ein [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] Element-ID, die darstellt, die aktuell ausgewählte Element oder die Elemente, die den Stamm der Hierarchie enthalten kann.|

## <a name="ivsselectionevents"></a>IVsSelectionEvents
 Beschreibt, welche Komponente von der IDE einfach, im ausgewählt wurde ein <xref:Microsoft.VisualStudio.Shell.Interop.IVsSelectionEvents.OnElementValueChanged%2A> aufrufen, z. B.

|Konstante|Wert|
|--------------|-----------|
|[SelectionElement.DocumentFrame](<xref:Microsoft.VisualStudio.VSConstants.SelectionElement#Microsoft_VisualStudio_VSConstants_SelectionElement_DocumentFrame>)|0x2|
|[SelectionElement.PropertyBrowserSID](<xref:Microsoft.VisualStudio.VSConstants.SelectionElement#Microsoft_VisualStudio_VSConstants_SelectionElement_PropertyBrowserSID>)|0 x 4|
|[SelectionElement.StartupProject](<xref:Microsoft.VisualStudio.VSConstants.SelectionElement#Microsoft_VisualStudio_VSConstants_SelectionElement_StartupProject>)|0x3|
|[SelectionElement.UndoManager](<xref:Microsoft.VisualStudio.VSConstants.SelectionElement#Microsoft_VisualStudio_VSConstants_SelectionElement_UndoManager>)|0x0|
|[SelectionElement.UserContext](<xref:Microsoft.VisualStudio.VSConstants.SelectionElement#Microsoft_VisualStudio_VSConstants_SelectionElement_UserContext>)|0 x 5|
|[SelectionElement.WindowFrame](<xref:Microsoft.VisualStudio.VSConstants.SelectionElement#Microsoft_VisualStudio_VSConstants_SelectionElement_WindowFrame>)|0x1|

## <a name="vsselelemid"></a>VSSELELEMID
 Konstanten verwendet, um eine neue Auswahl den anzugeben.

|Konstante|Wert|
|--------------|-----------|
|<xref:Microsoft.VisualStudio.VSConstants.VSSELELEMID>|2|
|<xref:Microsoft.VisualStudio.VSConstants.VSSELELEMID>|7|
|<xref:Microsoft.VisualStudio.VSConstants.VSSELELEMID>|4|
|<xref:Microsoft.VisualStudio.VSConstants.VSSELELEMID>|6|
|<xref:Microsoft.VisualStudio.VSConstants.VSSELELEMID>|3|
|<xref:Microsoft.VisualStudio.VSConstants.VSSELELEMID>|0|
|<xref:Microsoft.VisualStudio.VSConstants.VSSELELEMID>|5|
|<xref:Microsoft.VisualStudio.VSConstants.VSSELELEMID>|1|

## <a name="component-selector-dialog-constants"></a>Komponente Selektor Dialogfeld Konstanten

|Konstante|Wert|
|--------------|-----------|
|<xref:Microsoft.VisualStudio.VSConstants.CPDN_SELCHANGED>|WM_USER + 1280|
|<xref:Microsoft.VisualStudio.VSConstants.CPDN_SELDBLCLICK>|WM_USER + 1281|
|<xref:Microsoft.VisualStudio.VSConstants.CPPM_CLEARSELECTION>|WM_USER + 1290|
|<xref:Microsoft.VisualStudio.VSConstants.CPPM_GETSELECTION>|WM_USER + 1287|
|<xref:Microsoft.VisualStudio.VSConstants.CPPM_INITIALIZELIST>|WM_USER + 1285|
|<xref:Microsoft.VisualStudio.VSConstants.CPPM_INITIALIZETAB>|WM_USER + 1288|
|<xref:Microsoft.VisualStudio.VSConstants.CPPM_QUERYCANSELECT>|WM_USER + 1286|
|<xref:Microsoft.VisualStudio.VSConstants.CPPM_SETMULTISELECT>|WM_USER + 1289|

## <a name="see-also"></a>Siehe auch

- [IDE-definierte Befehle zum Erweitern von Projektsystemen](../extensibility/internals/ide-defined-commands-for-extending-project-systems.md)