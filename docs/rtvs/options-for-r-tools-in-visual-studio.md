---
title: Optionen für R Tools
description: Referenz der Optionen in Visual Studio für die Sprache R und zugehörige Funktionen.
ms.date: 12/04/2017
ms.prod: visual-studio-dev15
ms.technology: vs-rtvs
ms.topic: reference
dev_langs:
- R
f1_keywords:
- vs.toolsoptionspages.text_editor.r.advanced
- vs.toolsoptionspages.r_tools
- vs.toolsoptionspages.r_tools.advanced
- vs.toolsoptionspages.r_tools.#150
author: kraigb
ms.author: kraigb
manager: douge
ms.workload:
- data-science
ms.openlocfilehash: 5d284355af0d5ec406a5d355bf670a520d1a83e4
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/19/2018
---
# <a name="r-tools-for-visual-studio-options"></a>Optionen für R Tools für Visual Studio

Sie erreichen die Einstellungen über das Menü **R Tools > Optionen** oder über **Extras > Optionen** und dann durch Scrollen zu **R Tools**:

  ![Dialogfeld „Optionen“ für R Tools](media/options-dialog.png)

Auf Optionen und Einstellungen, die für R spezifisch sind, wird mit den nachstehenden Methoden zugegriffen. Sie müssen das Feld **Alle Einstellungen anzeigen** am unteren Rand des Dialogfelds **Optionen** auswählen, damit alle diese Abschnitte angezeigt werden.

