---
title: 'CA2236: Basisklassenmethoden auf ISerializable-Typen aufrufen'
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- CA2236
- CallBaseClassMethodsOnISerializableTypes
helpviewer_keywords:
- CA2236
- CallBaseClassMethodsOnISerializableTypes
ms.assetid: 5a15b20d-769c-4640-b31a-36e07077daae
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 81ea72439219431ee0a1a5403aa266e1b2601a78
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/26/2018
---
# <a name="ca2236-call-base-class-methods-on-iserializable-types"></a>CA2236: Basisklassenmethoden auf ISerializable-Typen aufrufen
|||
|-|-|
|TypeName|CallBaseClassMethodsOnISerializableTypes|
|CheckId|CA2236|
|Kategorie|Microsoft.Usage|
|Unterbrechende Änderung|Nicht unterbrechende Änderung|

## <a name="cause"></a>Ursache
 Ein Typ leitet sich von einem Typ, der implementiert die <xref:System.Runtime.Serialization.ISerializable?displayProperty=fullName> -Schnittstelle, und eine der folgenden Bedingungen zutrifft:

-   Der Typ implementiert den Serialisierungskonstruktor, d. h. einen Konstruktor mit der <xref:System.Runtime.Serialization.SerializationInfo?displayProperty=fullName>, <xref:System.Runtime.Serialization.StreamingContext?displayProperty=fullName> Parametersignatur, jedoch nicht den Serialisierungskonstruktor des Basistyps aufgerufen wird.

-   Der Typ implementiert die <xref:System.Runtime.Serialization.ISerializable.GetObjectData%2A?displayProperty=fullName> Methode jedoch nicht auf die <xref:System.Runtime.Serialization.ISerializable.GetObjectData%2A> Methode des Basistyps.

## <a name="rule-description"></a>Regelbeschreibung
 In einem benutzerdefinierten Serialisierungsprozess ein Typ implementiert die <xref:System.Runtime.Serialization.ISerializable.GetObjectData%2A> -Methode zum Serialisieren von dessen Felder und den Serialisierungskonstruktor Felder deserialisiert werden. Wenn der Typ von einem Typ abgeleitet wird, implementiert die <xref:System.Runtime.Serialization.ISerializable> -Schnittstelle ein, den Basistyp <xref:System.Runtime.Serialization.ISerializable.GetObjectData%2A> -Methode und der Serialisierungskonstruktor sollte aufgerufen werden, um serialisieren/Deserialisieren der Felder des Basistyps. Andernfalls, der Typ wird nicht werden serialisiert und deserialisiert ordnungsgemäß. Beachten Sie, dass wenn der abgeleitete Typ keine neuen Felder hinzugefügt, der Typ nicht zum Implementieren der <xref:System.Runtime.Serialization.ISerializable.GetObjectData%2A> -Methode oder den Serialisierungskonstruktor, oder rufen Sie die Entsprechungen für Basistyp.

## <a name="how-to-fix-violations"></a>Behandeln von Verstößen
 Um einen Verstoß gegen diese Regel zu beheben, rufen Sie den Basistyp <xref:System.Runtime.Serialization.ISerializable.GetObjectData%2A> -Methode oder der Serialisierung Konstruktor aus der entsprechenden abgeleiteten Typmethode oder der Konstruktor.

## <a name="when-to-suppress-warnings"></a>Wann sollten Warnungen unterdrückt werden?
 Unterdrücken Sie keine Warnung dieser Regel.

## <a name="example"></a>Beispiel
 Das folgende Beispiel zeigt einen abgeleiteten Typ, der die Regel erfüllt wird, indem Sie den Serialisierungskonstruktor aufrufen und <xref:System.Runtime.Serialization.ISerializable.GetObjectData%2A> Methode der Basisklasse.

 [!code-vb[FxCop.Usage.CallBaseISerializable#1](../code-quality/codesnippet/VisualBasic/ca2236-call-base-class-methods-on-iserializable-types_1.vb)]
 [!code-csharp[FxCop.Usage.CallBaseISerializable#1](../code-quality/codesnippet/CSharp/ca2236-call-base-class-methods-on-iserializable-types_1.cs)]

## <a name="related-rules"></a>Verwandte Regeln
 [CA2240: ISerializable ordnungsgemäß implementieren](../code-quality/ca2240-implement-iserializable-correctly.md)

 [CA2229: Serialisierungskonstruktoren implementieren](../code-quality/ca2229-implement-serialization-constructors.md)

 [CA2238: Serialisierungsmethoden korrekt implementieren](../code-quality/ca2238-implement-serialization-methods-correctly.md)

 [CA2235: Alle nicht serialisierbaren Felder markieren](../code-quality/ca2235-mark-all-non-serializable-fields.md)

 [CA2237: Markieren von ISerializable-Typen mit SerializableAttribute](../code-quality/ca2237-mark-iserializable-types-with-serializableattribute.md)

 [CA2239: Deserialisierungsmethoden für optionale Felder angeben](../code-quality/ca2239-provide-deserialization-methods-for-optional-fields.md)

 [CA2120: Sichere Serialisierungskonstruktoren](../code-quality/ca2120-secure-serialization-constructors.md)