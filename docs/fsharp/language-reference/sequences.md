---
title: シーケンス
description: '大量の順序付けられたデータのコレクションがあり、必ずしもすべての要素を使用するとは限らない場合に、F # シーケンスを使用する方法について説明します。'
ms.date: 08/13/2020
ms.openlocfilehash: c84e0aebcc79a595c0ae3b9075648fb629bdd65c
ms.sourcegitcommit: 8bfeb5930ca48b2ee6053f16082dcaf24d46d221
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/18/2020
ms.locfileid: "88559038"
---
# <a name="sequences"></a>シーケンス

*シーケンス*は、すべて1つの型からなる論理的な一連の要素です。 シーケンスは、大量の順序付けられたデータのコレクションがあり、すべての要素を使用するとは限らない場合に特に便利です。 個々のシーケンス要素は必要に応じてのみ計算されるので、すべての要素が使用されるわけではありません。 シーケンスは、のエイリアスである型によって表され `seq<'T>` <xref:System.Collections.Generic.IEnumerable%601> ます。 したがって、インターフェイスを実装するすべての .NET 型を <xref:System.Collections.Generic.IEnumerable%601> シーケンスとして使用できます。 [Seq モジュール](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-seqmodule.html)は、シーケンスに関連する操作のサポートを提供します。

## <a name="sequence-expressions"></a>シーケンス式

*シーケンス式*は、シーケンスに評価される式です。 シーケンス式は、さまざまな形式を取ることができます。 最も単純な形式は範囲を指定します。 たとえば、は、 `seq { 1 .. 5 }` エンドポイント1と5を含む5つの要素を含むシーケンスを作成します。 2つの2つの期間の間にインクリメント (またはデクリメント) を指定することもできます。 たとえば、次のコードでは、10の倍数のシーケンスが作成されます。

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1502.fs)]

シーケンス式は、シーケンスの値を生成する F # の式で構成されます。 プログラムで値を生成することもできます。

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1503.fs)]

前のサンプルでは、演算子を使用して `->` います。これにより、値がシーケンスの一部になる式を指定できます。 は、 `->` その後のコードのすべての部分が値を返す場合にのみ使用できます。

または、キーワードを指定し、次のオプションを指定することもでき `do` `yield` ます。

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1504.fs)]

次のコードでは、グリッドを表す配列へのインデックスと共に、座標ペアのリストが生成されます。 最初の式では、を指定する必要があることに注意して `for` `do` ください。

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1505.fs)]

`if`シーケンスで使用される式は、フィルターです。 たとえば、型の関数があると仮定して、素数だけのシーケンスを生成するには、次のように `isprime` `int -> bool` シーケンスを作成します。

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1506.fs)]

前に説明したように、を `do` 使用する分岐がないため、ここではを指定する必要があり `else` `if` ます。 を使用しようとすると `->` 、すべてのブランチが値を返さないというエラーが表示されます。

## <a name="the-yield-keyword"></a>`yield!` キーワード

場合によっては、要素のシーケンスを別のシーケンスに含めることが必要になることがあります。 シーケンスを別のシーケンス内に含めるには、キーワードを使用する必要があり `yield!` ます。

```fsharp
// Repeats '1 2 3 4 5' ten times
seq {
    for _ in 1..10 do
        yield! seq { 1; 2; 3; 4; 5}
}
```

を考えるもう1つの方法は、内部シーケンスを平坦化し、 `yield!` それを含んでいるシーケンスに含めることです。

`yield!`が式で使用されている場合、他のすべての単一の値ではキーワードを使用する必要があり `yield` ます。

```fsharp
// Combine repeated values with their values
seq {
    for x in 1..10 do
        yield x
        yield! seq { for i in 1..x -> i}
}
```

前の例では、ごとに `x` からまでのすべての値に加えて、の値が生成され `1` `x` `x` ます。

## <a name="examples"></a>例

最初の例では、反復処理、フィルター、および yield を含むシーケンス式を使用して、配列を生成します。 このコードは、1から100までの一連の素数をコンソールに出力します。

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1507.fs)]

次の例では、3つの要素の組で構成される乗算テーブルを作成します。各要素は2つの要素と製品で構成されています。

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1508.fs)]

