---
title: Webanwendungsvorlagen für Python
description: Eine Übersicht der Visual Studio-Vorlagen für in Python mithilfe der Bottle-, Flask- und Django-Frameworks erstellte Webanwendungen, einschließlich Debugkonfigurationen und Veröffentlichung im Azure App Service.
ms.date: 04/17/2018
ms.prod: visual-studio-dev15
ms.technology: vs-python
ms.topic: conceptual
author: kraigb
ms.author: kraigb
manager: douge
ms.workload:
- python
- data-science
ms.openlocfilehash: 6d76bc7868c78b1def09376cb2382aa39cff1cda
ms.sourcegitcommit: 928885ace538bef5b25961358d4f166d648f196a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/27/2018
---
# <a name="python-web-application-project-templates"></a>Projektvorlagen für Python-Webanwendungen

Python in Visual Studio unterstützt das Entwickeln von Webprojekten in Bottle-, Flask- und Django-Frameworks mit Projektvorlagen und einem Debugstartprogramm, das so konfiguriert werden kann, dass es mehrere Frameworks behandeln kann. Diese Vorlagen enthalten eine `requirements.txt`-Datei, um die erforderlichen Abhängigkeiten zu deklarieren. Wenn Sie ein Projekt aus einer dieser Vorlagen erstellen, fordert Visual Studio Sie dazu auf, diese Pakete zu installieren (siehe [Installieren der Projektanforderungen](#installing-project-requirements) weiter unten in diesem Artikel).

Sie können auch die generische Vorlage „Webprojekt“ für andere Frameworks wie z.B Pyramid verwenden. In diesem Fall werden keine Frameworks mit der Vorlage installiert. Installieren Sie stattdessen die erforderlichen Pakete in der Umgebung, die Sie für das Projekt verwenden (siehe [Verwalten von Python-Umgebungen](managing-python-environments-in-visual-studio.md)).

## <a name="using-a-project-template"></a>Verwenden einer Projektvorlage

Erstellen Sie mit **Datei** > **Neu** > **Projekt** ein neues Projekt aus einer Vorlage. Klicken Sie auf der linken Seite des Dialogfelds auf **Python** > **Web**, um Vorlagen für Webprojekte anzuzeigen. Wählen Sie dann eine Vorlage Ihrer Wahl aus, geben Sie Namen für das Projekt und die Projektmappe an, legen Sie Optionen für ein Projektmappenverzeichnis und Git-Repository fest, und klicken Sie auf **OK**.

![Dialogfeld „Neues Projekt“ für Web-Apps](media/projects-new-project-dialog-web.png)

Die zuvor erwähnte allgemeine Vorlage „Webprojekt“ stellt nur ein leeres Visual Studio-Projekt ohne Code bereit, das keine Annahmen trifft, außer dass es ein Python-Projekt ist. Ausführliche Informationen zur Vorlage „Azure Cloud Service“ finden Sie unter [Azure Cloud Service-Projekte für Python](python-azure-cloud-service-project-template.md).python-azure-cloud-service-project-template.md.

Alle anderen Vorlagen basieren auf dem Web-Frameworks Bottle, Flask oder Django und fallen in die drei Gruppen, die in den folgenden Abschnitten beschrieben werden. Apps, die mit diesen Vorlagen erstellt werden, enthalten ausreichend Code, um sie lokal auszuführen und zu debuggen. Jede Vorlage stellt auch das erforderliche [WSGI-App-Objekt](http://www.python.org/dev/peps/pep-3333/) (python.org) für die [Veröffentlichung in Azure App Service](publishing-python-web-applications-to-azure-from-visual-studio.md) zur Verfügung.

### <a name="blank-group"></a>Leere Gruppe

Alle Vorlagen für „leere (Framework)-Webprojekte“ erstellen ein Projekt mit mehr oder weniger gering gehaltenen Codebausteinen und den erforderlichen in einer `requirements.txt`-Datei deklarierten Abhängigkeiten.

| Vorlage | description |
| --- | --- |
| Leeres Bottle-Webprojekt | Generiert eine minimale App in `app.py` mit einer Homepage für `/` und einer `/hello/<name>`-Seite, die `<name>` mithilfe einer sehr kurzen Vorlage für eine Inline-Seite wiederholt. |
| Leeres Django-Webprojekt | Generiert ein Django-Projekt mit der grundlegenden Django-Websitestruktur, aber ohne Django-Apps. Weitere Informationen finden Sie unter [Django-Vorlagen](python-django-web-application-project-template.md) und [Learning Django Step 1 (Schritt 1 des Django-Tutorials)](learn-django-in-visual-studio-step-01-project-and-solution.md). |
| Leeres Flask-Webprojekt | Generiert eine minimale App mit einer einzelnen „Hallo Welt!“-Website für `/`. Diese App ähnelt dem Ergebnis der detaillierten exemplarischen Vorgehensweise unter [Schnellstart: Erstellen einer ersten Python-Web-App mit Visual Studio](../ide/quickstart-python.md?context=visualstudio/python/default).

### <a name="web-group"></a>Web-Gruppe

Alle Vorlagen für „(Framework)-Webprojekte“ erstellen eine Web-App mit einem identischen Design, unabhängig vom ausgewählten Framework. Die App verfügt über die Seiten „Home“, „Info“ und „Kontakte“ sowie einer Navigationsleiste und reaktives Design über Bootstrap. Jede App wird entsprechend der statischen Serverdateien (CSS, JavaScript und Schriftarten) konfiguriert und verwendet einen Seitenvorlagenmechanismus entsprechend dem Framework.

| Vorlage | description |
| --- | --- |
| Bottle-Webprojekt | Generiert eine App, bei der die statischen Dateien im Ordner `static` enthalten und durch den Code in `app.py` verarbeitet werden. Das Routing für die individuellen Seiten wird in `routes.py` enthalten, und der Ordner `views` enthält die Seitenvorlagen.|
| Django-Webprojekt | Generiert ein Django-Projekt und eine Django-App mit drei Seiten, Authentifizierungsunterstützung und einer SQLite-Datenbank (jedoch ohne Datenmodelle). Weitere Informationen finden Sie unter [Django-Vorlagen](python-django-web-application-project-template.md) und [Learning Django Step 4 (Schritt 4 des Django-Tutorials)](learn-django-in-visual-studio-step-04-full-django-project-template.md). |
| Flask-Webprojekt | Generiert eine App, bei der die statischen Dateien im Ordner `static` enthalten werden. Der Code in `views.py` verarbeitet das Routing mithilfe von Seitenvorlagen, die die Jinja-Engine im Ordner `templates` verwenden. Die Datei `runserver.py` enthält den Startcode. |
| Flask/Jade-Webprojekt | Generiert dieselbe App wie die Vorlage „Flask-Webprojekt“, verwendet jedoch die Jade-Vorlagen-Engine. |

### <a name="polls-group"></a>Umfragen-Gruppe

Die Vorlagen „(Framework)-Webprojekt für Umfragen“ erstellen eine Web-App, mit der Benutzer bei verschiedenen Umfragen abstimmen können. Jede App baut auf der Struktur von Webprojektvorlagen auf, um eine Datenbank zu verwenden und die Umfragen und Benutzerantworten zu verwalten. Die Apps enthalten entsprechende Datenmodelle und eine spezielle App-Seite („/seed“), die Umfragen aus einer `samples.json`-Datei lädt.

| Vorlage | description |
| --- | --- |
| Bottle-Webprojekt für Umfragen | Generiert eine App, die für eine In-Memory Database, für MongoDB oder für Azure Table Storage ausgeführt werden kann, die mithilfe der Umgebungsvariable `REPOSITORY_NAME` konfiguriert wird. Die Codes für Datenmodelle und Datenspeicher werden in dem Ordner `models` enthalten. Die Datei `settings.py` enthält Code, um zu bestimmen, welcher Datenspeicher verwendet wird. |
| Django-Webprojekt für Umfragen | Generiert ein Django-Projekt und eine Django-App mit drei Seiten und einer SQLite-Datenbank. Enthält Anpassungen an der Django-Verwaltungsschnittstelle, um einem authentifizierten Administrator zu berechtigen, Umfragen zu erstellen und zu verwalten. Weitere Informationen finden Sie unter [Django-Vorlagen](python-django-web-application-project-template.md) und [Learning Django Step 6 (Schritt 6 des Django-Tutorials)](learn-django-in-visual-studio-step-06-polls-django-web-project-template.md). |
| Flask-Webprojekt für Umfragen | Generiert eine App, die für eine In-Memory Database, für MongoDB oder für Azure Table Storage ausgeführt werden kann, die mithilfe der Umgebungsvariable `REPOSITORY_NAME` konfiguriert wird. Die Codes für Datenmodelle und Datenspeicher werden in dem Ordner `models` enthalten. Die Datei `settings.py` enthält Code, um zu bestimmen, welcher Datenspeicher verwendet wird. Die App verwendet die Jinja-Engine für Seitenvorlagen. |
| Flask/Jade-Webprojekt für Umfragen | Generiert dieselbe App wie die Vorlage „Flask-Webprojekt für Umfragen“, verwendet jedoch die Jade-Vorlagen-Engine. |

## <a name="installing-project-requirements"></a>Installieren von Projektanforderungen

Wenn Sie ein Projekt über eine frameworkspezifische Vorlage erstellen, wird ein Dialogfeld angezeigt, das Ihnen bei der Installation der erforderlichen Pakete mit pip hilft. Zudem empfehlen wir die Verwendung einer [virtuellen Umgebung](selecting-a-python-environment-for-a-project.md#using-virtual-environments) für Webprojekte, damit beim Veröffentlichen der Website die richtigen Abhängigkeiten enthalten sind:

![Dialogfeld, über das die erforderlichen Pakete für eine Projektvorlage installiert werden](media/template-web-requirements-txt-wizard.png)

Wenn Sie die Quellcodeverwaltung verwenden, lassen Sie in der Regel den Ordner für virtuelle Umgebungen aus, da diese Umgebung mithilfe von `requirements.txt` wiederhergestellt werden kann. Der beste Weg zum Auslassen des Ordners ist, zunächst **Ich führe die Installation selbst durch** in der oben gezeigt Eingabeaufforderung auszuwählen und dann den automatischen Commit zu deaktivieren, bevor Sie die virtuelle Umgebung erstellen. Ausführliche Informationen finden Sie unter [Learning Django Tutorial - Steps 1-2 and 1-3 (Django-Tutorial: Schritte 1-2 und 1-3)](learn-django-in-visual-studio-step-01-project-and-solution.md#step-1-2-examine-the-git-controls-and-publish-to-a-remote-repository)

Wählen Sie bei der Bereitstellung in Microsoft Azure App Service eine Version von Python als [Websiteerweiterung](https://aka.ms/PythonOnAppService), und installieren Sie Pakete manuell. Da Pakete in Azure App Service bei Bereitstellung über Visual Studio **nicht** automatisch anhand einer `requirements.txt`-Datei installiert werden, befolgen Sie außerdem die Konfigurationsdetails unter [aka.ms/PythonOnAppService](https://aka.ms/PythonOnAppService).

Die `requirements.txt`-Datei hingegen wird in Microsoft Azure Cloud Services *unterstützt*. Ausführliche Informationen finden Sie unter [Projekte für Azure-Clouddienste](python-azure-cloud-service-project-template.md).

## <a name="debugging"></a>Debuggen

Wenn ein Webprojekt zum Debuggen gestartet wird, startet Visual Studio den lokalen Webserver auf einem zufälligen Port und öffnet Ihren Standardbrowser mit dieser Adresse und diesem Port. Um zusätzliche Optionen anzugeben, klicken Sie mit der rechten Maustaste auf das Projekt, wählen Sie **Eigenschaften** aus, und wählen Sie dann die Registerkarte **Webstartprogramm** aus:

![Eigenschaften des Webstartprogramms für die generische Webvorlage](media/template-web-launcher-properties.png)

Gruppe **Debuggen**:

- **Suchpfade**, **Skriptargumente**, **Interpreterargumente** und **Interpreterpfad**: Diese Optionen stimmen mit denen für das [normale Debuggen](debugging-python-in-visual-studio.md) überein.
- **Start-URL**: Gibt die URL an, die in Ihrem Browser geöffnet wird. Sie wird standardmäßig auf `localhost` festgelegt.
- **Portnummer**: Gibt den Port an, der verwendet wird, wenn in der URL keiner angegeben ist. (Standardmäßig wird er von Visual Studio automatisch ausgewählt.) Durch diese Eigenschaft können Sie den Standardwert der `SERVER_PORT`-Umgebungsvariablen außer Kraft setzen, der von den Vorlagen zur Konfiguration des Ports verwendet wird, auf den der lokale Debugserver lauscht.

Durch die Eigenschaften in den Gruppen **Serverbefehl ausführen** und **Debugserverbefehl** (letzterer befindet sich weiter unten und wird in der Abbildung nicht gezeigt) wird festgelegt, wie der Webserver gestartet wird. Da für viele Frameworks die Verwendung eines Skripts außerhalb des aktuellen Projekts erforderlich ist, kann das Skript hier konfiguriert und der Name des Startmoduls als Parameter übergeben werden.

- **Befehl**: Hierbei kann es sich um ein Python-Skript (`*.py`-Datei), einen Modulnamen (wie in `python.exe -m module_name`) oder eine einzelne Codezeile (wie in `python.exe -c "code"`) handeln. Der Wert in der Dropdownliste gibt an, welcher dieser Typen beabsichtigt ist.
- **Argumente**: Diese Argumente werden in der Befehlszeile nach dem Befehl übergeben.
- **Umgebung**: eine durch Zeilenumbrüche getrennte Liste von `NAME=VALUE`-Paaren, durch die die Umgebungsvariablen angegeben werden. Diese Variablen werden nach allen Eigenschaften festgelegt, durch die die Umgebung möglicherweise modifiziert wird (z.B. Portnummer und Suchpfade), und können daher diese Werte überschreiben.

Jede Projekteigenschaft oder Umgebungsvariable kann mit der MSBuild-Syntax angegeben werden. Beispiel: `$(StartupFile) --port $(SERVER_PORT)`.
`$(StartupFile)` ist der relative Pfad zur Startdatei, und `{StartupModule}` ist der importierbare Name der Startdatei. `$(SERVER_HOST)` und `$(SERVER_PORT)` sind normale Umgebungsvariablen, die durch die Eigenschaften **Start-URL** und **Portnummer**, automatisch oder durch die Eigenschaft **Umgebung** festgelegt werden.

> [!Note]
> Werte unter **Serverbefehl ausführen** werden mit dem Befehl **Debuggen > Server starten** oder STRG+F5 verwendet. Werte in der Gruppe **Debugserverbefehl** werden mit dem Befehl **Debuggen > Debugserver starten** oder F5 verwendet.

### <a name="sample-bottle-configuration"></a>Beispiel für eine Bottle-Konfiguration

Die Vorlage **Bottle-Webprojekt** enthält Codebausteine, die die erforderliche Konfiguration vornehmen. Eine importierte Bottle-App enthält diesen Code jedoch möglicherweise nicht. In diesem Fall wird die App durch die folgenden Einstellungen über das installierte `bottle`-Modul gestartet:

- Gruppe **Serverbefehl ausführen**:
  - **Befehl**: `bottle` (Modul)
  - **Argumente**: `--bind=%SERVER_HOST%:%SERVER_PORT% {StartupModule}:app`

- Gruppe **Debugserverbefehl**:
  - **Befehl**: `bottle` (Modul)
  - **Argumente**: `--debug --bind=%SERVER_HOST%:%SERVER_PORT% {StartupModule}:app`

Die `--reload`-Option wird nicht empfohlen, wenn Sie Visual Studio für das Debuggen verwenden.

### <a name="sample-pyramid-configuration"></a>Beispiel für eine Pyramid-Konfiguration

Pyramid-Apps werden derzeit am besten über das `pcreate`-Befehlszeilentool erstellt. Nachdem eine App erstellt wurde, kann sie mithilfe der Vorlage [Aus vorhandenem Python-Code](managing-python-projects-in-visual-studio.md#creating-a-project-from-existing-files) importiert werden. Wählen Sie danach die Anpassung **Generisches Webprojekt**, um die Optionen zu konfigurieren. Bei diesen Einstellungen wird davon ausgegangen, dass Pyramid in einer virtuellen Umgebung unter `..\env` installiert ist.

- Gruppe **Debuggen**:
  - **Serverport**: 6543 (bzw. entsprechend der Konfiguration in den INI-Dateien)

- Gruppe **Serverbefehl ausführen**:
  - Befehl: `..\env\scripts\pserve-script.py` (Skript)
  - Argumente: `Production.ini`

- Gruppe **Debugserverbefehl**:
  - Befehl: `..\env\scripts\pserve-script.py` (Skript)
  - Argumente: `Development.ini`

> [!Tip]
> Wahrscheinlich müssen Sie die Eigenschaft **Arbeitsverzeichnis** Ihres Projekts konfigurieren, da Pyramid-Apps sich in der Regel eine Verzeichnisebene unterhalb des Projektstamms befinden.

### <a name="other-configurations"></a>Weitere Konfigurationen

Wenn Sie Einstellungen für ein anderes Framework verwenden, die Sie teilen möchten, oder wenn Sie Einstellungen für ein anderes Framework anfordern möchten, öffnen Sie ein [Problem in GitHub](https://github.com/Microsoft/PTVS/issues).

## <a name="convert-a-project-to-azure-cloud-service"></a>Konvertieren eines Projekts in Azure Cloud Service

Mit dem Befehl **In Microsoft Azure Cloud Services-Projekt konvertieren** (Abbildung unten) wird Ihrer Projektmappe ein Clouddienst-Projekt hinzugefügt. Dieses Projekt umfasst die Bereitstellungseinstellungen und die Konfiguration für die zu verwendenden virtuellen Computer und Dienste. Verwenden Sie den Befehl **Veröffentlichen** im Cloudprojekt zur Bereitstellung in Cloud Services. Mit dem Befehl **Veröffentlichen** im Python-Projekt erfolgt die Bereitstellung weiterhin auf Websites. Weitere Informationen finden Sie unter [Azure Cloud Service-Projekte](python-azure-cloud-service-project-template.md).

![Befehl „In Microsoft Azure Cloud Services-Projekt konvertieren“](media/template-web-convert-menu.png)

## <a name="see-also"></a>Siehe auch

- [Python item templates reference (Referenz für Python-Elementvorlagen)](python-item-templates.md)
- [Veröffentlichen in Azure App Service](publishing-python-web-applications-to-azure-from-visual-studio.md)
