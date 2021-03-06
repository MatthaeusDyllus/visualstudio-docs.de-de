---
title: -Command („devenv.exe“)
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-general
ms.topic: reference
helpviewer_keywords:
- Devenv, /command switch
- /command Devenv switch
ms.assetid: 13c20cd6-f09d-400a-8b7b-ecc266a32cef
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: c21402c3b2b71372aaf170c68c65777eba4e95bf
ms.sourcegitcommit: fe5a72bc4c291500f0bf4d6e0778107eb8c905f5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/07/2018
---
# <a name="command-devenvexe"></a>/Command (devenv.exe)
Öffnet die integrierte Entwicklungsumgebung (IDE) von [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] und führt dann den angegebenen Befehl aus.

## <a name="syntax"></a>Syntax

```cmd
devenv /command CommandName
```

## <a name="arguments"></a>Argumente
 `CommandName` ist erforderlich. Der vollständige Name eines [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)]-Befehls oder dessen Aliasname in doppelten Anführungszeichen. Weitere Informationen zur Syntax von Befehlen und Alias finden Sie unter [Visual Studio-Befehle](../../ide/reference/visual-studio-commands.md).

## <a name="remarks"></a>Hinweise
 Nachdem der Startvorgang abgeschlossen wurde, wird der genannte Befehl in der IDE ausgeführt. Bei Verwendung dieses Schalters wird in der IDE beim Start nicht die [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)]-Startseite angezeigt.

 Wenn ein Befehl mittels eines Add-Ins verfügbar gemacht wird, können Sie das Add-In mithilfe dieses Schalters von der Befehlszeile aus starten. Weitere Informationen finden Sie unter [Vorgehensweise: Steuern von Add-Ins mit dem Add-In-Manager](http://msdn.microsoft.com/Library/4f60444a-cb48-4cdb-8df4-941f6419aeeb).

## <a name="example"></a>Beispiel
 In diesem Beispiel wird [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] gestartet und automatisch das Makro "Open Favorite Files" ausgeführt.

```cmd
devenv /command "Macros.MyMacros.Module1.OpenFavoriteFiles"
```

## <a name="see-also"></a>Siehe auch

- [Devenv-Befehlszeilenschalter](../../ide/reference/devenv-command-line-switches.md)
- [Visual Studio-Befehlsaliase](../../ide/reference/visual-studio-command-aliases.md)