---
title: Aufrufe in die SharePoint-Objektmodelle | Microsoft Docs
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- SharePoint development in Visual Studio, client object model
- SharePoint development in Visual Studio, server object model
- SharePoint commands [SharePoint development in Visual Studio]
- SharePoint development in Visual Studio, extensibility features
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: 24d8c7824e9bf90538a7d4dd1ae230d37cfbdb2f
ms.sourcegitcommit: 4cd4aef53e7035d23e7d1d0f66f51ac8480622a1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/05/2018
ms.locfileid: "34765556"
---
# <a name="call-into-the-sharepoint-object-models"></a>Rufen Sie in der SharePoint-Objektmodelle
  Wenn Sie Erweiterungen für die SharePoint-Tools in Visual Studio erstellen, müssen Sie möglicherweise rufen Sie die SharePoint-APIs, um bestimmte Aufgaben ausführen. Bei der Erstellung eines benutzerdefinierten Bereitstellungsschritts für SharePoint-Projekte möglicherweise Sie z. B. SharePoint-APIs zum Ausführen einiger Aufgaben zum Bereitstellen von Projektmappen aufrufen.  
  
 [!INCLUDE[wss_14_long](../sharepoint/includes/wss-14-long-md.md)] und [!INCLUDE[moss_14_long](../sharepoint/includes/moss-14-long-md.md)] bieten zwei unterschiedliche Objektmodelle, die Sie in der SharePoint-Tools-Erweiterungen verwenden können: ein Serverobjektmodell und ein Clientobjektmodell. Beide Objektmodelle haben vor- und Nachteile im Kontext der SharePoint-Tools-Erweiterungen.  
  
 Einen Überblick über die SharePoint-Objektmodelle finden Sie unter [Überblick über die Programmierung Modell der SharePoint-Tools-Erweiterungen](../sharepoint/overview-of-the-programming-model-of-sharepoint-tools-extensions.md).  
  
## <a name="use-the-client-object-model-in-extension-projects"></a>Verwenden Sie das Clientobjektmodell in Erweiterungsprojekten
 Wenn Sie eine Erweiterung für die SharePoint-Tools entwickeln, können Sie das Clientobjektmodell in Ihrem Projekt wie einen beliebigen anderen Satz von verwalteten APIs. Sie können Verweise auf Assemblys in das Clientobjektmodell zu Ihrem Projekt hinzufügen, und Sie können APIs im Clientobjektmodell aufrufen, direkt aus Ihrem Code.  
  
 Allerdings hat das Clientobjektmodell zwei Nachteile im Kontext der SharePoint-Tools-Erweiterungen:  
  
-   Die Client-Objektmodell bietet nur eine Teilmenge des Server-Objektmodells. Wenn Sie SharePoint-Funktionen verwenden, die nicht in die Client-Objektmodell verfügbar gemacht werden müssen, müssen Sie das Serverobjektmodell verwenden.  
  
-   Obwohl mithilfe des Clientobjektmodells in SharePoint-Tools-Erweiterungen in den meisten Fällen funktionieren sollten, können einige Szenarien auftreten, in denen Aufrufe an den Client-Objektmodell nicht erwartungsgemäß funktionieren. Das Clientobjektmodell soll in Clientanwendungen verwendet werden, um SharePoint-Websites auf einem Remoteserver oder die Farm aufzurufen. SharePoint-Tools in Visual Studio funktionieren nur mit einer lokalen SharePoint-Installation auf dem Entwicklungscomputer. Daher bei der Verwendung des Clientobjektmodells in einer SharePoint-Tools-Erweiterung rufen Sie in einer SharePoint-Website auf dem lokalen Computer ist nicht wie das Clientobjektmodell konzipiert wurde.  
  
 Eine exemplarische Vorgehensweise, die das Clientobjektmodell in einer Erweiterung der SharePoint-Tools in Visual Studio veranschaulicht, finden Sie unter [Exemplarische Vorgehensweise: Aufrufen von in der SharePoint-Clientobjektmodell innerhalb einer Server-Explorererweiterung](../sharepoint/walkthrough-calling-into-the-sharepoint-client-object-model-in-a-server-explorer-extension.md).  
  
