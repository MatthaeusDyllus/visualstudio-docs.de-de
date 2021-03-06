---
title: 'CA1051: Sichtbare Instanzfelder nicht deklarieren'
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- CA1051
- DoNotDeclareVisibleInstanceFields
helpviewer_keywords:
- CA1051
- DoNotDeclareVisibleInstanceFields
ms.assetid: 2805376c-824c-462c-81d1-c51aaf7cabe7
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: dc08d39e842afa8bee9baa89f4c788f291d90ea2
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/26/2018
---
# <a name="ca1051-do-not-declare-visible-instance-fields"></a>CA1051: Sichtbare Instanzfelder nicht deklarieren
|||
|-|-|
|TypeName|DoNotDeclareVisibleInstanceFields|
|CheckId|CA1051|
|Kategorie|Microsoft.Design|
|Unterbrechende Änderung|Breaking|

## <a name="cause"></a>Ursache
 Ein extern sichtbarer Typ verfügt über eine extern sichtbare Instanzenfeld.

## <a name="rule-description"></a>Regelbeschreibung
 Ein Feld sollte primär als Implementierungsdetail verwendet werden. Felder sollten sein `private` oder `internal` und mithilfe von Eigenschaften verfügbar gemacht werden sollen. Es ist genauso einfach auf eine Eigenschaft zuzugreifen, ist es, die Zugriff auf ein Feld, und kann der Code in die Zugriffsmethoden einer Eigenschaft ändern, wie die Funktionen des Typs zu erweitern, ohne wichtige Änderungen einzuführen. Eigenschaften, die den Wert des einem privaten oder internen Feld zurückgeben sind optimiert, um Einklang mit bereit, den Zugriff auf ein Feld auszuführen; kaum Leistungsgewinn bezieht sich auf die Verwendung von extern sichtbaren Feldern über Eigenschaften zur Verfügung.

 Bezieht sich auf extern sichtbaren `public`, `protected`, und `protected internal` (`Public`, `Protected`, und `Protected Friend` in Visual Basic) Zugriffsebenen.

## <a name="how-to-fix-violations"></a>Behandeln von Verstößen
 Um einen Verstoß gegen diese Regel zu beheben, stellen Sie das Feld `private` oder `internal` und mithilfe einer extern sichtbaren Eigenschaft verfügbar gemacht.

## <a name="when-to-suppress-warnings"></a>Wann sollten Warnungen unterdrückt werden?
 Unterdrücken Sie keine Warnung dieser Regel. Extern sichtbare Feldern bieten keine Vorteile, die Eigenschaften nicht verfügbar sind. Darüber hinaus können nicht öffentlichen Felder geschützt werden, indem [Verknüpfungsaufrufe](/dotnet/framework/misc/link-demands). Finden Sie unter [CA2112: gesicherte Typen sollten keine Felder verfügbar](../code-quality/ca2112-secured-types-should-not-expose-fields.md).

## <a name="example"></a>Beispiel
 Das folgende Beispiel zeigt einen Typ (`BadPublicInstanceFields`), die mit dieser Regel verletzt. `GoodPublicInstanceFields` Zeigt den korrigierten Code.

 [!code-csharp[FxCop.Design.TypesPublicInstanceFields#1](../code-quality/codesnippet/CSharp/ca1051-do-not-declare-visible-instance-fields_1.cs)]

## <a name="related-rules"></a>Verwandte Regeln
 [CA2112: Gesicherte Typen sollten keine Felder verfügbar machen](../code-quality/ca2112-secured-types-should-not-expose-fields.md)

## <a name="see-also"></a>Siehe auch
 [Verknüpfungsaufrufe](/dotnet/framework/misc/link-demands)