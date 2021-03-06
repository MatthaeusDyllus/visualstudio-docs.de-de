---
title: Aufrufen von Debugger-Ereignissen | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- debugging [Debugging SDK], events
ms.assetid: b3440ac3-80af-40c6-bef4-cbf00fa67885
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 3960d464b1a6d44fb77eba23cd518fea1f2e5a39
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/16/2018
---
# <a name="calling-debugger-events"></a>Aufrufen von Debugger-Ereignisse
Ereignisse in Debugsitzungen werden in einer bestimmten Reihenfolge auftreten.  
  
## <a name="discussion"></a>Diskussion  
 Um das Muster der Aufrufe zwischen der Debugging-Modul (Deutschland) und die Sitzungs-Debug-Manager (SDM) zu verstehen, stellt die folgenden die aufrufende Reihenfolge der Ereignisse, die in eine typische Debuggingsitzung auftreten:  
  
1.  [Anfügen und Trennen an ein Programm](../../extensibility/debugger/attaching-and-detaching-to-a-program.md)  
  
2.  [Starten des Debuggers](../../extensibility/debugger/launching-the-debugger.md)  
  
3.  [Beenden eines Programms](../../extensibility/debugger/terminating-a-program.md)  
  
4.  [Erstellen eines Haltepunkts](../../extensibility/debugger/creating-a-breakpoint.md)  
  
5.  [Wenn ein Haltepunkt gebunden oder zunehmend aufgehoben](../../extensibility/debugger/when-a-breakpoint-binds-or-becomes-unbound.md)  
  
6.  [Haltepunkt-Fehler](../../extensibility/debugger/breakpoint-errors.md)  
  
7.  [Das Erreichen eines Haltepunkts](../../extensibility/debugger/hitting-a-breakpoint.md)  
  
8.  [Löschen eines Haltepunkts](../../extensibility/debugger/deleting-a-breakpoint.md)  
  
9. [Unterbrechungsmodus](../../extensibility/debugger/entering-break-mode.md)  
  
10. [Ausführen in Einzelschritten im Unterbrechungsmodus](../../extensibility/debugger/stepping-in-break-mode.md)  
  
11. [Auswertung von Ausdrücken im Unterbrechungsmodus](../../extensibility/debugger/expression-evaluation-in-break-mode.md)  
  
12. [Ausnahmebehandlung](../../extensibility/debugger/exception-handling-visual-studio-sdk.md)  
  
## <a name="see-also"></a>Siehe auch  
 [Erstellen eines benutzerdefinierten Debugmoduls](../../extensibility/debugger/creating-a-custom-debug-engine.md)