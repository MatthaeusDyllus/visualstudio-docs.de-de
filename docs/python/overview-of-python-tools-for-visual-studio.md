---
title: Übersicht zur Python-Unterstützung für Visual Studio unter Windows
description: Zusammenfassung der Python-Features in Visual Studio, durch die Visual Studio zur besten Python-IDE unter Windows wird (auch bekannt als Python-Tools für Visual Studio, PTVS).
ms.date: 05/07/2018
ms.prod: visual-studio-dev15
ms.technology: vs-python
ms.topic: overview
author: kraigb
ms.author: kraigb
manager: douge
ms.workload:
- python
- data-science
ms.openlocfilehash: 587517bdeabf9755e2678b03206059ef5b403255
ms.sourcegitcommit: 1466ac0f49ebf7448ea4507ae3f79acb25d51d3e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/22/2018
ms.locfileid: "34449168"
---
# <a name="working-with-python-in-visual-studio-on-windows"></a>Arbeiten mit Python in Visual Studio unter Windows

Python ist eine beliebte Programmiersprache, die zuverlässig, flexibel, leicht zu erlernen und für alle Betriebssysteme kostenlos ist und sowohl von einer starken Entwicklercommunity als auch vielen kostenlosen Bibliotheken unterstützt wird. Python unterstützt alle Arten von Entwicklung, einschließlich Webanwendungen, Webdienste, Desktop-Apps, Skripts und wissenschaftliche Berechnungen, und wird von vielen Universitäten, Wissenschaftlern, gelegentlichen und professionellen Entwicklern gleichermaßen verwendet. Weitere Informationen zur Sprache finden Sie unter [python.org](https://www.python.org) und [Python for Beginners](https://www.python.org/about/gettingstarted/).

Visual Studio ist eine leistungsstarke Python-IDE unter Windows. Visual Studio bietet über die Arbeitsauslastungen „Python-Entwicklung“ und „Data Science“ (Visual Studio 2017) und die kostenlose Erweiterung Python Tools für Visual Studio (Visual Studio 2015 und früher) [Open-Source](https://github.com/Microsoft/ptvs)-Unterstützung für die Python-Sprache.

Python wird gegenwärtig nicht von Visual Studio für Mac unterstützt, ist jedoch über Visual Studio Code unter Mac und Linux verfügbar (siehe [Questions and answers](#questions-and-answers) (Fragen unten Antworten)).

Einführung:

- Folgen Sie den [Installationsanweisungen](installing-python-support-in-visual-studio.md), um die Python-Arbeitsauslastung einzurichten.
- Machen Sie sich anhand der Abschnitte in diesem Artikel mit den Python-Funktionen von Visual Studio vertraut. Sie können sich auch [eine Videoreihe (Microsoft Virtual Academy)](https://mva.microsoft.com/en-US/training-courses/python-tools-for-visual-studio-2017-18121) mit einer Einführung zu Python in Visual Studio (22 Minuten gesamt) ansehen.
- Befolgen Sie eine oder mehrere der Schnellstartanweisungen, um ein Projekt zu erstellen. Falls Sie sich nicht entscheiden können, womit Sie anfangen möchten, beginnen Sie mit [Erstellen einer Web-App mit Flask](../ide/quickstart-python.md?context=visualstudio/python/default).
- Befolgen Sie das Tutorial [Working with Python in Visual Studio (Arbeiten mit Python in Visual Studio)](tutorial-working-with-python-in-visual-studio-step-01-create-project.md) für ein vollständiges End-to-End-Erlebnis.

## <a name="support-for-multiple-interpreters"></a>Unterstützung mehrerer Interpreter

Das Visual Studio-Fenster **Python-Umgebungen** (unten in einer breiten, erweiterten Ansicht dargestellt) bietet eine zentrale Stelle zum Verwalten aller Ihrer globalen Python-Umgebungen, Conda-Umgebungen und virtuellen Umgebungen. Visual Studio erkennt Python-Installationen in standardmäßigen Speicherorten automatisch, und Sie können benutzerdefinierte Installationen konfigurieren. Mit jeder Umgebung können Sie problemlos Pakete verwalten, ein interaktives Fenster für die Umgebung öffnen und auf Ordner der Umgebung zugreifen.

![Erweiterte Ansicht des Fensters „Python-Umgebungen“](media/environments-expanded-view.png)

Weitere Informationen finden Sie unter: 

- Video (2 min 35 s): [Verwalten von Python-Umgebungen](https://mva.microsoft.com/en-US/training-courses/python-tools-for-visual-studio-2017-18121?l=qrDmN4LWE_8305918567)
- Dokumentation: [Verwalten von Python-Umgebungen](managing-python-environments-in-visual-studio.md)
- Dokumentation: [Das Fenster „Python-Umgebungen“](python-environments-window-tab-reference.md)

## <a name="rich-editing-intellisense-and-code-comprehension"></a>Vielfältige Funktionen für die Bearbeitung, IntelliSense und Kennzeichnung von Code

Visual Studio bietet einen erstklassigen Python-Editor mit folgenden Funktionen: Syntaxfarben, automatische Vervollständigung für den gesamten Code und alle Bibliotheken, Codeformatierung, Signaturhilfe, Umgestaltung, Linting (unten dargestellt) und Typhinweise. Visual Studio bietet auch einzigartige Features wie die Klassenansicht, „Zur Definition wechseln“, „Alle Verweise suchen“ und Codeausschnitte. Durch die direkte Integration in das [interaktive-Fenster](#interactive-window) können Sie schnell Python-Code entwickeln, der bereits in einer Datei gespeichert ist.

![Codevervollständigungen für Python-Code in Visual Studio](media/code-editing-completions-simple.png)

Weitere Informationen finden Sie unter: 

- Video (2 min 30 s): [Bearbeiten von Python-Code](https://mva.microsoft.com/en-US/training-courses/python-tools-for-visual-studio-2017-18121?l=r2iQH5LWE_4605918567)
- Dokumentation: [Bearbeiten von Python-Code](editing-python-code-in-visual-studio.md)
- Dokumentation: [Codeformatierung](formatting-python-code.md)
- Dokumentation: [Umgestaltung](refactoring-python-code.md)
- Dokumentation: [Linting](linting-python-code.md)
- Dokumentation zu grundlegenden Visual Studio-Features: [Features des Code-Editors](../ide/writing-code-in-the-code-and-text-editor.md)

## <a name="interactive-window"></a>Interaktives Fenster

Für jede für Visual Studio geeignete Python-Umgebung können Sie einfach die gleiche interaktive Umgebung (REPL) für einen Python-Interpreter direkt in Visual Studio öffnen, statt eine separate Eingabeaufforderung zu verwenden. Sie können auch einfach zwischen Umgebungen wechseln.

![Interaktives Python-Fenster in Visual Studio](media/interactive-window.png)

Visual Studio bietet zudem eine enge Integration zwischen dem Python-Code-Editor und dem interaktivem Fenster. Mit der Tastenkombination **STRG+EINGABE** wird die aktuelle Codezeile (oder der Codeblock) im Editor bequem an das interaktive Fenster gesendet und dann wird zur nächsten Zeile (oder zum nächsten Block) gewechselt. Mit **STRG+EINGABE** können Sie problemlos schrittweise Code durchlaufen, ohne den Debugger auszuführen. Sie können mit der gleichen Tastenkombination auch markierten Code an das interaktive Fenster senden und mühelos Code aus dem interaktiven Fenster in den Editor einfügen. Zusammen ermöglichen diese Funktionen, dass Sie Details für ein Segment des Codes im interaktiven Fenster ausarbeiten und die Ergebnisse problemlos in einer Datei im Editor speichern können.

Visual Studio unterstützt zudem IPython/Jupyter in der REPL, einschließlich Inlineplots, .NET und Windows Presentation Foundation (WPF).

Weitere Informationen finden Sie unter: 

- Video (2 min 22 s): [Interaktives Python-Fenster](https://mva.microsoft.com/en-US/training-courses/python-tools-for-visual-studio-2017-18121?l=gJYKY5LWE_4605918567)
- Dokumentation: [Interaktives Fenster](python-interactive-repl-in-visual-studio.md)
- Dokumentation: [IPython in Visual Studio](interactive-repl-ipython.md)

## <a name="project-system-and-project-and-item-templates"></a>Projektsystem und Projekt- und Elementvorlagen

Mit Visual Studio können Sie die Komplexität eines Projekts handhaben, während es mit der Zeit wächst. Ein Projekt ist weitaus mehr als eine Ordnerstruktur: Sie müssen auch wissen, wie die verschiedenen Dateien verwendet werden und wie sie miteinander in Beziehung stehen. Mit Visual Studio können Sie App-Code, Testcode, Webseiten, JavaScript, Buildskripts usw. unterscheiden, wodurch wiederum für die Datei geeignete Features ermöglicht werden. Mit einer Visual Studio-Projektmappe können Sie darüber hinaus mehrere verwandte Projekte verwalten, z.B. ein Python-Projekt und ein C++-Erweiterungsprojekt.

![Eine Visual Studio-Projektmappe mit Python- und C++-Projekten](media/projects-solution-explorer-two-projects.png)

Projekt- und Elementvorlagen automatisieren die Einrichtung unterschiedlicher Arten von Projekten und Dateien. Dadurch sparen Sie wertvolle Zeit und müssen komplizierte und fehleranfällige Details nicht mehr verwalten. Visual Studio stellt Vorlagen für Web-, Azure-, Data Science-, Konsolen- und andere Arten von Projekten bereit. Zudem gibt es Vorlagen für Dateien, wie Python-Klassen, Komponententests, Azure-Webkonfigurationen, HTML und sogar Django-Apps.

[![Projekt- und Elementvorlagen für Python in Visual Studio](media/project-and-item-templates.png)](media/project-and-item-templates.png)

Weitere Informationen finden Sie unter: 

- Dokumentation: [Verwalten von Python-Projekten](managing-python-projects-in-visual-studio.md)
- Dokumentation: [Referenz für Python-Elementvorlagen](python-item-templates.md)
- Dokumentation: [Python-Projektvorlagen](managing-python-projects-in-visual-studio.md#project-templates)
- Dokumentation: [Arbeiten mit C++ und Python](working-with-c-cpp-python-in-visual-studio.md)
- Allgemeine Visual Studio-Featuredokumentation: [Projekt- und Elementvorlagen](../ide/creating-project-and-item-templates.md#visual-studio-templates)
- Allgemeine Visual Studio-Featuredokumentation: [Projektmappen und Projekte in Visual Studio](../ide/solutions-and-projects-in-visual-studio.md)

## <a name="full-featured-debugging"></a>Vollständige Debugfeatures

Eine der Stärken von Visual Studio ist der leistungsfähige Debugger. Speziell für Python ermöglicht Visual Studio Debuggen im gemischten Python/C++-Modus, Remotedebuggen unter Linux, Remotedebuggen in Azure, Debuggen im interaktiven Fenster und Debuggen von Python-Komponententests.

![Visual Studio-Debugger für Python mit dem Popup einer Ausnahme](media/debugging-exception-popup.png)

Weitere Informationen finden Sie unter: 

- Video (3 min 32 s): [Debuggen von Python](https://mva.microsoft.com/en-US/training-courses/python-tools-for-visual-studio-2017-18121?l=Ep5dp5LWE_3805918567)
- Dokumentation: [Debuggen von Python](debugging-python-in-visual-studio.md)
- Dokumentation: [Python/C++: Debuggen im gemischten Modus](debugging-mixed-mode-c-cpp-python-in-visual-studio.md)
- Dokumentation: [Remotedebuggen unter Linux](debugging-python-code-on-remote-linux-machines.md)
- Dokumentation: [Remotedebuggen in Azure](debugging-remote-python-code-on-azure.md)
- Allgemeine Visual Studio-Featuredokumentation: [Featuretour – Visual Studio Debugger](../debugger/debugger-feature-tour.md)

## <a name="profiling-tools-with-comprehensive-reporting"></a>Profilerstellungstools mit umfassender Berichterstellung

Mit der Profilerstellung wird untersucht, wie Zeit innerhalb der Anwendung aufgewendet wird. Visual Studio unterstützt die Profilerstellung mit CPython-basierten Interpretern und bietet die Möglichkeit, die Leistung zwischen verschiedenen Profilerstellungen zu vergleichen.

[![Visual Studio-Profiler-Ergebnisse für ein Python-Projekt](media/profiling-results.png)](media/profiling-results.png)

Weitere Informationen finden Sie unter: 

- Video (3 min 00 s): [Profilerstellung für Python](https://mva.microsoft.com/en-US/training-courses/python-tools-for-visual-studio-2017-18121?l=s6FoC6LWE_1005918567)
- Dokumentation: [Python-Profilerstellungstools](profiling-python-code-in-visual-studio.md)
- Allgemeine Visual Studio-Featuredokumenation: [Tour zur Profilerstellungsfunktion](../profiling/profiling-feature-tour.md). (Nicht alle Funktionen der Visual Studio-Profilerstellung stehen für Python zur Verfügung.)

## <a name="unit-testing-tools"></a>Tools für Unittests

Sie können Tests im Test-Explorer von Visual Studio ermitteln, ausführen und verwalten und Unittests problemlos debuggen.

![Debuggen eines Python-Komponententests in Visual Studio](media/unit-test-debugging.png)

Weitere Informationen finden Sie unter: 

- Video (2 min 31 s): [Testen von Python](https://mva.microsoft.com/en-US/training-courses/python-tools-for-visual-studio-2017-18121?l=hb46k6LWE_405918567)
- Dokumentation: [Tools für Unittests für Python](unit-testing-python-in-visual-studio.md)
- Allgemeine Visual Studio-Featuredokumentation: [Ausführen von Komponententests für Code](../test/unit-test-your-code.md).

## <a name="publishing-to-azure-and-azure-sdk-for-python"></a>Veröffentlichen in Azure und Azure SDK für Python

Visual Studio bietet integrierte Unterstützung für das Veröffentlichen von Web-Apps und Clouddiensten in Azure. Visual Studio enthält wichtige `web.config`-Elementvorlagen für dynamische und statische Inhalte. Die Python-Arbeitsauslastung umfasst auch das Azure SDK für Python, das die Nutzung von Azure-Diensten aus Windows-, Mac OS X- und Linux-Anwendungen vereinfacht.

![Veröffentlichen einer Python-Anwendung in Azure mit Visual Studio](media/azure-publish-dialog.png)

Weitere Informationen finden Sie unter: 

- Dokumentation: [Veröffentlichen in Azure](publishing-python-web-applications-to-azure-from-visual-studio.md)
- Dokumentation: [Azure SDK für Python](azure-sdk-for-python.md)

## <a name="python-training-on-microsoft-virtual-academy"></a>Python-Schulungen in der Microsoft Virtual Academy

|   |   |
|---|---|
| ![Kamerasymbol für video](../install/media/video-icon.png "Video ansehen") | <ul><li>[Einführung in das Programmieren mit Python](https://mva.microsoft.com/en-US/training-courses/introduction-to-programming-with-python-8360?l=lqhuMxFz_8904984382)</li><li>[Python für Einsteiger: Zeichenfolgen und Funktionen](https://mva.microsoft.com/en-US/training-courses/python-beginner-strings-and-functions-18015)</li><li>[Python-Grundlagen: Listen und Schleifen](https://mva.microsoft.com/en-US/training-courses/python-fundamentals-lists-and-loops-18019)</li><li>[Häufigste Fragen zu Python](https://mva.microsoft.com/en-US/training-courses/python-tools-for-visual-studio-2017-18121)</li></ul> |

## <a name="questions-and-answers"></a>Fragen und Antworten

**F. Wird Python von Visual Studio für Mac unterstützt?**

A. Zurzeit nicht, aber Sie können sich auf [UserVoice](https://visualstudio.uservoice.com/forums/563332-visual-studio-for-mac/suggestions/18670291-python-tools-for-visual-studio-mac) dafür einsetzen. Die [Visual Studio für Mac](/visualstudio/mac/)-Dokumentation identifiziert die aktuellen Entwicklungstypen, die unterstützt werden. In der Zwischenzeit funktioniert Visual Studio-Code auf Windows, Mac und Linux [problemlos mit Python über die verfügbaren Erweiterungen](https://code.visualstudio.com/docs/languages/python).

**F. Was kann ich verwenden, um die Benutzeroberfläche mit Python zu erstellen?**

A. Das Hauptangebot in diesem Bereich ist das [Qt-Projekt](https://www.qt.io/qt-for-application-development/) mit Bindungen für Python mit dem Namen [PySide (die offizielle Bindung)](http://wiki.qt.io/PySide) (siehe auch [PySide-Downloads](https://download.qt.io/official_releases/pyside/.)) und [PyQt](https://wiki.python.org/moin/PyQt). Derzeit umfasst die Python-Unterstützung in Visual Studio keine bestimmten Tools für die Entwicklung von Benutzeroberflächen.

**F. Kann mit einem Python-Projekt eine eigenständige ausführbare Datei erzeugt werden?**

A. Python ist im Allgemeinen eine interpretierte Sprache, bei der Code nach Bedarf in einer geeigneten, Python-fähigen Umgebung wie Visual Studio und Webservern ausgeführt wird. Visual Studio selbst bietet derzeit keine Möglichkeit, eine eigenständige ausführbare Datei zu erstellen, was im Wesentlichen ein Programm mit einem eingebetteten Python-Interpreter bedeutet. Es gibt jedoch innerhalb der Python-Community verschiedene Möglichkeiten, ausführbare Dateien zu erstellen, wie unter [StackOverflow](http://stackoverflow.com/questions/5458048/how-to-make-a-python-script-standalone-executable-to-run-without-any-dependency) beschrieben wird. CPython unterstützt es auch, in eine native Anwendung eingebettet zu werden, wie im Blogbeitrag [Using CPython's Embeddable Zip File (Verwenden der eingebetteten ZIP-Datei von CPython)](https://blogs.msdn.microsoft.com/pythonengineering/2016/04/26/cpython-embeddable-zip-file/) beschrieben wird.

## <a name="features-matrix"></a>Featurematrix

Python-Features können wie im [Installationshandbuch](installing-python-support-in-visual-studio.md) beschrieben in den folgenden Editionen von Visual Studio installiert werden:

- [Visual Studio 2017 (alle Editionen)](https://www.visualstudio.com/vs/)
- Visual Studio 2015 (alle Editionen)
- Visual Studio 2013 Community Edition
- Visual Studio 2013 Express für Web, Update 2 oder höher
- Visual Studio 2013 Express für Desktop, Update 2 oder höher
- Visual Studio 2013 (Pro-Edition oder höher)
- Visual Studio 2012 (Pro-Edition oder höher)
- Visual Studio 2010 SP1 (Pro-Edition oder höher, .NET 4.5 ist erforderlich)

Visual Studio 2015 und frühere Versionen sind unter [visualstudio.com/vs/older-downloads/](https://www.visualstudio.com/vs/older-downloads/) verfügbar.

> [!Important]
> Features werden nur für die neueste Visual Studio-Version unterstützt und gewartet. Sie sind für ältere Versionen zwar verfügbar, werden jedoch nicht mehr aktiv verwaltet.

| Python-Unterstützung | 2017 | 2015 | 2013 Comm | 2013 Desktop | 2013 Web | 2013 Pro+ | 2012 Pro+ | 2010 SP1 Pro+ |
| --- | --- | --- | --- | --- | --- | --- | --- | ---|
| Verwaltung mehrerer Interpreter | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; |
| Automatische Erkennung beliebte Interpreter | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; |
| Hinzufügen von benutzerdefinierten Interpretern | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; |
| Virtuelle Umgebungen | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; |
| PIP/einfache Installation | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; |
<br/>

| Projektsystem | 2017 | 2015 | 2013 Comm | 2013 Desktop | 2013 Web | 2013 Pro+ | 2012 Pro+ | 2010 SP1 Pro+ |
| --- | --- | --- | --- | --- | --- | --- | --- | ---|
| Neues Projekt aus vorhandenem Code | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; |
| Alle Dateien anzeigen | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; |
| Quellcodeverwaltung | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; |
| Git-Integration | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004;<sup>1</sup> | &#10007; |
<br/>

| Bearbeiten | 2017 | 2015 | 2013 Comm | 2013 Desktop | 2013 Web | 2013 Pro+ | 2012 Pro+ | 2010 SP1 Pro+ |
| --- | --- | --- | --- | --- | --- | --- | --- | ---|
| Syntaxhervorhebung | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; |
| Automatische Vervollständigung | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; |
| Signaturhilfe | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; |
| QuickInfo | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; |
| Objektkatalog/Klassenansicht | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; |
| Navigationsleiste | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; |
| Zur Definition wechseln | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; |
| Navigieren zu | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; |
| Alle Verweise suchen | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; |
| Automatischer Einzug | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; |
| Codeformatierung | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; |
| Umgestalten – Umbenennen | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; |
| Umgestalten – Methode extrahieren | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; |
| Umgestalten – Import hinzufügen/entfernen | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; |
| PyLint | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; |
<br/>

| Interaktives Fenster | 2017 | 2015 | 2013 Comm | 2013 Desktop | 2013 Web | 2013 Pro+ | 2012 Pro+ | 2010 SP1 Pro+ |
| --- | --- | --- | --- | --- | --- | --- | --- | ---|
| Interaktives Fenster | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; |
| IPython mit Inlinediagrammen | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; |
<br/>

| Desktop | 2017 | 2015 | 2013 Comm | 2013 Desktop | 2013 Web | 2013 Pro+ | 2012 Pro+ | 2010 SP1 Pro+ |
| --- | --- | --- | --- | --- | --- | --- | --- | ---|
| Konsole/Windows-Anwendung | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; |
| IronPython WPF (mit XAML-Designer) | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; |
| IronPython Windows Forms | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; |
<br/>

| Web | 2017 | 2015 | 2013 Comm | 2013 Desktop | 2013 Web | 2013 Pro+ | 2012 Pro+ | 2010 SP1 Pro+ |
| --- | --- | --- | --- | --- | --- | --- | --- | ---|
| Django-Webprojekt | &#10004; | &#10004; | &#10004; | &#10007; | &#10004; | &#10004; | &#10004; | &#10004; |
| Bottle-Webprojekt | &#10004; | &#10004; | &#10004; | &#10007; | &#10004; | &#10004; | &#10004; | &#10004; |
| Flask-Webprojekt | &#10004; | &#10004; | &#10004; | &#10007; | &#10004; | &#10004; | &#10004; | &#10004; |
| Generisches Webprojekt | &#10004; | &#10004; | &#10004; | &#10007; | &#10004; | &#10004; | &#10004; | &#10004; |
<br/>

| Azure | 2017 | 2015 | 2013 Comm | 2013 Desktop | 2013 Web | 2013 Pro+ | 2012 Pro+ | 2010 SP1 Pro+ |
| --- | --- | --- | --- | --- | --- | --- | --- | ---|
| Bereitstellung auf einer Website | &#10004; | &#10004; | &#10004; | &#10007; | &#10004; | &#10004; | &#10004; | &#10004;<sup>2</sup> |
| Bereitstellung für eine Webrolle | &#10004; | &#10004; | &#10004; | &#10007; | &#10004;<sup>4</sup> | &#10004;<sup>4</sup> | &#10004;<sup>3</sup> | &#10007; |
| Bereitstellung für eine Workerrolle | ? | ? | ? | &#10007; | &#10004;<sup>4</sup> | &#10004;<sup>4</sup> | &#10004;<sup>3</sup> | &#10007; |
| Ausführen im Azure-Emulator | ? | ? | ? | &#10007; | &#10004;<sup>4</sup> | &#10004;<sup>4</sup> | &#10004;<sup>3</sup> | &#10007; |
| Remotedebuggen | &#10004; | &#10004; | &#10004; | &#10007; | &#10004;<sup>6</sup> | &#10004;<sup>8</sup> | &#10004;<sup>8</sup> | &#10007; |
| Anfügen im Server-Explorer | &#10004; | &#10004; | &#10004; | &#10007; | &#10004;<sup>7</sup> | &#10004;<sup>7</sup> | &#10007; | &#10007; |
<br/>

| Django-Vorlagen | 2017 | 2015 | 2013 Comm | 2013 Desktop | 2013 Web | 2013 Pro+ | 2012 Pro+ | 2010 SP1 Pro+ |
| --- | --- | --- | --- | --- | --- | --- | --- | ---|
| Debuggen | &#10004; | &#10004; | &#10004; | &#10007; | &#10004; | &#10004; | &#10004; | &#10004; |
| Automatische Vervollständigung | &#10004; | &#10004; | &#10004; | &#10007; | &#10004;<sup>5</sup> | &#10004;<sup>5</sup> | &#10004; | &#10004; |
| Automatische Vervollständigung für CSS und JavaScript | &#10004; | &#10004; | &#10004; | &#10007; | &#10004;<sup>5</sup> | &#10004;<sup>5</sup> | &#10007; | &#10007; |
<br/>

| Debuggen | 2017 | 2015 | 2013 Comm | 2013 Desktop | 2013 Web | 2013 Pro+ | 2012 Pro+ | 2010 SP1 Pro+ |
| --- | --- | --- | --- | --- | --- | --- | --- | ---|
| Debuggen | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; |
| Debuggen ohne ein Projekt | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; |
| Debuggen – Anfügen an Bearbeitung | &#10004; | &#10004; | &#10004; | &#10004; | &#10007; | &#10004; | &#10004; | &#10004; |
| Debuggen im gemischten Modus | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10007; |
| Remotedebuggen (Windows, Mac OS X, Linux) | &#10004; | &#10004; | &#10004; | &#10004; | &#10007; | &#10004; | &#10004; | &#10004; |
| Debuggen im interaktiven Fenster | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; |
<br/>

<a name="matrix-profiling"></a>

| Profilerstellung | 2017 | 2015 | 2013 Comm | 2013 Desktop | 2013 Web | 2013 Pro+ | 2012 Pro+ | 2010 SP1 Pro+ |
| --- | --- | --- | --- | --- | --- | --- | --- | ---|
| Profilerstellung | &#10004; | &#10004; | &#10004; | &#10007; | &#10007; | &#10004; | &#10004; | &#10004; |
<br/>

| Test | 2017 | 2015 | 2013 Comm | 2013 Desktop | 2013 Web | 2013 Pro+ | 2012 Pro+ | 2010 SP1 Pro+ |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
| Test-Explorer | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10007; |
| Test ausführen | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10007; |
| Test debuggen | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10007; |
<br/>

1. Git-Unterstützung für Visual Studio 2012 steht in der Erweiterung Visual Studio-Tools für Git zur Verfügung (verfügbar im [Visual Studio-Katalog](http://visualstudiogallery.msdn.microsoft.com/abafc7d6-dcaa-40f4-8a5e-d6724bdb980c)).

1. Für die Bereitstellung auf der Azure-Website ist das [Azure SDK für .NET 2.1 – Visual Studio 2010 SP1](http://go.microsoft.com/fwlink/?LinkId=313855) erforderlich. Höhere Versionen unterstützen Visual Studio 2010 nicht.

1. Für die Unterstützung von Azure-Webrollen und -Workerrollen ist das [Azure SDK für .NET 2.3 – VS 2012](http://go.microsoft.com/fwlink/?LinkId=323511) oder höher erforderlich.

1. Für die Unterstützung von Azure-Webrollen und -Workerrollen ist das [Azure SDK für .NET 2.3 – VS 2013](http://go.microsoft.com/fwlink/?LinkId=323510) oder höher erforderlich.

1. Der Django-Vorlagen-Editor in Visual Studio 2013 weist einige bekannte Probleme auf, die durch die Installation von Update 2 gelöst werden.

1. Erfordert mindestens Windows 8. Visual Studio 2013 Express für Web weist kein Dialogfeld „An den Prozess anhängen“ auf. Remotedebuggen für Azure-Websites ist allerdings über den Befehl „Debugger anfügen“ (Python) im Server-Explorer möglich. Für das Remotedebuggen ist das [Azure SDK für .NET 2.3 – Visual Studio 2013](http://go.microsoft.com/fwlink/?LinkId=323510) oder höher erforderlich.

1. Erfordert mindestens Windows 8. Für den Befehl „Debugger anfügen“ (Python) im Server-Explorer ist das [Azure SDK für .NET 2.3 – Visual Studio 2013](http://go.microsoft.com/fwlink/?LinkId=323510) oder höher erforderlich.

1. Erfordert mindestens Windows 8.

## <a name="additional-resources"></a>Zusätzliche Ressourcen

- [WFastCGI-Brücke zwischen IIS und Python](https://pypi.org/p/wfastcgi) (pypi.org)
- [Kostenlose Python-Kurse in der Microsoft Virtual Academy](https://mva.microsoft.com/search/SearchResults.aspx#!q=python)
- [Top Python Questions at Microsoft Virtual Academy (Meistgestellte Fragen an der Microsoft Virtual Academy)](https://aka.ms/mva-top-python-questions)
