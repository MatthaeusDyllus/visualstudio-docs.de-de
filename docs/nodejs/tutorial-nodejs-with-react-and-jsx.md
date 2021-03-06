---
title: Erstellen von Node.js- und Express-Apps
description: In diesem Tutorial erfahren Sie, wie Sie mithilfe von Node.js-Tools für Visual Studio eine App erstellen.
ms.custom: mvc
ms.date: 02/19/2018
ms.technology: vs-nodejs
ms.topic: tutorial
ms.devlang: javascript
author: mikejo5000
ms.author: mikejo
manager: douge
dev_langs:
- JavaScript
ms.workload:
- nodejs
ms.openlocfilehash: 9958711ea64daee9876d3b16330685786b6d5825
ms.sourcegitcommit: b400528a83bea06d208d95c77282631ae4a93091
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/23/2018
ms.locfileid: "34454622"
---
# <a name="tutorial-create-a-nodejs-and-react-app-in-visual-studio"></a>Tutorial: Erstellen einer Node.js- und React-App in Visual Studio
Mit Visual Studio können Sie problemlos ein Node.js-Projekt erstellen sowie IntelliSense und andere integrierte Features nutzen, die Node.js unterstützen. In diesem Tutorial für Visual Studio erstellen Sie ein Node.js-Webanwendungsprojekt aus einer Visual Studio-Vorlage. Anschließend erstellen Sie mithilfe von React eine einfache App.

In diesem Tutorial lernen Sie, wie die folgenden Aufgaben ausgeführt werden:
> [!div class="checklist"]
> * Erstellen eines Node.js-Projekts
> * Hinzufügen von NPM-Paketen
> * Hinzufügen von React-Code zur App
> * Transpilieren von JSX
> * Fügen Sie den Debugger an.

## <a name="prerequisites"></a>Erforderliche Komponenten

