---
title: Debuggen im gemischten Modus wird nur unterstützt, wenn Microsoft .NET Framework 2.0 oder 3.0 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
f1_keywords:
- vs.debug.error.interop_unsupported_to_old
dev_langs:
- CSharp
- VB
- FSharp
- C++
ms.assetid: f607af6f-57fe-472a-a32e-b6202067aa96
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- dotnet
ms.openlocfilehash: 5492c79fa15582c5aeaf9b7794958a37bd569313
ms.sourcegitcommit: 3d10b93eb5b326639f3e5c19b9e6a8d1ba078de1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2018
---
# <a name="mixed-mode-debugging-is-only-supported-when-using-microsoft-net-framework-20-or-30"></a>Debuggen im gemischten Modus wird nur bei Verwendung von Microsoft .NET Framework, Version 2.0 oder 3.0, unterstützt
Ältere Versionen von Microsoft .NET Framework 2.0 bieten keine Unterstützung für das Debuggen im gemischten Modus von 64-Bit-Prozessen. Dies bedeutet, dass Sie während des Debuggens nicht von verwaltetem Code zu nativem Code oder von nativem Code zu verwaltetem Code wechseln können.  
  
 Sie können Folgendes tun, um dieses Problem zu umgehen:  
  
-   Aktualisieren Sie das Projekt, um Microsoft .NET Framework 2.0 oder 3.0 zu verwenden.  
  
-   Debuggen Sie den verwalteten und den nativen Code in separaten Debugsitzungen.  
  
-   Debuggen Sie den gemischten Code als 32-Bit-Prozess, wie in den folgenden Prozeduren beschrieben.  
  
### <a name="to-change-the-operating-system-to-32-bit-visual-basic-or-c"></a>So ändern Sie das Betriebssystem in 32-Bit (Visual Basic oder C#)  
  
1.  In **Projektmappen-Explorer**mit der rechten Maustaste auf das Projekt, und klicken Sie dann auf **Eigenschaften** im Kontextmenü.  
  
2.  Klicken Sie auf den Eigenschaftenseiten auf die **Kompilieren** oder **Debuggen** Registerkarte.  
  
3.  Klicken Sie auf **Plattform**, und wählen Sie dann **X86** aus der Liste der Plattformen.  
  
     Die Visual Basic- und C#-Compiler erzeugen standardmäßig Code, der mit jeder CPU ausgeführt werden kann. Auf einem 64-Bit-Computer werden diese Binärdateien als 64-Bit-Prozesse ausgeführt. Unter 32-Bit-Prozess ausführen möchten, müssen Sie auswählen **Win32**, nicht **"anycpu"**.  
  
### <a name="to-change-the-operating-system-to-32-bit-cc"></a>So ändern Sie das Betriebssystem in 32-Bit (C/C++)  
  
1.  In **Projektmappen-Explorer**mit der rechten Maustaste auf das Projekt, und klicken Sie dann auf **Eigenschaften** im Kontextmenü.  
  
     Klicken Sie auf den Eigenschaftenseiten auf **Plattform**, und wählen Sie dann **Win32** aus der Liste der Plattformen.  
  
### <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler  
  
-   Finden Sie unter [Einrichten von SQL-Debuggen](http://msdn.microsoft.com/en-us/3db09e68-edcc-42de-9c22-4e97cfd55ab3).  
  
## <a name="see-also"></a>Siehe auch  
 [Debuggen von 64-Bit-Anwendungen](../debugger/debug-64-bit-applications.md)