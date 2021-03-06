---
title: Ereignisbeschreibungen | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- debugging [Debugging SDK], events
ms.assetid: 09f61652-7e16-4bb0-8055-f61a84bf384e
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 600d9576d72dbd36b5ff7c2a0d9f0333f72dfafa
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/16/2018
---
# <a name="event-descriptions"></a>Ereignisbeschreibungen
Jede Art von Ereignis verfügt über einen bestimmten Zweck.  
  
## <a name="events-and-the-reasons-for-their-use"></a>Ereignisse und die Gründe für deren Verwendung  
  
|event|Beschreibung|  
|-----------|-----------------|  
|Dokumentereignisse aktivieren|Treten Sie auf, wenn die Debugging-Modul (DE) die IDE möchte zu öffnen oder ein Dokument in den Vordergrund bringen.|  
|Haltepunkt gebunden oder Fehlerereignisse Haltepunkt|Gesendet, wenn ein Haltepunkt gebunden ist oder wenn ein Haltepunkt kann nicht gebunden werden und ein Fehler zurückgegeben.|  
|Ungebundene Haltepunktereignisse|Treten Sie auf, wenn Sie ein gebundener Haltepunkt aus Code hebt die Bindung.|  
|Ereignisse können beendet werden.|Der IDE gesendet, um zu bestimmen, ob der Benutzer an einem bestimmten Punkt im Code beenden möchten.|  
|Haltepunktereignisse|Treten Sie auf, wenn ein Code- oder Datenmenge Haltepunkt erreicht wird.|  
|Text Dokumentereignisse|Treten Sie auf, wenn der Text in einem Dokument geändert wird. Diese Ereignisse werden nicht gesendet, durch die `IDebugEventCallBack2::Event` Methode.|  
|Ereignisse für Modul erstellen|Gesendet, wenn ein Modul zum ersten Mal erstellt wird.|  
|Eintrag punktereignisse|Gesendet, wenn das Programm, das gerade gedebuggt wird der Initialisierungscode ausgeführt und seine erste benutzerdefinierter Einstiegspunkt erreicht.|  
|Ausnahmeereignisse|Gesendet, wenn ein aktives Programm auf eine Ausnahme trifft.|  
|Ereignisse durch Abschluss der Ausdruck Auswertung|Gesendet, wenn asynchrone ausdrucksauswertung abgeschlossen ist.|  
|Symbol-Ereignisse suchen|Dann gesendet, wenn DE den Benutzer zur Symbolsuche für ein Modul um Unterstützung bitten muss.|  
|Ereignisse durch Abschluss der Auslastung|Senden nur auf, wenn das erste Programm Laden abgeschlossen ist und im ersten Codebeispiel wird in der Anwendung vor der Ausführung.|  
|Nachrichtenereignisse|Gesendet, wenn Nachrichten an Benutzer gesendet werden.|  
|Ladeereignisse für Module|Gesendet, wenn ein neues Modul geladen oder entladen wird.|  
|Ausgabeereignisse-Zeichenfolge|Gesendet, wenn das Programm die Debugausgabe schreibt.|  
|Erstellen und Zerstören von Ereignissen|An der Erstellung oder Löschung von Prozesse "," Programme "," Eigenschaften "," Sitzungen "und" Threads anzukündigen, damit der Visual Studio-IDE Nachverfolgen der Status der gedebuggten Programme von kann gesendet werden.|  
|Ereignisse durch Abschluss der Schritt|Gesendet, wenn ein Schritt abgeschlossen ist.|  
|Thread-Änderungsereignisse bei Namen|Gesendet, wenn der Benutzer den Namen eines Threads ändert.|  
|Ereignisse des Programms Name ändern|Gesendet, wenn der Benutzer den Namen eines Programms ändert.|  
  
## <a name="see-also"></a>Siehe auch  
 [Senden von Ereignissen](../../extensibility/debugger/sending-events.md)