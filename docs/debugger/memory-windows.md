---
title: Anzeigen von Arbeitsspeicher für Variablen im Debugger | Microsoft Docs
ms.custom: H1Hack27Feb2017
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
f1_keywords:
- vs.debug.memory
dev_langs:
- CSharp
- VB
- FSharp
- C++
- JScript
helpviewer_keywords:
- Memory window
- strings [Visual Studio], viewing
- debugger [Visual Studio], Memory window
- memory [Visual Studio], debugging
- debugging [Visual Studio], Memory window
- buffers, viewing
ms.assetid: 7f7a0439-10e4-4966-bb2d-51f04cda4fe2
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 550c5ffe641fac5bb2d080a892143bf3ff9744b0
ms.sourcegitcommit: 3d10b93eb5b326639f3e5c19b9e6a8d1ba078de1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2018
---
# <a name="use-the-memory-windows-in-the-visual-studio-debugger"></a>Verwenden Sie das Fenster "Arbeitsspeicher" in Visual Studio-Debugger
Die **Arbeitsspeicher** Fenster bietet einen Einblick in den belegten Speicherplatz, der von der Anwendung verwendet wird. Die **Überwachen** Fenster **Schnellüberwachung** Dialogfeld **"Auto"** Fenster und **"lokal"** Fenster zeigen Sie den Inhalt von Variablen, die an bestimmten Orten im Arbeitsspeicher gespeichert. Aber die **Arbeitsspeicher** Fenster zeigt das umfangreiche Bild. Diese Ansicht ist besonders angenehm beim Untersuchen von großen Datenmengen (beispielsweise Puffer oder umfangreiche Zeichenfolgen), die in den anderen Fenstern nicht gut dargestellt werden. Allerdings die **Arbeitsspeicher** Fenster ist nicht beschränkt auf das Anzeigen von Daten. Darin wird der gesamte Inhalt des Arbeitsspeichers angezeigt, unabhängig davon, ob es sich dabei um Daten, Code oder um zufällig verteilte Objekte in nicht zugewiesenem Arbeitsspeicher handelt.  
  
 Die **Arbeitsspeicher** Fenster ist nur verfügbar, wenn Debuggen auf Adressebene im aktiviert ist die **Optionen** Dialogfeld **Debuggen** Knoten. Die **Arbeitsspeicher** Fenster ist nicht verfügbar für Skriptsprachen oder SQL, Sprachen, die nicht das Konzept des Arbeitsspeichers erkannt wird.  
  
## <a name="opening-a-memory-window"></a>Öffnen eines Arbeitsspeicherfensters  
  
#### <a name="to-open-a-memory-window"></a>So öffnen Sie ein Arbeitsspeicherfenster  
  
1.  Beginnen Sie mit dem Debuggen, sofern Sie den Debugmodus noch nicht ausgewählt haben.  
  
2.  In der **Debuggen** Sie im Menü **Windows**. Zeigen Sie dann auf **Arbeitsspeicher** , und klicken Sie dann auf **Arbeitsspeicher 1**, **Arbeitsspeicher 2**, **Arbeitsspeicher 3**, oder **Arbeitsspeicher 4**. (Technisch anspruchsvolle Editionen von [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] haben nur einen einzigen **Arbeitsspeicher** Fenster. Wenn Sie eine dieser Editionen verwenden, klicken Sie einfach **Arbeitsspeicher**.)  
  
## <a name="paging-in-the-memory-window"></a>Paging im Fenster "Arbeitsspeicher"  
 Die **Arbeitsspeicher** Fenster verfügt über eine vertikale Bildlaufleiste, die eine nicht standardmäßige Funktionsweise besitzt. Der Adressbereich eines modernen Computers ist sehr groß, und eine Suche kann leicht fehlschlagen, wenn Sie das Bildlauffeld der Bildlaufleiste an eine zufällige Position ziehen. Aus diesem Grunde verhält sich das Bildlauffeld, als wäre es beidseitig mit einer Zugfeder verbunden, und verbleibt stets in der Mitte der Bildlaufleiste. In Anwendungen, die in nativem Code geschrieben sind, können Sie einen Bildlauf nach oben oder unten durchführen; die Durchführung eines freien Bildlaufs ist jedoch nicht möglich.  
  
 Höhere Speicheradressen werden unten im Fenster angezeigt. Um eine höhere Adresse anzuzeigen, führen Sie einen Bildlauf nach unten anstatt nach oben aus.  
  
#### <a name="to-page-up-or-down-in-memory"></a>So führen Sie im Speicher einen Bildlauf nach oben oder nach unten durch  
  
1.  Klicken Sie unter dem Ziehpunkt in der vertikalen Bildlaufleiste, um einen Bildlauf nach unten auszuführen (Navigieren zu einer höheren Speicheradresse).  
  
2.  Für einen Bildlauf nach oben (Navigieren zu einer niedrigeren Speicheradresse) klicken Sie über dem Bildlauffeld auf der vertikalen Bildlaufleiste.  
  
