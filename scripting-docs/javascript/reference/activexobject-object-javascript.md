---
title: ActiveXObject-Objekt (JavaScript) | Microsoft Docs
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-javascript
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- ActiveXObject
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- ActiveXObject object
- Automation objects, ActiveXObject objects
ms.assetid: 9c7bed07-853f-48aa-92db-3131324746ec
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 77bb743aeab563f7d7711e4caa9a0fcf0b45ff58
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/27/2017
---
# <a name="activexobject-object-javascript"></a>ActiveXObject-Objekt (JavaScript)
Ermöglicht einen Verweis auf ein Automatisierungsobjekt und gibt diesen zurück.  
  
 Dieses Objekt wird nur zur Instanziierung von Automatisierungsobjekten verwendet und besitzt keine Member.  
  
> [!WARNING]
>  Dieses Objekt ist eine Microsoft-Erweiterung und wird nur in Internet Explorer, nicht jedoch in [!INCLUDE[win8_appname_long](../../javascript/includes/win8-appname-long-md.md)]-Apps unterstützt.  
  
## <a name="syntax"></a>Syntax  
  
```  
  
newObj = new ActiveXObject(servername.typename[, location])  
```  
  
## <a name="parameters"></a>Parameter  
 `newObj`  
 Erforderlich. Der Variablenname, dem das `ActiveXObject` zugewiesen wird.  
  
 `servername`  
 Erforderlich. Der Name der Anwendung, die das Objekt bereitstellt.  
  
 `typename`  
 Erforderlich. Der Typ oder die Klasse des zu erstellenden Objekts.  
  
 `location`  
 Dies ist optional. Der Name des Netzwerkservers, auf dem das Objekt erstellt werden soll.  
  
## <a name="remarks"></a>Hinweise  
 Automatisierungsserver stellen mindestens einen Objekttyp bereit. Eine Textverarbeitungsanwendung kann z. B. ein Anwendungsobjekt, ein Dokumentobjekt und ein Symbolleistenobjekt bereitstellen.  
  
 Sie sind möglicherweise in der Lage, `servername.typename`-Werte auf einem Host-PC im Registrierungsschlüssel `HKEY_CLASSES_ROOT` zu identifizieren. Hier sind einige Beispiele von Werten, die Sie abhängig vom installierten Programm dort finden können:  
  
-   Excel.Application  
  
-   Excel.Chart  
  
-   Scripting.FileSystemObject  
  
-   WScript.Shell  
  
-   Word.Document  
  
> [!IMPORTANT]
>  ActiveX-Objekte stellen möglicherweise Sicherheitsprobleme dar. Um `ActiveXObject` zu verwenden, müssen Sie möglicherweise die Sicherheitseinstellungen in Internet Explorer an die entsprechende Sicherheitszone anpassen. Für die lokale Intranetzone müssen Sie normalerweise die benutzerdefinierte Einstellung auf "ActiveX-Steuerelemente initialisieren und ausführen, die nicht als 'sicher für Skripting' markiert sind" ändern.  
  
 Um Mitglieder ein Automatisierungsobjekt zu identifizieren, die Sie in Ihrem Code verwenden können, müssen Sie möglicherweise eine COM-Objektkatalog verwenden, z. B. die [OLE/COM-Objektkatalog](http://msdn.microsoft.com/library/d0kh9f4c.aspx), wenn keine Referenzdokumentation für das Automation-Objekt verfügbar ist.  
  
 Um ein Automatisierungsobjekt zu erstellen, weisen Sie einer Objektvariablen das neue `ActiveXObject`-Objekt zu:  
  
```JavaScript  
var ExcelApp = new ActiveXObject("Excel.Application");  
var ExcelSheet = new ActiveXObject("Excel.Sheet");  
```  
  
 Mit diesem Code wird die Anwendung gestartet, die das Objekt erstellt (in diesem Fall ein Microsoft Excel-Arbeitsblatt). Sobald ein Objekt erstellt wurde, wird im Code über die definierte Objektvariable darauf verwiesen. Im folgenden Beispiel können Sie auf Eigenschaften und Methoden des neuen Objekts zugreifen, indem Sie die `ExcelSheet`-Objektvariable und andere Excel-Objekte, einschließlich des Application-Objekts und der ActiveSheet.Cells-Auflistung, verwenden.  
  
```JavaScript  
// Make Excel visible through the Application object.  
ExcelSheet.Application.Visible = true;  
// Place some text in the first cell of the sheet.  
ExcelSheet.ActiveSheet.Cells(1,1).Value = "This is column A, row 1";  
// Save the sheet.  
ExcelSheet.SaveAs("C:\\TEST.XLS");  
// Close Excel with the Quit method on the Application object.  
ExcelSheet.Application.Quit();  
```  
  
## <a name="requirements"></a>Anforderungen  
 Wird in den folgenden Dokumentmodi unterstützt: Quirks, Internet Explorer 6 (Standardmodus), Internet Explorer 7 (Standardmodus), Internet Explorer 8 (Standardmodus), Internet Explorer 9 (Standardmodus), Internet Explorer 10 (Standardmodus) und Internet Explorer 11 (Standardmodus). Wird in [!INCLUDE[win8_appname_long](../../javascript/includes/win8-appname-long-md.md)] -Apps nicht unterstützt. Siehe [Versionsinformationen](../../javascript/reference/javascript-version-information.md).  
  
> [!NOTE]
>  Das Erstellen von `ActiveXObject` auf einem Remoteserver wird in [!INCLUDE[jsv9text](../../javascript/includes/jsv9text-md.md)] und höher nicht unterstützt.  
  
## <a name="see-also"></a>Siehe auch  
 [GetObject-Funktion](../../javascript/reference/getobject-function-javascript.md)   
 [Eindeutige Authentifizierung mithilfe von Magic von HTML5/WCF-Beispiel-app](http://code.msdn.microsoft.com/Unique-Authentication-f32d2da0)