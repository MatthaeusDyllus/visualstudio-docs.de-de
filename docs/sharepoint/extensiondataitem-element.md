---
title: ExtensionDataItem-Element | Microsoft Docs
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- ExtensionDataItem element
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: eb88c8adc3f32e428543e2bf1e0e80e9538678a2
ms.sourcegitcommit: 4cd4aef53e7035d23e7d1d0f66f51ac8480622a1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/05/2018
ms.locfileid: "34766506"
---
# <a name="extensiondataitem-element"></a>ExtensionDataItem-Element
  Eine benutzerdefinierte Daten-Element, das die SharePoint-Projektelement im Schlüssel/Wert-Format zugeordnet ist. Sowohl der Schlüssel und Wert müssen Zeichenfolgen sein.  
  
## <a name="syntax"></a>Syntax  
  
```xml  
<ExtensionDataItem Key = "Key of the data item"  
    Value = "Value of the data item" />  
```  
  
## <a name="attributes-and-elements"></a>Attribute und Elemente
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### <a name="attributes"></a>Attribute  
  
|Attribut|Beschreibung|  
|---------------|-----------------|  
|**Key**|Erforderliche **Xs: String** Attribut.<br /><br /> Der Schlüssel, der zum Speichern und Abrufen des Datenelements verwendet wird.|  
|**Wert**|Erforderliche **xs: String** Attribut.<br /><br /> Der Wert des Datenelements.|  
  
### <a name="child-elements"></a>Untergeordnete Elemente
 Keine  
  
### <a name="parent-elements"></a>Übergeordnete Elemente
  
|Element|Beschreibung|  
|-------------|-----------------|  
|[ExtensionData](../sharepoint/extensiondata-element.md)|Stellt eine Auflistung benutzerdefinierter Datenelemente, die SharePoint-Projektelements zugeordnet sind.|  
  
## <a name="remarks"></a>Hinweise  
 Wenn Sie benutzerdefinierte Daten mit einem SharePoint-Projektelement mithilfe Zuordnen der <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectItem.ExtensionData%2A> Eigenschaft ein <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectItem> -Objekt, Visual Studio speichert die Daten in eine neue **ExtensionDataItem** Element in der `.spdata` Datei für die Projektelement. Weitere Informationen finden Sie unter [speichern Daten in Erweiterungen des SharePoint-Projektsystem](../sharepoint/saving-data-in-extensions-of-the-sharepoint-project-system.md).  
  
## <a name="element-information"></a>Elementinformationen
  
|||  
|-|-|  
|**Namespace**|HTTP<nolink>: //schemas.microsoft.com/VisualStudio/<br>2010/SharePointTools/SharePointProjectItemModel| 
|**Schemaname**|SharePoint-Projektelementschema|  
|**Validierungsdatei**|"ProjectItemModelSchema.xsd" benannt|  
|**Kann leer sein**|Nein|  
  
## <a name="see-also"></a>Siehe auch
 [Referenz zum SharePoint-Projektelementschema](../sharepoint/sharepoint-project-item-schema-reference.md)  
  
  
