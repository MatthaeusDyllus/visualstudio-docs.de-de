---
title: Workflow-Designer - Send-Aktivitätsdesigners
ms.date: 11/04/2016
ms.topic: reference
ms.prod: visual-studio-dev15
ms.technology: vs-workflow-designer
f1_keywords:
- System.ServiceModel.Activities.Send.UI
ms.assetid: b514f2e4-767c-4b94-ac61-dd3a54d4b96d
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 099a512bcbca7136541c9896e32f43b9e518ed8b
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/26/2018
---
# <a name="send-activity-designer"></a>Send-Aktivitätsdesigner

Die **senden** Aktivitäts-Designer dient zum Erstellen und Konfigurieren einer <xref:System.ServiceModel.Activities.Send> Aktivität.

## <a name="the-send-activity"></a>Die Send-Aktivität

 Eine <xref:System.ServiceModel.Activities.Send>-Aktivität wird verwendet, um eine Nachricht an einen Dienst zu senden. Eine <xref:System.ServiceModel.Activities.ReceiveReply>-Aktivität kann an eine <xref:System.ServiceModel.Activities.Send>-Aktivität gebunden werden, die eine Nachricht als Teil eines Anforderungs-/Antwort-Nachrichtenaustauschmusters auf dem Client empfängt.

### <a name="using-the-send-activity-designer"></a>Verwenden des Send-Aktivitätsdesigners
 Die **senden** Aktivitäts-Designer finden Sie in der **Messaging** Kategorie der **Toolbox**, die erfolgt durch Klicken auf die **Toolbox** Registerkarte "im Workflow-Designer (Wählen Sie alternativ **Symbolleiste** aus der **Ansicht** Menüs oder STRG + ALT + X.)

 Die **senden** Aktivitäts-Designer gezogen werden kann, aus der **Toolbox** und sich der Workflow-Designer-Oberfläche gelöscht wird, wo Aktivitäten normalerweise platziert werden. Daraufhin wird eine <xref:System.ServiceModel.Activities.Send>-Aktivität mit dem <xref:System.Activities.Activity.DisplayName%2A>-Standardwert Send erstellt. Die <xref:System.Activities.Activity.DisplayName%2A> kann im Header des bearbeitet werden die **senden** Aktivitäts-Designer oder in der **DisplayName** Feld des Eigenschaftenrasters.

 Zum Erstellen einer <xref:System.ServiceModel.Activities.ReceiveReply> Aktivität und ihn mit dem ausgewählten <xref:System.ServiceModel.Activities.Send> Aktivität, mit der rechten Maustaste die **senden** Aktivität, und klicken Sie die **ReceiveReply erstellen** Element im Kontextmenü und die **ReceiveReplyForSend** Designer wird unterhalb der **senden** Designer. Die <xref:System.ServiceModel.Activities.ReceiveReply>-Aktivität ist eine Aktivität, die eine Nachricht als Teil eines Anforderungs-/Antwort-Nachrichtenaustauschmusters auf dem Client empfängt. Es kann konfiguriert werden, mit der **ReceiveReplyForSend** Designer.

 Alternativ können Sie die **SendAndReceiveReply** Dienstvorlagen-Designer in der **Messaging** Kategorie der **Toolbox** können verwendet werden, um ein paar vorkonfigurierter Erstellen<xref:System.ServiceModel.Activities.Send>und <xref:System.ServiceModel.Activities.ReceiveReply> Aktivitäten. Weitere Informationen zur Verwendung von der **SendAndReceiveReply** und **ReceiveReplyForSend** Vorlagen finden Sie unter der [SendAndReceiveReply](../workflow-designer/sendandreceivereply-template-designer.md) Thema.

### <a name="the-send-activity-properties"></a>Die Eigenschaften der Send-Aktivität
 In der folgenden Tabelle werden die <xref:System.ServiceModel.Activities.Send>-Eigenschaften aufgeführt, und es wird beschrieben, wie sie im Designer verwendet werden. Diese Eigenschaften können im Eigenschaftenraster oder auf die Oberfläche des Workflow-Designer bearbeitet werden.

