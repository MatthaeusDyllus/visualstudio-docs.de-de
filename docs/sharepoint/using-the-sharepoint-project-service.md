---
title: Verwenden des SharePoint-Projektdiensts | Microsoft Docs
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- SharePoint project service
- SharePoint development in Visual Studio, extensibility features
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: efe2e2073ead64bfbc697b9d6c824066af947580
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/16/2018
---
# <a name="using-the-sharepoint-project-service"></a>Verwenden des SharePoint-Projektdiensts
  Das SharePoint-Projektsystem beinhaltet einen Projektdienst, den Sie verwenden können, um mit dem Projektsystem zusammenhängende Aufgaben auszuführen. Der Projektdienst ist ein <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectService>-Objekt.  
  
 Sie können in jeder SharePoint-Tools-Erweiterung auf den SharePoint-Projektdienst zugreifen. Sie können auch in anderen Arten von Visual Studio-Erweiterungen, z. B. Add-Ins und VSPackages, auf ihn zugreifen. Weitere Informationen finden Sie unter [wie: Abrufen des SharePoint-Projektdiensts](../sharepoint/how-to-retrieve-the-sharepoint-project-service.md).  
  
## <a name="project-service-features"></a>Funktionen des Projektdiensts  
 In der folgenden Tabelle sind die Aufgaben aufgelistet, die Sie mithilfe des SharePoint-Projektdiensts und der <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectService>-Methode oder -Eigenschaft ausführen können, um die einzelnen Aufgaben auszuführen.  
  
|Aufgabe|Zu verwendender Member|  
|----------|-------------------|  
|Zugriff auf beliebige SharePoint-Projekte, die in Visual Studio geöffnet sind.|<xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectService.Projects%2A>-Eigenschaft.|  
|Zugriff auf alle verfügbaren SharePoint-Projektelementtypen (einschließlich integrierter und benutzerdefinierter Projektelementtypen).|<xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectService.ProjectItemTypes%2A>-Eigenschaft.|  
|Zugriff auf alle die Bereitstellungsschritte, die für SharePoint-Projekte verfügbar sind (einschließlich integrierter und benutzerdefinierter Bereitstellungsschritte).|<xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectService.DeploymentSteps%2A>-Eigenschaft.|  
|Zugriff auf Ereignisse, die ausgelöst werden, wenn ein Entwickler Code in einem SharePoint-Projekt umgestaltet.|<xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectService.CodeRefactoringEvents%2A>-Eigenschaft.|  
|Führen Sie eine benutzerdefinierte *SharePoint-Befehl* in der SharePoint-Serverobjektmodell aufruft. Weitere Informationen zu SharePoint-Befehlen finden Sie unter [Aufrufe in die SharePoint-Objektmodelle](../sharepoint/calling-into-the-sharepoint-object-models.md).|<xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectService.SharePointConnection%2A>-Eigenschaft.|  
|Konvertieren eines Typs im SharePoint-Projektsystem in einen Typ im Visual Studio-Automatisierungsobjektmodell oder -Integrationsobjektmodell und umgekehrt. Weitere Informationen finden Sie unter [Konvertieren zwischen SharePoint-Projektsystemtypen und anderen Visual Studio-Projekttypen](../sharepoint/converting-between-sharepoint-project-system-types-and-other-visual-studio-project-types.md).|<xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectService.Convert%2A>-Methode.|  
|Schreiben von Nachrichten an die **Ausgabe** Fenster oder **Fehlerliste** Fenster in Visual Studio.|<xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectService.Logger%2A>-Eigenschaft.|  
|Zugriff auf andere in Visual Studio verfügbare Dienste.|<xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectService.ServiceProvider%2A>-Eigenschaft.|  
|Abrufen des Pfads zum Installationsordner der lokalen SharePoint-Website, der zum Debuggen der Projektmappe verwendet wird.|<xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectService.SharePointInstallPath%2A>-Eigenschaft.|  
|Bestimmt, ob [!INCLUDE[moss_14_long](../sharepoint/includes/moss-14-long-md.md)] oder [!INCLUDE[wss_14_long](../sharepoint/includes/wss-14-long-md.md)] auf dem Computer installiert ist.|<xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectService.IsSharePointInstalled%2A>-Eigenschaft.|  
|Überprüfen einer Funktion oder eines Pakets in einer SharePoint-Lösung.|<xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectService.PackageValidationProvider%2A>-Eigenschaft.|  
  
## <a name="see-also"></a>Siehe auch  
 [Konvertieren zwischen SharePoint-Projektsystemtypen und anderen Visual Studio-Projekttypen](../sharepoint/converting-between-sharepoint-project-system-types-and-other-visual-studio-project-types.md)   
 [Vorgehensweise: Abrufen des SharePoint-Projektdiensts](../sharepoint/how-to-retrieve-the-sharepoint-project-service.md)   
 [Erweitern der SharePoint-Tools in Visual Studio](../sharepoint/extending-the-sharepoint-tools-in-visual-studio.md)   
 [Übersicht über das Programmiermodell von SharePoint-Tools-Erweiterungen](../sharepoint/overview-of-the-programming-model-of-sharepoint-tools-extensions.md)   
 [Gewusst wie: Abrufen eines Diensts vom DTE-Objekt](http://msdn.microsoft.com/library/bb166401.aspx)  
  
  