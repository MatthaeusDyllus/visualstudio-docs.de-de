---
title: 'Vorgehensweise: Reagieren auf das Just-in-Time-Debugger | Microsoft Docs'
ms.custom: ''
ms.date: 05/23/17
ms.technology: vs-ide-debug
ms.topic: conceptual
helpviewer_keywords:
- debugging [Visual Studio], Just-In-Time
- Just-In-Time debugging
ms.assetid: 14972d5f-69bc-479b-9529-03b8787b118f
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 1b97e2d6b9ca269a86c3b66ffbcc4bb441051f29
ms.sourcegitcommit: b400528a83bea06d208d95c77282631ae4a93091
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/23/2018
---
# <a name="how-to-respond-to-the-just-in-time-debugger"></a>Vorgehensweise: Reagieren auf das Just-in-Time-Debugger

Die Aktionen, die Sie durchführen soll, wenn Sie das Just-in-Time finden Sie unter Dialogfeld Debugger abhängig sind, was Sie tun möchten:

#### <a name="if-you-want-to-fix-or-debug-the-error-visual-studio-users"></a>Wenn Sie zu beheben oder den Fehler (Visual Studio-Benutzer) debuggen möchten

- Sie benötigen [Visual Studio installiert](http://www.visualstudio.com) um die ausführlichen Informationen zu diesem Fehler anzuzeigen und zu debuggen. Weitere Informationen finden Sie unter [mithilfe der Just-in-Time-Debugger Debuggen](../debugger/debug-using-the-just-in-time-debugger.md). Wenn Sie nicht den Fehler beheben, und beheben Sie die app, wenden Sie sich an den Besitzer der app zum Beheben des Fehlers.

#### <a name="if-you-want-to-prevent-the-just-in-time-debugger-dialog-box-from-appearing"></a>Wenn Sie, dass das Just-in-Time-Debugger-Dialogfeld angezeigt wird verhindern möchten

Sie können Maßnahmen, um zu verhindern, dass die Just-in-Time-Debugger-Dialogfeld nicht angezeigt wird. Wenn die app über den Fehler behandelt, können Sie normalerweise die app ausführen.

1. (Web-apps) Wenn Sie eine Web-app ausführen möchten, können Sie das Skriptdebugging deaktivieren.

    Deaktivieren Sie für Internet Explorer oder Microsoft Edge das Skriptdebuggen in das Dialogfeld "Internetoptionen" aus. Sie können diese Einstellungen nicht über Zugriff der **Systemsteuerung** > **Netzwerk und Internet** > **Internetoptionen** (die genauen Schritte hängen Ihre Version von Windows und Ihren Browser).

    ![JITInternetOptions](../debugger/media/jitinternetoptions.png "JITInternetOptions")

    Öffnen Sie dann erneut die Webseite, in dem den Fehler gefunden. Wenn diese Einstellung ändern, das Problem nicht behebt, wenden Sie sich an den Besitzer der Web-app, um das Problem zu beheben.

3. (Visual Studio-Benutzer) Wenn Sie Visual Studio installiert haben (oder war bereits installiert und entfernt), [deaktivieren Sie Just-in-Time-Debuggen](../debugger/debug-using-the-just-in-time-debugger.md) und führen Sie die app erneut aus.

    > [!IMPORTANT]
    > Wenn Sie deaktivieren Sie Just-in-Time-Debuggen und die app erkennt einen Ausnahmefehler (Fehler), entweder sehen Sie ein Dialogfeld Standardfehler stattdessen oder die app wird, stürzt ab, oder legen. Die app wird nicht ordnungsgemäß ausgeführt, bis zur Behebung des Fehlers (von Ihnen oder der Besitzer der app).

2. (ASP.NET und IIS) Wenn Sie eine ASP.NET Web-app in IIS hosten, deaktivieren Sie serverseitige debugging.

    In IIS-Manager mit der rechten Maustaste des Serverknoten und wählen Sie **wechseln Sie zur Ansicht "Features"**. Wählen Sie im Abschnitt ASP.NET **.NET Kompilierung** , und klicken Sie dann sicher, dass Sie auswählen, **"false"** mit dem Debug-Verhalten (die Schritte unterscheiden sich in älteren Versionen von IIS).
  
## <a name="see-also"></a>Siehe auch    
 [Debugger – Grundlagen](../debugger/debugger-basics.md)   
