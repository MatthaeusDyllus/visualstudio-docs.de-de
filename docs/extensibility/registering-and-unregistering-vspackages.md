---
title: Registrieren und Aufheben der Registrierung von VSPackages | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- registration, VSPackages
- VSPackages, registering
ms.assetid: e25e7a46-6a55-4726-8def-ca316f553d6b
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 73dccc4aef061aaac5f5c33e098a591a7c51fcbb
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/16/2018
---
# <a name="registering-and-unregistering-vspackages"></a>Registrieren und Aufheben der Registrierung von VSPackages
Verwenden Sie Attribute, zum Registrieren von einer VSPackages, aber  
  
## <a name="registering-a-vspackage"></a>Registrieren eine VSPackage  
 Attribute können Sie um die Registrierung eines verwalteten VSPackages zu steuern. Alle Registrierungsinformationen wird in eine PKGDEF-Datei enthalten. Weitere Informationen zu einem dateibasierten Registrierung, finden Sie unter [CreatePkgDef Utility](../extensibility/internals/createpkgdef-utility.md).  
  
 Der folgende Code zeigt, wie Sie die standardmäßigen Registrierungsattribute verwenden, um Ihr VSPackage zu registrieren.  
  
```csharp  
[PackageRegistration(UseManagedResourcesOnly = true)]  
[Guid("0B81D86C-0A85-4f30-9B26-DD2616447F95")]  
public sealed class BasicPackage : Package  
{. . .}  
```  
  
## <a name="unregistering-an-extension"></a>Aufheben der Registrierung einer Erweiterungs  
 Wenn Sie mit einer Vielzahl von verschiedenen VSPackages experimentieren wurde haben und sie aus der experimentellen Instanz entfernen möchten, können Sie nur Ausführen der **zurücksetzen** Befehl. Suchen Sie nach **Zurücksetzen der experimentellen Instanz von Visual Studio** auf der Startseite des Computers, oder führen Sie diesen Befehl von der Befehlszeile aus:  
  
```vb  
<location of Visual Studio 2015 install>\"Microsoft Visual Studio 14.0\VSSDK\VisualStudioIntegration\Tools\Bin\CreateExpInstance.exe" /Reset /VSInstance=14.0 /RootSuffix=Exp  
```  
  
 Wenn Sie eine Erweiterung, die Sie für Ihre Entwicklungsinstanz von Visual Studio installiert haben, deinstallieren möchten, wechseln Sie zu **Extras / Erweiterungen und Updates**, suchen Sie nach der Erweiterung, und klicken Sie auf **Deinstallieren**.  
  
 Ist aus irgendeinem Grund keine dieser Methoden erfolgreich an die Erweiterung deinstallieren, können Sie die Registrierung die VSPackage-Assembly, über die Befehlszeile wie folgt aufheben:  
  
```  
<location of Visual Studio 2015 install>\"Microsoft Visual Studio 14.0\VSSDK\VisualStudioIntegration\Tools\Bin\regpkg" /unregister <pathToVSPackage assembly>  
```  
  
<a name="using-a-custom-registration-attribute-to-register-an-extension"></a>  
  
## <a name="use-a-custom-registration-attribute-to-register-an-extension"></a>Verwenden eines benutzerdefinierten registrierungsattributs zum Registrieren einer Erweiterung  
  
In bestimmten Fällen müssen Sie möglicherweise ein neues Registrierungsattribut für die Erweiterung zu erstellen. Sie können Registrierungsattribute verwenden, um neuen Registrierungsschlüssel hinzuzufügen oder um neue Werte zu vorhandenen Schlüssel hinzuzufügen. Das neue Attribut ableiten muss <xref:Microsoft.VisualStudio.Shell.RegistrationAttribute>, und es muss die <xref:Microsoft.VisualStudio.Shell.RegistrationAttribute.Register%2A> und <xref:Microsoft.VisualStudio.Shell.RegistrationAttribute.Unregister%2A> Methoden.  
  
### <a name="creating-a-custom-attribute"></a>Erstellen eines benutzerdefinierten Attributs  
  
Der folgende Code zeigt, wie ein neues Registrierungsattribut erstellt wird.  
  
```csharp  
[AttributeUsage(AttributeTargets.Class, Inherited = true, AllowMultiple = false)]  
    public class CustomRegistrationAttribute : RegistrationAttribute  
    {  
    }  
```  
  
 Die <xref:System.AttributeUsageAttribute> dient auf Attributklassen an das Programmelement (Klasse, Methode usw.) in der das Attribut gilt, gibt an, ob sie mehr als einmal verwendet werden kann, und gibt an, ob es geerbt werden kann.  
  
### <a name="creating-a-registry-key"></a>Erstellen eines Registrierungsschlüssels  
  
Im folgenden Code wird das benutzerdefinierte Attribut erstellt eine **benutzerdefinierte** Unterschlüssel unter dem Schlüssel für das VSPackage, der registriert wird.  
  
```csharp  
public override void Register(RegistrationAttribute.RegistrationContext context)  
{  
    Key packageKey = null;  
    try  
    {   
        packageKey = context.CreateKey(@"Packages\{" + context.ComponentType.GUID + @"}\Custom");  
        packageKey.SetValue("NewCustom", 1);  
    }  
    finally  
    {  
        if (packageKey != null)  
            packageKey.Close();  
    }  
}  
  
public override void Unregister(RegistrationContext context)  
{  
    context.RemoveKey(@"Packages\" + context.ComponentType.GUID + @"}\Custom");  
}  
```  
  
### <a name="creating-a-new-value-under-an-existing-registry-key"></a>Erstellen einen neuen Wert in einen vorhandenen Registrierungsschlüssel  
  
Sie können benutzerdefinierte Werte für einen vorhandenen Schlüssel hinzufügen. Der folgende Code zeigt, wie ein VSPackage-Registrierungsschlüssel einen neuen Wert hinzu.  
  
```csharp  
public override void Register(RegistrationAttribute.RegistrationContext context)  
{  
    Key packageKey = null;  
    try  
    {   
        packageKey = context.CreateKey(@"Packages\{" + context.ComponentType.GUID + "}");  
        packageKey.SetValue("NewCustom", 1);  
    }  
    finally  
    {  
        if (packageKey != null)  
            packageKey.Close();  
                }  
}  
  
public override void Unregister(RegistrationContext context)  
{  
    context.RemoveValue(@"Packages\" + context.ComponentType.GUID, "NewCustom");  
}  
```
  
## <a name="see-also"></a>Siehe auch  
 [VSPackages](../extensibility/internals/vspackages.md)