---
title: 'Vorgehensweise: Festlegen von Präinstrumentations- und Postinstrumentationsbefehlen | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
f1_keywords:
- vs.performance.property.instrument
helpviewer_keywords:
- profiling tools, pre-instrument events
- events [Visual Studio], pre-instrument
- pre-instrument events, performance tools
ms.assetid: 6a8d5340-1d1b-4d81-88dd-8e1f435eb828
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 65c6bd02ae2a89f8ea8e66cb6d7b943344450375
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/19/2018
---
# <a name="how-to-specify-pre--and-post-instrument-commands"></a>Gewusst wie: Festlegen von Präinstrumentations- und Postinstrumentationsbefehlen

Sie können Befehle angeben, die ausgeführt werden, bevor oder nachdem die Binärdateien in einer Leistungssitzung instrumentiert werden. Jeder Befehl, der über die Befehlszeile ausgegeben werden kann, kann als Präinstrumentations- oder Postinstrumentationsereignis angegeben werden. Beispielsweise können Sie Befehle angeben, die das erneute Signieren einer Assembly mit einem Schlüssel mit starkem Namen in einer Batchdatei automatisiert, die ausgeführt wird, nachdem die Binärdateien instrumentiert werden.

Sie können Befehle für alle instrumentierten Binärdateien in der Profilerstellung oder für einzelne Binärdateien angeben. Sie können jedoch nur jeweils ein Präinstrumentationsbefehl vor dem Ausführen und nur ein Postinstrumentationsbefehl zum Ausführen nach dem Instrumentationsprozess angeben. Sie können keine Befehle für jeweils alle und für einzelne Binärdateien angeben. Wenn Sie Befehle für alle Binärdateien angeben, werden die Befehle vor oder nach der Instrumentation jeder Binärdatei in der Sitzung ausgeführt.

Das Arbeitsverzeichnis, in dem die Befehle ausgeführt werden, hängt vom Betriebssystem ab, auf dem Sie [!INCLUDE[vs_current_short](../code-quality/includes/vs_current_short_md.md)] ausführen und von der Zielplattform der profilierten Anwendung.

 **32-Bit-Computer**

Auf 32-Bit-Computern ist das Standardverzeichnis für Profilerstellungstools Laufwerk\Programme\Microsoft Visual Studio 10.0\Team Tools\Performance Tools.

**64-Bit-Computer**

Auf 64-Bit-Computern legen Sie den Pfad entsprechend der Zielplattform der profilierten Anwendung fest:

- Bei 32-Bit-Anwendungen lautet das Standardverzeichnis für Profilerstellungstools:

     *Laufwerk*\Programme (x86)\Microsoft Visual Studio 10.0\Team Tools\Performance Tools

- Bei 64-Bit-Anwendungen lautet das Standardverzeichnis für Profilerstellungstools:

     *Laufwerk*\Programme (x86)\Microsoft Visual Studio 10.0\Team Tools\Performance Tools\x64

## <a name="to-specify-pre-instrument-commands"></a>So geben Sie Präinstrumentationsbefehle an

1. Führen Sie einen der folgenden Schritte aus:

    - Zum Angeben von Präinstrumentationsbefehle für alle Binärdateien in einer Leistungssitzung wählen Sie den Knoten Leistungssitzung im **Leistungs-Explorer**, klicken Sie anschließend mit der rechten Maustaste und wählen Sie **Eigenschaften** aus.

    - Zum Angeben von Präinstrumentationsbefehlen für eine bestimmte Binärdatei klicken Sie mit der rechten Maustaste auf die Binärdatei in der Liste **Ziele** der Leistungssitzung und wählen Sie anschließend **Eigenschaften** aus.

2. Klicken Sie auf den **Eigenschaftenseiten** auf **Instrumentation** .

3. Geben Sie den Befehl im Textfeld **Befehlszeile** unter **Präinstrumentationsereignisse** ein.

    > [!NOTE]
    > Sie können auf die Auslassungszeichen **(…)** klicken, die neben dem Feld **Befehlszeile** stehen, um die entsprechende EXE-, CMD- oder BAT-Datei zu suchen und auszuwählen.

4. Klicken Sie auf **OK**.

     Um den Befehl zu deaktivieren, ohne ihn zu entfernen, wählen Sie das Kontrollkästchen **Aus Instrumentation ausschließen** aus. Verwenden Sie zum Ändern der Compiler- oder Linkereinstellungen die Eigenschaftenseiten des Projekts.

## <a name="to-specify-post-instrument-commands"></a>So geben Sie Postinstrumentationsbefehle an

1. Führen Sie einen der folgenden Schritte aus:

    - Zum Angeben von Postinstrumentationsbefehlen für alle Binärdateien in einer Leistungssitzung wählen Sie den Knoten Leistungssitzung im **Leistungs-Explorer**, klicken Sie anschließend mit der rechten Maustaste und wählen Sie **Eigenschaften** aus.

    - Zum Angeben von Präinstrumentationsbefehlen für eine bestimmte Binärdatei klicken Sie mit der rechten Maustaste auf die Binärdatei in der Liste **Ziele** der Leistungssitzung und wählen Sie anschließend **Eigenschaften** aus.

2. Klicken Sie auf den **Eigenschaftenseiten** auf **Instrumentation** .

3. Geben Sie den Befehl im Textfeld **Befehlszeile** unter **Postinstrumentationsereignisse** ein.

    > [!NOTE]
    > Sie können auf die Auslassungszeichen **(…)** klicken, die neben dem Feld **Befehlszeile** stehen, um die entsprechende EXE-, CMD- oder BAT-Datei zu suchen und auszuwählen.

4. Klicken Sie auf **OK**.

     Um den Befehl zu deaktivieren, ohne ihn zu entfernen, wählen Sie das Kontrollkästchen **Aus Instrumentation ausschließen** aus. Verwenden Sie zum Ändern der Compiler- oder Linkereinstellungen die Eigenschaftenseiten des Projekts.

## <a name="see-also"></a>Siehe auch

[Konfigurieren von Leistungssitzungen](../profiling/configuring-performance-sessions.md)