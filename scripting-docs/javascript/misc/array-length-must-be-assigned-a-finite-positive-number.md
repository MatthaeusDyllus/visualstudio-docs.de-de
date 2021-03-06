---
title: "Der Arraylänge muss eine endliche positive Ganzzahl zugewiesen sein | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.technology:
- javascript
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- VS.WebClient.Help.SCRIPT5030
dev_langs:
- JavaScript
- TypeScript
- DHTML
ms.assetid: c51c66a4-a543-4e95-b18d-2cfbcb3d1fdd
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 63a9d714173334192028b9096de41968befa85ef
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/27/2017
---
# <a name="array-length-must-be-assigned-a-finite-positive-number"></a>Der Arraylänge muss eine endliche positive Ganzzahl zugewiesen sein.
Beim Festlegen der **Länge** -Eigenschaft eines vorhandenen **Array** Sie angegebene Objekt, eine Arraylänge, die keine positive Zahl oder 0 (null). Dieser Fehler tritt auf, wenn Sie einen Wert zuweisen der **Länge** Eigenschaft ein `Array` -Objekt, das negativ ist oder keine Zahl (`NaN`). Beachten Sie, dass [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)] automatisch Bruchzahlen in ganze Zahlen konvertiert.  
  
### <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler  
  
-   Weisen Sie eine positive ganze Zahl zu der Length-Eigenschaft. Es gibt keine Obergrenze für die Größe eines Arrays, als der maximale Ganzzahlwert (ca. 4 Milliarden). Das folgende Beispiel veranschaulicht die richtige Methode zum Festlegen der **Länge** Eigenschaft ein **Array** Objekt.  
  
    ```JavaScript  
    var my_array = new Array();  
    my_array.length = 99;  
    ```  
  
## <a name="see-also"></a>Siehe auch  
 [Verwenden von Arrays](../../javascript/advanced/using-arrays-javascript.md)