---
title: Administratorhandbuch für Visual Studio
description: Erfahren Sie mehr zur Bereitstellung von Visual Studio in einer Unternehmensumgebung.
ms.custom: ''
ms.date: 05/15/2017
ms.technology: vs-acquisition
ms.prod: visual-studio-dev15
ms.topic: conceptual
helpviewer_keywords:
- network installation, Visual Studio
- administrator guide, Visual Studio
- installing Visual Studio, administrator guide
ms.assetid: 4af353f5-6cfd-4ebe-bcfb-f42306e451a0
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 39d9c6c3c63fe1c601a307ff006858a64db56c83
ms.sourcegitcommit: 4c0bc21d2ce2d8e6c9d3b149a7d95f0b4d5b3f85
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/20/2018
---
# <a name="visual-studio-2017-administrator-guide"></a>Administratorhandbuch für Visual Studio 2017

In Unternehmensumgebungen ist es üblich, dass Systemadministratoren Installationen für Endbenutzer über eine Netzwerkfreigabe oder mithilfe von Systemverwaltungssoftware bereitstellen. Wir haben das Visual Studio-Setupprogramm so gestaltet, dass es die unternehmensweite Bereitstellung unterstützt. Systemadministratoren können einen Speicherort für die Netzwerkinstallation erstellen, Standardwerte für die Installation vorkonfigurieren, Product Keys während des Installationsvorgangs bereitstellen und nach erfolgreicher Einführung Produktupdates verwalten. Dieses Handbuch für Administratoren bietet vom jeweiligen Szenario abhängige Anleitungen für die Unternehmensbereitstellung in Netzwerkumgebungen.

## <a name="deploying-visual-studio-2017-in-an-enterprise-environment"></a>Bereitstellen von Visual Studio 2017 in einer Unternehmensumgebung

