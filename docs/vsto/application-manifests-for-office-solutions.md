---
title: Anwendungsmanifeste für Office-Projektmappen
ms.custom: ''
ms.date: 02/02/2017
ms.technology: office-development
ms.prod: visual-studio-dev15
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- application manifests [Office development in Visual Studio]
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: 622d2066f6acfe1fdf344f06ee5bbbbdf3d9b410
ms.sourcegitcommit: 209c2c068ff0975994ed892b62aa9b834a7f6077
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/17/2018
---
# <a name="application-manifests-for-office-solutions"></a>Anwendungsmanifeste für Office-Projektmappen
  Ein Anwendungsmanifest ist eine XML-Datei, die die Assemblys beschreibt, die in einer Microsoft Office-Projektmappe geladen werden. Verwenden Sie die Microsoft Office-Entwicklungstools in Visual Studio die [!INCLUDE[ndptecclick](../vsto/includes/ndptecclick-md.md)] -Anwendungsmanifestschema, das definiert, der [ClickOnce-Anwendungsmanifest](/visualstudio/deployment/clickonce-application-manifest) Verweis.  
  
 Anwendungsmanifeste für Office-Projektmappen verwenden die folgenden [!INCLUDE[ndptecclick](../vsto/includes/ndptecclick-md.md)] -Elemente und -Attribute.  
  
