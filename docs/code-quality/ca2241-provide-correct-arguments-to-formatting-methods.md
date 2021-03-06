---
title: 'CA2241: Geeignete Argumente für Formatierungsmethoden angeben'
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- CA2241
- Provide correct arguments to formatting methods
- ProvideCorrectArgumentsToFormattingMethods
helpviewer_keywords:
- ProvideCorrectArgumentsToFormattingMethods
- CA2241
ms.assetid: 83639bc4-4c91-4a07-a40e-dc5e49a84494
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 5c695c9f6e8af0e61bed88fd5a880e5655ecb7d6
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/26/2018
---
# <a name="ca2241-provide-correct-arguments-to-formatting-methods"></a>CA2241: Geeignete Argumente für Formatierungsmethoden angeben
|||
|-|-|
|TypeName|ProvideCorrectArgumentsToFormattingMethods|
|CheckId|CA2241|
|Kategorie|Microsoft.Usage|
|Unterbrechende Änderung|Nicht unterbrechende Änderung|

## <a name="cause"></a>Ursache
 Die `format` Zeichenfolgenargument an eine Methode übergeben, z. B. <xref:System.Console.WriteLine%2A>, <xref:System.Console.Write%2A>, oder <xref:System.String.Format%2A?displayProperty=fullName> enthält keine Formatelements, die den einzelnen Objektargumenten (oder umgekehrt) entspricht.

## <a name="rule-description"></a>Regelbeschreibung
 Die Argumente von Methoden wie z. B. <xref:System.Console.WriteLine%2A>, <xref:System.Console.Write%2A>, und <xref:System.String.Format%2A> bestehen aus einer Formatzeichenfolge gefolgt von mehreren <xref:System.Object?displayProperty=fullName> Instanzen. Die Formatzeichenfolge besteht aus Text und eingebetteten Formatelementen im Format {Index [, Ausrichtung] [: "FormatString"]}. 'Index' ist eine nullbasierte ganze Zahl, die die den zu formatierenden Objekten angibt. Wenn ein Objekt nicht über einen entsprechenden Index in der Formatzeichenfolge verfügt, wird das Objekt ignoriert. Wenn das durch "Index" angegebene Objekt nicht vorhanden ist, eine <xref:System.FormatException?displayProperty=fullName> wird zur Laufzeit ausgelöst.

## <a name="how-to-fix-violations"></a>Behandeln von Verstößen
 Um einen Verstoß gegen diese Regel zu beheben, geben Sie ein Formatelement für jedes Objektargument, und geben Sie für jedes Formatelement eine Objekt-Argument.

## <a name="when-to-suppress-warnings"></a>Wann sollten Warnungen unterdrückt werden?
 Unterdrücken Sie keine Warnung dieser Regel.

## <a name="example"></a>Beispiel
 Das folgende Beispiel zeigt zwei Verstöße gegen diese Regel.

 [!code-vb[FxCop.Usage.FormattingArguments#1](../code-quality/codesnippet/VisualBasic/ca2241-provide-correct-arguments-to-formatting-methods_1.vb)]
 [!code-csharp[FxCop.Usage.FormattingArguments#1](../code-quality/codesnippet/CSharp/ca2241-provide-correct-arguments-to-formatting-methods_1.cs)]