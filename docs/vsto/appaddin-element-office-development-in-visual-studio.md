---
title: '&lt;AppAddin&gt; -Element (Office-Entwicklung in Visual Studio)'
ms.custom: ''
ms.date: 02/02/2017
ms.technology: office-development
ms.prod: visual-studio-dev15
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- application manifests [Office development in Visual Studio], <appAddin> element
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: 0defe437e0778ee9d3c134148a3ca7e4b4cd2ef9
ms.sourcegitcommit: 209c2c068ff0975994ed892b62aa9b834a7f6077
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/17/2018
---
# <a name="ltappaddingt-element-office-development-in-visual-studio"></a>&lt;AppAddin&gt; -Element (Office-Entwicklung in Visual Studio)
  Die **AppAddin** Element von der `vstov4` Namespace werden anpassungsspezifische Informationen für VSTO-Add-ins gespeichert.  
  
## <a name="syntax"></a>Syntax  
  
```xml 
<appAddin  
  application  
  loadBehavior  
  keyName>  
  <friendlyName>  
  <description>  
  <formRegions></formRegions>  
</appAddin>  
```  
  
## <a name="elements-and-attributes"></a>Elemente und Attribute  
 Die **AppAddin** Element ist erforderlich und befindet sich in der `vstov4` Namespace. Es Gib nur ein **AppAddin** Element in einem Anwendungsmanifest definiert.  
  
 Die **AppAddin** Element weist folgende Attribute.  
  
|Attribut|Beschreibung|  
|---------------|-----------------|  
|**Anwendung**|Erforderlich. Identifiziert die Microsoft Office-Anwendung. Einer der folgenden Werte ist möglich: Excel, InfoPath, Outlook, PowerPoint, Project, Visio oder Word.|  
|**loadBehavior**|Dies ist optional. Wird standardmäßig die **LoadBehavior** ist aktiviert, wenn dieser Wert auf. Zum Debuggen kann das VSTO-Add-In deaktiviert werden, indem der Wert auf 2 festgelegt wird. Weitere Informationen finden Sie in der Tabelle LoadBehavior-Werte in [Registrierungseinträge für VSTO-Add-ins](../vsto/registry-entries-for-vsto-add-ins.md).|  
|**Schlüsselname**|Erforderlich. Dieser Wert ist der Name des Registrierungsschlüssels, der von der Anwendung zum Laden des VSTO-Add-Ins verwendet wird. Weitere Informationen finden Sie unter [Registrierungseinträge für VSTO-Add-ins](../vsto/registry-entries-for-vsto-add-ins.md).|  
  
 Die **AppAddin** -Element weist die folgenden untergeordneten Elemente.  
  
### <a name="friendlyname"></a>friendlyName  
 Dies ist optional. Die **FriendlyName** Element wird erläutert [ &#60;FriendlyName&#62; Element &#40;Office-Entwicklung in Visual Studio&#41;](../vsto/friendlyname-element-office-development-in-visual-studio.md).  
  
### <a name="description"></a>Beschreibung  
 Dies ist optional. Die **Beschreibung** Element wird erläutert [ &#60;Beschreibung&#62; Element &#40;Office-Entwicklung in Visual Studio&#41;](../vsto/description-element-office-development-in-visual-studio.md).  
  
### <a name="formregions"></a>formRegions  
 Nur für Outlook-VSTO-Add-Ins erforderlich, die Formularbereiche enthalten. Die **FormRegions** Element wird erläutert [ &#60;FormRegions&#62; Element &#40;Office-Entwicklung in Visual Studio&#41;](../vsto/formregions-element-office-development-in-visual-studio.md).  
  
## <a name="vsto-add-in-example"></a>Beispiel für VSTO-Add-in  
  
### <a name="description"></a>Beschreibung  
 Im folgenden Codebeispiel wird veranschaulicht, **AppAddin** Elemente in einer Outlook-Projektmappe bereitgestellt, mit [!INCLUDE[ndptecclick](../vsto/includes/ndptecclick-md.md)]. Dieses Codebeispiel ist Teil eines umfangreicheren Beispiels [Anwendungsmanifeste für Office-Projektmappen](../vsto/application-manifests-for-office-solutions.md).  
  
### <a name="code"></a>Code  
  
```xml  
<vstov4:appAddIn   
  application="Outlook"   
  loadBehavior="3"   
  keyName="ContosoOutlookAddIn">  
  <vstov4:friendlyName>  
    ContosoOutlookAddIn  
  </vstov4:friendlyName>  
  <vstov4:description>  
    ContosoOutlookAddIn - Outlook VSTO Add-in   
    created with Visual Studio Tools for Office  
  </vstov4:description>  
  <vstov4:formRegions>  
    <vstov4:formRegion  
        name="OutlookAddIn1.FormRegion1">  
      <vstov4:messageClass name="IPM.Note" />  
      <vstov4:messageClass name="IPM.Contact" />  
      <vstov4:messageClass name="IPM.Appointment" />  
    </vstov4:formRegion>  
  </vstov4:formRegions>  
</vstov4:appAddIn>  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Anwendungsmanifeste für Office-Projektmappen](../vsto/application-manifests-for-office-solutions.md)   
 [Bereitstellungsmanifeste für Office-Projektmappen](../vsto/deployment-manifests-for-office-solutions.md)   
 [ClickOnce-Anwendungsmanifest](/visualstudio/deployment/clickonce-application-manifest)  
  
  