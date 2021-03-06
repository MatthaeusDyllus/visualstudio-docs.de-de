---
title: 'CA2242: Ordnungsgemäß auf NaN testen'
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- TestForNaNCorrectly
- CA2242
helpviewer_keywords:
- CA2242
ms.assetid: e12dcffc-e255-4e1e-8fdf-3c6054d44abe
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 164072203a4dc4dc9d0351f6c45f425260078848
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/26/2018
---
# <a name="ca2242-test-for-nan-correctly"></a>CA2242: Ordnungsgemäß auf NaN testen
|||
|-|-|
|TypeName|TestForNaNCorrectly|
|CheckId|CA2242|
|Kategorie|Microsoft.Usage|
|Unterbrechende Änderung|Nicht unterbrechende Änderung|

## <a name="cause"></a>Ursache
 Ein Ausdruck testen Sie einen Wert für <xref:System.Single.NaN?displayProperty=fullName> oder <xref:System.Double.NaN?displayProperty=fullName>.

## <a name="rule-description"></a>Regelbeschreibung
 <xref:System.Double.NaN?displayProperty=fullName>, die Not-a-Number darstellt, entsteht, wenn eine arithmetische Operation nicht definiert ist. Ein Ausdruck, der Gleichheit zwischen einem Wert getestet und <xref:System.Double.NaN?displayProperty=fullName> gibt immer `false`. Ein Ausdruck, der testet die Ungleichheit zwischen einem Wert und <xref:System.Double.NaN?displayProperty=fullName> gibt immer `true`.

## <a name="how-to-fix-violations"></a>Behandeln von Verstößen
 Um einen Verstoß gegen diese Regel zu beheben und genau zu bestimmen, ob ein Wert darstellt, <xref:System.Double.NaN?displayProperty=fullName>, verwenden Sie <xref:System.Single.IsNaN%2A?displayProperty=fullName> oder <xref:System.Double.IsNaN%2A?displayProperty=fullName> zum Testen des Werts.

## <a name="when-to-suppress-warnings"></a>Wann sollten Warnungen unterdrückt werden?
 Unterdrücken Sie keine Warnung dieser Regel.

## <a name="example"></a>Beispiel
 Das folgende Beispiel zeigt zwei Ausdrücke, die einen Wert auf falsch testen <xref:System.Double.NaN?displayProperty=fullName> und einen Ausdruck, ordnungsgemäß verwendet <xref:System.Double.IsNaN%2A?displayProperty=fullName> zum Testen des Werts.

 [!code-vb[FxCop.Usage.TestForNaN#1](../code-quality/codesnippet/VisualBasic/ca2242-test-for-nan-correctly_1.vb)]
 [!code-csharp[FxCop.Usage.TestForNaN#1](../code-quality/codesnippet/CSharp/ca2242-test-for-nan-correctly_1.cs)]