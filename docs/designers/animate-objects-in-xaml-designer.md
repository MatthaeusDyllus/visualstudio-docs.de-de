---
title: Animieren von Objekten im XAML-Designer
ms.date: 04/11/2018
ms.technology: vs-ide-designers
ms.topic: conceptual
ms.assetid: fb88fa26-e835-47f5-9771-2f279441c83c
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- uwp
ms.openlocfilehash: 46b08815a320faf7043d860b4cd96f4120409854
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/19/2018
---
# <a name="animate-objects-in-xaml-designer"></a>Animieren von Objekten im XAML-Designer

Sie können kurze Animationen erstellen, die Objekte bewegen, oder sie ein- und ausblenden.

Erstellen Sie zunächst ein *Storyboard*. Ein Storyboard enthält eine oder mehrere *Zeitachsen*. Legen Sie auf einer Zeitachse *Keyframes* fest, um Änderungen an den Eigenschaften zu markieren. Beim Ausführen der Animation interpoliert Blend dann die Eigenschaftsänderungen im festgelegten Zeitraum. Das Ergebnis ist ein reibungsloser Übergang. Sie können jede Eigenschaft animieren, die zu einem Objekt gehört, sogar nicht visuelle Eigenschaften.

Die folgende Abbildung zeigt ein Storyboard mit dem Namen **MoveUp**. Die Zeitachse enthält Keyframes, die die x- und y-Position eines Rechtecks markieren. Wenn diese Animation ausgeführt wird, wird das Rechteck nahtlos von einer Position zu einer anderen verschoben.

![MoveUp-Storyboard im XAML-Designer](../designers/media/982f031a-74a3-414a-abc2-a0f41a741075.png)

## <a name="see-also"></a>Siehe auch

- [Erstellen einer Benutzeroberfläche mit Blend für Visual Studio](../designers/creating-a-ui-by-using-blend-for-visual-studio.md)