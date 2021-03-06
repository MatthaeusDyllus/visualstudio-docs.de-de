---
title: 'Vorgehensweise: erstellen ein SharePoint-Lösungspakets mithilfe von MSBuild-Aufgaben | Microsoft Docs'
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
- VB
- CSharp
helpviewer_keywords:
- SharePoint development in Visual Studio, packages
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: 392724510e3145450cbea8ee70d23037ded073a1
ms.sourcegitcommit: 1466ac0f49ebf7448ea4507ae3f79acb25d51d3e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/22/2018
---
# <a name="how-to-create-a-sharepoint-solution-package-by-using-msbuild-tasks"></a>Gewusst wie: Erstellen eines SharePoint-Lösungspakets mithilfe von MSBuild-Aufgaben
  Sie können zu erstellen, bereinigen und überprüfen ein SharePoint-Paket (.wsp) mithilfe von Befehlszeilen MSBuild-Aufgaben auf einem Entwicklungscomputer. Diese Befehle können auch um während des Erstellungsprozesses mithilfe von Team Foundation Server auf einem Buildcomputer zu automatisieren.  
  
## <a name="building-a-sharepoint-package"></a>Erstellen ein SharePoint-Paket  
  
#### <a name="to-build-a-sharepoint-package"></a>Um ein SharePoint-Paket zu erstellen.  
  
1.  Auf der Windows **starten** Menü Wählen Sie **Programme**, **Zubehör**, **Eingabeaufforderung**.  
  
2.  Ändern Sie in das Verzeichnis, in dem das SharePoint-Projekt befindet.  
  
3.  Geben Sie den folgenden Befehl zum Erstellen eines Pakets für das Projekt aus. Ersetzen Sie *ProjectFileName* mit dem Namen des Projekts.  
  
    ```cmd  
    msbuild /t:Package ProjectFileName  
    ```  
  
     Beispielsweise könnten Sie die folgenden Befehle auf einem SharePoint-Projekt namens "ListDefinition1" Paket ausführen.  
  
    ```cmd  
    msbuild /t:Package ListDefinition1.vbproj  
    msbuild /t:Package ListDefinition1.csproj  
    ```  
  
## <a name="cleaning-a-sharepoint-package"></a>Bereinigen ein SharePoint-Paket  
  
#### <a name="to-clean-a-sharepoint-package"></a>So bereinigen ein SharePoint-Paket  
  
1.  Öffnen Sie ein Eingabeaufforderungsfenster.  
  
2.  Ändern Sie in das Verzeichnis, in dem das SharePoint-Projekt befindet.  
  
3.  Geben Sie den folgenden Befehl aus, um ein Paket für das Projekt zu bereinigen. Ersetzen Sie *ProjectFileName* mit dem Namen des Projekts.  
  
    ```cmd  
    msbuild /t:CleanPackage ProjectFileName  
    ```  
  
     Beispielsweise könnten Sie die folgenden Befehle auf einem SharePoint-Projekt namens ListDefinition1 bereinigen ausführen.  
  
    ```cmd  
    msbuild /t:CleanPackage ListDefinition1.vbproj  
    msbuild /t:CleanPackage ListDefinition1.csproj  
    ```  
  
## <a name="validating-a-sharepoint-package"></a>Überprüfen ein SharePoint-Paket  
  
#### <a name="to-validate-a-sharepoint-package"></a>So überprüfen Sie ein SharePoint-Paket  
  
1.  Öffnen Sie ein Eingabeaufforderungsfenster.  
  
2.  Ändern Sie in das Verzeichnis, in dem das SharePoint-Projekt befindet.  
  
3.  Geben Sie den folgenden Befehl zum Überprüfen von Paketen für das Projekt aus. Ersetzen Sie *ProjectFileName* mit dem Namen des Projekts.  
  
    ```cmd  
    msbuild /t:ValidatePackage ProjectFileName  
    ```  
  
     Beispielsweise könnten Sie die folgenden Befehle auf einem SharePoint-Projekt namens ListDefinition1 überprüfen ausführen.  
  
    ```cmd  
    msbuild /t:ValidatePackage ListDefinition1.vbproj  
    msbuild /t:ValidatePackage ListDefinition1.csproj  
    ```  
  
## <a name="setting-properties-in-a-sharepoint-package"></a>Festlegen von Eigenschaften in einem SharePoint-Paket  
  
#### <a name="to-set-a-property-in-a-sharepoint-package"></a>Festlegen von Eigenschaften in einem SharePoint-Paket  
  
1.  Öffnen Sie ein Eingabeaufforderungsfenster.  
  
2.  Ändern Sie in das Verzeichnis, in dem das SharePoint-Projekt befindet.  
  
3.  Geben Sie den folgenden Befehl zum Festlegen einer Eigenschaft in ein Paket für das Projekt aus. Ersetzen Sie *PropertyName* mit der Eigenschaft, die Sie festlegen möchten.  
  
    ```cmd  
    msbuild /property:PropertyName=Value  
    ```  
  
     Beispielsweise können Sie den folgenden Befehl aus, um die Warnstufe festlegen ausführen.  
  
    ```cmd  
    msbuild /property:WarningLevel = 2  
    ```  
  
## <a name="see-also"></a>Siehe auch  
 [Erstellen von SharePoint-Funktionen](../sharepoint/creating-sharepoint-features.md)   
 [Vorgehensweise: Anpassen einer SharePoint-Funktion](../sharepoint/how-to-customize-a-sharepoint-feature.md)   
 [Vorgehensweise: Hinzufügen und Entfernen von Elementen in SharePoint-Funktionen](../sharepoint/how-to-add-and-remove-items-to-sharepoint-features.md)  
  
  