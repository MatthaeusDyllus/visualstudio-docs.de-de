---
title: "Visualisieren von Daten mit R Tools für Visual Studio | Microsoft-Dokumentation"
ms.custom: 
ms.date: 5/1/2017
ms.prod: visual-studio-dev15
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-r
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 
caps.latest.revision: 1
author: kraigb
ms.author: kraigb
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Human Translation
ms.sourcegitcommit: 7a873df77756e5a957d327049566c8e0db1f3a8a
ms.openlocfilehash: cd9e0afac5c9a0975197cb65001f8f2698242b85
ms.contentlocale: de-de
ms.lasthandoff: 05/12/2017

---


# <a name="creating-visual-data-plots-with-r"></a>Erstellen von visuellen Datenplots mit R

Das Erstellen von Grafiken ist ein wichtiger Bestandteil der Arbeit von Datenanalysten. In R Tools für Visual Studio (RTVS) wird in mindestens einem Plotfenster gezeichnet, das Ihre Produktivität bei dieser entscheidenden Tätigkeit verbessern soll.

![Plotfenster](~/rtvs/media/plotting-hero-image.png)

In diesem Thema:

- [Das Plotfenster](#the-plot-window)
- [Mehrere Plotfenster](#multiple-plot-windows)
- [Plotversionsgeschichte](#plot-history)
- [Programmgesteuertes Bearbeiten von Plotfenstern](#programmatically-manipulating-plot-windows)

Das folgende Video (2 m, 2 s) bietet eine kurze Übersicht über das Zeichnen in RTVS:

<iframe width="560" height="315" src="https://www.youtube.com/embed/ZTbKmz5RSgY" frameborder="0" allowfullscreen></iframe>

## <a name="the-plot-window"></a>Das Plotfenster

Ein Plotfenster enthält eine Reihe von Plots, wobei jeder Plot durch einen `plot`-Befehl generiert wird. Durch `plot(1:100)` wird z.B. ein neues Plotfenster erstellt, wenn nicht bereits eines verfügbar ist:

![Lineare Kurve von 1 bis 100](~/rtvs/media/plotting-1-to-100.png)

Technisch gesehen rendern `plot`-Befehle in R die Ausgabe in ein R-Grafikgerät. Ein Plotfenster rendert den Inhalt eines R-Grafikgeräts, weshalb jedes Plotfenster eine Gerätenummer erhält.

Plotfenster sind nicht von Visual Studio-Projekten abhängig und bleiben geöffnet, während Sie Projekte öffnen und schließen.

Zum Generieren eines Plots wird das „aktive“ Plotfenster verwendet, wobei jeder vorherige Plot im Plotverlauf gespeichert wird (siehe [Plotversionsgeschichte](#plot-history)). Geben Sie beispielsweise `plot(100:1)` ein, und Sie werden bemerken, dass der Plot oben durch eine abfallende Linie ersetzt wird.

Wie alle anderen Visual Studio-Fenster unterstützt das Plotfenster benutzerdefinierte Layouts (siehe [Anpassen von Fensterlayouts in Visual Studio](../ide/customizing-window-layouts-in-visual-studio.md)). Plotfenster können an verschiedenen Orten innerhalb des Visual Studio-Rahmens andocken, ihre Größe kann innerhalb dieses Rahmens geändert werden oder sie können gänzlich aus dem Rahmen gezogen werden, um ihre Größe völlig unabhängig anzupassen. 

Durch die Größenanpassung eines Plotfensters wird immer der Plot erneut gerendert, um die beste Bildqualität bereitzustellen. In der Regel sollten Sie dies vor einem Export des Plots in eine Datei oder in die Zwischenablage mithilfe der im vorherigen Abschnitt beschriebenen Befehle tun.

## <a name="plot-window-commands"></a>Befehle für Plotfenster

Die Symbolleiste des Plotfensters enthält anwendbare Befehle, von denen die meisten auch über das Menü **R Tools > Plots** verfügbar sind.

| Schaltfläche | Befehl | Beschreibung | 
| --- | --- | --- |
| ![Schaltfläche „Neues Plotfenster“](~/rtvs/media/plotting-toolbar-01-new-plot-window.png) | Neues Plotfenster | Erstellt ein separates Plotfenster mit eigener Versionsgeschichte. Weitere Informationen unter [Mehrere Plotfenster](#multiple-plot-windows). |
| ![Schaltfläche „Plotfenster aktivieren“](~/rtvs/media/plotting-toolbar-02-activate-plot-window.png) | Plotfenster aktivieren | Legt das aktuelle Plotfenster als aktives Fenster fest, sodass nachfolgende `plot`-Befehle an dieses Fenster gerendert werden. Weitere Informationen unter [Mehrere Plotfenster](#multiple-plot-windows). Weitere Informationen unter [Mehrere Plotfenster](#multiple-plot-windows). |
| ![Schaltfläche „Plotverlaufsfenster“](~/rtvs/media/plotting-toolbar-03-plot-history.png) | Plotverlaufsfenster | Öffnet ein Fenster mit allen Plots im Verlauf (als Miniaturansichten angezeigt). Weitere Informationen unter [Plotverlauf](#plot-history). |
| ![Schaltflächen zum Plotverlauf](~/rtvs/media/plotting-toolbar-04-plot-history-arrows.png) | Vorheriger/Nächster Plot |  Navigiert zum vorherigen oder nächsten Plot im Verlauf. Sie können auch mit STRG+ALT+F11 (Vorheriger Plot) und STRG+Alt+F12 (Nächster Plot) durch den Verlauf navigieren. Weitere Informationen unter [Plotverlauf](#plot-history). |
| ![Schaltfläche „Als Bild speichern“](~/rtvs/media/plotting-toolbar-05-save-as-image.png)| Als Bild speichern | Fragt nach einem Dateinamen und speichert den aktuellen Plot (die Fensterinhalte bei der entsprechenden Fenstergröße) in eine Bilddatei. Die verfügbaren Formate sind `.png`, `.jpg`, `.bmp` und `.tif`. |
| ![Schaltfläche „Als PDF speichern“](~/rtvs/media/plotting-toolbar-06-save-as-pdf.png)| Als PDF speichern | Speichert den aktuellen Plot mithilfe der aktuellen Fenstergröße in einer PDF-Datei. Der Plot wird erneut gerendert, wenn die PDF-Datei skaliert wird. |
| ![Schaltfläche „Als Bitmap kopieren“](~/rtvs/media/plotting-toolbar-07-copy-as-bitmap.png)| Als Bitmap kopieren | Kopiert den Plot als Rasterbitmap in der aktuellen Fenstergröße in die Zwischenablage. | 
| ![Schaltfläche „Als Metafile kopieren“](~/rtvs/media/plotting-toolbar-08-copy-as-metafile.png)| Als Metafile kopieren | Kopiert den Plot als [Windows-Metadatei](https://en.wikipedia.org/wiki/Windows_Metafile) (Wikipedia) in die Zwischenablage | 
| ![Schaltfläche „Plot entfernen“](~/rtvs/media/plotting-toolbar-09-remove-plot.png)| Plot entfernen | Entfernt den aktuellen Plot aus dem Verlauf |
| ![Schaltfläche „Alle Zeichnungen löschen“](~/rtvs/media/plotting-toolbar-10-clear-all-plots.png) | Alle Zeichnungen löschen | Entfernt alle Plots aus dem Verlauf (erfordert eine Bestätigung) |

## <a name="multiple-plot-windows"></a>Mehrere Plotfenster

Da Datenanalysten häufig mit vielen Plots aus vielen verschiedenen Datasets arbeiten, ermöglicht es Ihnen RTVS, beliebig viele unabhängige Plotfenster zu erstellen, die innerhalb und außerhalb von Visual Studio beliebig angeordnet werden können. Allgemeine Informationen zum Andocken und Ändern der Größe von Fenstern finden Sie unter [Anpassen von Fensterlayouts in Visual Studio](../ide/customizing-window-layouts-in-visual-studio.md).

Neue Plotfenster lassen sich mithilfe der Symbolleistenschaltfläche oder über **R Tools > Plots > Neues Plotfenster** erstellen. Das neue Plotfenster wird das *aktive* Fenster, in dem neue Plots gerendert werden. Um das aktive Fenster zu ändern, öffnen Sie es, und wählen Sie die Symbolleistenschaltfläche „Plotfenster aktivieren“ oder **R Tools > Plots > Plotfenster aktivieren** aus.

Plots sind auch unabhängige Objekte. D.h., dass Sie sie kopieren oder zwischen Plotfenstern entweder mit Drag & Drop oder mit den Befehlen **Kopieren**, **Ausschneiden** und **Einfügen** im Kontextmenü und den Menüs **Bearbeiten** verschieben können.

 Das Standardverhalten für Drag & Drop ist Kopieren. Um zu verschieben, halten Sie während des Drag & Drop die UMSCHALTTASTE gedrückt.

## <a name="plot-history"></a>Plotverlauf

Plotbefehle werden in einem Plotverlauf für jedes Fenster beibehalten, um sicherzustellen, dass alle Ihre Plots aus einer Sitzung gespeichert werden. Um durch den Verlauf zu navigieren, verwenden Sie die Pfeiltasten auf der Symbolleiste des Plotfensters oder STRG+ALT+F11 und STRG+ALT+F12. Sie können auch einzelne Plots entfernen oder alle Plots mit den Symbolleistenschaltflächen oder der Menübefehle **R Tools > Plots** wieder aus dem Fenster löschen.

Um die gesamte Auflistung von Plots aufzurufen, öffnen Sie über die Symbolleistenschaltfläche oder **R Tools > Plots > Plotverlaufsfenster** das Plotverlaufsfenster.
Hierdurch wird eine Liste von Miniaturansichten für die Plots angezeigt, die in diesem Fenster angezeigt wurden, gruppiert nach den unterschiedlichen Plotfenstern (oder Geräten). Die Größe der Miniaturansichten wird mit den Zoomschaltflächen auf der Symbolleiste geändert.

![Plotverlaufsfenster](~/rtvs/media/plotting-plot-history-window.png)

Um einen Plot in einem zugehörigen Fenster zu öffnen, doppelklicken Sie auf den Plot, wählen Sie ihn aus, und wählen Sie im Kontextmenü (Rechtsklick) die Option **Plot anzeigen** oder die Symbolschaltfläche **Plot anzeigen** aus. Sie können auch einen einzelnen Plot auswählen und ihn über das Kontextmenü oder die Menüs **Bearbeiten** kopieren, ausschneiden und löschen.

Die Lebensdauer des fensterübergreifenden Plotverlaufs ist an die Lebensdauer der interaktiven R-Sitzung gebunden. Wenn Sie Ihre R-Sitzung zurücksetzen, oder Visual Studio beenden oder neu starten, wird Ihr Plotverlauf zurückgesetzt.

## <a name="programmatically-manipulating-plot-windows"></a>Programmgesteuertes Bearbeiten von Plotfenstern

Sie können Plotfenster programmgesteuert über den R-Code mithilfe der Gerätenummern zum Identifizieren der einzelnen Plotfenster bearbeiten. 

- `dev.list()`: Liste aller Grafikgeräte innerhalb der aktuellen R-Sitzung
- `dev.new()`: Erstellt ein neues Grafikgerät (ein neues Plotfenster)
- `dev.set(<device number>)`: Legen das aktive Grafikgerät fest
- `dev.off()`: Löscht das aktive Gerät
