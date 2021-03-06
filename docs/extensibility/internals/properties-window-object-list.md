---
title: Liste der Eigenschaften im Fenster Objekt | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- Properties window, object list
ms.assetid: 6c159c9d-345d-4b23-8ddd-9839d338b62f
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: b6b7d238f7ce64122ac18a52dab59afb063ce47e
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/16/2018
---
# <a name="properties-window-object-list"></a>Liste der Eigenschaften im Fenster Objekt
In der Objektliste der **Eigenschaften** Fenster ist eine Dropdown-Liste, die Ihnen ermöglicht, ändern Sie die Auswahl auf andere Objekte in mindestens einem ausgewählten Windows verfügbar. Wählen ein anderes Objekt aus, in dieser Liste löst einen Aufruf von <xref:Microsoft.VisualStudio.Shell.Interop.ISelectionContainer.SelectObjects%2A> um der Umgebung zu informieren, dass ein neues Objekt ausgewählt wurde. Die Informationen den **Eigenschaften** Fenster wird geändert, um die neu ausgewählte Objekt zugeordneten Eigenschaften anzuzeigen.  
  
## <a name="the-object-list"></a>Objektliste  
 Die Objektliste besteht aus zwei Felder: den Objektnamen (in Fettschrift angezeigt) und den Objekttyp.  
  
 Der Objektname, der auf der linken Seite des Objekttyps in Fettdruck angezeigt wird abgerufen, aus dem Objekt selbst mit den `Name` vom bereitgestellte Eigenschaft der <xref:Microsoft.VisualStudio.OLE.Interop.IProvideClassInfo> Schnittstelle. <xref:Microsoft.VisualStudio.OLE.Interop.IProvideClassInfo.GetClassInfo%2A>, auf die einzige Methode <xref:Microsoft.VisualStudio.OLE.Interop.IProvideClassInfo>, gibt <xref:Microsoft.VisualStudio.OLE.Interop.ITypeInfo> für diese Schnittstelle, Co-Klasse. Die **Eigenschaften** Fenster verwendet <xref:Microsoft.VisualStudio.OLE.Interop.IProvideClassInfo> abzurufenden den Namen der Co-Klasse, die als der Objektname in der Dropdown-Liste angezeigt wird.  
  
 Wenn das Objekt keine `Name` Eigenschaft, einen Namen wird die Objektliste im Bereich "Name" nicht angezeigt. Sie können eine Name-Eigenschaft auf das Objekt hinzufügen, wenn Sie den Namen in der Liste angezeigt werden soll.  
  
 Wenn das COM-Objekt nicht implementiert <xref:Microsoft.VisualStudio.OLE.Interop.IProvideClassInfo>, **Eigenschaften** Fenster werden die Namen der Schnittstelle anstelle des Objektnamens angegeben auf der linken Seite der Liste angezeigt.  
  
## <a name="see-also"></a>Siehe auch  
 [Erweitern von Eigenschaften](../../extensibility/internals/extending-properties.md)