|Eigenschaftenname|Erforderlich|Verwendung|
|-------------------|--------------|-----------|
|<xref:System.Activities.Activity.DisplayName%2A>|False|Der Anzeigename der <xref:System.ServiceModel.Activities.Send>-Aktivität. Der Standardwert lautet Send. Obwohl der <xref:System.Activities.Activity.DisplayName%2A> nicht zwingend erforderlich ist, wird empfohlen, einen Anzeigenamen zu verwenden.|
|<xref:System.ServiceModel.Activities.Send.OperationName%2A>|True|Der Name des Dienstvorgangs, der von dieser <xref:System.ServiceModel.Activities.Send>-Aktivität aufgerufen wurde. Diese Eigenschaft wird verwendet, um den Standardwert für die **Aktion** Eigenschaft Wenn die **Aktion** Eigenschaft nicht ausdrücklich festgelegt ist.|
|<xref:System.ServiceModel.Activities.Send.ServiceContractName%2A>|True|Der Name des Dienstvertrags, der von dem aufzurufenden Dienst implementiert wird.|
|<xref:System.ServiceModel.Activities.Send.Content%2A>|False|Gibt die zu empfangende Nachricht oder den zu empfangenden Parameterinhalt an. Dies kann entweder eine <xref:System.ServiceModel.Activities.ReceiveMessageContent>-Aktivität oder eine <xref:System.ServiceModel.Activities.ReceiveParametersContent>-Aktivität sein. Diese Eigenschaft bearbeiten, indem Sie auf die Schaltfläche mit den Auslassungspunkten neben der **Content** Feld im Eigenschaftenraster oder indem Sie auf die **definieren...**  neben der **Content** auf bezeichnen die **Receive** aktivitätsdesigneroberfläche. Beides anzeigen der **Inhaltsdefinition** Dialogfeld. Weitere Informationen dazu, wie Sie dieses Feld verwenden, finden Sie unter der [Content Vorgangsdefinition (Dialogfeld)](../workflow-designer/content-definition-dialog-box.md) Thema.|
|<xref:System.ServiceModel.Activities.Send.CorrelatesWith%2A>|False|Gibt den <xref:System.ServiceModel.Activities.CorrelationHandle> an, der verwendet wurde, um die Nachricht an die entsprechende Workflowinstanz weiterzuleiten.<br /><br /> Klicken Sie auf die Schaltfläche mit den Auslassungszeichen neben der <xref:System.ServiceModel.Activities.Send.CorrelatesWith%2A> Eigenschaft im Eigenschaftenraster So öffnen die **Ausdrucks-Editor** (Dialogfeld). Weitere Informationen zur Verwendung dieses Dialogfelds finden Sie unter der [Vorgehensweise: Verwenden Sie den Ausdrucks-Editor](../workflow-designer/how-to-use-the-expression-editor.md) Thema.|
|<xref:System.ServiceModel.Activities.Send.CorrelationInitializers%2A>|False|Gibt die Auflistung von <xref:System.ServiceModel.Activities.CorrelationInitializer>-Objekten an, die mehrere <xref:System.ServiceModel.Activities.CorrelationHandle>-Objekte initialisiert, die diese <xref:System.ServiceModel.Activities.Send>-Aktivität im Workflow konfigurieren. Klicken Sie auf die Schaltfläche mit den Auslassungszeichen neben der <xref:System.ServiceModel.Activities.Send.CorrelationInitializers%2A> Eigenschaft im Eigenschaftenraster So öffnen die **Korrelationsinitialisierer hinzufügen** (Dialogfeld). Weitere Informationen zu diesem Feld verwenden, finden Sie unter der [CorrelationInitializers-Dialogfeld hinzufügen](../workflow-designer/add-correlationinitializers-dialog-box.md) Thema.|
|<xref:System.ServiceModel.Activities.Send.KnownTypes%2A>|False|Eine Auflistung bekannter Typen für den von dieser <xref:System.ServiceModel.Activities.Send>-Aktivität aufzurufenden Dienstvorgang. Diese Eigenschaft muss in Verbindung mit der <xref:System.ServiceModel.Activities.Receive.SerializerOption%2A>-Eigenschaft verwendet werden, die auf <xref:System.Runtime.Serialization.DataContractSerializer> festgelegt wurde. Sie wird ignoriert, wenn der <xref:System.Xml.Serialization.XmlSerializer> verwendet wird.<br /><br /> Klicken Sie auf die Schaltfläche mit den Auslassungspunkten neben der **KnownTypes** Feld im Eigenschaftenraster zum Anzeigen der **Typauflistungs-Editor** Dialogfeld, in dem Sie relevante Typen hinzufügen können.<br /><br /> Klicken Sie auf die Schaltfläche mit den Auslassungspunkten neben der **KnownTypes** Feld im Eigenschaftenraster zum Anzeigen der **Typauflistungs-Editor** (Dialogfeld), in dem Sie relevante Typen hinzufügen können. Weitere Informationen zu diesem Feld verwenden, finden Sie unter der [Auflistung-Editor (Dialogfeld)](../workflow-designer/type-collection-editor-dialog-box.md) Thema.|
|<xref:System.ServiceModel.Activities.Send.ProtectionLevel%2A>|True|Gibt die <xref:System.Net.Security.ProtectionLevel>-Einstellung für die Nachricht an.<br /><br /> 1. <xref:System.Net.Security.ProtectionLevel> bedeutet, dass nur die Authentifizierung.<br />2. <xref:System.Net.Security.ProtectionLevel> bedeutet, dass Signierung von Daten, um die Integrität übertragener Daten sicherzustellen.<br />3. <xref:System.Net.Security.ProtectionLevel> bedeutet, dass Daten verschlüsselt und signiert, die Vertraulichkeit und Integrität übertragener Daten sicherzustellen.|
|<xref:System.ServiceModel.Activities.Send.SerializerOption%2A>|True|Das Serialisierungsprogramm, das für den Dienstvorgang verwendet werden soll, der von der <xref:System.ServiceModel.Activities.Send>-Aktivität aufgerufen werden soll. Der Standardwert lautet <xref:System.Runtime.Serialization.DataContractSerializer>, der unter Verwendung eines angegebenen Datenvertrags eine Instanz eines Typs in einen XML-Datenstrom oder ein Dokument serialisiert und daraus deserialisiert.|
|<xref:System.ServiceModel.Activities.Send.Action%2A>|False|Gibt den Aktionsheader der Nachricht an. Wenn sie nicht explizit festgelegt wird, sein Standardwert: https://tempuri.org/{service Vertrag Namespace} / {Dienstvertragsname} / {Vorgangsname}. Bei Festlegung für eine <xref:System.ServiceModel.Activities.Send>-Aktivität muss die <xref:System.ServiceModel.Activities.Receive>-Aktivität, die die Nachricht empfängt, über den gleichen Wert verfügen, damit die Nachricht ordnungsgemäß übermittelt werden kann.|
|<xref:System.ServiceModel.Activities.Send.TokenImpersonationLevel%2A>||Die für den Empfänger der Nachricht zulässige <xref:System.Security.Principal.TokenImpersonationLevel>-Instanz. Definiert die sicherheitsidentitätswechselstufen dar, mit die der Umfang steuern, zu dem eine Serverprozess im Auftrag eines Clientprozesses agieren kann.<xref:System.Security.Principal.TokenImpersonationLevel> Gibt an, dass eine Ebene des Identitätswechsels nicht zugewiesen ist. <xref:System.Security.Principal.TokenImpersonationLevel> gibt an, dass der Serverprozess keine Identifikationsinformationen zum Client abrufen und die Identität des Clients nicht annehmen kann. <xref:System.Security.Principal.TokenImpersonationLevel> gibt an, dass der Serverprozess zwar Informationen zum Client (z. B. die Sicherheits-IDs und Sicherheitsberechtigungen) abrufen, jedoch nicht die Identität des Clients annehmen kann. Dies ist nützlich für Server, die eigene Objekte exportieren (z. B. Datenbankprodukte, von denen Tabellen und Ansichten exportiert werden). Mit den abgerufenen Informationen zur Clientsicherheit können vom Server Entscheidungen im Rahmen der Zugriffsvalidierung getroffen werden, ohne dass andere Dienste verwendet werden können, die den Sicherheitskontext des Clients verwenden. <xref:System.Security.Principal.TokenImpersonationLevel> gibt an, dass der Serverprozess den Sicherheitskontext des Clients auf seinem lokalen System imitieren kann. Der Server kann den Client auf Remotesystemen nicht imitieren. <xref:System.Security.Principal.TokenImpersonationLevel> gibt an, dass der Serverprozess den Sicherheitskontext des Clients auf Remotesystemen imitieren kann.|
|<xref:System.ServiceModel.Activities.Send.Endpoint%2A>||Das <xref:System.ServiceModel.Endpoint>-Objekt, an das die <xref:System.ServiceModel.Activities.Send>-Aktivität eine Nachricht sendet. Wenn diese Eigenschaft festgelegt, wird die <xref:System.ServiceModel.Activities.Send.EndpointConfigurationName%2A> Eigenschaft sollte **null**.|
|<xref:System.ServiceModel.Activities.Send.EndpointAddress%2A>||Das <xref:System.ServiceModel.EndpointAddress>-Objekt, an das die Meldung gesendet wird.|
|<xref:System.ServiceModel.Activities.Send.EndpointConfigurationName%2A>||Der Name der Endpunktkonfiguration. Diese Eigenschaft wird beim Konfigurieren eines Endpunkts in einer Konfigurationsdatei festgelegt. Diese Eigenschaft sollte festgelegt werden, um den angegebenen Namen der  **\<Endpunkt >** Element in der Konfigurationsdatei. Wenn diese Eigenschaft festgelegt ist, die <xref:System.ServiceModel.Activities.Send.Endpoint%2A> Eigenschaft sollte **null**.|

## <a name="see-also"></a>Siehe auch

- [InitializeCorrelation](../workflow-designer/initializecorrelation-activity-designer.md)
- [CorrelationScope](../workflow-designer/correlationscope-activity-designer.md)
- [ReceiveAndSendReply](../workflow-designer/receiveandsendreply-template-designer.md)
- [Empfangen](../workflow-designer/receive-activity-designer.md)
- [SendAndReceiveReply](../workflow-designer/sendandreceivereply-template-designer.md)
- [TransactedReceiveScope](../workflow-designer/transactedreceivescope-activity-designer.md)