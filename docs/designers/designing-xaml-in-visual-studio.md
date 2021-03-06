---
title: Entwerfen von XAML-Code in Visual Studio
ms.date: 07/17/2017
ms.prod: visual-studio-dev15
ms.technology: vs-ide-designers
ms.topic: conceptual
ms.assetid: 288e2415-9fcf-408e-bc35-9848315e14fd
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- uwp
ms.openlocfilehash: 6eb91664c78f3c11039f519a306e55a76f9c8e5a
ms.sourcegitcommit: 58052c29fc61c9a1ca55a64a63a7fdcde34668a4
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2018
ms.locfileid: "34745723"
---
# <a name="design-xaml-in-visual-studio"></a>Entwerfen von XAML-Code in Visual Studio

Visual Studio und Blend für Visual Studio sind visuelle Tools zum Erstellen ansprechender Benutzeroberflächen und Rich-Media-Umgebungen mit XAML für eine Vielzahl von App-Typen. Beide Tools verwenden einen gemeinsamen Satz an Features, einschließlich eines visuellen XAML-Editors. Blend für Visual Studio bietet jedoch zusätzliche Entwurfstools für fortgeschrittene Aufgaben, wie z. B. Animation und Verhaltensweisen.

Der Entwurfsprozess einer App hängt von dem Tool, das Sie auswählen und Ihrer Zielplattform ab. In diesem Artikel werden die Verwendung von XAML-Entwurfstools in Visual Studio und Blend für Visual Studio verglichen. Eine detailliertere exemplarische Vorgehensweise zur Verwendung der Tools finden Sie in den folgenden Themen:

- [Erstellen einer Benutzeroberfläche mit dem XAML-Designer in Visual Studio](creating-a-ui-by-using-xaml-designer-in-visual-studio.md)
- [Erstellen einer Benutzeroberfläche mit Blend für Visual Studio](creating-a-ui-by-using-blend-for-visual-studio.md)

## <a name="choose-the-right-tool"></a>Auswählen des richtigen Tools

Die Auswahl des Entwurfstools ist im Wesentlichen abhängig von Ihren Fähigkeiten. Wenn Sie eher codeorientiert sind, können Sie XAML-Code in Visual Studio schreiben, um selbst fortschrittliche Entwurfsaufgaben zu erledigen. Sind Sie eher designorientiert, können Sie mit Blend für Visual Studio erweiterte Aufgaben ausführen, ohne Code schreiben zu müssen.

Sie können zwischen Visual Studio und Blend für Visual Studio wechseln. Sie können sogar in beiden dasselbe Projekt geöffnet haben. Änderungen an XAML-Dateien in einer IDE lassen sich beim Wechsel zur anderen IDE automatisch neu laden. Sie können das Neuladeverhalten über Optionen im Dialogfeld **Tools**, **Optionen** in beiden IDEs steuern.

### <a name="shared-capabilities"></a>Gemeinsam genutzte Funktionen

Für die meisten grundlegenden Aufgaben teilen sich die IDE für Visual Studio und Blend für Visual Studie denselben Fenster- und Funktionssatz, mit einigen geringfügigen Unterschieden. Hier einige Highlights:

- **Eine einheitliche Benutzeroberfläche:** Sie können Ihre Anwendungen innerhalb der vertrauten Umgebung der Visual Studio-Benutzeroberfläche entwickeln, was den Wechsel zwischen den IDEs zu einem angenehmeren und produktiveren Erlebnis macht. Blend für Visual Studio nutzt das „dunkle Design“ von Visual Studio, mit dem Sie sich durch eine Optimierung des Kontrasts zwischen Ihren Inhalten und der Benutzeroberfläche besser auf die entwickelten Inhalte konzentrieren können. Informationen hierzu finden Sie unter [Creating a UI by using XAML Designer (Erstellen einer Benutzeroberfläche mit XAML-Designer)](../designers/creating-a-ui-by-using-xaml-designer-in-visual-studio.md).

     ![Die Blend für Visual Studio-IDE](../designers/media/blendide.png)

- **XAML IntelliSense:** Beide IDEs unterstützen alle gemeinsamen Funktionen, die Sie von IntelliSense erwarten würden, einschließlich einer Anweisungsvervollständigung, der Unterstützung für gemeinsame Editoraktionen, wie z. B. Kommentieren und Formatieren von Code sowie die Navigation zu Ressourcen, zur Bindung und zum Code.

