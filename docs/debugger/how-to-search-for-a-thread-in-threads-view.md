---
title: 'Vorgehensweise: Suchen nach einem Thread in der Threadansicht | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
helpviewer_keywords:
- threads, searching
ms.assetid: 5609a9b3-c279-4426-9e2e-dd87896a6d6f
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: b5eee67e195821f89dbd820f930288eb24f20a11
ms.sourcegitcommit: 3d10b93eb5b326639f3e5c19b9e6a8d1ba078de1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2018
---
# <a name="how-to-search-for-a-thread-in-threads-view"></a>Gewusst wie: Suchen nach einem Thread in der Threadansicht
Sie können mithilfe der Thread-ID oder ein Modul Zeichenfolge als Suchkriterium für einen bestimmten Thread in der Threadansicht suchen. Sie können auch die ausgangsrichtung der Suche angeben. Die Felder im Dialogfeld werden die Attribute des ausgewählten Threads in die Threadstruktur anzeigen.  
  
### <a name="to-search-for-a-thread-in-threads-view"></a>Suchen Sie für einen Thread in der Threadansicht  
  
1.  Ordnen Sie die Fenster so, Spy++ und ein aktives [Threadansicht](../debugger/threads-view.md) Fenster sichtbar sind.  
  
2.  Aus der **Suche** Menü wählen **Thread suchen**.  
  
     Die [Thread-Dialogfeld "Fenstersuche"](../debugger/thread-search-dialog-box.md) wird geöffnet.  
  
3.  Geben Sie die Thread-ID oder einen Modulnamen als Suchkriterien.  
  
4.  Deaktivieren Sie alle Felder, die für die Sie keine Werte angeben möchten.  
  
    > [!TIP]
    >  Um alle Threads, die im Besitz von einem Modul zu suchen, deaktivieren Sie die **Thread** Textfeld und Typ des Moduls im Namen der **Modul** Feld. Verwenden Sie dann **Weitersuchen** Suche nach Threads fort.  
  
5.  Wählen Sie **einrichten** oder **unten** für die anfängliche Richtung der Suche.  
  
6.  Klicken Sie auf **OK**.  
  
 Wenn ein entsprechender Thread gefunden wird, wird es in der Ansicht Threadfenster hervorgehoben.