次の例では、を使用して `yield!` 個々のシーケンスを1つの最終シーケンスに結合する方法を示します。 この場合、バイナリツリー内の各サブツリーのシーケンスは、最後のシーケンスを生成するために再帰関数で連結されます。

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1509.fs)]

## <a name="using-sequences"></a>シーケンスの使用

シーケンスは、 [リスト](lists.md)と同じ機能の多くをサポートします。 シーケンスは、キー生成関数を使用したグループ化やカウントなどの操作もサポートします。 シーケンスは、サブシーケンスを抽出するためのさまざまな関数もサポートします。

リスト、配列、セット、マップなどの多くのデータ型は、列挙可能なコレクションであるため、暗黙的にシーケンスされます。 引数としてシーケンスを受け取る関数は、を実装するすべての .NET データ型に加えて、一般的な F # データ型に対して機能し `System.Collections.Generic.IEnumerable<'T>` ます。 リストを引数として受け取る関数と比較します。この関数はリストを受け取ることしかできません。 型は、 `seq<'T>` の型略称です `IEnumerable<'T>` 。 つまり、ジェネリックを実装する任意の型 `System.Collections.Generic.IEnumerable<'T>` (F # の配列、リスト、セット、マップを含む) と、ほとんどの .net コレクション型は、型と互換性があり、 `seq` シーケンスが必要な場合はどこでも使用できます。

## <a name="module-functions"></a>モジュール関数

[Fsharp.core 名前空間](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections.html)の[Seq モジュール](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-seqmodule.html)には、シーケンスを操作するための関数が含まれています。 これらの関数は、リスト、配列、マップ、およびセットとも連動します。これらの型はすべて列挙可能であるため、シーケンスとして扱うことができます。

## <a name="creating-sequences"></a>シーケンスの作成

シーケンス式を使用してシーケンスを作成するには、前に説明したように、または特定の関数を使用します。

