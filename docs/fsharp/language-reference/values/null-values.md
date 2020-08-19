---
title: null 値
description: 'F # プログラミング言語での null 値の使用方法について説明します。'
ms.date: 08/15/2020
ms.openlocfilehash: 3b2c7ebe7b8eff08f7c3e76b9715ccab1bbd5d36
ms.sourcegitcommit: 8bfeb5930ca48b2ee6053f16082dcaf24d46d221
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/18/2020
ms.locfileid: "88558349"
---
# <a name="null-values"></a>null 値

このトピックでは、F # での null 値の使用方法について説明します。

## <a name="null-value"></a>［NULL の値］

Null 値は通常、F # で値または変数に使用されるわけではありません。 ただし、null は、特定の状況では異常な値として表示されます。 型が F # で定義されている場合、 [AllowNullLiteral](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-core-allownullliteralattribute.html#Value) 属性が型に適用されない限り、null は通常の値として許可されません。 型が他の .NET 言語で定義されている場合は、null が有効な値であり、そのような型を相互運用するときに、F # コードで null 値が発生する可能性があります。

F # で定義され、f # から厳密に使用される型の場合、F # ライブラリを使用して null 値を直接作成する唯一の方法は、Unchecked を使用することです [。 defaultof](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-core-operators-unchecked.html#defaultof) または [Array. 0 create](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#zeroCreate). ただし、他の .NET 言語から使用される F # 型の場合や、F # で記述されていない API (.NET Framework など) でその型を使用している場合は、null 値が発生する可能性があります。

`option`別の .net 言語で null 値を使用できる参照変数を使用する場合は、F # で型を使用できます。 F # 型の場合、null で `option` はなく、オブジェクトがない場合はオプションの値を使用し `None` ます。 オブジェクトがある場合は、オプションの値を `Some(obj)` オブジェクトと共に使用し `obj` ます。 詳細については、[オプション](../options.md)に関するページを参照してください。 では、である場合に値をオプションにパックすることもでき `null` `Some x` `x` `null` ます。 このため、値がの場合はを使用することが重要です `None` `null` 。

`null`キーワードは F # 言語の有効なキーワードであり、.NET Framework api または別の .net 言語で記述されたその他の api を操作するときに使用する必要があります。 Null 値が必要になる可能性がある2つの状況は、.NET API を呼び出し、引数として null 値を渡す場合と、.NET メソッド呼び出しからの戻り値または出力パラメーターを解釈する場合です。

.NET メソッドに null 値を渡すには、 `null` 呼び出し元のコードでキーワードを使用するだけです。 これを次のコード例に示します。

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet701.fs)]

.NET メソッドから取得した null 値を解釈するには、可能であれば、パターンマッチングを使用します。 次のコード例は、パターン一致を使用し `ReadLine` て、入力ストリームの末尾を越えて読み取ろうとしたときにから返される null 値を解釈する方法を示しています。

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet702.fs)]

F # 型の Null 値は、を呼び出すを使用する場合など、他の方法でも生成でき `Array.zeroCreate` `Unchecked.defaultof` ます。 Null 値をカプセル化するためには、このようなコードに注意する必要があります。 F # 専用のライブラリでは、すべての関数で null 値をチェックする必要はありません。 他の .NET 言語との相互運用のためにライブラリを記述する場合は、C# や Visual Basic コードの場合と同様に、null 入力パラメーターのチェックを追加し、をスローすることが必要になる場合があり `ArgumentNullException` ます。

次のコードを使用すると、任意の値が null かどうかを確認できます。

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet703.fs)]

## <a name="see-also"></a>関連項目

- [値](index.md)
- [match 式](../match-expressions.md)
