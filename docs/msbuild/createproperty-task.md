---
title: CreateProperty-Aufgabe | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology: msbuild
ms.topic: reference
f1_keywords:
- http://schemas.microsoft.com/developer/msbuild/2003#CreateProperty
dev_langs:
- VB
- CSharp
- C++
- jsharp
helpviewer_keywords:
- CreateProperty task [MSBuild]
- MSBuild, CreateProperty task
ms.assetid: fbc31a88-62d4-43d2-b739-68ef3fac38f5
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 817d888a14d20b4778b28f81811b876c6d97ad61
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/19/2018
---
# <a name="createproperty-task"></a>CreateProperty-Aufgabe
Füllt Eigenschaften mit den übergebenen Werten auf. Dadurch können Werte aus einer Eigenschaft oder Zeichenfolge in eine andere kopiert werden.  
  
## <a name="attributes"></a>Attribute  
 In der folgenden Tabelle werden die Parameter der `CreateProperty` -Aufgabe beschrieben.  
  
|Parameter|description|  
|---------------|-----------------|  
|`Value`|Optionaler `String`-Ausgabeparameter.<br /><br /> Gibt den Wert an, der in die neue Eigenschaft kopiert werden soll|  
|`ValueSetByTask`|Optionaler `String`-Ausgabeparameter.<br /><br /> Enthält denselben Wert wie der `Value`-Parameter. Verwenden Sie diesen Parameter nur, wenn die Ausgabeeigenschaft nicht von [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] festgelegt werden soll, wenn es das umschließende Ziel überspringt, weil die Ausgaben auf dem neuesten Stand sind.|  
  
## <a name="remarks"></a>Hinweise  
 Zusätzlich zu den oben aufgeführten Parametern erbt diese Aufgabe Parameter von der <xref:Microsoft.Build.Tasks.TaskExtension>-Klasse, die selbst von der <xref:Microsoft.Build.Utilities.Task>-Klasse erbt. Eine Liste mit diesen zusätzlichen Parametern und ihren Beschreibungen finden Sie unter [TaskExtension Base Class](../msbuild/taskextension-base-class.md).  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird die `NewFile`-Eigenschaft mit der `CreateProperty`-Aufgabe und der Kombination der Werte der Eigenschaften `SourceFilename` und `SourceFileExtension` erstellt.  
  
```xml  
<Project xmlns="http://schemas.microsoft.com/developer/msbuild/2003">  
  
    <PropertyGroup>  
        <SourceFilename>Module1</SourceFilename>  
        <SourceFileExtension>vb</SourceFileExtension>  
    </PropertyGroup>  
  
    <Target Name="CreateProperties">  
  
        <CreateProperty  
            Value="$(SourceFilename).$(SourceFileExtension)">  
            <Output  
                TaskParameter="Value"  
                PropertyName="NewFile" />  
        </CreateProperty>  
  
    </Target>  
  
</Project>  
```  
  
 Nach dem Ausführen des Projekts, ist der Wert der `NewFile`-Eigenschaft `Module1.vb`.  
  
## <a name="see-also"></a>Siehe auch  
 [Task Reference](../msbuild/msbuild-task-reference.md)  (MSBuild-Aufgabenreferenz)  
 [Tasks (Aufgaben)](../msbuild/msbuild-tasks.md)