## <a name="use-the-server-object-model-in-extension-projects"></a>Verwenden Sie das Serverobjektmodell in Erweiterungsprojekten
 Das Serverobjektmodell ist eine Obermenge des Client-Objektmodells. Wenn Sie das Serverobjektmodell verwenden, können Sie alle Funktionen, die [!INCLUDE[wss_14_long](../sharepoint/includes/wss-14-long-md.md)] und [!INCLUDE[moss_14_long](../sharepoint/includes/moss-14-long-md.md)] programmgesteuert verfügbar machen.  

 SharePoint-Tools-Erweiterungen können APIs aus das Serverobjektmodell verwenden, aber sie können die APIs direkt aufrufen. Das Serverobjektmodell kann nur von einem 64-Bit-Prozess, der .NET Framework 3.5 abzielt aufgerufen werden. SharePoint-Tools-Erweiterungen erfordern jedoch die [!INCLUDE[net_v40_short](../sharepoint/includes/net-v40-short-md.md)] und in der 32-Bit-Visual Studio-Prozess ausgeführt. Dadurch wird verhindert, dass SharePoint-Tools-Erweiterungen verweisen auf Assemblys in das SharePoint-Serverobjektmodell direkt.  
  
 Wenn Sie das Serverobjektmodell in einer SharePoint-Tools-Erweiterung verwenden möchten, müssen Sie eine benutzerdefinierte erstellen *SharePoint-Befehl* zum Aufrufen der API. Sie definieren den SharePoint-Befehl in einer sekundären Assembly, die direkt in das Serverobjektmodell aufrufen kann. In Ihrem Erweiterungsprojekt Sie rufen den SharePoint-Befehl indirekt mithilfe der Methode "ExecuteCommand", der ein <xref:Microsoft.VisualStudio.SharePoint.ISharePointConnection> Objekt.  
  
 Weitere Informationen zum Erstellen und Verwenden von SharePoint-Befehlen finden Sie unter [wie: Erstellen eines SharePoint-Befehls](../sharepoint/how-to-create-a-sharepoint-command.md) und [wie: Ausführen eines SharePoint-Befehls](../sharepoint/how-to-execute-a-sharepoint-command.md). Informationen zum Bereitstellen von SharePoint-Befehlen finden Sie unter [Bereitstellen von Erweiterungen für SharePoint-Tools in Visual Studio](../sharepoint/deploying-extensions-for-the-sharepoint-tools-in-visual-studio.md).  
  
 Exemplarische Vorgehensweisen, die zum Erstellen und Verwenden von SharePoint-Befehle veranschaulichen, finden Sie unter [Exemplarische Vorgehensweise: Erstellen eines benutzerdefinierten Bereitstellungsschritts für SharePoint-Projekte](../sharepoint/walkthrough-creating-a-custom-deployment-step-for-sharepoint-projects.md) und [Exemplarische Vorgehensweise: Erweitern von Server-Explorer auf Web-Anzeige Teile](../sharepoint/walkthrough-extending-server-explorer-to-display-web-parts.md).  
  
### <a name="understand-how-sharepoint-commands-are-executed"></a>Verstehen Sie, wie die SharePoint-Befehle ausgeführt werden
 Assemblys, die SharePoint-Befehle definieren werden geladen, in einem 64-Bit-Host-Prozess mit dem Namen *vssphost4.exe*. Nachdem Sie in einer SharePoint-Tools-Erweiterung einen SharePoint-Befehl aufrufen, wird der Befehl ausgeführt, indem *vssphost4.exe* statt an den 32-Bit-Visual Studio-Prozess (*devenv.exe*). Sie können steuern, einige Aspekte wie SharePoint-Befehle ausgeführt werden, indem Sie Werte in der Registrierung festlegen. Weitere Informationen finden Sie unter [Debuggen von Erweiterungen für SharePoint-Tools in Visual Studio](../sharepoint/debugging-extensions-for-the-sharepoint-tools-in-visual-studio.md).  
  
## <a name="see-also"></a>Siehe auch
 [Vorgehensweise: Erstellen eines SharePoint-Befehls](../sharepoint/how-to-create-a-sharepoint-command.md)   
 [Vorgehensweise: Ausführen eines SharePoint-Befehls](../sharepoint/how-to-execute-a-sharepoint-command.md)   
 [Übersicht über das Programmiermodell von Erweiterungen für SharePoint-Tools](../sharepoint/overview-of-the-programming-model-of-sharepoint-tools-extensions.md)  
  