- **Grundlegenden Debugfunktionen:** Sie können in Blend jetzt debuggen, einschließlich dem Festlegen von Haltepunkten in Ihrem Code zum Debuggen Ihrer laufenden App. Für ein einheitliches Debugerlebnis in Visual Studio beinhaltet Blend für Visual Studio die meisten der Debugfenster und -symbolleisten von Visual Studio. Erweiterte Debugfunktionen, z. B. die Diagnose und die Codeanalyse, sind hingegen nur in Visual Studio verfügbar. Siehe [Debugging in Visual Studio](../debugger/debugging-in-visual-studio.md).

- **Oberfläche für erneutes Laden einer Datei:** Sie können die XAML-Dateien sowohl in Blend für Visual Studio als auch in Visual Studio bearbeiten und dafür sorgen, dass die bearbeiteten Dateien automatisch beim Wechsel zwischen ihnen neu geladen werden. Um Workflow-Unterbrechungen zu minimieren, können Sie jetzt Ihre Datei-Neuladeeinstellungen im Dialogfeld „Datei neu laden“ festlegen.

     ![Oberfläche für erneutes Laden einer Datei](../designers/media/blendfilereload.png)

- **Synchronisiert Layouts und Einstellungen:** Mit benutzerdefinierten Layouts können Sie Anpassungen des Tool-Fensterlayouts speichern und anwenden. Visual Studio synchronisiert diese Anpassungen und Einstellungen sowohl für Visual Studio als auch für Blend für Visual Studio computerübergreifend, wenn Sie sich bei demselben Microsoft-Konto anmelden. Weitere Informationen finden Sie unter [Personalisieren der Visual Studio-IDE](../ide/personalizing-the-visual-studio-ide.md).

- **ein gemeinsamer Projektmappen-Explorer:** Der Projektmappen-Explorer bietet eine strukturierte Ansicht für Ihre Projekte und Ihre Dateien sowie einen schnellen Zugriff auf die zugehörigen Befehle. Mit dem Projektmappen-Explorer ist es einfacher, mit großen Firmenprojekten zu arbeiten. Informationen hierzu finden Sie unter [Solutions and Projects (Projektmappen und Projekte)](../ide/solutions-and-projects-in-visual-studio.md).

