---
title: 列挙
description: 'リテラルの代わりに F # の列挙を使用して、コードを読みやすく、保守しやすくする方法について説明します。'
ms.date: 08/15/2020
ms.openlocfilehash: 5f298691ce48a06c203930c7742cf007c819dc33
ms.sourcegitcommit: 9c45035b781caebc63ec8ecf912dc83fb6723b1f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/25/2020
ms.locfileid: "88812108"
---
# <a name="enumerations"></a>列挙

列挙型とも呼ばれる*列挙体**は、値*のサブセットにラベルが割り当てられる整数型です。 リテラルの代わりに使用すると、コードの読み取りおよび保守が容易になります。

## <a name="syntax"></a>構文

```fsharp
type enum-name =
| value1 = integer-literal1
| value2 = integer-literal2
...
```

## <a name="remarks"></a>解説

列挙体は、値を指定できる点を除いて、単純な値を持つ判別共用体とよく似ています。 値は通常、0または1から始まる整数、またはビット位置を表す整数です。 列挙体がビット位置を表すことを目的としている場合は、 [Flags](xref:System.FlagsAttribute) 属性も使用する必要があります。

列挙型の基になる型は、使用されるリテラルから決定されます。したがって、たとえば、、などのサフィックスでリテラルを使用して、 `1u` `2u` 符号なし整数 () 型にすることができ `uint32` ます。

名前付きの値を参照する場合は、列挙型自体の名前を修飾子として使用する必要があり `enum-name.value1` ます。これは、だけではありません `value1` 。 この動作は、判別共用体の動作とは異なります。 これは、列挙体には常に [RequireQualifiedAccess](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-core-requirequalifiedaccessattribute.html) 属性が含まれているためです。

次のコードは、列挙体の宣言と使用方法を示しています。

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet2101.fs)]

次のコードに示すように、適切な演算子を使用して、列挙型を基になる型に簡単に変換できます。

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet2102.fs)]

列挙型は、、、、、、、、、、およびのいずれかの基になる型を持つことができます `sbyte` `byte` `int16` `uint16` `int32` `uint32` `int64` `uint16` `uint64` `char` 。 列挙型は、から継承される型として .NET Framework で表され `System.Enum` ます。これは、から継承され `System.ValueType` ます。 したがって、これらは、スタックに配置されている値型、または親オブジェクトのインラインにある値型であり、基になる型の値は列挙体の有効な値です。 これは、名前のない値をキャッチするパターンを指定する必要があるため、列挙値でパターンマッチングを行う場合に非常に重要です。

`enum`F # ライブラリの関数は、定義済みの名前付きの値の1つ以外の値であっても、列挙値を生成するために使用できます。 関数は次のように使用し `enum` ます。

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet2103.fs)]

既定の `enum` 関数は、型で動作し `int32` ます。 そのため、基になるその他の型を持つ列挙型では使用できません。 代わりに、次のものを使用します。

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet2104.fs)]

さらに、列挙型のケースは常にとして出力され `public` ます。 これは、C# およびその他の .NET プラットフォームと一致するようにするためです。

## <a name="see-also"></a>関連項目

- [F# 言語リファレンス](index.md)
- [キャストと変換](casting-and-conversions.md)
