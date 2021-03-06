---
title: Erstellen benutzerdefinierter Ansichten von verwalteten Objekten | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
f1_keywords:
- vs.debug.data.elements
dev_langs:
- CSharp
- VB
- FSharp
- C++
helpviewer_keywords:
- data types [C#], custom
- custom data types
- managed code, custom data types
- autoexp.dat file
- mcee_cs.dat file
- debugger, expanding data types
- mcee_mc.dat file
ms.assetid: 9969e9b2-9008-4729-8a14-0d6deaa61576
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- dotnet
ms.openlocfilehash: 6be491a5c7a0ceb0ed536416cdd3b273f96b4bb1
ms.sourcegitcommit: 3d10b93eb5b326639f3e5c19b9e6a8d1ba078de1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2018
---
# <a name="create-custom-views-of-managed-objects"></a>Erstellen Sie benutzerdefinierter Ansichten von verwalteten Objekten
Sie können die Art anpassen, wie Datentypen von Visual Studio in Debuggervariablenfenstern angezeigt werden.  
  
## <a name="attributes"></a>Attribute  
 In C# und Visual Basic können Sie Erweiterungen für benutzerdefinierte Daten mit <xref:System.Diagnostics.DebuggerTypeProxyAttribute>, <xref:System.Diagnostics.DebuggerDisplayAttribute> und <xref:System.Diagnostics.DebuggerBrowsableAttribute> hinzufügen.  
  
 In [!INCLUDE[dnprdnlong](../code-quality/includes/dnprdnlong_md.md)]-Code bietet Visual Basic keine Unterstützung des DebuggerBrowsable-Attributs. Diese Einschränkung wurde in aktuelleren Versionen von .NET Framework entfernt.  
  
## <a name="visualizers"></a>Schnellansichten  
 Sie können eine Schnellansicht schreiben, um einen beliebigen verwalteten Datentyp anzuzeigen. Weitere Informationen finden Sie unter [wie: Schreiben einer Schnellansicht](../debugger/how-to-write-a-visualizer.md).  
  
## <a name="native-code"></a>Systemeigener Code  
 Für systemeigenen Code können Sie der Datei autoexp.dat benutzerdefinierte Datentyperweiterungen hinzufügen. Diese Datei befindet sich im Verzeichnis Programme\Microsoft Visual Studio 11.0\Common7\Packages\Debugger. Anweisungen zum Schreiben von Regeln für die Datei `autoexp` befinden sich in der Datei selbst.  
  
> [!CAUTION]
>  Die Struktur dieser Datei und die Syntax der autoexp-Regeln können in den verschiedenen Versionen von Visual Studio unterschiedlich sein.  
  
 Auch die Ansichten von systemeigenen Typen können angepasst werden, und zwar durch das Schreiben eines Expression Evaluator-Add-Ins. Weitere Informationen finden Sie unter [EEAddIn Sample: Debugging Expression Evaluator-Add-In](http://msdn.microsoft.com/en-us/d4f6b068-c812-45bc-9ec0-7e0363c4bb9e).  
  
## <a name="see-also"></a>Siehe auch  
 [Verwenden des DebuggerTypeProxy-Attributs](../debugger/using-debuggertypeproxy-attribute.md)   
 [Verwenden des DebuggerDisplay-Attributs](../debugger/using-the-debuggerdisplay-attribute.md)   
 [Überwachen "und" Schnellüberwachung Windows](../debugger/watch-and-quickwatch-windows.md)   
 [Verbessern des Debuggens mit den Debuggeranzeigeattributen](/dotnet/framework/debug-trace-profile/enhancing-debugging-with-the-debugger-display-attributes)