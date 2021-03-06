---
title: Auswählen und Installieren von Python-Interpretern
description: Dieser Artikel enthält eine vollständige Liste der Python-Interpreter, die in Visual Studio unterstützt werden, sowie kurze Anweisungen dazu, wo die entsprechenden Installationsprogramme zu finden sind.
ms.date: 02/20/2018
ms.prod: visual-studio-dev15
ms.technology: vs-python
ms.topic: conceptual
author: kraigb
ms.author: kraigb
manager: douge
ms.workload:
- python
- data-science
ms.openlocfilehash: 4bf9c65d44739dd1b9164731f1097ce29050e6d8
ms.sourcegitcommit: 33c954fbc8e05f7ba54bfa2c0d1bc1f9bbc68876
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/07/2018
---
# <a name="installing-python-interpreters"></a>Installieren von Python-Interpretern

Bei der Installation der Workload für die Python-Entwicklung in Visual Studio 2017 wird standardmäßig auch Python 3 (64-Bit) installiert. Optional können Sie auch die 32-Bit- und 64-Bit-Versionen von Python 2, Python 3, Anaconda 2 und Anaconda 3 installieren, wie unter [Installation](installing-python-support-in-visual-studio.md) beschrieben.

Sie können die in der folgenden Tabelle aufgelisteten Interpreter auch manuell außerhalb des Visual Studio-Installationsprogramms installieren. Wenn Sie beispielsweise Anaconda 3 vor Visual Studio installiert haben, ist keine erneute Installation über das Visual Studio-Installationsprogramm erforderlich.

Für **Visual Studio 2015 und frühere Versionen** müssen Sie einen der Interpreter manuell installieren.

Visual Studio (alle Versionen) überprüft die Registrierung (gemäß den Angaben unter [PEP 514 - Python registration in the Windows registry](https://www.python.org/dev/peps/pep-0514/) ([PEP 514 – Registrieren von Python in der Windows-Registrierung]) und erkennt so automatisch jeden installierten Python-Interpreter und die zugehörige Umgebung.

Wenn Visual Studio keine installierte Umgebung findet, folgen Sie den Anweisungen unter [Manuelles Identifizieren einer vorhandenen Umgebung](managing-python-environments-in-visual-studio.md#manually-identify-an-existing-environment).

Visual Studio zeigt im Fenster [Python-Umgebungen](managing-python-environments-in-visual-studio.md) alle bekannten Umgebungen an und erkennt Updates für vorhandene Interpreter automatisch.

| Interpreter | description |
| --- | --- |
| [CPython](https://www.python.org/) | Der „native“ und am häufigsten verwendete Interpreter, verfügbar in 32- und 64-Bit-Versionen (32-Bit wird empfohlen). Er umfasst die neuesten Sprachfeatures, die maximale Python-Paketkompatibilität, vollständige Unterstützung für das Debuggen und Interoperabilität mit [IPython](http://ipython.org/). Siehe auch: [Should I use Python 2 or Python 3? (Sollte ich Python 2 oder Python 3 verwenden?)](http://wiki.python.org/moin/Python2orPython3). Beachten Sie, dass Visual Studio 2015 und frühere Versionen Python 3.6 nicht unterstützen, und den Fehler „Unsupported python version 3.6“ (Nicht unterstützte Python-Version 3.6) ausgeben können. Verwenden Sie stattdessen Python 3.5 oder frühere Versionen. |
| [IronPython](https://github.com/IronLanguages/ironpython2) | Eine .NET-Implementierung von Python, verfügbar in 32-Bit- und 64-Bit-Versionen, die C#-/F#-/Visual Basic-Interoperabilität, Zugriff auf .NET APIs, Python-Standarddebuggen (jedoch kein C++-Debuggen im gemischten Modus) und IronPython-/C#-Debuggen im gemischten Modus bietet. IronPython unterstützt jedoch keine virtuelle Umgebungen. |
| [Anaconda](https://www.continuum.io) | Eine offene Data Science-Plattform, die von Python unterstützt wird und die neueste Version von CPython sowie die meisten der nicht leicht zu installierenden Pakete enthält. Wir empfehlen diesen Interpreter, wenn keine andere Entscheidung möglich ist. |
| [PyPy](http://www.pypy.org/) | Eine leistungsstarke JIT-Implementierung für die Ablaufverfolgung von Python, die gut für Programme mit langer Ausführungszeit und Situationen, in denen Sie Leistungsprobleme identifizieren, jedoch keine anderen Lösungen finden können, geeignet ist. Der Interpreter kann mit Visual Studio verwendet werden, bietet jedoch nur eingeschränkte Unterstützung für erweiterte Debugfunktionen. |
| [Jython](http://www.jython.org/) | Eine Implementierung von Python auf der Java Virtual Machine (JVM). Ähnlich wie bei IronPython kann in Jython ausgeführter Code mit Java-Klassen und -Bibliotheken interagieren, aber möglicherweise viele für CPython vorgesehene Bibliotheken nicht verwenden. Der Interpreter kann mit Visual Studio verwendet werden, bietet jedoch nur eingeschränkte Unterstützung für erweiterte Debugfunktionen. |

Wenn Sie als Entwickler neue Formen der Erkennung für Python-Umgebungen bereitstellen möchten, finden Sie unter [PTVS Environment Detection](https://github.com/Microsoft/PTVS/wiki/Extensibility-Environments) (PTVS-Umgebungserkennung, github.com) weitere Informationen.

## <a name="moving-an-interpreter"></a>Verschieben eines Interpreters

Wenn Sie einen vorhandenen Interpreter an einen neuen Speicherort im Dateisystem verschieben, erkennt Visual Studio diese Änderung nicht automatisch.

- Wenn Sie den Speicherort des Interpreters ursprünglich über das Fenster **Python-Umgebungen** angegeben haben, verwenden Sie die Registerkarte **Konfigurieren** in diesem Fenster, um den neuen Speicherort zu ermitteln. Weitere Informationen finden Sie unter [Manuelles Identifizieren einer vorhandenen Umgebung](managing-python-environments-in-visual-studio.md#manually-identify-an-existing-environment).

- Wenn Sie den Interpreter mit einem Installationsprogramm installiert haben, führen Sie die folgenden Schritte aus, um den Interpreter am neuen Speicherort neu zu installieren:

  1. Stellen Sie den Python-Interpreter an seinem ursprünglichen Speicherort wieder her.
  2. Deinstallieren Sie den Interpreter mithilfe des Installationsprogramms; dabei werden die Registrierungseinträge gelöscht.
  3. Installieren Sie den Interpreter am gewünschten Speicherort neu.
  4. Starten Sie Visual Studio neu. Das Programm sollte den neuen Speicherort automatisch erkennen.

Mit diesem Prozess stellen Sie sicher, dass die Registrierungseinträge, die den Speicherort des von Visual Studio verwendeten Interpreters identifizieren, ordnungsgemäß aktualisiert werden. Durch die Verwendung eines Installationsprogramms werden auch Probleme durch möglicherweise vorhandene Nebenwirkungen behoben.

## <a name="see-also"></a>Siehe auch

- [Verwalten von Python-Umgebungen](managing-python-environments-in-visual-studio.md)
- [Auswählen eines Interpreters für ein Projekt](selecting-a-python-environment-for-a-project.md)
- [Verwenden von "requirements.txt" für Abhängigkeiten](managing-required-packages-with-requirements-txt.md)
- [Suchpfade](search-paths.md)
- [Das Fenster „Python-Umgebungen“](python-environments-window-tab-reference.md)