Sie können Visual Studio 2017 auf Clientarbeitsstationen bereitstellen, solange jeder Zielcomputer die [minimalen Installationsanforderungen](https://www.visualstudio.com/en-us/productinfo/vs2017-system-requirements-vs) erfüllt. Egal, ob Sie über Software, z.B. System Center oder über eine Batchdatei bereitstellen, Sie sollten in der Regel die folgenden Schritte durchlaufen:

1. [Erstellen Sie eine Netzwerkfreigabe, die Visual Studio-Produktdateien enthält](create-a-network-installation-of-visual-studio.md) an einem Speicherort im Netzwerk.

2. [Wählen Sie die Arbeitsauslastungen und Komponenten](workload-and-component-ids.md) aus, die installiert werden sollen.

3. [Erstellen Sie eine Antwortdatei](automated-installation-with-response-file.md), die Standardinstallationsoptionen enthält. [Erstellen Sie alternativ ein Installationsskript](use-command-line-parameters-to-install-visual-studio.md), das Befehlszeilenparametern zum Steuern der Installation verwendet.

4. [Wenden Sie optional einen Volumenlizenz-Produktschlüssel](automatically-apply-product-keys-when-deploying-visual-studio.md) als Teil des Installationsskripts an, damit Benutzer die Software nicht separat aktivieren müssen.

5. Aktualisieren Sie das Netzwerklayout, [um zu steuern, wann Produktupdates an Ihre Endbenutzer übermittelt werden](controlling-updates-to-visual-studio-deployments.md).

6. Legen Sie optional Registrierungsschlüssel fest, [um zu steuern, was auf Clientarbeitsstationen zwischengespeichert wird](set-defaults-for-enterprise-deployments.md).

7. Verwenden Sie zum Ausführen des Skripts auf der Ziel-Entwicklerarbeitsstationen die Bereitstellungstechnologie Ihrer Wahl.

8. [Aktualisieren Sie den Netzwerkspeicherort mit den neuesten Updates](update-a-network-installation-of-visual-studio.md) für Visual Studio durch regelmäßiges Ausführen des Befehls, den Sie in Schritt 1 verwendet haben, um aktualisierte Komponenten hinzuzufügen.

> [!IMPORTANT]
> Beachten Sie, dass sich Installationen über eine Netzwerkfreigabe den ursprünglichen Quellspeicherort „merken“. Dies bedeutet, dass Sie zur Reparatur eines Clients möglicherweise zur Netzwerkfreigabe zurückkehren müssen, über die der Client ursprünglich installiert wurde. Wählen Sie die Netzwerkadresse sorgfältig aus, sodass sie der Lebensdauer der Visual Studio 2017-Clients in Ihrer Organisation entspricht.

## <a name="visual-studio-tools"></a>Visual Studio Tools

Wir haben mehrere Tools zur Verfügung gestellt, mit denen Sie [installierte Instanzen von Visual Studio auf Clientcomputern erkennen und verwalten](tools-for-managing-visual-studio-instances.md) können:

> [!TIP]
> Zusätzlich zur Dokumentation im Administratorhandbuch ist der [Blog von Heath Stewart](https://blogs.msdn.microsoft.com/heaths/tag/vs2017/) eine gute Quelle für Informationen zum Setup von Visual Studio 2017.

## <a name="get-support"></a>Support aufrufen

Manchmal kann etwas schiefgehen. Wenn bei der Installation von Visual Studio ein Fehler auftritt, lesen Sie den Artikel [Problembehandlung bei Visual Studio 2017-Installations- und -Upgradefehlern](troubleshooting-installation-issues.md). Wenn keiner der Schritte zur Problembehandlung hilfreich ist, können Sie uns per Livechat kontaktieren, um Hilfe bei der Installation zu erhalten (nur in englischer Sprache). Einzelheiten finden Sie auf der [Visual Studio-Supportseite](https://www.visualstudio.com/vs/support/#talktous).

Hier sind einige weitere Supportoptionen:

* Sie können uns über Produktprobleme mit dem Tool [Problem melden](../ide/how-to-report-a-problem-with-visual-studio-2017.md) informieren, das sowohl im Visual Studio-Installer als auch in der Visual Studio-IDE angezeigt wird.
* Sie können uns einen Produktvorschlag unter [UserVoice](https://visualstudio.uservoice.com/forums/121579) mitteilen.
* Sie können Probleme mit Produkten und Antworten in der [Visual Studio-Entwicklercommunity](https://developercommunity.visualstudio.com/) finden.
* Sie können auch über die [Visual Studio-Unterhaltung in der Gitter-Community](https://gitter.im/Microsoft/VisualStudio) Kontakt zu uns oder zu anderen Visual Studio-Entwicklern aufnehmen. (Diese Option erfordert ein [GitHub](https://github.com/)-Konto.)

## <a name="see-also"></a>Siehe auch

* [Installieren von Visual Studio 2017](install-visual-studio.md)
* [Verwenden von Befehlszeilenparametern zum Installieren von Visual Studio 2017](use-command-line-parameters-to-install-visual-studio.md)
  * [Beispiele für Befehlszeilenparameter](command-line-parameter-examples.md)
  * [Referenz der Arbeitsauslastungs- und Komponenten-IDs](workload-and-component-ids.md)
* [Erstellen einer netzwerkbasierten Installation von Visual Studio](create-a-network-installation-of-visual-studio.md)
  * [Installieren der für eine Offlineinstallation von Visual Studio erforderlichen Zertifikate](install-certificates-for-visual-studio-offline.md)
* [Automatisieren von Visual Studio mit einer Antwortdatei](automated-installation-with-response-file.md)
* [Automatisches Anwenden von Produktschlüsseln bei der Bereitstellung von Visual Studio](automatically-apply-product-keys-when-deploying-visual-studio.md)
* [Festlegen von Standardeinstellungen für Unternehmensbereitstellungen von Visual Studio](set-defaults-for-enterprise-deployments.md)
* [Deaktivieren oder Verschieben des Paketcaches](disable-or-move-the-package-cache.md)
* [Aktualisieren einer netzwerkbasierten Installation von Visual Studio](update-a-network-installation-of-visual-studio.md)
* [Steuern von Updates für Visual Studio-Bereitstellungen](controlling-updates-to-visual-studio-deployments.md)
* [Tools zum Erkennen und Verwalten von Visual Studio-Instanzen](tools-for-managing-visual-studio-instances.md)
