---
title: Visual Studio-Tools für Office-Laufzeit-Installationsszenarien
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- Visual Studio Tools for Office runtime, installation scenarios
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: 2af3f4834fecfe4fcfba30f736892057893ed143
ms.sourcegitcommit: 4cd4aef53e7035d23e7d1d0f66f51ac8480622a1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/05/2018
ms.locfileid: "34767724"
---
# <a name="visual-studio-tools-for-office-runtime-installation-scenarios"></a>Visual Studio-Tools für Office-Laufzeit-Installationsszenarien
  Sie können Visual Studio 2010-Tools für Office-Laufzeit auf drei Arten installieren:  
  
-   Wenn Sie Visual Studio installieren.  
  
-   Wenn Sie Microsoft Office installieren.  
  
-   Wenn Sie Visual Studio 2010-Tools für Office-Laufzeit installieren.  
  
 Die installierten Laufzeitkomponenten hängen von der Konfiguration des Computers und dem Installationsszenario ab.  
  
## <a name="runtime-components-that-are-installed-in-each-installation-scenario"></a>In den einzelnen Installationsszenarien installierte Laufzeitkomponenten  
 Visual Studio 2010-Tools für Office-Laufzeit besteht aus drei Komponenten: das Ladeprogramm für Office-Projektmappen, die Office-Erweiterungen für .NET Framework 3.5 und Office-Erweiterungen für die [!INCLUDE[net_v40_short](../sharepoint/includes/net-v40-short-md.md)] oder höher. Wenn Sie die Laufzeit installieren, wird das Ladeprogramm für Office-Projektmappen immer installiert. Die Installation der Office-Erweiterungen für .NET Framework hängt von der Konfiguration des Computers und dem Installationsszenario ab. Wenn eine der Office-Erweiterungen bei der erstmaligen Installation der Laufzeit nicht installiert werden kann, installiert die Laufzeit die fehlenden Office-Erweiterungen später automatisch, sobald bestimmte Anforderungen erfüllt sind. Diese Funktion der Laufzeit aufgerufen wird *bei Bedarf installieren*.  
  
 In der folgenden Tabelle ist dargestellt, welche Laufzeitkomponenten bei den einzelnen Laufzeitinstallationsszenarios standardmäßig installiert werden. Weitere Informationen zu den einzelnen Szenarien finden Sie weiter unten.  
  
|Laufzeitinstallationsszenario|Ladeprogramm für Office-Projektmappen|Office-Erweiterungen für .NET Framework 3.5|Office-Erweiterungen für [!INCLUDE[net_v40_short](../sharepoint/includes/net-v40-short-md.md)]|Office-Erweiterungen für [!INCLUDE[net_v45](../vsto/includes/net-v45-md.md)]|  
|-----------------------------------|----------------------------|--------------------------------------------------|---------------------------------------------------------------------------------------|---------------------------------------------------------------------------|  
|Mit [!INCLUDE[vs_dev12](../vsto/includes/vs-dev12-md.md)] und höher|Ja|Ja, wenn .NET Framework 3.5 bereits installiert ist.|Ja|Ja|  
|Mit [!INCLUDE[office14_long](../vsto/includes/office14-long-md.md)]|Ja|Ja, wenn .NET Framework 3.5 bereits installiert ist.|Nein|Nein|  
|Mit Office 2010 Service Pack 1 (SP1) oder höher|Ja|Ja, wenn .NET Framework 3.5 bereits installiert ist.|Ja, wenn [!INCLUDE[net_v40_short](../sharepoint/includes/net-v40-short-md.md)] bereits installiert ist.|Nein|  
|Mit dem verteilbaren Laufzeitpaket|Ja|Ja, wenn .NET Framework 3.5 bereits installiert ist.|Ja, wenn [!INCLUDE[net_v40_short](../sharepoint/includes/net-v40-short-md.md)] bereits installiert ist.|Ja, wenn [!INCLUDE[net_v45](../vsto/includes/net-v45-md.md)] bereits installiert ist.|  
  
### <a name="install-the-runtime-with-visual-studio-or-the-microsoft-office-developer-tools-for-visual-studio"></a>Installieren der Laufzeitmoduls mit Visual Studio oder Microsoft Office Developer Tools für Visual Studio  
 Wenn Sie die Office Developer Tools in Visual Studio installieren, werden die Office-Erweiterungen für [!INCLUDE[net_v45](../vsto/includes/net-v45-md.md)] und [!INCLUDE[net_v40_short](../sharepoint/includes/net-v40-short-md.md)] immer auf dem Entwicklungscomputer installiert. Die Office-Erweiterungen für .NET Framework 3.5 werden nur installiert, wenn .NET Framework 3.5 bereits auf dem Entwicklungscomputer vorhanden ist. Falls Sie .NET Framework 3.5 nach der Installation von [!INCLUDE[vs_dev12](../vsto/includes/vs-dev12-md.md)] installieren, installiert die Laufzeit automatisch die Office-Erweiterungen für .NET Framework 3.5, wenn Sie zum ersten Mal ein Office-Projekt mit der Zielversion .NET Framework 3.5 erstellen.  
  