|Element|Beschreibung|Attribute|  
|-------------|-----------------|----------------|  
|[&#60;Assembly&#62; Element &#40;ClickOnce-Anwendung&#41;](/visualstudio/deployment/assembly-element-clickonce-deployment)|Erforderlich. Ein Element der obersten Ebene.|**ManifestVersion**|  
|[&#60;AssemblyIdentity&#62; Element &#40;ClickOnce-Anwendung&#41;](/visualstudio/deployment/assemblyidentity-element-clickonce-deployment)|Erforderlich. Gibt die primäre Assembly der [!INCLUDE[ndptecclick](../vsto/includes/ndptecclick-md.md)] -Anwendung an.|**name**<br /><br /> **version**<br /><br /> **PublicKeyToken**<br /><br /> **ProcessorArchitecture**<br /><br /> **language**|  
|[&#60;TrustInfo&#62; Element &#40;ClickOnce-Anwendung&#41;](/visualstudio/deployment/trustinfo-element-clickonce-application)|Gibt die Sicherheitsanforderungen der Anwendung an.|Keiner|  
|[&#60;EntryPoint&#62; Element &#40;ClickOnce-Anwendung&#41;](/visualstudio/deployment/entrypoint-element-clickonce-application)|Erforderlich. Gibt den Einstiegspunkt des Anwendungscodes für die Ausführung an.|**name**<br /><br /> **dependencyName**<br /><br /> **customHostSpecified**|  
|[&#60;Abhängigkeit&#62; Element &#40;ClickOnce-Anwendung&#41;](/visualstudio/deployment/dependency-element-clickonce-deployment)|Erforderlich. Gibt jede Abhängigkeit an, die für die Ausführung der Anwendung erforderlich ist. Gibt optional Assemblys an, die vorinstalliert werden müssen.|Keiner|  
|[&#60;Datei&#62; Element &#40;ClickOnce-Anwendung&#41;](/visualstudio/deployment/file-element-clickonce-application)|Erforderlich. Gibt jede Nicht-Assemblydatei an, die von der Anwendung verwendet wird. Kann COM-Isolationsdaten (Component Object Model) enthalten, die der Datei zugeordnet sind.|**name**<br /><br /> **size**|  
  
 Anwendungsmanifeste für Office-Projektmappen verwenden das folgenden Element im `co.v1` -Elemente.  
  
```xml  
<entryPoint>  
    <co.v1:customHostSpecified />  
</entryPoint>   
```  
  
 Diese Anwendungsmanifeste weisen auch die folgenden Elemente und Attribute im `vstav3` -Namespace auf.  
  
```xml  
<addIn>  
  <entryPointsCollection>  
    <entryPoints>  
      <entryPoint>  
      </entryPoint>  
    </entryPoints>  
  </entryPointsCollection>  
  <update></update>  
  <postActions>  
    <postAction>  
      <postActionData>  
      </postActionData>  
    <postAction>  
  </postActions>  
  <application>  
    <customizations>  
      <customization>  
      </customization>  
    </customizations>  
  </application  
</addIn>  
```  
  
|Element|Beschreibung|Attribute|  
|-------------|-----------------|----------------|  
|[&#60;CustomHostSpecified&#62; Element &#40;Office-Entwicklung in Visual Studio&#41;](../vsto/customhostspecified-element-office-development-in-visual-studio.md)|Erforderlich. Markiert das Manifest ausdrücklich als Office-Projektmappe.|Keiner|  
|[&#60;AddIn&#62; Element &#40;Office-Entwicklung in Visual Studio&#41;](../vsto/addin-element-office-development-in-visual-studio.md)|Erforderlich. Speichert Einstiegspunkte in einem einzelnen Namespace.|Keiner|  
|[&#60;EntryPointsCollection&#62; Element &#40;Office-Entwicklung in Visual Studio&#41;](../vsto/entrypointscollection-element-office-development-in-visual-studio.md)|Erforderlich. Gruppiert alle Assemblys für eine oder mehrere Office-Projektmappen.|**ID**|  
|[&#60;EntryPoints&#62; Element &#40;Office-Entwicklung in Visual Studio&#41;](../vsto/entrypoints-element-office-development-in-visual-studio.md)|Erforderlich. Gruppiert alle Assemblys, die in einer Office-Projektmappe ausgeführt werden.|Keiner|  
|[&#60;EntryPoint&#62; Element &#40;Office-Entwicklung in Visual Studio&#41;](../vsto/entrypoint-element-office-development-in-visual-studio.md)|Erforderlich. Gibt die Assemblys an, die in einer Office-Projektmappe ausgeführt werden.|**class**<br /><br /> **Vertrag**|  
|[&#60;Aktualisieren Sie&#62; Element &#40;Office-Entwicklung in Visual Studio&#41;](../vsto/update-element-office-development-in-visual-studio.md)|Erforderlich. Konfiguriert Updates für die Projektmappe.|**Aktiviert**<br /><br /> **Ablaufdatum**|  
|[&#60;PostActions&#62; Element &#40;Office-Entwicklung in Visual Studio&#41;](../vsto/postactions-element-office-development-in-visual-studio.md)|Dies ist optional. Gruppiert alle Aktionen nach der Bereitstellung, die nach der Installation von Office-Projektmappen ausgeführt werden.|Keiner|  
|[&#60;PostAction&#62; Element &#40;Office-Entwicklung in Visual Studio&#41;](../vsto/postaction-element-office-development-in-visual-studio.md)|Dies ist optional. Gibt eine Aktion nach der Bereitstellung an.|Keiner|  
|[&#60;PostActionData&#62; Element &#40;Office-Entwicklung in Visual Studio&#41;](../vsto/postactiondata-element-office-development-in-visual-studio.md)|Dies ist optional. Konfiguriert Daten für eine Aktion nach der Bereitstellung.|Keiner|  
|[&#60;Anwendung&#62; Element &#40;Office-Entwicklung in Visual Studio&#41;](../vsto/application-element-office-development-in-visual-studio.md)|Erforderlich. Umschließt die anwendungsspezifischen Informationen in einem einzelnen Knoten.|Keiner|  
|[&#60;Anpassungen&#62; Element &#40;Office-Entwicklung in Visual Studio&#41;](../vsto/customizations-element-office-development-in-visual-studio.md)|Erforderlich. Speichert alle anwendungshostspezifischen Informationen in einem separaten Namespace.|Keiner|  
|[&#60;Anpassung&#62; Element &#40;Office-Entwicklung in Visual Studio&#41;](../vsto/customization-element-office-development-in-visual-studio.md)|Erforderlich. Speichert anwendungshostspezifische Informationen in einem separaten Namespace.|**xmlns**|  
|[&#60;Dokument&#62; Element &#40;Office-Entwicklung in Visual Studio&#41;](../vsto/document-element-office-development-in-visual-studio.md)|Nur für Projektmappen auf Dokumentebene erforderlich. Speichert anpassungsspezifische Informationen.|**solutionId**|  
|[&#60;AppAddin&#62; Element &#40;Office-Entwicklung in Visual Studio&#41;](../vsto/appaddin-element-office-development-in-visual-studio.md)|Nur für Projektmappen auf Anwendungsebene erforderlich. Speichert anpassungsspezifische Informationen.|**Anwendung**<br /><br /> **loadBehavior**<br /><br /> **Schlüsselname**|  
|[&#60;FriendlyName&#62; Element &#40;Office-Entwicklung in Visual Studio&#41;](../vsto/friendlyname-element-office-development-in-visual-studio.md)|Dies ist optional. Speichert den Namen des VSTO-Add-Ins, das in der Liste der installierten VSTO-Add-Ins angezeigt wird.|Keiner|  
|[&#60;Beschreibung&#62; Element &#40;Office-Entwicklung in Visual Studio&#41;](../vsto/description-element-office-development-in-visual-studio.md)|Nur für VSTO-Add-Ins erforderlich. Speichert die Beschreibung, die in der Liste der installierten Programme angezeigt wird.|Keiner|  
|[&#60;FormRegions&#62; Element &#40;Office-Entwicklung in Visual Studio&#41;](../vsto/formregions-element-office-development-in-visual-studio.md)|Nur für Outlook-VSTO-Add-Ins erforderlich, die Formularbereiche enthalten.|Keiner|  
|[&#60;FormRegion&#62; Element &#40;Office-Entwicklung in Visual Studio&#41;](../vsto/formregion-element-office-development-in-visual-studio.md)|Nur für Outlook-VSTO-Add-Ins erforderlich, die Formularbereiche enthalten.|**Name**|  
|[&#60;VstoRuntime&#62; Element &#40;Office-Entwicklung in Visual Studio&#41;](../vsto/vstoruntime-element-office-development-in-visual-studio.md)|Erforderlich. Beschreibt eine bestimmte Version der Visual Studio Tools for Office-Laufzeit, die von der Office-Projektmappe unterstützt wird.|**release**<br /><br /> **version**<br /><br /> **supportUrl**|  
  
## <a name="remarks"></a>Hinweise  
 Anwendungs- und Bereitstellungsmanifeste in Office-Projektmappen können manuell bearbeitet werden. Danach müssen Sie die Anwendung erneut anmelden und die Bereitstellungsmanifeste mit dem Manifest Tool zum Generieren und bearbeiten (*mage.exe* und *mageui.exe*). Weitere Informationen finden Sie unter [wie: Signieren Sie Anwendungs- und Bereitstellungsmanifeste erneut](/visualstudio/deployment/how-to-re-sign-application-and-deployment-manifests).  
  
## <a name="file-location"></a>Dateispeicherort  
 Ein Anwendungsmanifest ist für eine einzelne Version einer Projektmappe spezifisch. Aus diesem Grund müssen die Anwendungsmanifeste getrennt von Bereitstellungsmanifesten gespeichert werden. [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] platziert die versionsspezifischen Dateien in einem Unterverzeichnis mit dem Namen der zugewiesenen Version in der *Anwendungsdateien* Unterverzeichnis im Ordner "Veröffentlichen".  
  
## <a name="file-name-syntax"></a>Dateinamensyntax  
 Der Name einer Anwendungsmanifestdatei muss den vollständigen Namen und die Erweiterung der Anwendung, das in der **AssemblyIdentity** -Element angegeben, gefolgt von der Erweiterung Manifest. Angenommen, ein Anwendungsmanifest, das auf verweist die *"OutlookAddIn1.dll"* Anpassung würde die folgende Syntax für Dateinamen verwenden.  
  
 `OutlookAddIn1.dll.manifest`  
  
## <a name="see-also"></a>Siehe auch  
 [Bereitstellungsmanifeste für Office-Projektmappen](../vsto/deployment-manifests-for-office-solutions.md)   
 [ClickOnce-Anwendungsmanifest](/visualstudio/deployment/clickonce-application-manifest)  
  
  