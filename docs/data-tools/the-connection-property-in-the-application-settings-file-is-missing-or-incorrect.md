---
title: Die Verbindungseigenschaft in der Application Settings-Datei fehlt oder ist fehlerhaft.
ms.date: 11/04/2016
ms.topic: reference
ms.assetid: 77724510-ff59-4d43-b933-a0434e1ac597
author: gewarren
ms.author: gewarren
manager: douge
ms.prod: visual-studio-dev15
ms.technology: vs-data-tools
ms.workload:
- data-storage
ms.openlocfilehash: 857c9436b3a1279671702575d3ab479d9c2282f4
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/26/2018
---
# <a name="the-connection-property-in-the-application-settings-file-is-missing-or-incorrect"></a>Die Verbindungseigenschaft in der Application Settings-Datei fehlt oder ist fehlerhaft.

Die Verbindungseigenschaft fehlt in der Datei mit den Anwendungseinstellungen, oder sie ist falsch. Stattdessen wurde die Verbindungszeichenfolge aus der DBML-Datei verwendet.

Die DBML-Datei enthält einen Verweis auf eine Verbindungszeichenfolge in der Datei mit den Anwendungseinstellungen, die nicht gefunden wurde. Diese Meldung dient nur zu Informationszwecken; Einstellung für die Verbindungszeichenfolge wird erstellt, wenn **OK** geklickt wird.

Um auf diese Meldung zu reagieren, wählen Sie **OK**. Die Verbindungsinformationen, die in der DBML-Datei enthalten sind, werden den Anwendungseinstellungen hinzugefügt.

## <a name="see-also"></a>Siehe auch

- [O/R-Designer-Meldungen](../data-tools/o-r-designer-messages.md)
- [LINQ to SQL-tools in Visual Studio](../data-tools/linq-to-sql-tools-in-visual-studio2.md)