## <a name="selecting-a-memory-location"></a>Auswählen eines Arbeitsspeicherorts  
 Wenn Sie sofort zu einer ausgewählten Speicherbereich wechseln möchten, können Sie dies tun, indem mithilfe eines Drag-and-Drop-Vorgangs oder bearbeiten den Wert in der **Adresse** Feld. Die **Adresse** Feld akzeptiert wird, nicht nur numerische Werte, sondern auch Ausdrücke, die als Adressen ausgewertet. Wird standardmäßig die **Arbeitsspeicher** Fenster behandelt eine **Adresse** Ausdruck als live-Ausdruck, der Ausführung des Programms erneut ausgewertet wird. Live-Ausdrücke können sehr hilfreich sein. Sie können beispielsweise dazu verwendet werden, den Speicher anzuzeigen, auf den ein Zeiger verweist.  
  
#### <a name="to-select-a-memory-location-by-dragging-and-dropping"></a>So wählen Sie einen Arbeitsspeicherort per Drag & Drop aus  
  
1.  Wählen Sie in einem beliebigen Fenster eine Speicheradresse oder eine Zeigervariable aus, die eine Speicheradresse enthält.  
  
2.  Ziehen Sie die Adresse oder ein Zeiger auf die **Arbeitsspeicher** Fenster.  
  
#### <a name="to-select-a-memory-location-by-editing"></a>So wählen Sie eine Speicheradresse durch Eingeben aus  
  
1.  In der **Arbeitsspeicher** wählen die **Adresse** Feld.  
  
2.  Geben oder fügen Sie die Adresse, die Sie verwenden möchten, finden Sie unter, und drücken dann die **EINGABETASTE**.  
  
## <a name="changing-the-way-the-memory-window-displays-information"></a>Ändern der Anzeigemethode für Informationen im Fenster "Arbeitsspeicher"  
 Sie können ändern, wie die **Arbeitsspeicher** Speicherinhalts im Fenster. Standardmäßig wird der Speicherinhalt in Form einer ganzen Zahl mit 1 Byte im Hexadezimalformat angezeigt. Die Anzahl der Spalten wird automatisch durch die aktuelle Breite des Fensters bestimmt.  
  
#### <a name="to-change-the-format-of-the-memory-contents"></a>So ändern Sie das Format des Speicherinhalts  
  
1.  Mit der rechten Maustaste die **Arbeitsspeicher** Fenster.  
  
2.  Wählen Sie das gewünschte Format aus.  
  
#### <a name="to-change-the-number-of-columns-in-the-memory-window"></a>So ändern Sie die Anzahl der Spalten im Fenster "Arbeitsspeicher"  
  
1.  Auf der Symbolleiste am oberen Rand der **Arbeitsspeicher** Fenster, suchen Sie die **Spalten** Liste.  
  
2.  In der **Spalten** wählen Sie die Anzahl der Spalten, die Sie anzeigen oder auswählen möchten **automatisch** für automatische Anpassung an die Breite des Fensters anpassen.  
  
 Wenn Sie nicht, dass der Inhalt möchten der **Arbeitsspeicher** Fenster geändert, während das Programm ausgeführt wird, können Sie die Auswertung von live-Ausdrücken deaktivieren.  
  
#### <a name="to-toggle-live-evaluation"></a>So schalten Sie die Liveauswertung um  
  
1.  Mit der rechten Maustaste die **Arbeitsspeicher** Fenster.  
  
2.  Klicken Sie im Kontextmenü auf **automatisch neu auswerten**.  
  
     Wenn die Live-Auswertung aktiv ist, ist die Option ausgewählt. Indem Sie auf die Option klicken, wird die Live-Auswertung ausgeschaltet. Wenn die Live-Auswertung deaktiviert ist, ist die Option nicht ausgewählt, und indem Sie auf die Option klicken, wird die Live-Auswertung eingeschaltet.  
  
 Sie können ausblenden oder anzeigen die Symbolleiste am oberen Rand der **Arbeitsspeicher** Fenster. Sie können nicht auf das Adressfeld oder andere Tools zugreifen, wenn die Symbolleiste ausgeblendet ist.  
  
#### <a name="to-toggle-the-toolbar"></a>So blenden Sie die Symbolleiste ein oder aus  
  
1.  Mit der rechten Maustaste ein **Arbeitsspeicher** Fenster.  
  
2.  Klicken Sie im Kontextmenü auf **Symbolleiste anzeigen**.  
  
     Je nach ihrem vorherigen Zustand wird die Symbolleiste ein- bzw. ausgeblendet.  
  
## <a name="following-a-pointer-through-memory"></a>Verfolgen eines Zeigers im Arbeitsspeicher  
 In Anwendungen, die im systemeigenen Code geschrieben wurden, können Sie als Live-Ausdrücke Registernamen verwenden. Zur Verfolgung des Stapels können Sie z. B. den Stapelzeiger verwenden.  
  
#### <a name="to-follow-a-pointer-through-memory"></a>So verfolgen Sie einen Zeiger im Arbeitsspeicher  
  
1.  In der **Arbeitsspeicher** Fenster **Adresse** geben einen Zeigerausdruck. Die Zeigervariable muss sich im aktuellen Gültigkeitsbereich befinden. Je nach verwendeter Sprache müssen Sie u. U. den entsprechenden Verweis aufheben.  
  
2.  Drücken Sie die **EINGABETASTE**.  
  
     Jetzt, wenn Sie verwenden einen Ausführungsbefehl wie z. B. **Schritt**, die Speicheradresse, die angezeigt wird, wird automatisch ändert sich, wenn der Mauszeiger ändert.  
  
## <a name="see-also"></a>Siehe auch  
 [Anzeigen von Daten im Debugger](../debugger/viewing-data-in-the-debugger.md)