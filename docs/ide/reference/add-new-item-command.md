---
title: Befehl "Neues Element hinzufügen"
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-general
ms.topic: reference
f1_keywords:
- project.addnewitem
helpviewer_keywords:
- Add New Item command
- File.AddNewItem command
ms.assetid: 63b7df32-db83-463b-bbe7-7ff011fe5298
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 8084cdebf4cba1bf3bb79ac1fbf386837b977d97
ms.sourcegitcommit: fe5a72bc4c291500f0bf4d6e0778107eb8c905f5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/07/2018
---
# <a name="add-new-item-command"></a>Befehl "Neues Element hinzufügen"
Fügt der aktuellen Projektmappe ein neues Projektmappenelement wie eine HTM-, CSS-, TXT- oder Framesetdatei hinzu und öffnet dieses.

## <a name="syntax"></a>Syntax

```cmd
File.AddNewItem [filename] [/t:templatename] [/e:editorname]
```

## <a name="arguments"></a>Argumente
 `filename` ist optional. Der Pfad und der Dateiname des Elements, das der Projektmappe hinzugefügt werden soll.

## <a name="switches"></a>Schalter
 /t: `templatename` ist optional. Gibt den Typ der zu erstellenden Datei an. Wenn kein Vorlagenname angegeben wird, wird standardmäßig eine Textdatei erstellt.

 Die Argumentsyntax /t:`templatename` gibt die im Dialogfeld **Neues Projektmappenelement hinzufügen** gefundenen Informationen wieder. Es muss die vollständige Kategorie, gefolgt vom Dateityp, eingegeben werden; der Name der Kategorie wird mit einem umgekehrten Schrägstrich (`\`) vom Dateityp getrennt und die gesamte Zeichenfolge in Anführungszeichen eingeschlossen.

 Um z.B. eine neue Textdatei zu erstellen, geben Sie für das Argument /t:`templatename` Folgendes ein:

```cmd
/t:"General\Style Sheet"
```

 /e: `editorname` ist optional. Name des Editors, in dem die Datei geöffnet wird. Wenn zwar das Argument, aber kein Editorname angegeben wurde, wird das Dialogfeld **Öffnen mit** angezeigt.

 Die Argumentsyntax /e:`editorname` verwendet die Editornamen wie im Dialogfeld **Öffnen mit** angezeigt, wobei der Name in Anführungszeichen eingeschlossen ist.

 Um ein Stylesheet im Quellcode-Editor zu öffnen, geben Sie für das Argument /e:`editorname` beispielsweise Folgendes ein:

```cmd
/e:"Source Code (text) Editor"
```

## <a name="example"></a>Beispiel
 In diesem Beispiel wird der aktuellen Projektmappe ein neues Projektmappenelement, MyHTMLpg, hinzugefügt.

```cmd
>File.AddNewItem MyHTMLpg /t:"General\HTML Page"
```

## <a name="see-also"></a>Siehe auch

- [Visual Studio-Befehle](../../ide/reference/visual-studio-commands.md)
- [Befehlsfenster](../../ide/reference/command-window.md)
- [Feld „Suchen/Befehl“](../../ide/find-command-box.md)
- [Visual Studio-Befehlsaliase](../../ide/reference/visual-studio-command-aliases.md)