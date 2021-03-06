---
title: Setup von Visual Studio für Mac-Tools für Unity
description: Einrichten und Installieren von Unity-Tools für die Verwendung in Visual Studio für Mac
author: dantogno
ms.author: v-davian
ms.date: 07/17/2017
ms.assetid: 83FDD7A3-5D16-4B4B-9080-078E3FB5C623
ms.openlocfilehash: f9a6da6c30132d6303705019919dfcad9f8cd484
ms.sourcegitcommit: b400528a83bea06d208d95c77282631ae4a93091
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/23/2018
---
# <a name="setup-visual-studio-for-mac-tools-for-unity"></a>Setup von Visual Studio für Mac-Tools für Unity

In diesem Abschnitt werden die ersten Schritte für die Verwendung von Visual Studio für Mac-Tools für Unity erläutert.

## <a name="install-visual-studio-for-mac"></a>Installieren von Visual Studio für Mac

Laden Sie Visual Studio für Mac herunter und installieren Sie es. Alle Editionen von Visual Studio für Mac unterstützen Visual Studio für Mac-Tools für Unity, einschließlich der kostenlosen Community Edition:

* Laden Sie Visual Studio für Mac unter [visualstudio.com](https://www.visualstudio.com/) herunter.
* Visual Studio für Mac-Tools für Unity werden automatisch während des Installationsprozesses installiert.
* Weitere Informationen zur Installation finden Sie im [Installationshandbuch](installation.md).

## <a name="confirm-that-the-visual-studio-for-mac-tools-for-unity-extension-is-enabled"></a>Aktivierung der Erweiterung „Visual Studio für Mac-Tools für Unity“ bestätigen

Obwohl die Erweiterung „Visual Studio für Mac-Tools für Unity“ standardmäßig aktiviert sein sollte, können sie dies bestätigen, indem Sie die installierte Versionsnummer überprüfen:

1.  Klicken Sie im Menü von Visual Studio auf **Erweiterungen...**.

  ![Auswählen von Erweiterungen](media/setup-vsmac-tools-unity-image1.png)

2.  Erweitern Sie den Abschnitt „Spieleentwicklung“ und bestätigen Sie den Eintrag „Visual Studio für Mac-Tools für Unity“.

  ![Anzeigen des Eintrags „Unity“](media/setup-vsmac-tools-unity-image2.png)

## <a name="install-unity"></a>Installieren von Unity

Visual Studio für Mac-Tools für Unity erfordert Unity 5.6.1 oder höher. Alle Unity-Pläne funktionieren mit Visual Studio-Tools für Unity, einschließlich des kostenlosen persönlichen Plans. Laden Sie Unity unter [store.unity.com](https://store.unity.com/) herunter.

> [!NOTE]
> Überprüfen Sie, ob Visual Studio-Tools für Unity in Ihrer Version von Unity aktiviert sind, indem Sie im Unity-Menü auf **About Unity** (Informationen zu Unity) klicken und unten links im Dialogfeld nach dem Text „Visual Studio-Tools für Unity aktiviert“ suchen.
>
>   ![Informationen zu Unity](media/setup-vsmac-tools-unity-image3.png)

## <a name="configure-unity-for-use-with-visual-studio-for-mac"></a>Konfigurieren von Unity für die Verwendung mit Visual Studio für Mac

Visual Studio muss als externer Skript-Editor in Unity festgelegt werden:

1.  Klicken Sie im Unity-Menü auf **Einstellungen...**.

  ![Auswählen von Einstellungen](media/setup-vsmac-tools-unity-image4.png)

2.  Klicken Sie im Dialogfeld "Einstellungen" auf die Registerkarte **Externe Tools**.

3.  Klicken Sie in der Dropdownliste des externen Skript-Editors auf **Visual Studio**, falls dieses aufgelistet ist und andernfalls auf **Durchsuchen...**.

  ![Auswählen von Visual Studio](media/setup-vsmac-tools-unity-image5.png)

4.  Wenn Sie auf **Durchsuchen...** geklickt haben, navigieren Sie zum Anwendungsverzeichnis, wählen Sie Visual Studio aus, und klicken Sie auf **Öffnen**.

  ![Auswählen von „Öffnen“](media/setup-vsmac-tools-unity-image6.png)

5.  Sobald Visual Studio in der Liste des **externen Skript-Editors** ausgewählt wurde, schließen Sie das Dialogfeld „Einstellungen“, um den Konfigurationsprozess abzuschließen.