- Codeformatierungsoptionen (siehe [Editor-Optionen](editing-r-code-in-visual-studio.md#editor-options)): Menü **Extras > Optionen**, dann **Text-Editor > R > Formatierung** wählen.
- Linting-Optionen (siehe [Linting](linting-r-code.md)): Menü **Extras > Optionen**, dann **Text-Editor > R > Lint** wählen.
- Erweiterte Editor-Optionen (siehe [diesen Artikel](#text-editor--r--advanced-options)): Menü **Extras > Optionen**, dann **Text-Editor > R > Erweitert** auswählen.
- Verhaltensoptionen ([in diesem Artikel beschrieben](#r-tools--advanced-options)): Menü **R Tools > Optionen** oder **Extras> Optionen** > **R Tools**.

Der Befehl **R Tools > Data Science-Einstellungen** wirkt sich auch auf eine Reihe anderer Einstellungen in Visual Studio allgemein aus. Dieser Befehl wird im nächsten Abschnitt beschrieben.

<a name="data-scientist-layout"></a>

## <a name="r-tools--data-science-settings"></a>R Tools > Data Science-Einstellungen

Das Menüelement **R-Tools > Data Science-Einstellungen** konfiguriert die Visual Studio-IDE mit einem Layout, das für die Bedürfnisse von Data Scientists optimiert wurde. Besonders ist, dass diese Option die Fenster [Interaktiv](interactive-repl-for-r-in-visual-studio.md), [Variablen-Explorer](variable-explorer.md) und [Arbeitsbereiche](r-workspaces-in-visual-studio.md) öffnet:

![Fensterlayout für Datenspezialisten in Visual Studio](media/installation-data-scientist-layout-result.png)

Um andere Visual Studio-Einstellungen später wiederherzustellen, verwenden Sie zunächst den Befehl **Tools > Einstellungen importieren und exportieren**, wählen Sie **Ausgewählte Umgebungseinstellungen importieren** aus, und geben Sie den Dateinamen an. Verwenden Sie den gleichen Befehl, und wählen Sie **Ausgewählte Umgebungseinstellungen importieren** aus, um dieses Einstellungen wiederherzustellen. Sie können auch die gleichen Befehle verwenden, wenn Sie das Layout für Datenspezialisten ändern und es später erneut ausführen möchten und nicht direkt den Befehl **Data Science-Einstellungen** verwenden möchten.

## <a name="text-editor--r--advanced-options"></a>Text-Editor > R > Erweiterte Optionen

Diese Optionen steuern das Verhalten bezüglich Formatierung, IntelliSense, Gliederung, Einrückung und Syntaxprüfung für R.

![Dialogfeld „Optionen“ für Text-Editor von R mit erweiterten Optionen](media/options-dialog-advanced-text-editor.png)

Jede Option ist entweder ein- oder ausgeschaltet, um das jeweilige Verhalten zu steuern. Weitere Informationen zu den Auswirkungen der einzelnen Optionen finden Sie im Hilfefenster am unteren Rand des Dialogfelds. Beachten Sie, dass Sie den oberen Teil des Hilfebereichs nach oben ziehen können, um den Bereich zu vergrößern.

![Erweiterter Hilfebereich im Dialogfeld „Erweiterte Optionen“ des Text-Editors von R](media/options-dialog-advanced-text-editor2.png)

## <a name="r-tools--advanced-options"></a>R Tools > Erweiterte Optionen

Über den Menübefehl **R Tools > Optionen** wird das Dialogfeld **Optionen** mit den Optionen für R geöffnet.

  ![Dialogfeld „Optionen“ für R Tools](media/options-dialog.png)

In den folgenden Abschnitten werden die verschiedenen, auf dieser Seite verfügbaren Optionen beschrieben.

### <a name="debugging"></a>Debuggen

Diese Optionen steuern, wie Werte im [Variablen-Explorer](variable-explorer.md) und in Debuggertoolfenstern für lokale Variablen und Überwachung verarbeitet werden (siehe [Debuggen](debugging-r-in-visual-studio.md)).

| Option | Standardwert | description |
| --- | --- | --- |
| Aktive Bindungen auswerten | `True` | Wenn der Wert `True` entspricht, wird sichergestellt, dass Sie immer den aktuellsten Wert erhalten, wenn Sie Variablen und Eigenschaften prüfen. Das Risiko ist, dass die Überprüfung der Ausdrücke zu Nebenwirkungen führen kann, je nachdem, wie sie implementiert wurden. |
| Variablen mit vorangestelltem Punkt anzeigen | `False` | Gibt an, ob Variablen, denen `.` vorangestellt wird, angezeigt werden. |

### <a name="grid-view"></a>Rasteransicht

| Option | Standardwert | description |
| --- | --- | --- |
| Dynamische Auswertung | `False` | Standardmäßig erstellt die `View(<expression>)`-Funktion eine Momentaufnahme der Daten als Datenrahmen, was bei großen Datasets zu einer erheblichen Belegung von Arbeitsspeicher führen kann. Das Festlegen dieser Option auf `True` bedeutet, dass der Ausdruck ausgewertet wird, wenn das Raster aktualisiert wird, um nur die angezeigten Daten abzurufen. Wenn sich jedoch der Ausdruck ändert, ändern sich auch die Daten, was für „dplyr pip“-Ausdrücke ungeeignet sein kann. |

### <a name="help"></a>Hilfe

| Option | Standardwert | description |
| --- | --- | --- |
| F1-Webbrowser | `Internal` | Steuert, wie Hilfe angezeigt wird, wenn Sie nach einem Begriff mithilfe von STRG+F1 suchen. Wenn sie auf `Internal` festgelegt ist, wird die Hilfe innerhalb eines Toolfensters in Visual Studio gerendert. Wenn sie auf `External` festgelegt ist, wird die Hilfe in Ihrem Standardwebbrowser angezeigt. |
| F1-Websuchzeichenfolge | `R site:stackoverflow.com` | Steuert, wie Suchbegriffe Ihrer Suchmaschine übergeben werden, wenn Sie STRG+F1 auf einem Begriff im Editor drücken. Standardmäßig ist die Zeichenfolge `R site:stackoverflow.com`, was `R` an Ihren Suchbegriff anfügt. `site:stackoverflow.com` ist eine Direktive für die Suchmaschine, die dieser mitteilt, dass die Suche im Bereich der Seiten innerhalb der Domäne `stackoverflow.com` durchgeführt werden soll. |
| Browser der R-Hilfe | `Automatic` | Steuert, wie Hilfe angezeigt wird, wenn Sie in der R-Dokumentation mithilfe von F1, `?` oder `??` suchen. Wenn sie auf `Automatic` festgelegt wurde, wird die Hilfe im entsprechenden Fenster gerendert. Die HTML-Hilfe erscheint beispielsweise in einem Visual Studio-Toolfenster, wobei PDFs in Ihrem Standard-PDF-Programm angezeigt werden. Wenn sie auf `External` festgelegt wurde, wird die Hilfe in Ihrem Standardwebbrowser gerendert. |

### <a name="history"></a>Versionsgeschichte

| Option | Standardwert | description |
| --- | --- | --- |
| Verlauf immer speichern | `True` | Steuert, ob RTVS Ihren Verlauf immer in eine `.RHistory`-Datei Ihres Arbeitsverzeichnisses schreibt, wenn das Projekt geschlossen wird. Der Verlauf wird auch gespeichert, wenn Sie Ihr Projekt vor dem Schließen nicht speichern. |
| Suchfilter zurücksetzen | `True` | Bestimmt, ob das Fenster „Verlauf“ Ihren Befehlsverlauf filtern kann, damit nur die Befehle angezeigt werden, deren Teilzeichenfolge mit dem Filterbegriff im Dialogfeld „R-Verlauf“ übereinstimmen. Diese Einstellung bestimmt, ob Ihr Suchfilter „Verlauf“ zurückgesetzt werden soll, wenn Sie einen neuen Befehl ausführen oder zu einem neuen Projekt wechseln, wodurch eine andere `.RHistory`-Datei geladen wird. Mit der Standardeinstellung `True` müssen Sie sich beim Ausführen eines Befehls, für den ein Filter festgelegt wurde, nicht mehr wundern, warum der zuvor ausgeführte Befehl nicht im Verlauf angezeigt wurde. |
| Mehrzeilige Auswahl verwenden | `True` | Gibt an, ob Sie eine mehrzeilige Anweisung im Verlauf mit einem einzigen Klick auswählen können. Ermöglicht auch die Navigation in den interaktiven Fenstern nach Anweisungen statt nach Zeilen mit den Schaltflächen NACH-OBEN/NACH-UNTEN. |

### <a name="html"></a>HTML

| Option | Standardwert | description |
| --- | --- | --- |
| Browser für HTML-Seiten | `External` | Bestimmt, wo Inhalt gerendert wird, z.B. ein `ggvis`-Plot oder eine `shiny`-Anwendung. `Internal` zeigt HTML-Ausgabe in einem Toolfenster in Visual Studio an; `External` zeigt HTML-Ausgabe in Ihrem Standardbrowser an. |

### <a name="logging"></a>Protokollierung

| Option | Standardwert | description |
| --- | --- | --- |
| Protokollieren von Ereignissen | `Normal` | Steuert die Ausführlichkeit der Protokollierung, die für die RTVS-Diagnose genutzt wird. Die Standardeinstellung `Normal` erstellt eine Protokolldatei in Ihrem `TEMP`-Verzeichnis. Wenn sie auf `Traffic` festgelegt sind, protokolliert die RTVS-Erweiterung alle Befehle und stellt die Antworten in Ihrer Sitzung dar. Diese Protokolldateien befinden sich immer auf Ihrem Computer, sind aber womöglich hilfreich, um Probleme in RTVS zu diagnostizieren. |

### <a name="markdown"></a>Markdown

| Option | Standardwert | description |
| --- | --- | --- |
| Markdownvorschaubrowser | `External` | Bestimmt, wo die RMarkdown-HTML-Ausgabe angezeigt wird. `Internal` zeigt RMarkdown-HTML-Dokumente in einem Toolfenster in Visual Studio an; `External` zeigt RMarkdown-HTML mithilfe Ihres Standardbrowsers an. |

### <a name="r-engine"></a>R-Modul

| Option | Standardwert | description |
| --- | --- | --- |
| Codepage | `(OS Default)` | Legt die Codepage (Gebietsschema) für R fest. Standardmäßig wird das zugrunde liegende Gebietsschema des Betriebssystems verwendet. | 
| CRAN-Spiegel | `(Use .Rprofile)` | Legt den standardmäßigen CRAN-Spiegel für Paketinstallationen fest. Die Standardeinstellung von `Use .Rprofile` respektiert Einstellungen für den CRAN-Spiegel in Ihrer `.RProfile`-Datei. |

### <a name="workspace"></a>Arbeitsbereich

| Option | Standardwert | description |
| --- | --- | --- |
| Arbeitsbereich beim Öffnen des Projekts laden | `No` | Die Einstellung auf `Yes` ermöglicht das Laden von Sitzungsdaten von der `.RData`-Datei in die globale Umgebung, wenn das Projekt geöffnet wird. |
| Beim Zurücksetzen zum Speichern des Arbeitsbereichs auffordern | `Yes` | Die Einstellung auf `No` deaktiviert die Aufforderung, Ihren Arbeitsbereich durch Klicken auf die Schaltfläche „Zurücksetzen“ im interaktiven Fenster zu speichern. |
| Beim Schließen des Projekts Arbeitsbereich speichern | `No` | Die Einstellung auf `Yes` ermöglicht die Speicherung der globalen Umgebung in die `.RData`-Datei, wenn das Projekt geschlossen wird. |
| Vor dem Arbeitsbereichswechsel Bestätigungsdialogfeld anzeigen | `Yes` | Die Einstellung auf `No` deaktiviert die Aufforderung zur Bestätigung, wenn zwischen unterschiedlichen Arbeitsbereichen gewechselt wird. Weitere Informationen finden Sie unter [Switching between workspaces (Wechseln zwischen Arbeitsbereichen)](r-workspaces-in-visual-studio.md#switching-between-workspaces). |
| Computerladeanzeige anzeigen | `False` | Steuert die Sichtbarkeit des CPU-, Arbeitsspeicher- und Netzwerklastindikators auf der Statusleiste. Da der Indikator Netzwerkdatenverkehr verursacht, ist es hilfreich, hierfür `False` in Szenarien mit Fernmessung beizubehalten. Wenn Sie diese Option ändern, müssen Sie Visual Studio neu starten. |
