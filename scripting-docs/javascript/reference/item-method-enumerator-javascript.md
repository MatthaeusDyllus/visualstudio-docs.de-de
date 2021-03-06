---
title: Item-Methode (Enumerator) (JavaScript) | Microsoft Docs
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
- item
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- Item method
ms.assetid: a88e93f2-42df-4578-a4f9-0760bd074185
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 94275b2c82f199c96ef2d6c7d667fd27fba2702d
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/27/2017
---
# <a name="item-method-enumerator-javascript"></a>item-Methode (Enumerator) (JavaScript)
Gibt das aktuelle Element in der Auflistung zurück  
  
> [!WARNING]
>  Dieses Objekt wird nur in Internet Explorer unterstützt.  
  
## <a name="syntax"></a>Syntax  
  
```  
  
enumObj.item()   
```  
  
## <a name="remarks"></a>Hinweise  
 Der erforderliche *enumObj* -Verweis ist ein beliebiges `Enumerator` -Objekt.  
  
 Die **Element** -Methode gibt das aktuelle Element zurück. Wenn die Sammlung leer ist, oder das aktuelle Element nicht definiert ist, gibt sie **nicht definiert**zurück.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Code wird die **Element** -Methode verwendet, um ein Element der `Drives` -Sammlung zurückzugeben.  
  
```JavaScript  
function ShowDrives()  
{  
    var s = "";  
    var bytesPerGB = 1024 * 1024 * 1024;  
  
    var fso = new ActiveXObject("Scripting.FileSystemObject");  
    var e = new Enumerator(fso.Drives);  
  
    e.moveFirst();  
    while (e.atEnd() == false)  
    {  
        var drv = e.item();  
  
        s += drv.Path + " - ";  
  
        if (drv.IsReady)  
        {  
            var freeGB = drv.FreeSpace / bytesPerGB;  
            var totalGB = drv.TotalSize / bytesPerGB;  
  
            s += freeGB.toFixed(3) + " GB free of ";  
            s += totalGB.toFixed(3) + " GB";  
        }  
        else  
        {  
            s += "Not Ready";  
        }  
  
        s += "<br />";  
  
        e.moveNext();  
    }  
    return(s);  
}  
```  
  
## <a name="requirements"></a>Anforderungen  
 Wird in den folgenden Dokumentmodi unterstützt: Quirksmodus, Internet Explorer 6-Standardmodus, Internet Explorer 7-Standardmodus, Internet Explorer 8-Standardmodus, Internet Explorer 9-Standardmodus und Internet Explorer 10-Standardmodus. Wird in [!INCLUDE[win8_appname_long](../../javascript/includes/win8-appname-long-md.md)] -Apps nicht unterstützt. Siehe [Versionsinformationen](../../javascript/reference/javascript-version-information.md).  
  
 **Gilt für**: [Enumerator Object](../../javascript/reference/enumerator-object-javascript.md)  
  
## <a name="see-also"></a>Siehe auch  
 [AtEnd-Methode (Enumerator)](../../javascript/reference/atend-method-enumerator-javascript.md)   
 [MoveFirst-Methode (Enumerator)](../../javascript/reference/movefirst-method-enumerator-javascript.md)   
 [moveNext-Methode (Enumerator)](../../javascript/reference/movenext-method-enumerator-javascript.md)