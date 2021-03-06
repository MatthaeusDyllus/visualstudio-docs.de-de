---
title: UpdateManifestForBrowserApplication-Aufgabe | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology: msbuild
ms.topic: reference
dev_langs:
- VB
- CSharp
- C++
- jsharp
helpviewer_keywords:
- UpdateManifestForBrowserApplication task [WPF MSBuild]
- adding the <hostInBrowser /> element to the application manifest [WPF MSBuild]
- building XBAP projects [WPF MSBuild]
- UpdateManifestForBrowserApplication task [WPF MSBuild], parameters
ms.assetid: 653339f7-654b-4d64-a26a-5c9f27036895
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 0f944d8546fd9124bc881f8421943d34a86698c5
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/19/2018
---
# <a name="updatemanifestforbrowserapplication-task"></a>UpdateManifestForBrowserApplication-Aufgabe
Der <xref:Microsoft.Build.Tasks.Windows.UpdateManifestForBrowserApplication>-Task wird ausgeführt, um das **\<hostInBrowser />**-Element dem Anwendungsmanifest (*projectname*.exe.manifest) hinzuzufügen, wenn ein [!INCLUDE[TLA#tla_xbap](../msbuild/includes/tlasharptla_xbap_md.md)]-Projekt erstellt wird.  
  
## <a name="task-parameters"></a>Aufgabenparameter  
  
|Parameter|description|  
|---------------|-----------------|  
|`ApplicationManifest`|Erforderlicher **ITaskItem[]**-Parameter.<br /><br /> Gibt den Pfad und den Namen der Anwendungsmanifestdatei an, der Sie das `<hostInBrowser />` Element hinzufügen möchten.|  
|`HostInBrowser`|Erforderlicher **boolescher** Parameter.<br /><br /> Gibt an, ob das Anwendungsmanifest geändert werden soll, um das **\<hostInBrowser />**-Element einzufügen. Wenn **true**, dann ist ein neues `<`**hostInBrowser />**-Element im **\<entryPoint />**-Element enthalten. Beachten Sie, dass der Einschluss von Elementen kumulativ ist: Wenn ein **\<hostInBrowser />**-Element bereits vorhanden ist, wird es weder entfernt noch überschrieben. Stattdessen wird ein zusätzliches **\<hostInBrowser />**-Element erstellt. Wenn **false**, dann ist das Anwendungsmanifest nicht geändert.|  
  
## <a name="remarks"></a>Hinweise  
 [!INCLUDE[TLA2#tla_xbap#plural](../msbuild/includes/tla2sharptla_xbapsharpplural_md.md)] wird mithilfe von [!INCLUDE[TLA#tla_clickonce](../msbuild/includes/tlasharptla_clickonce_md.md)] ausgeführt und muss aus diesem Grund mit unterstützenden Bereitstellungs- und Anwendungsmanifesten veröffentlicht werden. [!INCLUDE[TLA#tla_msbuild](../msbuild/includes/tlasharptla_msbuild_md.md)] verwendet die [GenerateApplicationManifest](http://msdn2.microsoft.com/library/6wc2ccdc.aspx)-Aufgabe zum Generieren eines Anwendungsmanifests.  
  
 Anschließend muss ein zusätzliches Element, **\<hostInBrowser />**, dem Anwendungsmanifest hinzugefügt werden, um eine Anwendung zu konfigurieren, die von einem Browser gehostet wird; wie im folgenden Beispiel gezeigt:  
  
```xml  
<!--MyXBAPApplication.exe.manifest-->  
<?xml version="1.0" encoding="utf-8"?>  
<asmv1:assembly ... >  
    <asmv1:assemblyIdentity ... />  
    <application />  
    <entryPoint>  
      ...  
      <hostInBrowser xmlns="urn:schemas-microsoft-com:asm.v3" />  
    </entryPoint>  
  ...  
/>  
```  
  
 Die <xref:Microsoft.Build.Tasks.Windows.UpdateManifestForBrowserApplication> Aufgabe wird ausgeführt, wenn ein [!INCLUDE[TLA2#tla_xbap](../msbuild/includes/tla2sharptla_xbap_md.md)] Projekt erstellt wird, um das `<hostInBrowser />` Element hinzuzufügen.  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel zeigt, wie Sie sicherstellen, dass das `<hostInBrowser />` Element in einer Anwendungsmanifestdatei eingefügt wird.  
  
```xml  
<Project xmlns="http://schemas.microsoft.com/developer/msbuild/2003">  
  <UsingTask   
    TaskName="Microsoft.Build.Tasks.Windows.UpdateManifestForBrowserApplication"  
    AssemblyFile="C:\Program Files\Reference Assemblies\Microsoft\Framework\v3.0\PresentationBuildTasks.dll" />  
  <Target Name="UpdateManifestForBrowserApplicationTask">  
    <UpdateManifestForBrowserApplication  
      ApplicationManifest="MyXBAPApplication.exe.manifest"  
      HostInBrowser="true" />  
  </Target>  
</Project>  
```  
  
## <a name="see-also"></a>Siehe auch  
 [WPF-MSBuild-Referenz](../msbuild/wpf-msbuild-reference.md)   
 [Task Reference](../msbuild/wpf-msbuild-task-reference.md)  (MSBuild-Aufgabenreferenz)  
 [MSBuild Reference](../msbuild/msbuild-reference.md)  (MSBuild-Referenz)  
 [Task Reference](../msbuild/msbuild-task-reference.md)  (MSBuild-Aufgabenreferenz)  
 [Erstellen einer WPF-Anwendung (WPF)](/dotnet/framework/wpf/app-development/building-a-wpf-application-wpf)   
 [Übersicht über WPF-XAML-Browseranwendungen](/dotnet/framework/wpf/app-development/wpf-xaml-browser-applications-overview)