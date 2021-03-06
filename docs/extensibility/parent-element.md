---
title: Parent-Element | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- VSCT XML schema elements, Parent
- Parent element (VSCT XML schema)
ms.assetid: e4624ac8-1b9a-4940-910a-528a661cefad
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 795654925a92f3e9ac0718e070e85c0f4f7f21c7
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/16/2018
---
# <a name="parent-element"></a>Parent-Element
Das übergeordnete Element eines Felds Schaltfläche oder Kombinationsfeld kann nur eine Gruppe sein. Das übergeordnete Element eines Menüs oder einer Gruppe kann eine beliebige andere Menü bzw. Gruppe sein. In einem [CommandPlacement Element](../extensibility/commandplacement-element.md), dieses Element ist erforderlich; in allen anderen Fällen ist er optional. Wenn dieses Element nicht angegeben ist, das übergeordnete Element des `Group_Undefined:0` wird impliziert werden.  
  
## <a name="syntax"></a>Syntax  
  
```  
<Parent guid="guidMyCommandSet" id="MyParentGroupOrMenu" />  
```  
  
## <a name="attributes-and-elements"></a>Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### <a name="attributes"></a>Attribute  
  
|Attribut|Beschreibung|  
|---------------|-----------------|  
|guid|Erforderlich. GUID der GUID/ID Befehlsbezeichner.|  
|ID|Erforderlich. ID der GUID/ID Befehlsbezeichner.|  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
 Keiner  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|[CommandTable-Element](../extensibility/commandtable-element.md)|Definiert die Elemente aus, die Befehle, die eine VSPackage bereitstellt, der integrierten Entwicklungsumgebung (IDE) darstellen. Beispielsweise Menüelemente, Menüs, Symbolleisten und Kombinationsfelder.|  
|[Buttons-Element](../extensibility/buttons-element.md)|Gruppen [Schaltflächenelement](../extensibility/button-element.md) Elemente.|  
|[Menus-Element](../extensibility/menus-element.md)|Definiert alle Menüs, die eine VSPackage implementiert.|  
|[Groups-Element](../extensibility/groups-element.md)|Enthält Einträge, die die Befehlsgruppen eines VSPackage definieren.|  
  
## <a name="see-also"></a>Siehe auch  
 [VSCT-Dateien (Visual Studio Command Table)](../extensibility/internals/visual-studio-command-table-dot-vsct-files.md)