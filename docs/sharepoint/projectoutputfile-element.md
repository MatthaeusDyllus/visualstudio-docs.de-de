---
title: ProjectOutputFile-Element | Microsoft Docs
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- ProjectOutputFile element
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: f77cb92e62d5a5aec4d5e43fe295a3bab279c579
ms.sourcegitcommit: 0aafcfa08ef74f162af2e5079be77061d7885cac
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2018
ms.locfileid: "34692157"
---
# <a name="projectoutputfile-element"></a>ProjectOutputFile-Element
  Stellt die Ausgabe von einem separaten Projekt mit dem Projektelement eingeschlossen werden soll, wenn er für SharePoint bereitgestellt wird.  
  
## <a name="syntax"></a>Syntax  
  
```xml  
<ProjectOutputFile ProjectId = "GUID of the project"  
    ProjectPath = "Relative path of the project"  
    Target = "Deployment path of the project output"  
    Type = "Type of deployment for the project output" />  
```  
  
## <a name="type"></a>Typ  
 **ProjectOutputFileType**  
  
## <a name="attributes-and-elements"></a>Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### <a name="attributes"></a>Attribute  
  
|Attribut|Beschreibung|  
|---------------|-----------------|  
|**projectId**|Erforderliche **xs: String** Attribut.<br /><br /> Die GUID des abhängigen Projekts, das die Ausgabe verfügt, die Sie einschließen möchten. Dies entspricht der **ProjectGuid** Element in der abhängigen Projektdatei.|  
|**ProjectPath**|Erforderliche **xs: String** Attribut.<br /><br /> Der relative Pfad, einschließlich des Dateinamens Projekt des abhängigen Projekts, das die Ausgabe verfügt, die Sie einschließen möchten. Dieser Pfad ist relativ zum Stammordner der SharePoint-Projekt, das die SharePoint-Projektelement enthält.|  
|**Target**|Optionale **xs: String** Attribut.<br /><br /> Der Pfad, in dem die Ausgabe des abhängigen Projekts ist, auf dem SharePoint-Server, relativ zum Stammordner Bereitstellung bereitgestellt werden. Stammordner der Bereitstellung richtet sich nach den Bereitstellungstyp, der gemäß der **Typ** Attribut.<br /><br /> Weitere Informationen finden Sie die Beschreibungen für die **Bereitstellungspfad** und **Bereitstellungsstamm-** Eigenschaften von SharePoint-Projektelemente in [Entwickeln von SharePoint-Lösungen](../sharepoint/developing-sharepoint-solutions.md).|  
|**Type**|Erforderliche **xs: String** Attribut.<br /><br /> Die Art der Bereitstellung für die Ausgabe des abhängigen Projekts verwendet werden soll. Weitere Informationen zu den möglichen Werten finden Sie in der Beschreibung für die **Bereitstellungstyp** Eigenschaft der SharePoint-Projektelemente im [Entwickeln von SharePoint-Lösungen](../sharepoint/developing-sharepoint-solutions.md).|  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
 Keine  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|[Dateien](../sharepoint/files-element.md)|Gibt die Dateien mit SharePoint-Projektelements eingeschlossen werden soll, wenn er für SharePoint bereitgestellt wird.|  
  
## <a name="remarks"></a>Hinweise  
 Verwenden der **ProjectOutputFile** Element, um die Ausgabe eines Projekts in der Bereitstellung des SharePoint-Projektelements einzuschließen. Sie können angeben, ein anderes Projekt oder das gleiche Projekt, das das Projektelement enthält. Weitere Informationen finden Sie unter [Bereitstellen von Pack- und Bereitstellungsinformationen in Projektelementen](../sharepoint/providing-packaging-and-deployment-information-in-project-items.md).  
  
## <a name="element-information"></a>Elementinformationen  
  
|||  
|-|-|  
|**Namespace**|HTTP<nolink>: //schemas.microsoft.com/VisualStudio/<br>2010/SharePointTools/SharePointProjectItemModel|  
|**Schemaname**|SharePoint-Projektelementschema|  
|**Validierungsdatei**|"ProjectItemModelSchema.xsd" benannt|  
|**Kann leer sein**|Nein|  
  
## <a name="see-also"></a>Siehe auch  
 [SharePoint-Projektelementschema](../sharepoint/sharepoint-project-item-schema-reference.md)   
 [Bereitstellen von Pack- und Bereitstellungsinformationen in Projektelementen](../sharepoint/providing-packaging-and-deployment-information-in-project-items.md)   
 [Entwickeln von SharePoint-Projektmappen](../sharepoint/developing-sharepoint-solutions.md)  
  
  