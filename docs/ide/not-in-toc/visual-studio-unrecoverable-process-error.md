---
title: Nicht behebbare Prozessfehler in Visual Studio
ms.date: 02/23/2017
ms.topic: troubleshooting
helpviewer_keywords:
- editor
author: gewarren
ms.author: gewarren
manager: douge
ms.prod: visual-studio-dev15
ms.technology: vs-ide-general
ms.workload:
- multiple
ms.openlocfilehash: 1db7f2729ded01eedda6fff6d18ca1b2ee3607b6
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/26/2018
---
# Nicht behebbare Prozessfehler in Visual Studio

Visual Studio 2017 verwendet mehrere Out-of-Proc-Prozesse, um die erforderlichen Hintergrundaufgaben, wie z.B. Live-Komponententests, Code-Analyzer und mehr auszuführen. Diese Prozesse werden Out-of-Proc ausgeführt, um Leistungsvorteile von Visual Studio zu nutzen, z.B. dass Visual Studio schneller reagieren kann, wenn ressourcenintensive, langfristige Jobs ausgeführt werden. Da Visual Studio ein 32-Bit-Prozess ist, bietet die Out-of-Proc-Ausführung von Prozessen anspruchsvollen speicherintensiven Arbeiten einen größeren Speicherplatz, in dem ausgeführt werden soll.

Wenn einer dieser erforderlichen Prozesse aus irgendeinem Grund endet, wird eine Popup Informationsleiste mit der folgenden Meldung angezeigt:

„Unfortunately, a process used by Visual Studio has encountered an unrecoverable error. We recommend saving your work, and then closing and restarting Visual Studio.“ (Leider ist bei einem Prozess mit Visual Studio ein nicht behebbarer Fehler aufgetreten. Wir empfehlen Ihnen, Ihre Arbeit abzuspeichern und Visual Studio anschließend neu zu starten.)

Wenn diese Meldung angezeigt wird, müssen Sie Ihre Arbeit sofort speichern, und anschließend Visual Studio schließen und neu starten. Wenn Sie dies nicht tun, kann Visual Studio jederzeit abstürzen.

## Liste der Prozesse

Es folgt eine Liste der von Visual Studio verwendeten Out-of-Proc-Prozesse, die ausgeführt werden müssen, sodass Visual Studio ordnungsgemäß arbeitet.

- Microsoft.Alm.Shared.Remoting.RemoteContainer.dll
- Microsoft.CodeAnalysis.LiveUnitTesting.EntryPoint
- PerfWatson2.exe
- ServiceHub.Host.Node.x86.exe
- ServiceHub.IdentityHost.exe
- ServiceHub.VSDetouredHost.exe
- ServiceHub.SettingsHost.exe
- ServiceHub.Host.CLR.x86.exe
- ServiceHub.RoslynCodeAnalysisService32.exe
- „ServiceHub.RoslynCodeAnalysisService.exe“
- WindowsAzureGuestAgent.exe
- WindowsAzureTelemetryService.exe
- WaAppAgent.exe