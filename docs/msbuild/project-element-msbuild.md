---
title: Project-Element (MSBuild) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/13/2017
ms.technology: msbuild
ms.topic: reference
f1_keywords:
- http://schemas.microsoft.com/developer/msbuild/2003#Project
dev_langs:
- VB
- CSharp
- C++
- jsharp
helpviewer_keywords:
- ToolsVersion attribute [MSBuild]
- <Project> element [MSBuild]
- Project element [MSBuild]
ms.assetid: d1cda56a-dbef-4109-9201-39e962e3f653
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 44f63cf4517320b9acea0d289723a511dfeb9570
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/19/2018
---
# <a name="project-element-msbuild"></a>Project-Element (MSBuild)
Erforderliches Stammelement einer [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] -Projektdatei.  

## <a name="syntax"></a>Syntax  

```  
<Project InitialTargets="TargetA;TargetB"  
         DefaultTargets="TargetC;TargetD"  
         TreatAsLocalProperty="PropertyA;PropertyB"  
         ToolsVersion=<version number>
         Sdk="name[/version]"
         xmlns="http://schemas.microsoft.com/developer/msbuild/2003">  
    <Sdk... />
    <Choose>... </Choose>  
    <PropertyGroup>... </PropertyGroup>  
    <ItemGroup>... </ItemGroup>  
    <Target>... </Target>  
    <UsingTask.../>  
    <ProjectExtensions>... </ProjectExtensions>  
    <Import... />  
</Project>  
```  

## <a name="attributes-and-elements"></a>Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  

### <a name="attributes"></a>Attribute  

|Attribut|description|  
|---------------|-----------------|  
|`DefaultTargets`|Optionales Attribut.<br /><br /> Das Standardziel oder die Standardziele, die zum Einstiegspunkt des Builds werden, wenn kein Ziel angegeben wurde. Mehrere Ziele werden durch Semikolons (;) getrennt.<br /><br /> Wenn kein Standardziel im `DefaultTargets`-Attribut oder der [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)]-Befehlszeile angegeben ist, führt das Modul das erste Ziel in der Projektdatei aus, nachdem die [Import](../msbuild/import-element-msbuild.md)-Elemente ausgewertet wurden.|  
|`InitialTargets`|Optionales Attribut.<br /><br /> Die anfänglichen Ziele werden ausgeführt bevor die Ziele im `DefaultTargets`-Attribut oder in der Befehlszeile angegeben werden . Mehrere Ziele werden durch Semikolons (;) getrennt.|  
|`Sdk`|Optionales Attribut. <br /><br /> Der SDK-Name und optional die Version, mit denen implizite Importanweisungen, die der PROJ-Datei hinzugefügt werden, erstellt werden. Wenn keine Version angegeben wird, versucht MSBuild eine Standardversion aufzulösen.  Beispielsweise `<Project Sdk="Microsoft.NET.Sdk" />` oder `<Project Sdk="My.Custom.Sdk/1.0.0" />`.|  
|`ToolsVersion`|Optionales Attribut.<br /><br /> Die Version des Toolsets, das MSBuild verwendet, um die Werte für $(MSBuildBinPath) und (MSBuildToolsPath) zu bestimmen.|  
|`TreatAsLocalProperty`|Optionales Attribut.<br /><br /> Eigenschaftennamen, die nicht als global betrachtet werden. Dieses Attribut verhindert, dass bestimmte Befehlszeileneigenschaften Eigenschaftswerte überschreiben, die in einer Projekt- oder Zieldatei und allen nachfolgenden Importen festgelegt sind. Mehrere Eigenschaften werden durch Semikolons (;) getrennt.<br /><br /> Diese globalen Eigenschaften überschreiben normalerweise Eigenschaftswerte, die in der Projektdatei oder in Zieldateien festgelegt werden. Wenn die Eigenschaft im `TreatAsLocalProperty`-Wert aufgeführt wird, überschreibt der globale Eigenschaftenwert die Eigenschaftenwerte nicht, die in dieser Datei und allen nachfolgenden Importen festgelegt werden. Weitere Informationen finden Sie unter [Vorgehensweise: Erstellen identischer Quelldateien mit unterschiedlichen Optionen](../msbuild/how-to-build-the-same-source-files-with-different-options.md). **Hinweis:** Festlegen globaler Eigenschaften in der Befehlszeile mithilfe des Schalters **/property** (oder **/p**). Globale Eigenschaften können auch für untergeordnete Projekte in einem Build mit mehreren Projekten festgelegt oder geändert werden, indem das `Properties`-Attribut der MSBuild-Aufgabe verwendet wird. Weitere Informationen finden Sie unter [MSBuild-Aufgabe](../msbuild/msbuild-task.md).|  
|`Xmlns`|Optionales Attribut.<br /><br /> Wenn das `xmlns`-Attribut angegeben wird, muss als Wert http://schemas.microsoft.com/developer/msbuild/2003 festgelegt sein.|  

