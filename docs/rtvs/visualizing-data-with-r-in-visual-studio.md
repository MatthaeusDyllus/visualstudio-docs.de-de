---
title: Visualisieren von Daten mit R
description: Zeichnen von Daten aus R-Programmen in Visual Studio mithilfe von Plotfenstern.
ms.date: 06/29/2017
ms.prod: visual-studio-dev15
ms.technology: vs-rtvs
ms.topic: conceptual
author: kraigb
ms.author: kraigb
manager: douge
ms.workload:
- data-science
ms.openlocfilehash: 0a11ef12a4ca38c2973c01575b59ef35826bc4a8
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/19/2018
---
# <a name="creating-visual-data-plots-with-r"></a>Erstellen von visuellen Datenplots mit R

Das Erstellen von Grafiken ist ein wichtiger Bestandteil der Arbeit von Datenanalysten. In R Tools für Visual Studio (RTVS) wird in mindestens einem Plotfenster gezeichnet, das Ihre Produktivität bei dieser entscheidenden Tätigkeit verbessern soll.

![Plotfenster](media/plotting-hero-image.png)

|   |   |
|---|---|
| ![Kamerasymbol für video](../install/media/video-icon.png "Video ansehen") | [Sehen Sie sich ein Video (youtube.com)](https://www.youtube.com/watch?v=ZTbKmz5RSgY) zum Plotten mit R an (2m 02s). |

## <a name="the-plot-window"></a>Das Plotfenster

Ein Plotfenster enthält eine Reihe von Plots, wobei jeder Plot durch einen `plot`-Befehl generiert wird. Durch `plot(1:100)` wird z.B. ein neues Plotfenster erstellt, wenn nicht bereits eines verfügbar ist:

![Lineare Kurve von 1 bis 100](media/plotting-1-to-100.png)

Technisch gesehen rendern `plot`-Befehle in R die Ausgabe in ein R-Grafikgerät. Ein Plotfenster rendert den Inhalt eines R-Grafikgeräts, weshalb jedes Plotfenster eine Gerätenummer erhält.

Plotfenster sind nicht von Visual Studio-Projekten abhängig und bleiben geöffnet, während Sie Projekte öffnen und schließen.

Zum Generieren eines Plots wird das „aktive“ Plotfenster verwendet, wobei jeder vorherige Plot im Plotverlauf gespeichert wird (siehe [Plotversionsgeschichte](#plot-history)). Geben Sie z.B. `plot(100:1)` ein, und das erste Diagramm wird durch eine Linie nach unten ersetzt.

Wie alle anderen Visual Studio-Fenster. unterstützt das Plotfenster benutzerdefinierte Layouts (siehe [Anpassen von Fensterlayouts in Visual Studio](../ide/customizing-window-layouts-in-visual-studio.md)). Plotfenster können an verschiedenen Orten innerhalb des Visual Studio-Rahmens andocken, ihre Größe kann innerhalb dieses Rahmens geändert werden oder sie können gänzlich aus dem Rahmen gezogen werden, um ihre Größe völlig unabhängig anzupassen. 

Durch die Größenanpassung eines Plotfensters wird immer der Plot erneut gerendert, um die beste Bildqualität bereitzustellen. In der Regel sollten Sie die Größenanpassung eines Plots vor einem Export des Plots in eine Datei oder in die Zwischenablage mithilfe der im vorherigen Abschnitt beschriebenen Befehle durchführen.

## <a name="plot-window-commands"></a>Befehle für Plotfenster

Die Symbolleiste des Plotfensters enthält anwendbare Befehle, von denen die meisten auch über das Menü **R Tools > Plots** verfügbar sind.

| Schaltfläche | Befehl | description | 
| --- | --- | --- |
| ![Schaltfläche „Neues Plotfenster“](media/plotting-toolbar-01-new-plot-window.png) | Neues Plotfenster | Erstellt ein separates Plotfenster mit eigener Versionsgeschichte. Weitere Informationen unter [Mehrere Plotfenster](#multiple-plot-windows). |
| ![Schaltfläche „Plotfenster aktivieren“](media/plotting-toolbar-02-activate-plot-window.png) | Plotfenster aktivieren | Legt das aktuelle Plotfenster als aktives Fenster fest, sodass nachfolgende `plot`-Befehle an dieses Fenster gerendert werden. Weitere Informationen unter [Mehrere Plotfenster](#multiple-plot-windows). Weitere Informationen unter [Mehrere Plotfenster](#multiple-plot-windows). |
| ![Schaltfläche „Plotverlaufsfenster“](media/plotting-toolbar-03-plot-history.png) | Plotverlaufsfenster | Öffnet ein Fenster mit allen Plots im Verlauf (als Miniaturansichten angezeigt). Weitere Informationen unter [Plotverlauf](#plot-history). |
| ![Schaltflächen zum Plotverlauf](media/plotting-toolbar-04-plot-history-arrows.png) | Vorheriger/Nächster Plot |  Navigiert zum vorherigen oder nächsten Plot im Verlauf. Sie können auch mit STRG+ALT+F11 (Vorheriger Plot) und STRG+Alt+F12 (Nächster Plot) durch den Verlauf navigieren. Weitere Informationen unter [Plotverlauf](#plot-history). |
| ![Schaltfläche „Als Bild speichern“](media/plotting-toolbar-05-save-as-image.png)| Als Bild speichern | Fragt nach einem Dateinamen und speichert den aktuellen Plot (die Fensterinhalte bei der entsprechenden Fenstergröße) in eine Bilddatei. Die verfügbaren Formate sind `.png`, `.jpg`, `.bmp` und `.tif`. |
| ![Schaltfläche „Als PDF speichern“](media/plotting-toolbar-06-save-as-pdf.png)| Als PDF speichern | Speichert den aktuellen Plot mithilfe der aktuellen Fenstergröße in einer PDF-Datei. Der Plot wird erneut gerendert, wenn die PDF-Datei skaliert wird. |
| ![Schaltfläche „Als Bitmap kopieren“](media/plotting-toolbar-07-copy-as-bitmap.png)| Als Bitmap kopieren | Kopiert den Plot als Rasterbitmap in der aktuellen Fenstergröße in die Zwischenablage. | 
| ![Schaltfläche „Als Metafile kopieren“](media/plotting-toolbar-08-copy-as-metafile.png)| Als Metafile kopieren | Kopiert den Plot als [Windows-Metadatei](https://en.wikipedia.org/wiki/Windows_Metafile) (Wikipedia) in die Zwischenablage | 
| ![Schaltfläche „Plot entfernen“](media/plotting-toolbar-09-remove-plot.png)| Plot entfernen | Entfernt den aktuellen Plot aus dem Verlauf |
| ![Schaltfläche „Alle Zeichnungen löschen“](media/plotting-toolbar-10-clear-all-plots.png) | Alle Zeichnungen löschen | Entfernt alle Plots aus dem Verlauf (erfordert eine Bestätigung) |

## <a name="multiple-plot-windows"></a>Mehrere Plotfenster

Da Datenspezialisten häufig mit vielen Plots aus vielen verschiedenen Datasets arbeiten, ermöglicht Ihnen RTVS das Erstellen von vielen unabhängigen Plotfenstern. Sie können diese Fenster dann in der Visual Studio-Frame oder außerhalb dieses Frames beliebig anordnen. Allgemeine Informationen zum Andocken und Ändern der Größe von Fenstern finden Sie unter [Anpassen von Fensterlayouts in Visual Studio](../ide/customizing-window-layouts-in-visual-studio.md).

Neue Plotfenster lassen sich mithilfe der Symbolleistenschaltfläche oder über **R Tools > Plots > Neues Plotfenster** erstellen. Das neue Plotfenster wird das *aktive* Fenster, in dem neue Plots gerendert werden. Um das aktive Fenster zu ändern, öffnen Sie es, und wählen Sie die Symbolleistenschaltfläche „Plotfenster aktivieren“ oder **R Tools > Plots > Plotfenster aktivieren** aus.

Plots sind auch unabhängige Objekte. D.h., dass Sie sie kopieren oder zwischen Plotfenstern entweder mit Drag & Drop oder mit den Befehlen **Kopieren**, **Ausschneiden** und **Einfügen** im Kontextmenü und den Menüs **Bearbeiten** verschieben können.

Das Standardverhalten für Drag & Drop ist Kopieren. Um zu verschieben, halten Sie während des Drag & Drop die UMSCHALTTASTE gedrückt.

## <a name="plot-history"></a>Plotverlauf

Plotbefehle werden in einem Plotverlauf für jedes Fenster beibehalten, um sicherzustellen, dass alle Ihre Plots aus einer Sitzung gespeichert werden. Um durch den Verlauf zu navigieren, verwenden Sie die Pfeiltasten auf der Symbolleiste des Plotfensters oder STRG+ALT+F11 und STRG+ALT+F12. Sie können auch einzelne Plots entfernen oder alle Plots mit den Symbolleistenschaltflächen oder der Menübefehle **R Tools > Plots** wieder aus dem Fenster löschen.

Um die gesamte Auflistung von Plots aufzurufen, öffnen Sie über die Symbolleistenschaltfläche oder **R Tools > Plots > Plotverlaufsfenster** das Plotverlaufsfenster.
Der Verlauf zeigt eine Liste von Miniaturansichten für die Plots an, die in diesem Fenster angezeigt wurden, gruppiert nach den unterschiedlichen Plotfenstern (oder Geräten). Die Größe der Miniaturansichten wird mit den Zoomschaltflächen auf der Symbolleiste geändert.

![Plotverlaufsfenster](media/plotting-plot-history-window.png)

Um einen Plot in einem zugehörigen Fenster zu öffnen, doppelklicken Sie auf den Plot, wählen Sie ihn aus, und wählen Sie im Kontextmenü (Rechtsklick) die Option **Plot anzeigen** oder die Symbolschaltfläche **Plot anzeigen** aus. Sie können auch einen einzelnen Plot auswählen und ihn über das Kontextmenü oder die Menüs **Bearbeiten** kopieren, ausschneiden und löschen.

Die Lebensdauer des fensterübergreifenden Plotverlaufs ist an die Lebensdauer der interaktiven R-Sitzung gebunden. Wenn Sie Ihre R-Sitzung zurücksetzen, oder Visual Studio beenden oder neu starten, wird Ihr Plotverlauf zurückgesetzt.

## <a name="programmatically-manipulating-plot-windows"></a>Programmgesteuertes Bearbeiten von Plotfenstern

Sie können Plotfenster programmgesteuert über den R-Code mithilfe der Gerätenummern zum Identifizieren der einzelnen Plotfenster bearbeiten. 

- `dev.list()`: Liste aller Grafikgeräte innerhalb der aktuellen R-Sitzung
- `dev.new()`: Erstellt ein neues Grafikgerät (ein neues Plotfenster)
- `dev.set(<device number>)`: Legen das aktive Grafikgerät fest
- `dev.off()`: Löscht das aktive Gerät
