---
title: Szenarios zum Bearbeiten von Auslastungstests in Visual Studio
ms.date: 10/03/2016
ms.topic: conceptual
helpviewer_keywords:
- load tests, scenarios
- load tests, user activities
- load tests, modeling scenarios
ms.assetid: fec04f2e-bf38-4d44-b2ec-fa50f58fd0d9
author: gewarren
ms.author: gewarren
manager: douge
ms.prod: visual-studio-dev15
ms.technology: vs-ide-test
ms.openlocfilehash: efc9c9af36e5484728b05db1171bb2e9bc30ba0b
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/26/2018
---
# <a name="edit-load-test-scenarios"></a>Bearbeiten von Auslastungstestszenarios

Ein *Szenario* für einen Auslastungstest gibt das Auslastungsmuster, die Testmischung, der Browsermix und die Netzwerkmischung an. Szenarios sind wichtig, da Sie so Tests zur Simulation komplexer und realistischer Arbeitsauslastungen konfigurieren können.

Sie können z. B. eine E-Commerce-Website testen, deren Internet-Front-End von mehreren hundert Kunden mit vielen unterschiedlichen Verbindungsgeschwindigkeiten und verschiedenen Browsern gleichzeitig genutzt wird. Dieselbe Website verfügt möglicherweise auch über eine Administrationsfunktion, die von internen Mitarbeitern zum Aktualisieren von Produkten und zur Anzeige von Statistiken verwendet wird. Diese internen Benutzer werden i. d. R. über den gleichen Browser und über eine schnelle LAN-Verbindung auf die Website zugreifen. Sie möchten die Eigenschaften dieser beiden verschiedenen Benutzergruppen in unterschiedlichen Szenarien kapseln. Jedes Szenario kann einen virtuellen Benutzertyp enthalten. In diesem Fall kann ein Auslastungstestszenario für die virtuellen Kunden und eine weiteres Szenario für die virtuellen internen Benutzer der Website erstellt werden.

## <a name="scenario-components"></a>Szenariokomponenten

Alle Erstkonfigurationsoptionen und -einstellungen, die Sie angeben, wenn Sie einen Auslastungstest erstellen, können später im Auslastungstest-Editor geändert werden. Sie können auch neue Szenarios, Laufzeiteinstellungen und Indikatorensätze zu einem Auslastungstest hinzufügen.

![Auslastungstestszenarien](../test/media/loadtesteditinscenarios.png)

Szenarien enthalten folgende Komponenten:

|||
|-|-|
|Begriff|Definition|
|Browsermix|Simuliert den Zugriff virtueller Benutzer auf eine Website über verschiedene Webbrowser.|
|Auslastungsmuster|Gibt die Anzahl von während eines Auslastungstests aktiven virtuellen Benutzern sowie die Rate an, mit der neue Benutzer gestartet werden. Zum Beispiel Einzelschritt, Konstante oder Zielbasiert.|
|Testmischungsmodell|Gibt die Wahrscheinlichkeit an, dass ein virtueller Benutzers einen bestimmten Test in einem Auslastungstestszenario ausführt. Zum Beispiel 20% Wahrscheinlichkeit der Ausführung von TestA und 80% Wahrscheinlichkeit der Ausführung von TestB. Das Testmischungsmodell sollte den Zielen des Tests für ein bestimmtes Szenario entsprechen.|
|Testmischung|Die Testmischung setzt sich aus der Auswahl von Webleistungs- und Komponententests, die im Szenario enthalten sind, und der Verteilung dieser Tests zusammen.|
|Netzwerkmischung|Simuliert den Zugriff virtueller Benutzer auf eine Website über verschiedene Netzwerkverbindungen. Die Netzwerkmischung bietet Optionen wie LAN, Kabelmodem und andere.|

Ein Szenario verfügt über mehrere weitere Eigenschaften, die Sie mit dem Auslastungstest-Editor bearbeiten können. Weitere Informationen finden Sie unter [Load Test Scenario Properties (Auslastungstestszenario-Eigenschaften)](../test/load-test-scenario-properties.md).

## <a name="tasks"></a>Aufgaben