空のシーケンスは、 [seq](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-seqmodule.html#empty)を使用して作成できます。また、 [seq. シングルトン](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-seqmodule.html#singleton)を使用して、指定した要素のシーケンスを1つだけ作成することもできます。

[!code-fsharp[Main](~/samples/snippets/fsharp/fssequences/snippet9.fs)]

[Seq.init](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-seqmodule.html#init)を使用して、指定した関数を使用して要素が作成されるシーケンスを作成できます。 シーケンスのサイズも指定します。 この関数は [List.init](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#init)と同じですが、シーケンスを反復処理するまで要素は作成されません。 次のコードは、`Seq.init` の使用例です。

[!code-fsharp[Main](~/samples/snippets/fsharp/fssequences/snippet10.fs)]

出力は次のようになります。

```console
0 10 20 30 40
```

Seq. [ofArray](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-seqmodule.html#ofArray) と [Seq. Ofarray&#60; t&#62; 関数](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-seqmodule.html#ofList)を使用すると、配列とリストからシーケンスを作成できます。 ただし、キャスト演算子を使用して、配列とリストをシーケンスに変換することもできます。 次のコードは、両方の手法を示しています。

[!code-fsharp[Main](~/samples/snippets/fsharp/fssequences/snippet11.fs)]

[Seq. cast](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-seqmodule.html#cast)を使用すると、で定義されているような、弱く型指定されたコレクションからシーケンスを作成できます `System.Collections` 。 このように弱く型指定されたコレクションには要素型があり、 `System.Object` 非ジェネリック型を使用して列挙され `System.Collections.Generic.IEnumerable&#96;1` ます。 次のコードは、を使用してを `Seq.cast` シーケンスに変換する方法を示してい `System.Collections.ArrayList` ます。

[!code-fsharp[Main](~/samples/snippets/fsharp/fssequences/snippet12.fs)]

無限のシーケンスを定義するには、 [Seq.initInfinite](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-seqmodule.html#initInfinite) 関数を使用します。 このようなシーケンスでは、要素のインデックスから各要素を生成する関数を指定します。 無限のシーケンスは、レイジー評価のために可能です。要素は、必要に応じて、指定した関数を呼び出すことによって作成されます。 次のコード例では、浮動小数点数の無限のシーケンスが生成されます。この例では、連続した整数の2乗の reciprocals が連続して作成されています。

[!code-fsharp[Main](~/samples/snippets/fsharp/fssequences/snippet13.fs)]

[Seq](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-seqmodule.html#unfold) は、状態を受け取るコンピュテーション関数からシーケンスを生成し、シーケンス内の後続の各要素を生成するように変換します。 状態は、各要素を計算するために使用される値であり、各要素が計算されるたびに変更できます。 の2番目の引数 `Seq.unfold` は、シーケンスを開始するために使用される初期値です。 `Seq.unfold` 状態にオプションの種類を使用します。これにより、値を返すことによってシーケンスを終了でき `None` ます。 次のコードは、 `seq1` `fib` 操作によって生成されるシーケンス (と) の2つの例を示して `unfold` います。 1つ目のは、 `seq1` 数が20までの単純なシーケンスです。 2番目のは、を `fib` 使用し `unfold` てフィボナッチシーケンスを計算します。 フィボナッチシーケンス内の各要素は前の2つのフィボナッチ数の合計であるため、状態の値は、シーケンス内の前の2つの数値で構成される組になります。 初期値は `(1,1)` 、シーケンスの最初の2つの数値です。

[!code-fsharp[Main](~/samples/snippets/fsharp/fssequences/snippet14.fs)]

出力は次のようになります。

```console
The sequence seq1 contains numbers from 0 to 20.

0 1 2 3 4 5 6 7 8 9 10 11 12 13 14 15 16 17 18 19 20

The sequence fib contains Fibonacci numbers.

2 3 5 8 13 21 34 55 89 144 233 377 610 987 1597
```

次のコードは、ここで説明するシーケンスモジュール関数の多くを使用して無限シーケンスの値を生成および計算する例です。 コードの実行には数分かかる場合があります。

[!code-fsharp[Main](~/samples/snippets/fsharp/fssequences/snippet15.fs)]

## <a name="searching-and-finding-elements"></a>要素の検索と検索

シーケンスは、リストで使用できる機能をサポートし [ています](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-seqmodule.html#exists)。 [list.exists2](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-seqmodule.html#exists)、 [seq、Seq](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-seqmodule.html#find)、seq。 [findindex](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-seqmodule.html#findIndex) [、Seq](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-seqmodule.html#pick). [tryfind](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-seqmodule.html#tryFind)、および [seq. tryfindindex](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-seqmodule.html#tryFindIndex)。 シーケンスで使用できるこれらの関数のバージョンによって、シーケンスは検索対象の要素までのみ評価されます。 例については、「 [リスト](lists.md)」を参照してください。

## <a name="obtaining-subsequences"></a>サブシーケンスの取得

[Seq. filter](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-seqmodule.html#filter) と [seq. choose](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-seqmodule.html#choose) は、リストで使用できる対応する関数と似ています。ただし、フィルター処理と選択は、シーケンス要素が評価されるまで発生しません。

[Seq. truncate](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-seqmodule.html#truncate) は、別のシーケンスからシーケンスを作成しますが、シーケンスは指定した数の要素に制限されます。 [Seq. take](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-seqmodule.html#take) は、シーケンスの先頭から指定された数の要素のみを含む新しいシーケンスを作成します。 指定した数よりも多い要素がシーケンス内にある場合、はを `Seq.take` スロー `System.InvalidOperationException` します。 との違いは、 `Seq.take` `Seq.truncate` `Seq.truncate` 要素の数が指定した数よりも小さい場合、はエラーを生成しないという点です。

次のコードは、との動作との違いを示して `Seq.truncate` `Seq.take` います。

[!code-fsharp[Main](~/samples/snippets/fsharp/fssequences/snippet16.fs)]

エラーが発生する前の出力は次のとおりです。

```console
1 4 9 16 25
1 4 9 16 25 36 49 64 81 100
1 4 9 16 25
1 4 9 16 25 36 49 64 81 100
```

[Seq](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-seqmodule.html#takeWhile)を使用することにより、述語関数 (ブール関数) を指定し、述語が返される元のシーケンスの要素で構成される別のシーケンスからシーケンスを作成でき `true` ます。ただし、述語が返す最初の要素の前には停止し `false` ます。 [Seq. skip](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-seqmodule.html#skip) は、指定された数の別のシーケンスの最初の要素をスキップし、残りの要素を返すシーケンスを返します。 [Seq. skipWhile](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-seqmodule.html#skipWhile) は、述語が返された場合に別のシーケンスの最初の要素をスキップし、残りの要素を返すシーケンスを返します。このシーケンスは、 `true` 述語が返す最初の要素から始まり `false` ます。

次のコード例は、の動作と、、、およびの違いを示してい `Seq.takeWhile` `Seq.skip` `Seq.skipWhile` ます。

[!code-fsharp[Main](~/samples/snippets/fsharp/fssequences/snippet17.fs)]

出力は次のとおりです。

```console
1 4 9
36 49 64 81 100
16 25 36 49 64 81 100
```

## <a name="transforming-sequences"></a>シーケンスの変換

[Seq (ペア](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-seqmodule.html#pairwise) ) は、入力シーケンスの連続する要素を組にグループ化する新しいシーケンスを作成します。

[!code-fsharp[Main](~/samples/snippets/fsharp/fssequences/snippet18.fs)]

[Seq. ウィンドウ](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-seqmodule.html#windowed) は似ていますが `Seq.pairwise` 、組のシーケンスを生成するのではなく、シーケンスから隣接する要素 ( *ウィンドウ*) のコピーを格納する配列のシーケンスを生成します。 各配列で隣接する要素の数を指定します。

次のコード例は、`Seq.windowed` の使用方法を示します。 この場合、ウィンドウ内の要素の数は3です。 この例では `printSeq` 、前のコード例で定義されているを使用します。

[!code-fsharp[Main](~/samples/snippets/fsharp/fssequences/snippet180.fs)]

出力は次のとおりです。

初期シーケンス:

```console
1.0 1.5 2.0 1.5 1.0 1.5

Windows of length 3:
[|1.0; 1.5; 2.0|] [|1.5; 2.0; 1.5|] [|2.0; 1.5; 1.0|] [|1.5; 1.0; 1.5|]

Moving average:
1.5 1.666666667 1.5 1.333333333
```

## <a name="operations-with-multiple-sequences"></a>複数のシーケンスを持つ操作

[Seq.zip](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-seqmodule.html#zip) と [Seq.zip3](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-seqmodule.html#zip3) は、2つまたは3つのシーケンスを受け取り、組のシーケンスを生成します。 これらの関数は、 [リスト](lists.md)で使用できる対応する関数に似ています。 1つのシーケンスを2つ以上のシーケンスに分割する対応する機能はありません。 シーケンスにこの機能が必要な場合は、シーケンスをリストに変換し、 [unzip](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#unzip)を使用します。

## <a name="sorting-comparing-and-grouping"></a>並べ替え、比較、およびグループ化

リストでサポートされている並べ替え関数は、シーケンスでも使用できます。 これに [は、](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-seqmodule.html#sort) SortBy および [seq](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-seqmodule.html#sortBy)が含まれます。 これらの関数は、シーケンス全体を反復処理します。

2つのシーケンスを比較するには、 [Seq. compareWith](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-seqmodule.html#compareWith) 関数を使用します。 関数は、連続する要素を順番に比較し、最初の等しくないペアが検出されたときに停止します。 その他の要素は、比較には関与しません。

`Seq.compareWith` の使用方法を次のコードに示します。

[!code-fsharp[Main](~/samples/snippets/fsharp/fssequences/snippet19.fs)]

前のコードでは、最初の要素のみが計算され、検査され、結果は-1 になります。

[CountBy](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-seqmodule.html#countBy) は、各要素の *キー* と呼ばれる値を生成する関数を受け取ります。 各要素に対してこの関数を呼び出すことにより、各要素に対してキーが生成されます。 `Seq.countBy` 次に、キー値を含むシーケンスと、キーの各値を生成した要素の数を返します。

[!code-fsharp[Main](~/samples/snippets/fsharp/fssequences/snippet201.fs)]

出力は次のとおりです。

```console
(1, 34) (2, 33) (0, 33)
```

前の出力は、キー1、キー2を生成した33値、およびキー0を生成した33値を生成した、元のシーケンスの34要素があることを示しています。

シーケンスの要素をグループ化するには、 [Seq. groupBy](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-seqmodule.html#groupBy)を呼び出します。 `Seq.groupBy` は、シーケンスと、要素からキーを生成する関数を受け取ります。 関数は、シーケンスの各要素に対して実行されます。 `Seq.groupBy` 組のシーケンスを返します。各組の最初の要素はキーで、2番目の要素はそのキーを生成する要素のシーケンスです。

次のコード例では、を使用して、 `Seq.groupBy` 0、1、および2の個別のキー値を持つ3つのグループに、1 ~ 100 の一連の数値を分割しています。

[!code-fsharp[Main](~/samples/snippets/fsharp/fssequences/snippet202.fs)]

出力は次のとおりです。

```console
(1, seq [1; 4; 7; 10; ...]) (2, seq [2; 5; 8; 11; ...]) (0, seq [3; 6; 9; 12; ...])
```

[Seq](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-seqmodule.html#distinct)を呼び出すことで、重複する要素を排除するシーケンスを作成できます。 または、 [seq.distinctby](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-seqmodule.html#distinctBy)を使用することもできます。この場合、各要素に対して呼び出されるキー生成関数を受け取ります。 結果のシーケンスには、一意のキーを持つ元のシーケンスの要素が含まれます。それより前の要素に対して重複するキーを生成する要素は破棄されます。

`Seq.distinct` の使用方法を次のコード例に示します。 `Seq.distinct` は、バイナリ数値を表すシーケンスを生成して、個別の要素だけが0と1であることを示すことによって示されます。

[!code-fsharp[Main](~/samples/snippets/fsharp/fssequences/snippet22.fs)]

次のコードは、 `Seq.distinctBy` 負の数値と正の数値を格納し、キー生成関数として絶対値関数を使用するシーケンスを使用してを開始することで、を示しています。 結果のシーケンスには、シーケンス内の負の数値に対応する正の数値がすべて不足しています。負の数値はシーケンスの前に表示されるため、同じ絶対値またはキーを持つ正の数値の代わりに選択されるためです。

[!code-fsharp[Main](~/samples/snippets/fsharp/fssequences/snippet23.fs)]

## <a name="readonly-and-cached-sequences"></a>読み取り専用とキャッシュされたシーケンス

[Seq. readonly](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-seqmodule.html#readonly) は、シーケンスの読み取り専用コピーを作成します。 `Seq.readonly` は、配列などの読み取り/書き込みコレクションがあり、元のコレクションを変更しない場合に便利です。 この関数は、データのカプセル化を維持するために使用できます。 次のコード例では、配列を含む型が作成されます。 プロパティは配列を公開しますが、配列を返すのではなく、を使用して配列から作成されたシーケンスを返し `Seq.readonly` ます。

[!code-fsharp[Main](~/samples/snippets/fsharp/fssequences/snippet24.fs)]

[Seq. cache](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-seqmodule.html#cache) は、シーケンスの格納されているバージョンを作成します。 `Seq.cache`シーケンスの再評価を避けるため、またはシーケンスを使用する複数のスレッドがある場合は、を使用して、各要素が1回だけ動作するようにする必要があります。 複数のスレッドで使用されているシーケンスがある場合は、元のシーケンスの値を列挙して計算するスレッドを1つ持つことができ、残りのスレッドはキャッシュされたシーケンスを使用できます。

## <a name="performing-computations-on-sequences"></a>シーケンスに対する計算の実行

単純な算術演算は、 [seq. average](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-seqmodule.html#average)、seq. [sum](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-seqmodule.html#sum)、seq. [AverageBy](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-seqmodule.html#averageBy)、 [seq. sumby](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-seqmodule.html#sumBy)などのリストのようなものです。

[Seq](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-seqmodule.html#fold)、 [Seq](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-seqmodule.html#reduce)、および [seq. scan](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-seqmodule.html#scan) は、リストで使用できる対応する関数に似ています。 シーケンスは、サポートを一覧表示するこれらの関数の全バリエーションのサブセットをサポートします。 詳細と例については、「 [リスト](lists.md)」を参照してください。

## <a name="see-also"></a>関連項目

- [F# 言語リファレンス](index.md)
- [F# の型](fsharp-types.md)
