---
title: Options
description: '名前付きの値または変数に実際の値が存在しない可能性がある場合に F # のオプションの型を使用する方法について説明します。'
ms.date: 08/13/2020
ms.openlocfilehash: 0618590c10f6ecac51a23483ca0ab6cd66f2df4f
ms.sourcegitcommit: 8bfeb5930ca48b2ee6053f16082dcaf24d46d221
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/18/2020
ms.locfileid: "88557569"
---
# <a name="options"></a>Options

F # のオプションの種類は、名前付きの値または変数に実際の値が存在しない可能性がある場合に使用されます。 オプションには基になる型があり、その型の値を保持できるか、値がない可能性があります。

## <a name="remarks"></a>注釈

次のコードは、オプションの型を生成する関数を示しています。

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1404.fs)]

ご覧のように、入力 `a` が0より大きい場合 `Some(a)` はが生成されます。  それ以外の場合 `None` は、が生成されます。

値 `None` は、オプションに実際の値がない場合に使用されます。 それ以外の場合、この式は `Some( ... )` オプションに値を与えます。 値 `Some` とは、次の関数のように、 `None` パターンマッチングに役立ち `exists` `true` ます。この関数は、オプションに値がある場合はを返し、そうでない場合はを返し `false` ます。

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1401.fs)]

## <a name="using-options"></a>オプションを使用する

オプションは、次のコードに示すように、検索で一致する結果が返されない場合によく使用されます。

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1403.fs)]

前のコードでは、リストは再帰的に検索されます。 関数は、 `tryFindMatch` `pred` ブール値と検索するリストを返す述語関数を受け取ります。 述語を満たす要素が見つかった場合、再帰は終了し、関数は式のオプションとして値を返し `Some(head)` ます。 空のリストが一致すると、再帰は終了します。 その時点では、値が見つからなかったため、 `head` `None` が返されます。

コレクション内で存在する可能性がある値または存在しない可能性がある値を検索する多くの F # ライブラリ関数は、型を返し `option` ます。 慣例により、これらの関数は、など `try` のプレフィックスで始まり [`Seq.tryFindIndex`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-seqmodule.html#tryFindIndex) ます。

オプションは、値が存在しない場合にも役立ちます。たとえば、値を構築しようとしたときに例外がスローされる可能性がある場合などです。 これを次のコード例に示します。

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1402.fs)]

前の例の関数は、 `openFile` ファイルが正常に開かれた場合にオブジェクトを返し、例外が発生した場合には `string -> File option` オブジェクトを返すため、型があり `File` `None` ます。 状況によっては、伝達を許可するのではなく、例外をキャッチするための適切な設計選択ではない場合があります。

`null`また、オプションの場合は、または null の値を渡すこともでき `Some` ます。 通常、これは回避され、通常はルーチン F # プログラミングで使用されますが、.NET の参照型の性質によって可能です。

## <a name="option-properties-and-methods"></a>オプションのプロパティとメソッド

オプションの種類は、次のプロパティとメソッドをサポートしています。

|プロパティまたはメソッド|Type|説明|
|------------------|----|-----------|
|[なし](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-core-fsharpoption-1.html#None)|`'T option`|値を持つオプション値を作成できるようにする静的プロパティ `None` 。|
|[IsNone](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-core-fsharpoption-1.html#IsNone)|`bool`|`true`オプションに値がある場合は、を返し `None` ます。|
|[IsSome](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-core-fsharpoption-1.html#IsSome)|`bool`|オプションに以外の値がある場合は、を返し `true` `None` ます。|
|[一部](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-core-fsharpoption-1.html#Some)|`'T option`|値がではないオプションを作成する静的メンバー `None` 。|
|[Value](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-core-fsharpoption-1.html#Value)|`'T`|基になる値を返すか、値がの場合はをスローし `System.NullReferenceException` `None` ます。|

## <a name="option-module"></a>オプションモジュール

[オプションに](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-core-optionmodule.html)対して操作を実行する便利な関数を含むモジュールがあります。 一部の関数はプロパティの機能を繰り返しますが、関数が必要なコンテキストで役に立ちます。 [IsNone](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-core-optionmodule.html#isNone)は、オプションが値を保持しているかどうかをテストするモジュール関数でもあり[ます](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-core-optionmodule.html#isSome)。 [オプション。 get](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-core-optionmodule.html#get) は値を取得します (存在する場合)。 値がない場合は、をスロー `System.ArgumentException` します。

値がある場合、 [bind](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-core-optionmodule.html#bind) 関数は値に対して関数を実行します。 関数は、引数を1つだけ受け取る必要があります。また、パラメーターの型は、オプションの型である必要があります。 関数の戻り値は、もう1つのオプションの種類です。

オプションモジュールには、リスト、配列、シーケンス、およびその他のコレクション型で使用できる関数に対応する関数も含まれています。 これらの関数には、、、、、、 [`Option.map`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-core-optionmodule.html#map) [`Option.iter`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-core-optionmodule.html#iter) 、およびがあり [`Option.forall`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-core-optionmodule.html#forall) [`Option.exists`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-core-optionmodule.html#exists) [`Option.foldBack`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-core-optionmodule.html#foldBack) [`Option.fold`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-core-optionmodule.html#fold) [`Option.count`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-core-optionmodule.html#count) ます。 これらの関数は、0個または1個の要素のコレクションのようにオプションを使用できます。 詳細と例については、コレクション関数の [一覧](lists.md)での説明を参照してください。

## <a name="converting-to-other-types"></a>他の型への変換

オプションは、リストまたは配列に変換できます。 オプションがこれらのデータ構造体のいずれかに変換されると、結果のデータ構造体には0個または1個の要素が含まれます。 オプションを配列に変換するには、を使用し [`Option.toArray`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-core-optionmodule.html#toArray) ます。 オプションを一覧に変換するには、を使用し [`Option.toList`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-core-optionmodule.html#toList) ます。

## <a name="see-also"></a>関連項目

- [F# 言語リファレンス](index.md)
- [F# の型](fsharp-types.md)
