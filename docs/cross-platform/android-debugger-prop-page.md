---
title: Android-Debuggereigenschaften (C++) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 10/23/2017
ms.technology: vs-ide-mobile
ms.topic: conceptual
ms.assetid: 789f7a1c-38b4-41d0-809b-14f4d96c8116
author: corob
ms.author: mblome
manager: douge
f1_keywords:
- VC.Project.AndroidDebugger.DebuggerType
- VC.Project.AndroidDebugger.AndroidDeviceID
- VC.Project.AndroidDebugger.PackagePath
- VC.Project.AndroidDebugger.LaunchActivity
ms.workload:
- xplat-cplusplus
ms.openlocfilehash: 7d18125c6666a8eb68becd828da36ecdab077507
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/16/2018
---
# <a name="android-debugger-properties"></a>Android-Debuggereigenschaften

Eigenschaft | description | Auswahlmöglichkeiten
--- | ---| ---
Debuggertyp | Gibt den Codetyp an, der debuggt werden soll. | **Nur systemeigen**<br>**Nur Java**<br>
Debugziel | Gibt den Emulator oder das Gerät an, das zum Debuggen verwendet werden soll. Verwenden Sie bitte „Android Virtual Device (AVD) Manager“, um ein Gerät zu starten, wenn keine Emulatoren ausgeführt werden.
Zu startendes Paket | Gibt den Speicherort der APK-Datei an, für die das Debugging ausgeführt wird. Wählen Sie diese Option aus, um anzugeben, dass ein bestimmtes Paket (Android-Anwendungspaket) beim Debuggen der Anwendung gestartet werden soll.
Starten der Aktivität | Die Android-Aktivität, die zum Start der Anwendung verwendet wird, muss mit der im Anwendungsmanifest verwendeten Aktivität übereinstimmen. Drücken Sie auf „Apply“ (Anwenden), um die Liste aus AndroidManifest.xml abzurufen und dynamisch aufzufüllen.
Zusätzliche Symbolsuchpfade | Zusätzlicher Suchpfad für Debugsymbole
Zusätzliche Suchpfade für Java-Quellen | Zusätzliche Suchpfade für Java-Quelldateien. (Gilt nur, wenn Debuggertyp „nur Java“ ist.)