### <a name="child-elements"></a>Untergeordnete Elemente  

|Element|description|  
|-------------|-----------------|  
|[Auswählen](../msbuild/choose-element-msbuild.md)|Optionales Element.<br /><br /> Bewertet untergeordnete Elemente, um einen Satz von auszuwertenden `ItemGroup`-Elementen und/oder `PropertyGroup`-Elementen auszuwählen.|  
|[Importieren](../msbuild/import-element-msbuild.md)|Optionales Element.<br /><br /> Ermöglicht den Import einer Projektdatei in eine andere Projektdatei. Es kann kein oder mehrere `Import`-Elemente in einem Projekt geben.|  
|[ItemGroup](../msbuild/itemgroup-element-msbuild.md)|Optionales Element.<br /><br /> Ein Gruppierungselement für einzelne Elemente. Elemente werden mit dem [Item](../msbuild/item-element-msbuild.md)-Element angegeben. Es kann kein oder mehrere `ItemGroup`-Elemente in einem Projekt geben.|  
|[ProjectExtensions](../msbuild/projectextensions-element-msbuild.md)|Optionales Element.<br /><br /> Bietet eine Möglichkeit, die nicht-[!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)]-Informationen in einer [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)]-Projektdatei beizubehalten. Es kann kein oder mehrere `ProjectExtensions`-Elemente in einem Projekt geben.|  
|[PropertyGroup](../msbuild/propertygroup-element-msbuild.md)|Optionales Element.<br /><br /> Ein Gruppierungselement für einzelne Eigenschaften. Eigenschaften werden mit dem [Property](../msbuild/property-element-msbuild.md)-Element angegeben. Es kann kein oder mehrere `PropertyGroup`-Elemente in einem Projekt geben.|
|[Sdk](../msbuild/sdk-element-msbuild.md)|Optionales Element.<br /><br /> Verweist auf ein [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)]-Projekt-SDK.  Dieses Element kann alternativ zum Sdk-Attribut verwendet werden.|  
|[Target](../msbuild/target-element-msbuild.md)|Optionales Element.<br /><br /> Enthält eine Reihe von Aufgaben, die [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] sequenziell ausführt. Aufgaben werden mit dem [Aufgaben](../msbuild/task-element-msbuild.md)-Element angegeben. Es kann kein oder mehrere `Target`-Elemente in einem Projekt geben.|  
|[UsingTask](../msbuild/usingtask-element-msbuild.md)|Optionales Element.<br /><br /> Bietet eine Möglichkeit, Aufgaben in [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] zu registrieren. Es kann kein oder mehrere `UsingTask`-Elemente in einem Projekt geben.|  

### <a name="parent-elements"></a>Übergeordnete Elemente  
 Keine  

## <a name="see-also"></a>Siehe auch  
 [Vorgehensweise: Angeben des zuerst zu erstellenden Ziels](../msbuild/how-to-specify-which-target-to-build-first.md)   
 [Befehlszeilenreferenz](../msbuild/msbuild-command-line-reference.md)   
 [Referenz zum Projektdateischema](../msbuild/msbuild-project-file-schema-reference.md)   
 [MSBuild](../msbuild/msbuild.md)