* Sie müssen Visual Studio 2017 und die Workload für die Node.js-Entwicklung installiert haben.

    Falls Sie Visual Studio noch nicht installiert haben, können Sie es [hier](http://www.visualstudio.com) gratis herunterladen.

    Falls Sie über Visual Studio bereits verfügen, aber die Workload noch installieren müssen, klicken Sie auf den Link **Visual Studio-Installer öffnen** im linken Bereich des Dialogfelds **Neues Projekt**. Der Visual Studio-Installer wird gestartet. Klicken Sie auf die Workload **Node.js-Entwicklung** und anschließend auf **Ändern**.

* Die Node.js-Laufzeit muss installiert sein.

    Wenn sie nicht bereits installiert ist, installieren Sie die LTS-Version über die [Node.js](https://nodejs.org/en/download/)-Website. Im Allgemeinen erkennt Visual Studio die installierte Node.js-Runtime automatisch. Wird die installierte Laufzeit nicht erkannt, können Sie das Projekt so konfigurieren, dass es auf die installierte Laufzeit auf der Eigenschaftenseite verweist (klicken Sie hierfür nach dem Erstellen des Projekts mit der rechten Maustaste auf den Projektknoten, und wählen Sie **Eigenschaften** aus).

    Dieses Tutorial wurde mit der Version 8.9.4 getestet.

## <a name="create-a-project"></a>Erstellen eines Projekts
Erstellen Sie zunächst ein Projekt für die Node.js-Webanwendung.

1. Öffnen Sie Visual Studio 2017.

1. Klicken Sie in der Menüleiste im oberen Bereich auf **Datei** > **Neu** > **Projekt...**.

1. Erweitern Sie im Dialogfeld **Neues Projekt** im linken Bereich den Eintrag **JavaScript**, und klicken Sie auf **Node.js**. Klicken Sie im mittleren Bereich auf **Leere Node.js-Webanwendung**, geben Sie den Namen **NodejsWebAppBlank** ein, und klicken Sie anschließend auf **OK**.

     Wenn die Projektvorlage **Leere Node.js-Webanwendung** nicht angezeigt wird, müssen Sie zunächst die Workload für die Node.js-Entwicklung installieren.

    Visual Studio erstellt die neue Projektmappe und öffnet das Projekt.

    ![Node.js-Projekt im Projektmappen-Explorer](../nodejs/media/tutorial-nodejs-react-project-structure.png)

    - Ihr Projekt wird fettgedruckt dargestellt, mit dem Namen, den Sie im Dialogfeld **Neues Projekt** festgelegt haben. Im Dateisystem wird dieses Projekt durch eine *NJSPROJ*-Datei im Projektordner dargestellt. Klicken Sie mit der rechten Maustaste auf das Projekt, und wählen Sie **Eigenschaften** aus, um Eigenschaften und Umgebungsvariablen festzulegen, die dem Projekt zugeordnet sind. Roundtrips mit anderen Entwicklungstools sind möglich, da die Projektdatei keine benutzerdefinierte Änderungen an der Node.js-Projektquelle vornimmt.

    - Auf der oberen Ebene finden Sie eine Projektmappe, die standardmäßig denselben Namen hat wie Ihr Projekt. Eine Projektmappe, die auf dem Datenträger durch eine *SLN*-Datei dargestellt wird, ist ein Container für mindestens ein zugehöriges Projekt.

    - Der npm-Knoten zeigt alle installierten npm-Pakete. Sie können mit der rechten Maustaste darauf klicken, um über ein Dialogfeld npm-Pakete zu suchen und zu installieren.

    - Projektdateien wie z.B. *server.js* werden unter dem Projektknoten angezeigt. Die Startdatei des Projekts lautet *server.js*.

## <a name="add-npm-packages"></a>Hinzufügen von NPM-Paketen

Diese App erfordert mehrere NPM-Module, damit sie ordnungsgemäß ausgeführt wird.

* react
* react-dom
* express
* path
* ts-loader
* typescript
* webpack
* webpack-cli

1. Klicken Sie im Projektmappen-Explorer (rechter Bereich) mit der rechten Maustaste auf den **NPM**-Knoten im Projekt, und wählen Sie **Neue NPM-Pakete installieren** aus.

    Wählen Sie im Dialogfeld **Neue NPM-Pakete installieren** die aktuellste Paketversion aus, oder geben Sie eine Version an, die Sie installieren möchten. Wenn Sie die aktuelle Version dieser Pakete installieren, jedoch zu einem späteren Zeitpunkt unerwartete Fehler auftreten, müssen Sie möglicherweise die weiter unten beschriebenen Paketversionen installieren.

1. Suchen Sie im Dialogfeld **Neue NPM-Pakete installieren** das React-Paket, und klicken Sie auf **Paket installieren**, um es zu installieren.

    ![NPM-Pakete installieren](../nodejs/media/tutorial-nodejs-react-install-packages.png)

    Im Fenster **Ausgabe** wird der Fortschritt beim Installieren des Pakets angezeigt. Nach dem Installieren wird das Paket unter dem **NPM**-Knoten angezeigt.

    Die *package.json*-Datei des Projekts wird mit den neuen Paketinformationen einschließlich der Paketversion aktualisiert.

1. Verwenden Sie anstelle der Benutzeroberfläche den folgenden Code, und fügen Sie ihn in „package.json“ ein, um nach den restlichen Paketen zu suchen und sie hinzuzufügen. Ersetzen Sie den `dependencies`-Abschnitt durch den folgenden Code:

    ```js
    "dependencies": {
      "express": "4.16.2",
      "path": "0.12.7",
      "react": "16.2.0",
      "react-dom": "16.2.0",
      "ts-loader": "4.0.1",
      "typescript": "2.7.2",
      "webpack": "4.1.1",
      "webpack-cli": "2.0.11"
    }
    ```

1. Klicken Sie mit der rechten Maustaste auf den **NPM**-Knoten im Projekt, und wählen Sie **Fehlende NPM-Pakete installieren** aus.

    Im Fenster **Ausgabe** wird der Fortschritt beim Installieren der Pakete angezeigt.

    Die folgenden NPM-Module werden im Projektmappen-Explorer angezeigt, nachdem sie installiert wurden.

    ![NPM-Pakete](../nodejs/media/tutorial-nodejs-react-npm-modules.png)

    > [!NOTE]
    > Wenn Sie NPM-Pakete über die Befehlszeile installieren möchten, klicken Sie mit der rechten Maustaste auf den Projektknoten, und klicken Sie dann auf **Eingabeaufforderung hier öffnen**. Verwenden Sie die Node.js-Standardbefehle, um die Pakete zu installieren.

## <a name="add-project-files"></a>Hinzufügen von Projektdateien

Mit den folgenden Schritten fügen Sie dem Projekt vier neue Dateien hinzu.

* *app.tsx*
* *webpack-config.js*
* *index.html*
* *tsconfig.json*

Fügen Sie für diese einfache App die neuen Projektdateien dem Projektstammverzeichnis hinzu. (In den meisten Apps werden die Dateien in der Regel Unterordnern hinzugefügt und die relativen Pfadverweise entsprechend angepasst.)

1. Klicken Sie im Projektmappen-Explorer mit der rechten Maustaste auf das Projekt **NodejsWebAppBlank**, und klicken Sie auf **Hinzufügen** > **Neues Element**.

1. Klicken Sie im Dialogfeld **Neues Element hinzufügen** auf **TypeScript JSX-Datei**, geben Sie den Namen *app.tsx* ein, und klicken Sie auf **OK**.

1. Wiederholen Sie diese Schritte, um die Datei *webpack-config.js* hinzuzufügen.

1. Wiederholen Sie dieselben Schritte, um dem Projekt die Datei *index.html* hinzuzufügen. Wählen Sie anstelle einer JavaScript-Datei die Option **HTML-Datei** aus.

1. Wiederholen Sie dieselben Schritte, um dem Projekt die Datei *tsconfig.json* hinzuzufügen. Wählen Sie anstelle einer JavaScript-Datei die Option **TypeScript-JSON-Konfigurationsdatei** aus.

## <a name="add-app-code"></a>Hinzufügen von App-Code

1. Öffnen Sie *server.js*, und ersetzen Sie den Code durch den folgenden:

    ```javascript
    'use strict';
    var path = require('path');
    var express = require('express');

    var app = express();

    var staticPath = path.join(__dirname, '/');
    app.use(express.static(staticPath));

    // Allows you to set port in the project properties.
    app.set('port', process.env.PORT || 3000);

    var server = app.listen(app.get('port'), function() {
        console.log('listening');
    });
    ```

   Der vorherige Code verwendet Express, um Node.js als Webanwendungsserver zu starten. Dieser Code legt den Port auf die Portnummer fest, die in den Projekteigenschaften konfiguriert wird (die Standard-Portnummer in den Eigenschaften lautet 1337). Klicken Sie zum Öffnen der Projekteigenschaften im Projektmappen-Explorer mit der rechten Maustaste auf das Projekt, und wählen Sie **Eigenschaften** aus.

1. Öffnen Sie *app.tsx*, und fügen Sie den folgenden Code hinzu:

    ```javascript
    declare var require: any

    var React = require('react');
    var ReactDOM = require('react-dom');

    class Hello extends React.Component {
        render() {
            return (
                <h1>Welcome to React!!</h1>
            );
        }
    }

    ReactDOM.render(<Hello />, document.getElementById('root'));
    ```

    Der vorherige Code verwendet zum Anzeigen einer einfachen Nachricht JSX-Syntax und React.

1. Öffnen Sie *index.html*, und ersetzen Sie den **body**-Abschnitt durch den folgenden Code:

    ```html
    <body>
        <div id="root"></div>
        <!-- scripts -->
        <script src="./dist/app-bundle.js"></script>
    </body>
    ```

    Diese HTML-Seite lädt die Datei *app-bundle.js*, die den in einfaches JavaScript transpilierten JSX- und React-Code enthält. *app-bundle.js* ist momentan eine leere Datei. Im nächsten Abschnitt konfigurieren Sie Optionen, um den Code zu transpilieren.

## <a name="configure-webpack-and-typescript-compiler-options"></a>Konfigurieren von Webpack- und TypeScript-Compileroptionen

In den vorherigen Schritten haben Sie dem Projekt die Datei *webpack-config.js* hinzugefügt. Als Nächstes fügen Sie Webpack-Konfigurationscode hinzu. Sie fügen eine einfache Webpack-Konfiguration zur Angabe einer Eingabedatei (*app.tsx*) und einer Ausgabedatei (*app-bundle.js*) hinzu, um JSX in einfaches JavaScript zu bündeln und zu transpilieren. Für die Transpilierung konfigurieren Sie auch mehrere TypeScript-Compileroptionen. Dieser Code stellt eine Basiskonfiguration als Einführung in Webpack und den TypeScript-Compiler dar.

1. Öffnen Sie im Projektmappen-Explorer die Datei *webpack-config.js*, und fügen Sie den folgenden Code hinzu:

    ```json
    module.exports = {
        devtool: 'source-map',
        entry: "./app.tsx",
        mode: "development",
        output: {
            filename: "./app-bundle.js"
        },
        resolve: {
            extensions: ['.Webpack.js', '.web.js', '.ts', '.js', '.jsx', '.tsx']
        },
        module: {
            rules: [
                {
                    test: /\.tsx$/,
                    exclude: /(node_modules|bower_components)/,
                    use: {
                        loader: 'ts-loader'
                    }
                }
            ]
        }
    }
    ```

    Durch den Webpack-Konfigurationscode verwendet Webpack das TypeScript-Ladeprogramm, um JSX zu transpilieren.

1. Öffnen Sie „tsconfig.json“, und fügen Sie den folgenden Code hinzu, der die TypeScript-Compileroptionen angibt:

    ```json
    {
      "compilerOptions": {
        "noImplicitAny": false,
        "module": "commonjs",
        "noEmitOnError": true,
        "removeComments": false,
        "sourceMap": true,
        "target": "es5",
        "jsx": "react"
      },
      "exclude": [
        "node_modules"
      ],
      "files": [
        "app.tsx"
      ]
    }
    ```

    „app.tsx“ wird als Quelldatei angegeben.

## <a name="transpile-the-jsx"></a>Transpilieren von JSX

1. Klicken Sie im Projektmappen-Explorer mit der rechten Maustaste auf den Projektknoten, und wählen Sie **Eingabeaufforderung hier öffnen** aus.

1. Geben Sie in der Eingabeaufforderung folgenden Befehl ein:

    `node_modules\.bin\webpack app.tsx --config webpack-config.js`

    Das Ergebnis wird im Fenster „Eingabeaufforderung“ angezeigt.

    ![Ausführen von Webpack](../nodejs/media/tutorial-nodejs-react-run-webpack.png)

    Werden anstatt der vorherigen Ausgabe Fehler angezeigt, müssen Sie diese beheben, damit Ihre App funktioniert. Wenn sich Ihre NPM-Paketversionen von den in diesem Tutorial verwendeten Versionen unterscheiden, kann dies eine der Fehlerursachen darstellen. Sie können die Fehler beheben, indem Sie exakt die in den vorherigen Schritten beschriebenen Versionen verwenden. Zudem müssen Sie möglicherweise zum Beheben der Fehler eine neuere Version installieren, wenn eine oder mehrere der Paketversionen als veraltet markiert wurden und zu einem Fehler führen.

1. Klicken Sie im Projektmappen-Explorer mit der rechten Maustaste auf den Projektknoten, und wählen Sie **Hinzufügen** > **Vorhandener Ordner** aus. Klicken Sie anschließend auf den *dist*-Ordner und auf **Ordner auswählen**.

    Visual Studio fügt dem Projekt den *dist*-Ordner hinzu, der die Dateien *app-bundle.js* und *app-bundle.js.map* enthält.

1. Öffnen Sie zum Anzeigen des transpilierten JavaScript-Codes die Datei *app-bundle.js*.

1. Wenn Sie aufgefordert werden, die extern geänderten Dateien erneut zu laden, klicken Sie auf **Ja, alle**.

    ![Laden geänderter Dateien](../nodejs/media/tutorial-nodejs-react-reload-files.png)

Bei jeder Änderung, die Sie an *app.tsx* vornehmen, müssen Sie den Webpack-Befehl erneut ausführen.

## <a name="run-the-app"></a>Ausführen der App

1. Vergewissern Sie sich, dass Chrome als aktuelles Debugziel ausgewählt ist.

    ![Auswählen von Chrome als Debugziel](../nodejs/media/tutorial-nodejs-react-debug-target.png)

1. Drücken Sie zum Ausführen der App **F5** (**Debuggen** > **Debuggen starten**), oder klicken Sie auf die Schaltfläche mit dem grünen Pfeil.

    Ein Node.js-Konsolenfenster wird geöffnet, in dem der Port angezeigt wird, den der Debugger abhört.

    Visual Studio startet die Anwendung durch Öffnen der Startdatei *server.js*.

    ![Ausführen von React im Browser](../nodejs/media/tutorial-nodejs-react-running-react.png)

1. Schließen Sie das Browserfenster.

1. Schließen Sie das Konsolenfenster.

## <a name="set-a-breakpoint-and-run-the-app"></a>Festlegen eines Haltepunkts und Ausführen der App

1. Klicken Sie in *server.js* auf den Bundsteg links neben der `staticPath`-Deklaration, um einen Haltepunkt festzulegen:

    ![Haltepunkt festlegen](../nodejs/media/tutorial-nodejs-react-set-breakpoint.png)

    Haltepunkte sind eine einfache und wichtige Funktion zum zuverlässigen Debuggen. Ein Haltepunkt gibt an, wo Visual Studio im ausgeführten Code angehalten werden soll. So können Sie einen Blick auf die Werte von Variablen oder das Speicherverhalten werfen oder überprüfen, ob eine Verzweigung im Code ausgeführt wird.

1. Drücken Sie **F5** (**Debuggen** > **Debuggen starten**), um die App auszuführen.

    Der Debugger hält an dem von Ihnen festgelegten Haltepunkt an (die aktuelle Anweisung ist gelb gekennzeichnet). Jetzt können Sie den App-Status überprüfen, indem Sie auf die derzeitigen Variablen im Bereich zeigen. Verwenden Sie dafür Debuggerfenster wie **Lokal** und **Überwachen**.

1. Drücken Sie **F5**, um die App fortzusetzen.

1. Wenn Sie die Chrome-Entwicklertools verwenden möchten, drücken Sie **F12**. Mit diesen Tools können Sie das DOM untersuchen und mithilfe der JavaScript-Konsole mit der App interagieren.

1. Schließen Sie den Webbrowser und die Konsole.

## <a name="set-and-hit-a-breakpoint-in-the-client-side-react-code"></a>Festlegen und Erreichen eines Haltepunkts im clientseitigen React-Code

Im vorherigen Abschnitt haben Sie den Debugger an den serverseitigen Node.js-Code angehängt. Wenn der Debugger von Visual Studio angehängt werden und Haltepunkte im clientseitigen React-Code erreichen soll, benötigt er Hilfe beim Identifizieren des richtigen Prozesses. Eine Möglichkeit, dies zu erreichen, ist die folgende:

1. Schließen Sie alle Chrome-Fenster.

1. Öffnen Sie über das Windows-**Startmenü** den Befehl **Ausführen** (klicken Sie mit der rechten Maustaste auf die Schaltfläche, und wählen Sie **Ausführen** aus), und geben Sie den folgenden Befehl ein:

    `chrome.exe --remote-debugging-port=9222`

    Dadurch wird Chrome mit aktiviertem Debuggen gestartet.

1. Wechseln Sie zu Visual Studio, und legen Sie wie in der folgenden Abbildung dargestellt einen Haltepunkt im *app-bundle.js*-Code in der `render()`-Funktion fest:

    ![Haltepunkt festlegen](../nodejs/media/tutorial-nodejs-react-set-breakpoint-client-code.png)

1. Wenn Chrome bereits als Debugziel in Visual Studio ausgewählt wurde, drücken Sie **STRG+F5** (**Debuggen** > **Starten ohne Debuggen**), um die App im Browser auszuführen.

    Die App wird daraufhin in einer neuen Registerkarte im Browser geöffnet.

1. Wählen Sie **Debuggen** > **An den Prozess anhängen** aus.

1. Wählen Sie im Dialogfeld **An den Prozess anhängen** im Feld **Anhängen an** den Eintrag **WebKit-Code** aus. Geben Sie im Filterfeld **Chrome** ein, um die Suchergebnisse zu filtern.

1. Wählen Sie den Chrome-Prozess mit dem richtigen Hostport aus (in diesem Beispiel 1337), und klicken Sie auf **Anhängen**.

    ![Anhängen an den Prozess](../nodejs/media/tutorial-nodejs-react-attach-to-process.png)

    Der Debugger wurde ordnungsgemäß angehängt, wenn DOM Explorer und die JavaScript-Konsole in Visual Studio geöffnet werden. Diese Debugtools ähneln den Chrome-Entwicklertools und den F12-Tools für Edge.

    > [!NOTE]
    > Wenn der Debugger nicht angefügt wird, und die Meldung „Das Anfügen an den Prozess ist nicht möglich. Ein Vorgang ist für den derzeitigen Zustand unzulässig.“ angezeigt wird, verwenden Sie den Task-Manager, um alle Instanzen von Chrome zu schließen, bevor Sie Chrome im Debugmodus starten. Möglicherweise werden Chrome-Erweiterungen ausgeführt, die den vollständigen Debugmodus verhindern.

1. Da der Code mit dem Haltepunkt bereits ausgeführt wurde, aktualisieren Sie zum Erreichen des Haltepunkts die Browserseite.

    Während der Unterbrechung im Debugger können Sie den App-Status überprüfen, indem Sie mit dem Mauszeiger auf Variablen zeigen und Debuggerfenster verwenden. Sie können den Debugger durch Navigieren im Code nach vorne verschieben (**F5**, **F10** und **F11**).

    Sie können den Haltepunkt je nach Umgebung und Browserstatus entweder in *app-bundle.js* oder im zugeordneten Speicherort in *app.tsx* erreichen. In beiden Fällen können Sie durch den Code navigieren und Variablen überprüfen.

    * Wenn Sie in *app.tsx* Code unterbrechen müssen und dies nicht können, verwenden Sie **An den Prozess anhängen**, wie in den vorherigen Schritten beschrieben, um den Debugger anzuhängen. Öffnen Sie dann im Projektmappen-Explorer die dynamisch generierte *app.tsx*-Datei, indem Sie **Skriptdokumente** > **app.tsx** öffnen, einen Haltepunkt festlegen und die Seite in Ihrem Browser aktualisieren.

        Alternativ, wenn Sie Code in einer *app.tsx*-Datei unterbrechen müssen, dies jedoch nicht möglich ist, verwenden Sie die `debugger;`-Anweisung in *app.tsx*, oder legen Sie Haltepunkte in den Chrome-Entwicklertools fest.

    * Wenn Sie Code in *app bundle.js* unterbrechen müssen, dies jedoch nicht möglich ist, entfernen Sie die Quellzuordnungsdatei *app bundle.js.map*.

    > [!TIP]
    > Sobald Sie mit diesen Schritten erstmalig an den Prozess angehängt haben, können Sie in Visual Studio 2017 schnell erneut an diesen Prozess anhängen, indem Sie **Debuggen** > **Erneut an Prozess anhängen** auswählen.

## <a name="next-steps"></a>Nächste Schritte

In diesem Tutorial haben Sie erfahren, wie eine Node.js- und React-App erstellt, JSX transpiliert und Debugging ausgeführt wird. Weitere Informationen zu den Node.js-Tools für Visual Studio finden Sie auf der entsprechenden Wiki-Seite.

> [!div class="nextstepaction"]
> [Node.js-Tools für Visual Studio](https://github.com/Microsoft/nodejstools)
