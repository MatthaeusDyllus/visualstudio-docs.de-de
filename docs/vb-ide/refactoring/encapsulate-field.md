---
title: Field - Umgestaltung (Visual Basic) kapseln | Microsoft Docs
ms.custom: 
ms.date: 12/14/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
ms.devlang: VB
ms.assetid: 39a9ed11-363f-4dda-af3b-0affe6db1d42
author: gewarren
ms.author: gewarren
manager: ghogen
f1_keywords: vs.csharp.refactoring.encapsulatefield
dev_langs: VB
ms.openlocfilehash: 9575ad83ead4960016ba7814642cacb1db04ea4d
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2017
---
# <a name="encapsulate-a-field-in-visual-basic"></a>Kapseln von einem Feld in Visual Basic
**Was:** können Sie ein Feld an eine Eigenschaft aktivieren, und aktualisieren alle Verwendungen dieses Felds die neu erstellte Eigenschaft verwenden.

**Wann:** Sie verwenden möchten, verschieben Sie ein Feld in einer Eigenschaft, und aktualisieren Sie alle Verweise auf dieses Feld.  

**Grund:** Sie andere Klassen auf ein Feld zugreifen möchten, aber nicht möchten diese Klassen direkten Zugriff.  Umschließen das Feld in einer Eigenschaft, konnte Sie Code, um zu überprüfen, ob den Wert zugewiesen wird, z. B. schreiben.

**Vorgehensweise:**

1. Markieren Sie, oder platzieren Sie den Textcursor innerhalb der Name des Felds zum Kapseln von:

   ![Hervorgehobene code](media/encapsulate_highlight.png)

1. Als Nächstes führen Sie eine der folgenden:
   * **Tastatur**
     * Drücken Sie **STRG + R**, klicken Sie dann **STRG + E**.  (Beachten Sie, dass Ihre Tastenkombination je nach dem gewählten Profil möglicherweise abweicht.)
     * Drücken Sie **STRG +.** Trigger die **Schnellaktionen und Refactorings** Menü, und wählen Sie **Feld kapseln** Eintrag aus der Vorschau-Fenster-Popupfenster.
   * **Maus**
     * Wählen Sie **Bearbeiten > Umgestalten > Feld kapseln**.
     * Mit der rechten Maustaste in des Codes, wählen Sie die **Schnellaktionen und Refactorings** im Menü, und wählen Sie **Feld kapseln** Eintrag aus der Vorschau-Fenster-Popupfenster.

   Auswahl | Beschreibung
   --------- | -----------
   **Kapseln Sie Feld ein (und verwenden Sie die Eigenschaft)** | Kapselt das Feld mit einer Eigenschaft, und aktualisiert alle Verwendungen des Felds, das die generierte Eigenschaft verwenden
   **Feld einkapseln (jedoch weiterhin verwendet, Feld)** | Kapselt das Feld mit einer Eigenschaft, aber belassen alle Verwendungen des Felds unberührt

   Die Eigenschaft wird sofort erstellt und Verweise auf das Feld aktualisiert, wenn Sie ausgewählt haben.

   > [!TIP]
   > Verwenden der [ **Vorschau der Änderungen** ](../../ide/preview-changes.md) Link im Popup-Fenster zu sehen, was das Ergebnis sein wird, bevor Sie endgültig.

   ![Kapseln von eigenschaftenergebnis](media/encapsulate_result.png)

## <a name="see-also"></a>Siehe auch  
[Refactoring (Visual Basic)](../refactoring-vb.md)  
[Vorschau der Änderungen](../../ide/preview-changes.md)