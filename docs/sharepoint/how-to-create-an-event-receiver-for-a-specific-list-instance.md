---
title: 'Vorgehensweise: Erstellen eines Ereignisempfängers für eine bestimmte Listeninstanz | Microsoft Docs'
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- SharePoint development in Visual Studio, event receivers
- event receivers [SharePoint development in Visual Studio]
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: 4e5c68db8d1c9809e487fc8f64159d8b385a96a2
ms.sourcegitcommit: 1466ac0f49ebf7448ea4507ae3f79acb25d51d3e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/22/2018
---
# <a name="how-to-create-an-event-receiver-for-a-specific-list-instance"></a>Gewusst wie: Erstellen eines Ereignisempfängers für eine bestimmte Listeninstanz
  Ein Liste Instanz Ereignisempfänger antwortet auf Ereignisse, die in einer beliebigen Instanz einer Listendefinition auftreten. Obwohl die ereignisvorlage für den Empfänger nicht die Zielgruppenadressierung für eine bestimmte Listeninstanz aktiviert wird, können Sie einen Ereignisempfänger ändern, der auf einer Listendefinition Reaktion auf Ereignisse in eine bestimmte Listeninstanz begrenzt ist.  
  
 Ersetzen Sie für eine bestimmte Listeninstanz in der Datei "Elements.xml" für den Ereignisempfänger entwickeln `ListTemplateId` mit `ListUrl` und die URL der Listeninstanz hinzufügen.  
  
## <a name="creating-a-list-instance-event-receiver"></a>Erstellen einen Liste Instanz Ereignisempfänger  
 Die folgenden Schritte zeigen, wie einen Liste Element-Ereignisempfänger, um nur auf Ereignisse reagieren, die in eine benutzerdefinierte Ankündigungen-Listeninstanz auftreten zu ändern.  
  
#### <a name="to-modify-an-event-receiver-to-respond-to-a-specific-list-instance"></a>So ändern Sie einen Ereignisempfänger zum Reagieren auf eine bestimmte Listeninstanz  
  
1.  Öffnen Sie die SharePoint-Website in einem Browser.  
  
2.  Klicken Sie im Bereich "Navigation" **listet** Link.  
  
3.  In der **Alle Websiteinhalte einblenden** Seite, und wählen Sie die **erstellen** Link.  
  
4.  In der **erstellen** Dialogfeld Wählen Sie die **Ankündigungen** geben, nennen Sie die Ankündigung **TestAnnouncements**, und wählen Sie dann die **erstellen**Schaltfläche.  
  
5.  In [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)], ein Ereignisempfängerprojekt erstellen.  
  
6.  In der **Art-Ereignisempfänger verwenden, möchten Sie?** wählen **Listenelementereignisse**.  
  
    > [!NOTE]  
    >  Sie können auch eine beliebige andere Art von Ereignisempfänger, die auf einer Listendefinition, z. B. Bereiche auswählen **-e-Mail-Listenereignisse** oder **Listenworkflowereignisse**.  
  
7.  In der **welches Element der Ereignisquelle werden sollten?** wählen **Ankündigungen**.  
  
8.  In der **die folgenden Ereignisse behandeln** Liste der **ein Element hinzugefügt wird** Kontrollkästchen, und wählen Sie dann die **Fertig stellen** Schaltfläche.  
  
9. In **Projektmappen-Explorer**, unter EventReceiver1, öffnen Sie die Datei "Elements.xml".  
  
     Ereignisempfänger verweist derzeit die Listendefinition Ankündigungen mithilfe der folgenden Zeile:  
  
    ```xml  
    <Receivers ListTemplateId="104">  
    ```  
  
     Ändern Sie diese Zeile in den folgenden Text ein:  
  
    ```xml  
    <Receivers ListUrl="Lists/TestAnnouncements">  
    ```  
  
     Dies weist den Ereignisempfänger, um nur auf Ereignisse reagieren, die in der neuen auftreten **TestAnnouncements** Ankündigungsliste, die Sie gerade erstellt haben. Sie können ändern, die `ListURL` Attribut auf eine beliebige Listeninstanz auf dem SharePoint-Server verweisen.  
  
10. Öffnen Sie die Codedatei für die-Ereignisempfänger verwenden, und legen Sie einen Haltepunkt in der ItemAdding-Methode.  
  
11. Wählen Sie die F5-Taste zum Erstellen und führen Sie die Projektmappe aus.  
  
12. Wählen Sie in SharePoint, die **TestAnnouncements** Link im Navigationsbereich.  
  
13. Wählen Sie die **neue Ankündigung hinzufügen** Link.  
  
14. Geben Sie einen Titel für die Ankündigung, und wählen Sie dann die **speichern** Schaltfläche.  
  
     Beachten Sie, dass der Haltepunkt erreicht wird, wenn benutzerdefinierte Ankündigungen das neue Element hinzugefügt wird.  
  
15. Wählen Sie zum Fortsetzen die Taste F5.  
  
16. Wählen Sie im Navigationsbereich die **listet** verknüpfen, und wählen Sie dann die **Ankündigungen** Link.  
  
17. Fügen Sie eine neue Ankündigung an.  
  
     Beachten Sie die Ereignisempfänger nicht auf die neue Ankündigung ausgelöst werden, da der Empfänger konfiguriert ist, um nur für Ereignisse in die Listeninstanz benutzerdefinierten ankündigungslistenerdienst zu reagieren **TestAnnouncements**.  
  
## <a name="see-also"></a>Siehe auch  
 [Vorgehensweise: Erstellen eines Ereignisempfängers](../sharepoint/how-to-create-an-event-receiver.md)   
 [Entwickeln von SharePoint-Projektmappen](../sharepoint/developing-sharepoint-solutions.md)  
  
  