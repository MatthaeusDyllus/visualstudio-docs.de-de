---
title: Seite "Verweise", Projekt-Designer (Visual Basic)
ms.date: 06/21/2017
ms.prod: visual-studio-dev15
ms.technology: vs-ide-general
ms.topic: reference
f1_keywords:
- vb.ProjectPropertiesReference
- vb.ProjectPropertiesUnusedReference
- vb.ProjectPropertiesReferencePaths
helpviewer_keywords:
- References page in Project Designer
- Project Designer, References page
- Unused References dialog box
ms.assetid: 5a47c595-e084-401c-86e1-74e0bf74fd86
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 35534c0c6965dd7f7db01e2299ff71572b8de9e7
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/26/2018
---
# <a name="references-page-project-designer-visual-basic"></a>Seite "Verweise", Projekt-Designer (Visual Basic)
Verwenden Sie die Seite **Verweise** des **Projekt-Designers**, um Verweise, Webverweise und wichtige Namespaces in Ihrem Projekt zu verwalten. Projekte können Verweise auf COM-Komponenten, XML-Webdienste, Klassenbibliotheken oder Assemblys von .NET Framework oder andere Klassenbibliotheken enthalten. Weitere Informationen zum Verwenden von Verweisen finden Sie unter [Verwalten von Verweisen in einem Projekt](../../ide/managing-references-in-a-project.md).

 Um auf die Seite **Verweise** zuzugreifen, wählen Sie einen Projektknoten (nicht den Knoten **Projektmappe**) im **Projektmappen-Explorer**. Wählen Sie dann in der Menüleiste die Option **Projekt** und dann **Eigenschaften** aus. Sobald der Projekt-Designer angezeigt wird, klicken Sie auf die Registerkarte **Dienste**.

## <a name="uielement-list"></a>UIElement-Liste
 Mit folgenden Optionen können Sie Verweise und importierte Namespaces in Ihrem Projekt auswählen oder entfernen.

 **Nicht verwendete Verweise**

 Klicken Sie auf diese Schaltfläche, um auf das Dialogfeld **Nicht verwendete Verweise** zuzugreifen.

 Mit dem Dialogfeld **Nicht verwendete Verweise** können Sie Verweise entfernen, die in Ihrem Projekt enthalten sind, die aber nicht vom Code verwendet werden. Es enthält ein Raster, das die **Verweisnamen**, den **Pfad** und andere Informationen zu den nicht verwendeten Namespaceverweisen in Ihrem Projekt. Wählen Sie im Raster die Namespaceverweise, die Sie aus Ihrem Projekt entfernen möchten, und klicken Sie auf **Entfernen**.

 **Verweispfade**

 Klicken Sie auf diese Schaltfläche, um auf das Dialogfeld **Verweispfade** zuzugreifen.

> [!NOTE]
> Wenn das Projektsystem einen Assemblyverweis findet, löst das System den Verweis auf, indem es die folgenden Speicherorte in folgender Reihenfolge durchsucht:

>
>  1.  Der Projektordner. Die Projektordnerdateien werden im **Projektmappen-Explorer**, wenn **Alle Dateien anzeigen** nicht aktiv ist.
> 2.  Ordner, die im Dialogfeld **Verweispfade** angegeben sind.
> 3.  Ordner, die Dateien im Dialogfeld **Verweis hinzufügen** anzeigen
> 4.  Der OBJ-Ordner des Projekts (Wenn Sie Ihrem Projekt einen COM-Verweis hinzufügen, werden möglicherweise mindestens eine Assembly in den OBJ-Ordner eingefügt.)

 **Verweise**

 Diese Liste zeigt alle Verweise im Projekt, sowohl verwendete als auch nicht verwendete.

 **Add**

 Klicken Sie auf diese Schaltfläche, um einen Verweis oder einen Webverweis in der Liste **Verweise** einzufügen.

 Klicken Sie auf **Verweise**, um Ihrem Projekt einen Verweis mit dem Dialogfeld „Verweis hinzufügen“ hinzuzufügen.

 Klicken Sie auf **Webverweise**, um Ihrem Projekt einen Webverweis mit dem Dialogfeld „Webverweis hinzufügen“ hinzuzufügen.

 **Entfernen**

 Wählen Sie mindestens einen Verweis aus der Liste **Verweise** aus, und klicken Sie anschließend auf diese Schaltfläche, um ihn zu löschen.

 **Aktualisieren von Webverweisen**

 Wählen Sie mindestens einen Webverweis aus der Liste **Webverweise** aus, und klicken Sie anschließend auf diese Schaltfläche, um ihn zu aktualisieren.

 **Importierte Namespaces**

 Sie können Ihren eigenen Namespace in diesem Feld eingeben oder auf **Benutzerimport hinzufügen** klicken, um ihn in der Namespaceliste hinzuzufügen.

 Sie können Aliase für von Benutzern importierte Namespaces erstellen. Um dies zu tun, geben Sie Ihren Alias und den Namespace im Format *alias*=*namespace* ein. Dies ist praktisch, wenn Sie lange Namespaces verwenden, z.B.: `Http= MyOrg.ObjectLib.Internet.WebRequestMethods.Http`.

 **Benutzerimport hinzufügen**

 Klicken Sie auf diese Schaltfläche, um den im Feld **Importierte Namespaces** angegebenen Namespace der Liste der importierten Namespaces hinzuzufügen. Die Schaltfläche ist nur dann aktiviert, wenn der angegebene Namespace sich noch nicht in der Liste befindet.

 **Namespacesliste**

 Diese Liste zeigt alle verfügbaren Namespaces. Die Kontrollkästchen für Namespaces in Ihrem Projekt sind aktiviert.

 **Benutzerimport aktualisieren**

 Wählen Sie einen vom Benutzer angegebenen Namespace in der Namespaceliste aus, geben Sie den Namen im Feld **Importierte Namespaces** ein, der den Namespace ersetzen soll, und klicken Sie anschließend auf diese Schaltfläche, um den neuen Namespace zu ändern. Die Schaltfläche ist nur dann aktiviert, wenn der ausgewählte Namespace ein Namespace ist, den Sie der Liste mit der Schaltfläche **Benutzerimport hinzufügen** hinzugefügt haben. Sie können Folgendes hinzufügen:

-   Klassen oder Namespaces, wie z.B. <xref:System.Math?displayProperty=fullName>

-   Aliasimporte, wie z.B. `VB=Microsoft.VisualBasic`

-   XML-Namespaces, wie z.B. `<xmlns:xsl="http://www.w3.org/1999/XSL/Transform">`

## <a name="see-also"></a>Siehe auch

- [Verwalten von Verweisen in einem Projekt](../../ide/managing-references-in-a-project.md)
- [Gewusst wie: Hinzufügen oder Entfernen von importierten Namespaces (Visual Basic)](../../ide/how-to-add-or-remove-imported-namespaces-visual-basic.md)
- [Imports-Anweisung (XML-Namespace)](/dotnet/visual-basic/language-reference/statements/imports-statement-xml-namespace)
