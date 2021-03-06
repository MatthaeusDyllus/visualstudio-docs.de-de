---
title: Element-Dateien | Microsoft Docs
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- Files element
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: 330c408aa0e283eb282b93f77726ccc5d9547795
ms.sourcegitcommit: 4cd4aef53e7035d23e7d1d0f66f51ac8480622a1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/05/2018
ms.locfileid: "34766905"
---
# <a name="files-element"></a>Files-Element
  Gibt die Dateien, die mit der SharePoint-Projektelement, z. B. featuredateien-Element und die Ausgabe der abhängigen nicht-SharePoint-Projekten bereitgestellt.  
  
## <a name="syntax"></a>Syntax  
  
```xml  
<Files>  
  <ProjectItemFile.../>  
  <ProjectOutputFile.../>  
</Files>  
```  
  
## <a name="type"></a>Typ  
 **FileCollectionType**  
  
## <a name="attributes-and-elements"></a>Attribute und Elemente
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### <a name="attributes"></a>Attribute  
 Keine  
  
### <a name="child-elements"></a>Untergeordnete Elemente
  
|Element|Beschreibung|  
|-------------|-----------------|  
|[ProjectItemFile](../sharepoint/projectitemfile-element.md)|Optionale **ProjectItemFileType** Element.<br /><br /> Stellt eine SharePoint-Datei, z. B. Elementdatei Feature, das Projektelement enthalten sein soll, wenn er für SharePoint bereitgestellt wird.|  
|[ProjectOutputFile](../sharepoint/projectoutputfile-element.md)|Optionale **ProjectOutputFileType** Element.<br /><br /> Stellt die Ausgabe eines Projekts mit dem Projektelement eingeschlossen werden soll, wenn er für SharePoint bereitgestellt wird.|  
  
### <a name="parent-elements"></a>Übergeordnete Elemente
  
|Element|Beschreibung|  
|-------------|-----------------|  
|[ProjectItem](../sharepoint/projectitem-element.md)|Stellt ein SharePoint-Projektelement dar. Dieses Element das erforderliche Stammelement von der `.spdata` Datei.|  
  
## <a name="element-information"></a>Elementinformationen
  
|||  
|-|-|  
|**Namespace**|HTTP<nolink>: //schemas.microsoft.com/VisualStudio/<br>2010/SharePointTools/SharePointProjectItemModel|  
|**Schemaname**|SharePoint-Projektelementschema|  
|**Validierungsdatei**|"ProjectItemModelSchema.xsd" benannt|  
|**Kann leer sein**|Nein|  
  
## <a name="see-also"></a>Siehe auch
 [Referenz zum SharePoint-Projektelementschema](../sharepoint/sharepoint-project-item-schema-reference.md)  
  
  