> [!WARNING]  
>  Sie können kein Office-Projekt mit [!INCLUDE[vs_dev12](../vsto/includes/vs-dev12-md.md)] oder höher erstellen, das .NET Framework 3.5 als Ziel verwendet.  
  
 Weitere Informationen zu den Office Developer Tools zu installieren, finden Sie unter [Vorgehensweise: konfigurieren ein Computers zum Entwickeln von Office-Projektmappen](../vsto/how-to-configure-a-computer-to-develop-office-solutions.md).  
  
### <a name="install-the-runtime-with-office"></a>Installieren der Laufzeitmoduls mit Office  
 Wenn Sie Office installieren, werden die Office-Erweiterungen für .NET Framework 3.5 installiert, sofern .NET Framework 3.5 bereits auf dem Computer vorhanden ist. Falls Sie .NET Framework 3.5 nach der Installation von Office installieren, installiert die Laufzeit automatisch die Office-Erweiterungen für .NET Framework 3.5, wenn zum ersten Mal von einer Office-Anwendung versucht wird, eine Projektmappe mit der Zielversion .NET Framework 3.5 zu laden.  
  
 Die Office-Erweiterungen für [!INCLUDE[net_v40_short](../sharepoint/includes/net-v40-short-md.md)] oder höher werden nicht zusammen mit Office installiert. Dies gilt auch, wenn [!INCLUDE[net_v40_short](../sharepoint/includes/net-v40-short-md.md)] oder höher beim Installieren von Office bereits vorhanden ist.  
  
 Die Office-Erweiterungen für [!INCLUDE[net_v40_short](../sharepoint/includes/net-v40-short-md.md)] werden zusammen mit Office installiert. Endbenutzer erhalten die Office-Erweiterungen für [!INCLUDE[net_v45](../vsto/includes/net-v45-md.md)] durch Installieren eines Windows-Updates.  
  
 Um sicherzustellen, dass Ihre Benutzer für Ihre Anwendung verwenden, die notwendigen Erweiterungen verfügen, schließen Sie die neueste Version von Visual Studio 2010-Tools für Office-Laufzeit als erforderliche Komponente für Ihre Lösung. Weitere Informationen zu Voraussetzungen finden Sie unter [erforderliche Komponenten für Office-Projektmappen für die Bereitstellung](http://msdn.microsoft.com/en-us/9f672809-43a3-40a1-9057-397ce3b5126e).  
  
### <a name="install-the-runtime-by-using-the-runtime-redistributable"></a>Installieren Sie die Laufzeit mithilfe des verteilbaren Laufzeitpakets  
 Sie können die Laufzeit installieren, die Visual Studio 2010-Tools für Office-Laufzeit manuell ausführen oder das verteilbare Paket als erforderliche Komponente einschließen, wenn Sie eine Office-Projektmappe bereitstellen.  
  
 Bei der Installation der Laufzeitmoduls mit Visual Studio 2010-Tools für Office-Laufzeit, die Office-Erweiterungen für .NET Framework 3.5 und Office-Erweiterungen für die [!INCLUDE[net_v40_short](../sharepoint/includes/net-v40-short-md.md)] oder höher installiert werden, wenn die entsprechenden Versionen von .NET Framework befinden sich bereits auf dem Computer vorhanden. Ist eine dieser .NET Framework-Versionen beim Installieren der Laufzeit nicht auf dem Computer vorhanden, werden die Office-Erweiterungen für die fehlende .NET Framework-Version zu diesem Zeitpunkt nicht installiert. Falls Sie die fehlende .NET Framework-Version zu einem späteren Zeitpunkt installieren, installiert die Laufzeit die entsprechenden Office-Erweiterungen automatisch, wenn das nächste Mal eine Projektmappe, die die Erweiterungen erfordert, installiert (wenn die Laufzeit mit einer mit ClickOnce bereitgestellten Projektmappe installiert wurde) oder geladen wird (wenn die Laufzeit mit einer mit Windows Installer bereitgestellten Projektmappe installiert wurde).  
  
 Weitere Informationen zum Einschließen erforderlicher Komponenten in einer ClickOnce-Projektmappe finden Sie unter [Vorgehensweise: Installieren der erforderlichen Komponenten auf Endbenutzercomputern zum Ausführen von Office-Projektmappen](http://msdn.microsoft.com/en-us/74dd2c52-838f-4abf-b2b4-4d7b0c2a0a98). Weitere Informationen zur manuellen Installation der Laufzeit über das redistributable Package finden Sie unter [Vorgehensweise: Installieren der Visual Studio-Tools für Office-Laufzeit](../vsto/how-to-install-the-visual-studio-tools-for-office-runtime-redistributable.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Visual Studio-Tools für Office-laufzeitübersicht](../vsto/visual-studio-tools-for-office-runtime-overview.md)   
 [Assemblys in Visual Studio-Tools für Office-Laufzeit](../vsto/assemblies-in-the-visual-studio-tools-for-office-runtime.md)  
  
  