---
title: Einschließen von Bildschirm- und Stimmaufzeichnungen Im Rahmen von Tests mit Testeinstellungen in Visual Studio
ms.date: 10/03/2016
ms.topic: conceptual
helpviewer_keywords:
- test settings, recording desktop video
ms.assetid: 2cefe8c2-430a-4cb4-bbe0-f3edb2e5bc03
author: gewarren
ms.author: gewarren
manager: douge
ms.prod: visual-studio-dev15
ms.technology: vs-ide-test
ms.openlocfilehash: 44994b7b643d63f548092aba9a878b939f3968af
ms.sourcegitcommit: 58052c29fc61c9a1ca55a64a63a7fdcde34668a4
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2018
ms.locfileid: "34750993"
---
# <a name="how-to-include-recordings-of-the-screen-and-voice-during-tests-using-test-settings"></a>Gewusst wie: Einschließen von Aufzeichnungen von Bildschirm und Stimme während der Tests mit Testeinstellungen

Im Konfigurations-Editor in Visual Studio können Sie den Adapter für diagnostische Daten konfigurieren, der den Bildschirm und die Stimme des Benutzers aufzeichnet, der den Test ausführt. Dieser Adapter für diagnostische Daten speichert eine Bildschirm- und Stimmenaufzeichnung der Desktopsitzung während des Tests. Die Aufzeichnung wird mit dem Testergebnis gespeichert, oder sie kann einem Fehler angefügt werden. Andere Teammitglieder können die Videoaufzeichnungen verwenden, um schwer zu reproduzierende Anwendungsfehler zu isolieren.

> [!WARNING]
> Bei der Bildschirm- und Stimmenaufzeichnung werden Konfigurationen mit mehreren Monitoren nicht unterstützt.

Die Bildschirm- und Stimmenaufzeichnung kann sowohl für manuelle als auch für automatisierte Tests verwendet werden. Wenn Sie beispielsweise einen Test der programmierten UI remote ausführen, können Sie den Desktop aufzeichnen, um die Ausführung des Tests der programmierten UI anzuzeigen. Weitere Informationen dazu, wie Sie eine Remotebildschirm- und Remotestimmaufzeichnung vornehmen können, finden Sie unter [How to: Set Up Your Test Agent to Run Tests that Interact with the Desktop (Vorgehensweise: Einrichten Ihres Test-Agents für mit dem Desktopcomputer interagierende Ausführungstests)](../test/how-to-set-up-your-test-agent-to-run-tests-that-interact-with-the-desktop.md).

## <a name="to-configure-screen-and-voice-recording-for-your-test-settings"></a>So konfigurieren Sie Bildschirm- und Stimmenaufzeichnung für Ihre Testeinstellungen

1.  Öffnen Sie die Testeinstellungen, die Sie für die Bildschirm- und Stimmenaufzeichnung konfigurieren möchten. Weitere Informationen finden Sie unter [Collect diagnostic data while testing (VSTS) (Erfassen von Diagnosedaten beim Testen (VSTS))](/vsts/manual-test/collect-diagnostic-data) oder [Collect Diagnostic Information Using Test Settings (Erfassen von Diagnoseinformationen mithilfe von Testeinstellungen)](../test/collect-diagnostic-information-using-test-settings.md).

2.  Wählen Sie in den Testeinstellungen die **Rolle** aus, die für die Bildschirm- und Stimmaufzeichnung verwendet werden soll.

    > [!NOTE]
    > Bei manuellen und automatisierten Tests ist dies der Computer, auf dem die Tests ausgeführt werden.

3.  Wählen Sie den **Bildschirm- und Sprachrecorder** aus, und klicken Sie dann auf **Konfigurieren**.

     Das Dialogfeld "Adapter für diagnostische Daten konfigurieren – Bildschirm- und Stimmenaufzeichnung" wird angezeigt.

     ![Videokonfiguration](../test/media/testsettingvideoconfiggdr.png)

4.  Optional: Klicken Sie auf **Stimmaufzeichnung aktivieren**, um Audioinhalte aufzuzeichnen.

5.  Optional: Aktivieren Sie das Kontrollkästchen neben **Bei erfolgreichem Testfall Aufzeichnung speichern**, um festzulegen, dass die Bildschirm- und Stimmaufzeichnung sowohl für fehlgeschlagene als auch für erfolgreiche Tests gespeichert wird.

    > [!WARNING]
    > Wenn Sie **Bei erfolgreichem Testfall Aufzeichnung speichern** aktivieren, wird die Aufzeichnung zusammen mit den Testergebnissen gespeichert, wodurch Speicherplatz auf dem Server belegt wird. Sie können das Test Attachment Cleaner-Tool verwenden, um diese Anhänge zu löschen.

6.  Konfigurieren Sie unter **Qualität der Bildschirmaufzeichnung** die folgenden Dropdownlistenoptionen:

    1.  **Framerate:** Geben Sie an, wie viele Frames pro Sekunde in der Bildschirm- und Stimmenaufzeichnung verwendet werden sollen. Der Standardwert ist 4 Frames pro Sekunde. Werte zwischen 2 und 20 sind zulässig.

    2.  **Bitrate:** Geben Sie an, wie viele Kilobytes pro Sekunde in der Bildschirm- und Stimmenaufzeichnung verwendet werden sollen. Der Standardwert ist 512. Werte zwischen 512 und 10.000 sind zulässig.

    3.  **Qualität (1 bis 100):** Sie können die Qualität der Bildschirm- und Stimmaufzeichnung angeben, indem Sie einen Bereich zwischen 1 und 100 auswählen. Der Standardwert ist 50 (mittlerer Bereich).

7.  Klicken Sie auf **OK**. Die Einstellungen für Diagnoseablaufverfolgungs-Sammler werden jetzt konfiguriert und für die Testeinstellungen gespeichert.

    > [!TIP]
    > Um die Konfiguration dieses Adapter für diagnostische Daten zurückzusetzen, wählen Sie **Auf Standardkonfiguration zurücksetzen** für Visual Studio und **Standard wiederherstellen** für Microsoft Test Manager aus.

## <a name="see-also"></a>Siehe auch

- [Collect diagnostic data while testing (VSTS) (Sammeln von Diagnosedaten beim Testen (VSTS))](/vsts/manual-test/collect-diagnostic-data)
- [Collect diagnostic data in manual tests (VSTS) (Sammeln von Diagnosedaten in manuellen Tests (VSTS))](/vsts/manual-test/mtm/collect-more-diagnostic-data-in-manual-tests)
- [Collect Diagnostic Information Using Test Settings (Sammeln von Diagnoseinformationen mithilfe von Testeinstellungen)](../test/collect-diagnostic-information-using-test-settings.md)
- [Run manual tests (VSTS) (Ausführen manueller Tests (VSTS))](/vsts/manual-test/getting-started/run-manual-tests)