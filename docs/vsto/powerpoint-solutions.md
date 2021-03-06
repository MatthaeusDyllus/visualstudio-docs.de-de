---
title: PowerPoint-Projektmappen
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- Office solutions [Office development in Visual Studio], PowerPoint
- templates [Office development in Visual Studio], PowerPoint
- solutions [Office development in Visual Studio], PowerPoint
- projects [Office development in Visual Studio], PowerPoint
- PowerPoint [Office development in Visual Studio]
- Office projects [Office development in Visual Studio], PowerPoint
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: c7436bbb7ce904f8c969652e3f4ff0a794116c9c
ms.sourcegitcommit: 0aafcfa08ef74f162af2e5079be77061d7885cac
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2018
ms.locfileid: "34692706"
---
# <a name="powerpoint-solutions"></a>PowerPoint-Projektmappen
  Visual Studio stellt Projektvorlagen bereit, die Sie zum Erstellen von VSTO-Add-Ins für Microsoft Office PowerPoint verwenden können. Mit VSTO-Add-Ins können Sie PowerPoint automatisieren, PowerPoint-Features erweitern oder die PowerPoint-Benutzeroberfläche anpassen.  
  
 Weitere Informationen zu VSTO-Add-ins finden Sie unter [Einstieg in das Programmieren von VSTO-Add-ins](../vsto/getting-started-programming-vsto-add-ins.md) und [Architektur von VSTO-Add-ins](../vsto/architecture-of-vsto-add-ins.md). Wenn Sie mit Microsoft Office-Programmierung noch nicht vertraut sind, finden Sie unter [Einstieg in die &#40;Office-Entwicklung in Visual Studio&#41;](../vsto/getting-started-office-development-in-visual-studio.md).  
  
 [!INCLUDE[appliesto_pptallapp](../vsto/includes/appliesto-pptallapp-md.md)]  
  
> [!NOTE]  
>  Bei der Entwicklung von Lösungen, die über die Office-Erfahrungen erweitern "interested" [mehrere Plattformen](https://dev.office.com/add-in-availability)? Sehen Sie sich die neue [Office-Add-ins Modell](https://dev.office.com/docs/add-ins/overview/office-add-ins). Office-Add-ins haben einen geringen Ressourcenbedarf im Vergleich zu VSTO-add-ins und Lösungen, und Sie können sie mithilfe von fast allen Web-Technologien, wie HTML5, JavaScript, CSS3 und XML-Programmierung erstellen.  
  
 ![Link zu Video](../vsto/media/playvideo.gif "Link zu Video") eine entsprechende Videodemo finden Sie unter [Gewusst wie: Erstellen einer Add-in für Microsoft PowerPoint?](http://go.microsoft.com/fwlink/?LinkId=132767).  
  
## <a name="automate-powerpoint-by-using-the-powerpoint-object-model"></a>Automatisieren von PowerPoint mithilfe von PowerPoint-Objektmodell  
 Das PowerPoint-Objektmodell macht viele Typen verfügbar, die Sie zum Automatisieren von PowerPoint verwenden können. Diese Typen ermöglichen Ihnen das Schreiben von Code zum Ausführen häufiger Aufgaben:  
  
-   Programmgesteuertes Erstellen und Formatieren von Präsentationen  
  
-   Hinzufügen oder Entfernen von Folien in Präsentationen  
  
-   Hinzufügen oder Ändern von Formen in einer Folie  
  
 Wenn Sie in einem VSTO-Add-In auf das PowerPoint-Objektmodell zugreifen möchten, verwenden Sie das `Application` -Feld der `ThisAddIn` -Klasse im Projekt. Das `Application` -Feld gibt ein <xref:Microsoft.Office.Interop.PowerPoint.Application> -Objekt zurück, das die aktuelle Instanz von PowerPoint darstellt. Weitere Informationen finden Sie unter [Programm VSTO-Add-Ins](../vsto/programming-vsto-add-ins.md).  
  
 Bei einem Aufruf des PowerPoint-Objektmodells verwenden Sie Typen, die in der primären Interopassembly für PowerPoint bereitgestellt werden. Die primäre Interopassembly dient als Brücke zwischen verwaltetem Code im VSTO-Add-In und dem COM-Objektmodell in PowerPoint. Alle Typen in der primären Interopassembly für PowerPoint werden im <xref:Microsoft.Office.Interop.PowerPoint> -Namespace definiert. Weitere Informationen zu primären Interopassemblys finden Sie unter [Übersicht über die Entwicklung von Office-Lösungen &#40;VSTO&#41; ](../vsto/office-solutions-development-overview-vsto.md) und [primären Interopassemblys von Office](../vsto/office-primary-interop-assemblies.md).  
  
##  <a name="WordOMDocumentation"></a> Verwenden der Dokumentation für das PowerPoint-Objektmodell  
 Ausführliche Informationen zum PowerPoint-Objektmodell finden Sie in der Referenz für die primäre Interopassembly (PIA) für PowerPoint und der VBA-Objektmodellreferenz.  
  
### <a name="primary-interop-assembly-reference"></a>Primäre Interop-Assembly-Verweis  
 In der Referenzdokumentation für die PowerPoint-PIA werden die Typen in der primären Interopassembly für PowerPoint beschrieben. In dieser Dokumentation wird von folgendem Speicherort verfügbar: [Referenz für die primäre Interop-Assembly von PowerPoint 2010](http://go.microsoft.com/fwlink/?LinkId=189588).  
  
 Weitere Informationen zum Entwurf der PowerPoint-PIA, z. B. zu Unterschieden zwischen Klassen und Schnittstellen in der PIA und zur Implementierung von Ereignissen in der PIA, finden Sie unter [Übersicht über Klassen und Schnittstellen in primären Interopassemblys für Office ](http://go.microsoft.com/fwlink/?LinkId=199885).  
  
### <a name="vba-object-model-reference"></a>VBA-Objektmodellreferenz  
 Die VBA-Objektmodellreferenz dokumentiert das PowerPoint-Objektmodell, das für VBA (Visual Basic for Applications)-Code verfügbar gemacht wird. Weitere Informationen finden Sie unter [PowerPoint 2010-Objektmodellreferenz](http://go.microsoft.com/fwlink/?LinkId=199770)  
  
 Alle Objekte und Member in der VBA-Objektmodellreferenz entsprechen Typen und Membern in der primären Interopassembly (PIA) für PowerPoint. Beispielsweise entspricht das Presentation-Objekt in der VBA-Objektmodellreferenz der <xref:Microsoft.Office.Interop.PowerPoint.Presentation> -Typ in der PowerPoint-PIA. Obwohl die VBA-Objektmodellreferenz Codebeispiele für die meisten Eigenschaften, Methoden und Ereignisse enthält, müssen Sie den VBA-Code in dieser Referenz in Visual Basic oder Visual C# übersetzen, wenn Sie ihn in einem mit Visual Studio erstellten VSTO-Add-In-Projekt für PowerPoint verwenden möchten.  
  
## <a name="customize-the-user-interface-of-powerpoint"></a>Anpassen der Benutzeroberfläche von PowerPoint  
 Sie können die Benutzeroberfläche von PowerPoint folgendermaßen ändern:  
  
|Aufgabe|Weitere Informationen|  
|----------|--------------------------|  
|Erstellen eines benutzerdefinierten Aufgabenbereichs|[Benutzerdefinierte Aufgabenbereiche](../vsto/custom-task-panes.md)|  
|Hinzufügen von benutzerdefinierten Registerkarten zum Menüband|[Übersicht über das Menüband](../vsto/ribbon-overview.md)|  
|Hinzufügen benutzerdefinierter Gruppen zu einer integrierten Registerkarte auf dem Menüband|[Vorgehensweise: Anpassen einer integrierten Registerkarte](../vsto/how-to-customize-a-built-in-tab.md)|  
  
 Weitere Informationen zum Anpassen der Benutzeroberfläche von PowerPoint und anderen Microsoft Office-Anwendungen finden Sie unter [Anpassung der Office-Benutzeroberfläche](../vsto/office-ui-customization.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Exemplarische Vorgehensweise: Erstellen des ersten VSTO-Add-Ins für PowerPoint](../vsto/walkthrough-creating-your-first-vsto-add-in-for-powerpoint.md)   
 [Erste Schritte zum Programmieren von VSTO-Add-ins](../vsto/getting-started-programming-vsto-add-ins.md)   
 [Übersicht über die Entwicklung von Office-Lösungen &#40;VSTO&#41;](../vsto/office-solutions-development-overview-vsto.md)   
 [Architektur von VSTO-Add-ins](../vsto/architecture-of-vsto-add-ins.md)   
 [Vorgehensweise: Erstellen von Office-Projekten in Visual Studio](../vsto/how-to-create-office-projects-in-visual-studio.md)   
 [Programmieren von VSTO-Add-ins](../vsto/programming-vsto-add-ins.md)   
 [Schreiben von Code in Office-Projektmappen](../vsto/writing-code-in-office-solutions.md)   
 [Primäre Interopassemblys für Office](../vsto/office-primary-interop-assemblies.md)   
 [Anpassung der Office-Benutzeroberfläche](../vsto/office-ui-customization.md)   
 [PowerPoint 2010 in Office-Entwicklung](http://go.microsoft.com/fwlink/?LinkId=199015)  
  
  