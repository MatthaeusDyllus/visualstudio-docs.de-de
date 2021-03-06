---
title: 'Vorgehensweise: Hinzufügen von Steuerelementen zur Backstage-Ansicht '
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- customizing the Ribbon, menus
- controls, Ribbon
- menus, customizing
- Microsoft Office Button
- custom Ribbon, menus
- Ribbon, customizing
- Office button
- Ribbon, menus
- Microsoft Office Menu
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: 6b775c7613b8cc0953e419b2546ec017c96e8454
ms.sourcegitcommit: 697162f54d3c4e30df702fd0289e447e211e3a85
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/25/2018
---
# <a name="how-to-add-controls-to-the-backstage-view"></a>Vorgehensweise: Hinzufügen von Steuerelementen zur Backstage-Ansicht
  Können Sie dem Menüband-Designer zum Hinzufügen von Steuerelementen zum Menü, das geöffnet wird, wenn Sie auf die **Datei** Registerkarte. Beim Ausführen der Anwendung, Steuerelemente, die Sie zum Hinzufügen der **Datei** Registerkarte angezeigt werden, eine Gruppe namens **-Add-ins**.  
  
 Sie können keine Steuerelemente vor oder nach integrierten Steuerelementen positionieren, mithilfe des Menüband-Designers in Visual Studio. Ein integriertes Steuerelement ist ein Steuerelement, das bereits in der Backstage-Ansicht angezeigt wird. Wenn Sie Steuerelemente vor oder nach integrierten Steuerelementen positionieren möchten, müssen Sie eine Menüband-XML verwenden. Weitere Informationen zu **Menüband (XML)**, finden Sie unter [Menüband-XML-](../vsto/ribbon-xml.md). Weitere Informationen zum Anpassen der Backstage-Ansicht finden Sie unter [Einführung in die Office 2010-Backstage-Ansicht für Entwickler](http://go.microsoft.com/fwlink/?LinkId=182189) und [anpassen die Office 2010-Backstage-Ansicht für Entwickler](http://go.microsoft.com/fwlink/?LinkId=182188).  
  
 [!INCLUDE[appliesto_ribbon](../vsto/includes/appliesto-ribbon-md.md)]  
  
### <a name="to-add-controls-to-backstage-view"></a>Zum Hinzufügen von Steuerelementen zur Backstage-Ansicht  
  
1.  Öffnen Sie das Element "Menüband" in der Entwurfsansicht.  
  
     Informationen zur Vorgehensweise beim Hinzufügen einer **Menüband (visueller Designer)** finden Sie dem Projekt [wie: Erste Schritte beim Anpassen des Menübands](../vsto/how-to-get-started-customizing-the-ribbon.md).  
  
2.  Klicken Sie im Menüband-Designer auf die **Datei** Registerkarte.  
  
     Menü-Designer wird angezeigt. Diese Entwurfsoberfläche enthält keine Steuerelemente.  
  
3.  Aus der **Steuerelemente für Office-Menübänder** auf der Registerkarte die **Toolbox**, ziehen Sie eines der folgenden Steuerelemente auf der Designer im Menü:  
  
    -   Schaltfläche  
  
    -   CheckBox  
  
    -   Katalog  
  
    -   Menü  
  
    -   Trennzeichen  
  
    -   SplitButton  
  
    -   ToggleButton  
  
4.  Ziehen Sie Steuerelemente auf das Menü an neue Positionen verschieben.  
  
## <a name="see-also"></a>Siehe auch  
 [Übersicht über das Menüband](../vsto/ribbon-overview.md)   
 [Menüband-Designer](../vsto/ribbon-designer.md)   
 [Menüband-XML](../vsto/ribbon-xml.md)   
 [Vorgehensweise: Erste Schritte Anpassen des Menübands](../vsto/how-to-get-started-customizing-the-ribbon.md)   
 [Exemplarische Vorgehensweise: Erstellen einer benutzerdefinierten Registerkarte mit Menüband-Designer](../vsto/walkthrough-creating-a-custom-tab-by-using-the-ribbon-designer.md)  
  
  