- **Team Explorer:** Mit Team Explorer können Sie Ihre Projekte mit GIT- oder TFS-Repositorys zur Erleichterung der Zusammenarbeit im Team verwalten. Siehe [Arbeiten im Team Explorer](http://msdn.microsoft.com/Library/fd7a5cf7-7916-4fa0-b5e6-5a83cf377a02)

- **NuGet:** können Sie in Visual Studio und Blend für Visual Studio NuGet-Pakete verwalten. NuGet ist eine Paket-Manager für .NET Framework, der die Installation und Deinstallation von Paketen aus einer Projektmappe vereinfacht.

## <a name="advanced-capabilities-in-blend-for-visual-studio"></a>Erweiterte Funktionen in Blend für Visual Studio

Verwenden Sie Blend für Visual Studio für die folgenden Aufgaben, um Ihre Produktivität zu steigern. Dies sind die Bereiche, in denen Blend mehr Schnelligkeit und Funktionalität bietet als Visual Studio-Designer oder Code allein.

|Beschreibung|Visual Studio|Blend for Visual Studio|Weitere Informationen|
|--------|-------------------|-----------------------------|----------------------|
|**Erstellen von Animationen**|Es gibt kein Designwerkzeug für Animationen; Sie müssen sie programmgesteuert erstellen. Dies erfordert ein grundlegendes Verständnis des Animations- und Zeitsteuerungssystems in WPF sowie umfangreiche Codierungskenntnisse.|Sie können Animationen in Blend für Visual Studio visuell erstellen und eine Vorschau anzeigen. Dies ist schneller und präziser, als Animationen in Code zu erstellen. Sie können Trigger hinzufügen, um die Benutzerinteraktion zu verarbeiten, und Sie können zum Code wechseln, um Ereignishandler und andere Funktionen zu verarbeiten.|[Animate objects (Animieren von Objekten)](../designers/animate-objects-in-xaml-designer.md)|
|**Umwandeln von Formen und Text in Pfade für eine einfachere Bearbeitung**|Wird nicht unterstützt.|Sie können geringfügige oder erhebliche Änderungen an den Formen (z. B. Rechtecke und Ellipsen) vornehmen, indem Sie sie in Pfade konvertieren, die eine bessere Bearbeitungssteuerung bieten.  Sie können Pfade umformen oder kombinieren und zusammengesetzte Pfade aus mehreren Formen erstellen.<br /><br /> Sie können auch Textblöcke in Pfade umwandeln, um sie als Vektorgrafiken zu bearbeiten.|[Zeichnen von Formen und Pfaden](../designers/draw-shapes-and-paths.md)|
|**Hinzufügen von Interaktivität zu Ihren Benutzeroberflächendesigns**|Erfordert C#-, Visual Basic- oder C++-Code.|Ziehen Sie Verhalten auf Steuerelemente, um Ihren statischen Designs Interaktivität hinzuzufügen. Verhalten sind sofort einsatzbereite Codeausschnitte, die Funktionen wie Drag & Drop, Zoom und Änderungen des visuellen Zustands kapseln. Es gibt immer mehr Verhalten, aus denen Sie wählen können. Zudem können Sie Ihre eigenen erstellen.<br /><br /> Sie können dann jedes Verhalten anpassen, indem Sie dessen Eigenschaften in Blend für Visual Studio ändern oder indem Sie Ereignishandler in den Code einfügen.|[Insert controls and modify their behavior (Einfügen von Steuerelementen und Ändern des Verhaltens)](../designers/insert-controls-and-modify-their-behavior-in-xaml-designer.md)|
|**Verwenden von Adobe-Bildmaterial**|Wird nicht unterstützt.|Importieren Sie Adobe FXG-, Photoshop- oder Illustrator-Bildmaterial, und implementieren Sie die Benutzeroberfläche in Blend für Visual Studio.|[Insert images, videos, and audio clips (Einfügen von Bildern, Videos und Audioclips)](../designers/insert-images-videos-and-audio-clips-in-xaml-designer.md)|
|**Bearbeiten von Steuerelementen, Vorlagen und Stilen**|Erfordert die Codierung von sowie Kenntnisse über WPF-Stile und -Vorlagen.|Wandeln Sie ein Bild in ein Steuerelement um.<br /><br /> Verwenden Sie die Tools zum Bearbeiten von Vorlagen, um Steuerelemente, Stile und Vorlagen mit nur wenigen Mausklicks zu ändern.<br /><br /> Beispielsweise können Sie Blend für Visual Studio-Ressourcen verwenden, um WPF-Standardsteuerelemente (z. B. Schaltflächen, Listenfeldern, Bildlaufleisten, Menüs usw.) zu implementieren und um die Farbe, den Stil oder die zugrunde liegende Vorlage direkt in Blend zu ändern. Sie können dann, falls gewünscht, zum Code wechseln, um Ihrer Arbeit den letzten Schliff zu geben.|[Modify the style of objects (Ändern des Stils von Objekten)](../designers/modify-the-style-of-objects-in-blend.md)|
|**Verbinden der Benutzeroberfläche mit Daten**|Sie können eine Datenquelle aus Ressourcen, wie SQL Server-Datenbanken, WCF oder Webdiensten, Objekten oder SharePoint-Listen, erstellen und die Datenquelle mit den Steuerelementen der Benutzeroberfläche verknüpfen.<br /><br /> Daten müssen für ein interaktives Designerlebnis zur Entwurfszeit manuell erstellt werden.|Erstellen Sie mühelos die Beispieldaten für die Prototyperstellung und für Tests. Wechseln Sie zu den Livedaten, wenn Sie bereit sind.<br /><br /> Die Blend-Funktionen zur Datengenerierung von Visual Studio sind hervorragend. Sie können Namen, Zahlen, URLs, Fotos problemlos bei laufendem Betrieb hinzufügen, wodurch Sie potenziell viel Zeit sparen.<br /><br /> Bei Live-Daten können Sie die Steuerelemente der Benutzeroberfläche mit einer XML-Datei oder einer beliebigen CLR-Datenquelle verknüpfen.|[Display data (Anzeigen von Daten)](../designers/display-data-in-blend.md)|

Informationen zu erweiterten XAML-Designs finden Sie unter [Erstellen einer Benutzeroberfläche mit Blend für Visual Studio](../designers/creating-a-ui-by-using-blend-for-visual-studio.md).