|Aufgaben|Verwandte Themen|
|-----------|-----------------------|
|**Hinzufügen von simulierten Szenario-Interaktionspausen:** Mithilfe von Reaktionszeiten wird menschliches Verhalten simuliert, das dazu führt, dass Benutzer zwischen Interaktionen mit einer Website Pausen machen. Reaktionszeiten treten zwischen den Anforderungen in einem Webleistungstest und zwischen Testiterationen in einem Auslastungstestszenario auf. Die Verwendung von Reaktionszeiten in einem Auslastungstest kann bei der Erzeugung genauerer Auslastungssimulationen nützlich sein.|-   [Editing Think Times to Simulate Website Human Interaction Delays (Bearbeiten von Reaktionszeiten zum Simulieren von Website-Interaktionsverzögerungen des Benutzers)](../test/edit-think-times-in-load-test-scenarios.md)|
|**Angeben der Anzahl virtueller Benutzer für das Szenario:** Sie können die Auslastungsmustereigenschaften konfigurieren, um anzugeben, wie die simulierte Benutzerauslastung während eines Auslastungstests angepasst wird. Sie erhalten drei integrierte Auslastungsmuster: konstant, schrittweise und zielbasiert. Sie wählen das Auslastungsmuster aus und passen die Werte der Eigenschaften entsprechend Ihren Anforderungen an den Auslastungstest an.|-   [Editing Load Patterns to Model Virtual User Activities (Bearbeiten von Auslastungsmustern zur Modellierung von Aktivitäten virtueller Benutzer)](../test/edit-load-patterns-to-model-virtual-user-activities.md)|
|**Konfigurieren der Wahrscheinlichkeit, dass ein virtueller Benutzer einen Test im Szenario ausführt:** Sie können die Testmischung verwenden, die die Wahrscheinlichkeit angibt, dass ein virtueller Benutzer in einem Auslastungstestszenario einen angegebenen Test ausführt. Auf diese Weise können Sie Auslastungen realitätsnaher simulieren. Anstatt nur einen Workflow für die Anwendungen zu verwenden können Sie mehrere Workflows simulieren. Dies stellt eine bessere Annäherung an die tatsächliche Interaktion zwischen Endbenutzern und Anwendungen dar.|-   [Bearbeiten von Textmischungsmodellen](../test/edit-test-mix-models-to-specify-the-probability-of-a-virtual-user-running-a-test.md)|
|**Hinzufügen oder Entfernen eines Webleistungs- oder Komponententests zu bzw. aus einem Auslastungstestszenario:** Ein Webleistungs- oder Komponententest kann einem Auslastungstest in einem Szenario hinzugefügt bzw. daraus entfernt werden. Ein Auslastungstest umfasst ein oder mehrere Szenarien, von denen jedes einen oder mehrere Webleistungs- oder Komponententests enthält.|-   [Editing the Test Mix (Bearbeiten der Testmischung)](../test/edit-the-test-mix-to-specify-which-web-browsers-types-in-a-load-test-scenario.md)|
|**Konfigurieren der gewünschten Netzwerkmischung für das Szenario:** Mit der Netzwerkmischung können Netzwerkauslastungen in einem Auslastungstestszenario realistischer simuliert werden. Die Auslastung wird durch Verwendung einer heterogenen Mischung von Netzwerktypen anstelle eines einzigen generiert. Sie erreichen so eine bessere Annäherung an die Interaktion zwischen Endbenutzern und Anwendungen. Das Netzwerkmischungsmodell sollte den Zielen des jeweiligen Szenarios entsprechend festgelegt werden.|-   [Specifying Virtual Network Types (Angeben von virtuellen Netzwerktypen)](../test/specify-virtual-network-types-in-a-load-test-scenario.md)|
|**Auswählen des geeigneten Webbrowsermixes für das Szenario:** Mit dem Browsermix können Webauslastungen in einem Auslastungstestszenario realistischer simuliert werden. Die Auslastung wird dabei nicht durch einen einzelnen Browser, sondern durch eine heterogene Browsermischung erzeugt. Dies ergibt eine bessere Annäherung an die Auslastung durch die Browser, die im Normalfall mit Ihren Anwendungen verwendet werden.|-   [Specifying Web Browsers Types (Angeben von Webbrowsertypen)](../test/edit-the-test-mix-to-specify-which-web-browsers-types-in-a-load-test-scenario.md)|
|**Konfigurieren von Testiterationseinstellungen für das Szenario:** Sie können ein Auslastungstestszenario bearbeiten, um mit dem Auslastungstest-Editor und dem Eigenschaftenfenster Testiterationseinstellungen zu konfigurieren. Standardmäßig wird ein Szenario ohne eine maximale Anzahl von Testiterationen eingerichtet. Sie können die maximale Anzahl von Iterationen im Szenario und die Länge der Pause zwischen den Iterationen optional konfigurieren.|-   [Configuring Test Iterations for Scenarios (Konfigurieren von Testiterationen für Szenarios)](../test/configure-test-iterations-in-a-load-test-scenario.md)|
|**Konfigurieren von Verzögerungseinstellungen für das Szenario:** Mit dem Auslastungstest-Editor und dem Eigenschaftenfenster können Sie vor dem Start eines Szenarios in einem Auslastungstest eine Verzögerung angeben. Die Eigenschaft **Startzeit verzögern** kann z.B. verwendet werden, wenn Sie in einem Szenario mit der Erstellung von Elementen beginnen müssen, die in einem anderen Szenario benötigt werden. Sie können das Szenario, in dem die Elemente verwendet werden sollen, verzögern, damit in dem Szenario, in dem die Elemente erstellt werden, einige Daten ausgefüllt werden.|-   [Konfigurieren von Szenariostartverzögerungen](../test/configure-scenario-start-delays.md)|
|**Angeben der in einem Auslastungstestszenario zu verwendenden Remotecomputer:** Nachdem Sie einen Auslastungstest erstellt haben, können Sie die Eigenschaften des Auslastungstestszenarios bearbeiten, um anzugeben, welche Test-Agents eingeschlossen werden sollen. Weitere Informationen finden Sie unter [Testcontroller und Test-Agents](configure-test-agents-and-controllers-for-load-tests.md).|-   [How to: Specify Test Agents to Use (Vorgehensweise: Angeben der zu verwendenden Test-Agents)](../test/how-to-specify-test-agents-to-use-in-load-test-scenarios.md)|

## <a name="see-also"></a>Siehe auch

- [Editing load tests (Bearbeiten von Auslastungstests)](../test/edit-load-tests.md)
- [Auslastungstestszenario-Eigenschaften](../test/load-test-scenario-properties.md)