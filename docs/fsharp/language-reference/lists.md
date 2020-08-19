---
title: リスト
description: 'F # のリストについて説明します。同じ型の順序付けられ、変更できない一連の要素です。'
ms.date: 08/13/2020
ms.openlocfilehash: 16d7195039d25cf63630f5cc3be6563b1bf45c44
ms.sourcegitcommit: 8bfeb5930ca48b2ee6053f16082dcaf24d46d221
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/18/2020
ms.locfileid: "88559168"
---
# <a name="lists"></a>リスト

F# のリストは、順序が指定されており変更できない一連の同じ型の要素です。 リストに対して基本的な操作を実行するには、 [List モジュール](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html)の関数を使用します。

## <a name="creating-and-initializing-lists"></a>リストの作成と初期化

リストを定義するには、次のコード行に示すように、セミコロンで区切って明示的にリストした要素を角かっこで囲みます。

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1301.fs)]

要素間に改行を挿入することもできます。その場合はセミコロンの区切り記号を省略できます。 要素の初期化式が長い場合、各要素にコメントを含める場合は、改行の構文を使用するとコードが読みやすくなります。

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet13011.fs)]

通常、リストの要素はすべて同じ型である必要があります。 例外として、要素が基本型として指定されているリストには、派生型の要素を含めることができます。 したがって次に示す例は、`Button` と `CheckBox` の両方が `Control` から派生しているため、受け入れられます。

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet13012.fs)]

また、次のコードで示すように、整数を範囲演算子 (`..`) で区切って示した範囲を使用して、リストの要素を定義することもできます。

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1302.fs)]

空のリストは、間に何も含まない 1 組の角かっこで示します。

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1304.fs)]

シーケンス式を使用してリストを作成することもできます。 詳細については、「 [シーケンス式](sequences.md#sequence-expressions) 」を参照してください。 たとえば、次のコードでは 1 から 10 までの整数の 2 乗のリストが作成されます。

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1303.fs)]

## <a name="operators-for-working-with-lists"></a>リストの操作に使用する演算子

リストに要素を付加するには、`::` (cons) 演算子を使用します。 `list1` が `[2; 3; 4]` の場合、次のコードでは `list2` が `[100; 2; 3; 4]` として作成されます。

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1305.fs)]

互換性のある型を含むリストを連結するには、次のコードに示すように `@` 演算子を使用します。 `list1` が `[2; 3; 4]` であり、`list2` が `[100; 2; 3; 4]` の場合、このコードでは `list3` が `[2; 3; 4; 100; 2; 3; 4]` として作成されます。

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1306.fs)]

リストに対する操作を実行する関数は、 [List モジュール](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html)で使用できます。

F# のリストは変更できないため、変更操作を行うと、既存のリストが変更されるのではなく、新しいリストが生成されます。

F # のリストは、シングルリンクリストとして実装されます。これは、リストの先頭にのみアクセスする操作が O (1) であり、要素アクセスが O (*n*) であることを意味します。

## <a name="properties"></a>プロパティ

リスト型では次のプロパティがサポートされています。

|プロパティ|Type|説明|
|--------|----|-----------|
|[矢印](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-list-1.html#Head)|`'T`|1 番目の要素。|
|[空](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-list-1.html#Empty)|`'T list`|該当する型の空のリストを返す静的プロパティ。|
|[IsEmpty](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-list-1.html#IsEmpty)|`bool`|リストに要素がない場合は `true` です。|
|[Item](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-list-1.html#Item)|`'T`|指定したインデックスの要素 (起点を 0 とする)。|
|[[データ型]](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-list-1.html#Length)|`int`|要素の数。|
|[Tail](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-list-1.html#Tail)|`'T list`|1 番目の要素を除いたリスト。|

これらのプロパティを使用したいくつかの例を次に示します。

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1307.fs)]

## <a name="using-lists"></a>リストの使用

 リストを使用してプログラミングを行うと、少量のコードで複雑な操作を実行できます。 このセクションでは、関数型プログラミングにおいて重要なリストに対する一般的な操作について説明します。

### <a name="recursion-with-lists"></a>リストを使用した再帰

リストは、再帰的なプログラミング技法に非常に適しています。 リストのすべての要素に対して実行する必要がある操作があるとします。 この操作を再帰的に実行するには、リストの先頭に対して処理を行った後にリストの後部 (元のリストの最初の要素を除いた要素で構成される、元のリストより小さいリスト) を次の再帰レベルに戻します。

このような再帰関数を記述するには、パターン マッチで cons 演算子 (`::`) を使用します。これによって、リストの先頭を末尾から分離できます。

パターン マッチを使用して、リストに対する操作を実行する再帰関数を実装する方法を次のコード例に示します。

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet13071.fs)]

このコードは小さいリストでは問題なく動作しますが、リストが大きくなると、スタックがオーバーフローする可能性があります。 次に示すコードは、再帰関数の処理では標準的な技法であるアキュムレータ引数を使用して、このコードを改善したものです。 アキュムレータ引数を使用すると、関数の後部が再帰的になり、スタック領域を節約できます。

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet13072.fs)]

関数 `RemoveAllMultiples` は、2 つのリストを受け取る再帰関数です。 1 番目のリストは、倍数を削除する数値が格納されたリストで、2 番目のリストは、数値を削除する元のリストです。 次の例のコードでは、この再帰関数を使用してリストから素数以外をすべて削除します。その結果、素数のリストが残ります。

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1308.fs)]

出力は次のようになります。

```console
Primes Up To 100:
[2; 3; 5; 7; 11; 13; 17; 19; 23; 29; 31; 37; 41; 43; 47; 53; 59; 61; 67; 71; 73; 79; 83; 89; 97]
```

## <a name="module-functions"></a>モジュール関数

[List モジュール](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html)には、リストの要素にアクセスする関数が用意されています。 先頭の要素には、最も迅速かつ簡単にアクセスできます。 プロパティ [head](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-list-1.html#Head) またはモジュール関数リストを使用します [。 head](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#head). [Tail プロパティまた](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-list-1.html#Tail)は[tail 関数を](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#tail)使用して、リストの末尾にアクセスできます。 インデックスによって要素を検索するには、 [List. n](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#nth) 関数を使用します。 `List.nth` はリストを走査します。 そのため、O (*n*) です。 コードで `List.nth` を頻繁に使用する場合は、リストの代わりに配列を使用すると、効果的である可能性があります。 配列での要素のアクセスは O(1) です。

### <a name="boolean-operations-on-lists"></a>リストに対するブール演算

[IsEmpty](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#isEmpty)関数は、リストに要素があるかどうかを判断します。

[List. exists](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#exists)関数は、ブール値のテストをリストの要素に適用し、 `true` いずれかの要素がテストに適合する場合はを返します。 [List.exists2](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#exists2) は似ていますが、2つのリストの要素の連続するペアで動作します。

`List.exists` を使用したコードの例を次に示します。

[!code-fsharp[Main](~/samples/snippets/fsharp/lists/snippet1.fs)]

出力は次のようになります。

```console
For list [0; 1; 2; 3], contains zero is true
```

次の例は、`List.exists2` の使い方を示しています。

[!code-fsharp[Main](~/samples/snippets/fsharp/lists/snippet2.fs)]

出力は次のようになります。

```console
Lists [1; 2; 3; 4; 5] and [5; 4; 3; 2; 1] have at least one equal element at the same position.
```

リストのすべての要素が条件を満たしているかどうかをテストする場合は、forall を使用できます[。](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#forall)

[!code-fsharp[Main](~/samples/snippets/fsharp/lists/snippet3.fs)]

出力は次のようになります。

```console
true
false
```

同様に、 [array.forall2](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#forall2) は、2つのリスト内の対応する位置にあるすべての要素が、要素の各ペアに関係するブール式を満たすかどうかを判断します。

[!code-fsharp[Main](~/samples/snippets/fsharp/lists/snippet4.fs)]

出力は次のようになります。

```console
true
false
```

### <a name="sort-operations-on-lists"></a>リストに対する並べ替え操作

[リスト並べ替え](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#sort)、 [sortBy](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#sortBy)、および関数を使用し[た sortwith](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#sortWith)リスト。 並べ替え関数は、これら 3 つの関数のどれを使用するかを判断します。 `List.sort` は、既定の一般的な比較を使用します。 一般的な比較は、汎用の比較関数に基づくグローバル演算子を使用して、値を比較します。 この比較は、単純な数値型、タプル、レコード、判別共用体、リスト、配列、および `System.IComparable` を実装する任意の型など、広範な要素型で効率的に動作します。 `System.IComparable` を実装する型の場合は、汎用的な比較で `System.IComparable.CompareTo()` 関数が使用されます。 また、汎用的な比較は文字列にも使用できますが、カルチャに依存しない並べ替え順序が使用されます。 関数型のようなサポートされない型には、汎用的な比較を使用できません。 また、既定の汎用的な比較は、小さい構造の型の場合に最高のパフォーマンスを示します。比較と並べ替えが頻繁に必要な大きい構造の型の場合は、`System.IComparable` を実装し、`System.IComparable.CompareTo()` メソッドを効率的に実装することを考慮してください。

`List.sortBy` 関数は、並べ替え基準として使用される値を返す関数を受け取り、`List.sortWith` 関数は、比較関数を引数として受け取ります。 これら 2 つの関数は、比較をサポートしない型を使用するとき、またはカルチャを認識する文字列の場合のように複雑な比較セマンティクスを必要とする比較の場合に役立ちます。

次の例は、`List.sort` の使い方を示しています。

[!code-fsharp[Main](~/samples/snippets/fsharp/lists/snippet5.fs)]

出力は次のようになります。

```console
[-2; 1; 4; 5; 8]
```

次の例は、`List.sortBy` の使い方を示しています。

[!code-fsharp[Main](~/samples/snippets/fsharp/lists/snippet6.fs)]

出力は次のようになります。

```console
[1; -2; 4; 5; 8]
```

次の例は、`List.sortWith` の使い方を示しています。 この例では、カスタムの比較関数 `compareWidgets` を使用して、まず、カスタム型の 1 つのフィールドを比較し、最初のフィールドの値が同じである場合は、さらに別のフィールドを比較しています。

[!code-fsharp[Main](~/samples/snippets/fsharp/lists/snippet7.fs)]

出力は次のようになります。

```console
[{ID = 92;
Rev = 1;}; {ID = 92;
Rev = 1;}; {ID = 100;
Rev = 2;}; {ID = 100;
Rev = 5;}; {ID = 110;
Rev = 1;}]
```

### <a name="search-operations-on-lists"></a>リストに対する検索操作

リストに対するさまざまな検索操作がサポートされています。 最も単純な [リストです。 find](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#find)を使用すると、特定の条件に一致する最初の要素を検索できます。

次のコード例では、`List.find` を使用して、5 で割り切れる最初の数をリストから検索する方法を示します。

[!code-fsharp[Main](~/samples/snippets/fsharp/lists/snippet8.fs)]

The result is 5.

最初に要素を変換する必要がある場合は、 [List. pick](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#pick)を呼び出します。この関数は、オプションを返す関数を受け取り、である最初のオプション値を検索し `Some(x)` ます。 `List.pick` は要素を返す代わりに、結果 `x` を返します。 一致する要素が見つからない場合、`List.pick` は `System.Collections.Generic.KeyNotFoundException` をスローします。 `List.pick` の使用方法を次のコードに示します。

[!code-fsharp[Main](~/samples/snippets/fsharp/lists/snippet9.fs)]

出力は次のようになります。

```console
"b"
```

別の検索操作のグループである [tryFind](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#tryFind) と関連する関数は、オプション値を返します。 `List.tryFind` 関数は、条件を満たす要素がリストにある場合は、その最初の要素を返します。条件を満たす要素がない場合は、オプション値 `None` を返します。 バリエーション [リスト. tryFindIndex](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#tryFindIndex) は、要素自体ではなく、要素が見つかった場合はそのインデックスを返します。 これらの関数を次のコードに示します。

[!code-fsharp[Main](~/samples/snippets/fsharp/lists/snippet10.fs)]

出力は次のようになります。

```console
The first even value is 22.
The first even value is at position 8.
```

### <a name="arithmetic-operations-on-lists"></a>リストに対する算術演算

Sum や average などの一般的な算術演算は、 [List モジュール](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html)に組み込まれています。 [List. sum](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#sum)を使用するには、リスト要素の型が演算子をサポートし、値が0である必要があり `+` ます。 すべての組み込み数値型はこの条件を満たしています。 [List. average](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#average)を使用するには、要素型が剰余のない除算をサポートしている必要があります。これには整数型は含まれませんが、浮動小数点型は許可されます。 AverageBy[関数および](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#sumBy)[リスト](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#averageBy)関数は、パラメーターとして関数を受け取ります。この関数の結果は、合計または平均の値を計算するために使用されます。

次のコードは、`List.sum`、 `List.sumBy`、および `List.average` の使用方法を示しています。

[!code-fsharp[Main](~/samples/snippets/fsharp/lists/snippet11.fs)]

出力は `1.000000`になります。

`List.averageBy` の使用方法を次のコードに示します。

[!code-fsharp[Main](~/samples/snippets/fsharp/lists/snippet12.fs)]

出力は `5.5`になります。

### <a name="lists-and-tuples"></a>リストとタプル

タプルを含むリストは、zip 関数および unzip 関数で操作できます。 これらの関数は、単一値の 2 つのリストを結合してタプルのリストを 1 つ生成したり、タプルの 1 つのリストを分割して単一の値のリストを 2 つ生成したりします。 最も単純な [List.zip](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#zip) 関数は、1つの要素の2つのリストを受け取り、組のペアのリストを1つ生成します。 別のバージョン ( [List.zip3](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#zip3)) は、1つの要素の3つのリストを受け取り、3つの要素を持つ組のリストを1つ生成します。 次のコード例は、`List.zip` の使用方法を示します。

[!code-fsharp[Main](~/samples/snippets/fsharp/lists/snippet13.fs)]

出力は次のようになります。

```console
[(1, -1); (2, -2); (3; -3)]
```

次のコード例は、`List.zip3` の使用方法を示します。

[!code-fsharp[Main](~/samples/snippets/fsharp/lists/snippet14.fs)]

出力は次のようになります。

```console
[(1, -1, 0); (2, -2, 0); (3, -3, 0)]
```

対応する unzip のバージョン、array.unzip3、および[リスト](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#unzip3)は、組内の組と戻り値[のリストを](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#unzip)取得します。最初のリストには各組の最初の要素が含まれ、2番目のリストには各組の2番目の要素が含まれます。

次のコード例は、 [unzip](https://msdn.microsoft.com/library/639db80c-41b5-45bb-a6b4-1eaa04d61d21)の使用方法を示しています。

[!code-fsharp[Main](~/samples/snippets/fsharp/lists/snippet15.fs)]

出力は次のようになります。

```console
([1; 3], [2; 4])
[1; 3] [2; 4]
```

次のコード例は、 [array.unzip3](https://msdn.microsoft.com/library/43078c77-32ec-4342-85b3-c31ccf984db4)の使用方法を示しています。

[!code-fsharp[Main](~/samples/snippets/fsharp/lists/snippet16.fs)]

出力は次のようになります。

```console
([1; 4], [2; 5], [3; 6])
```

### <a name="operating-on-list-elements"></a>リスト要素に対する操作

F# は、リストの要素に対するさまざまな操作をサポートしています。 最も単純なのは [iter](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#iter)です。これを使用すると、リストのすべての要素に対して関数を呼び出すことができます。 バリエーションには [array.iter2](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#iter2)が含まれてい [ます。これ](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#iteri)により、 `List.iter` 各要素のインデックスは、各要素に対して呼び出される関数に引数として渡され、 [array.iteri2](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#iteri2)はとの機能を組み合わせたものであることを除いて、2つのリストの要素に対して操作を実行でき `List.iter2` `List.iteri` ます。 次のコード例にこれらの関数を示します。

[!code-fsharp[Main](~/samples/snippets/fsharp/lists/snippet17.fs)]

出力は次のようになります。

```console
List.iter: element is 1
List.iter: element is 2
List.iter: element is 3
List.iteri: element 0 is 1
List.iteri: element 1 is 2
List.iteri: element 2 is 3
List.iter2: elements are 1 4
List.iter2: elements are 2 5
List.iter2: elements are 3 6
List.iteri2: element 0 of list1 is 1; element 0 of list2 is 4
List.iteri2: element 1 of list1 is 2; element 1 of list2 is 5
List.iteri2: element 2 of list1 is 3; element 2 of list2 is 6
```

リスト要素を変換する、よく使用されるもう1つの関数は、list [. map です。](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#map)これにより、リストの各要素に関数を適用し、すべての結果を新しいリストに入れることができます。 [List.map2](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#map2) と [list.map3](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#map3) は、複数のリストを受け取るバリエーションです。 また、 [array.mapi2 とリスト](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#mapi2)を使用することもできます。この場合、要素に[加えて、](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#mapi)関数は各要素のインデックスを渡す必要があります。 `List.mapi2` と `List.mapi` の唯一の違いは、`List.mapi2` では 2 つのリストが使用される点です。 次の例は、 [List. map](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#map)を示しています。

[!code-fsharp[Main](~/samples/snippets/fsharp/lists/snippet18.fs)]

出力は次のようになります。

```console
[2; 3; 4]
```

次の例は、`List.map2` の使用方法を示しています。

[!code-fsharp[Main](~/samples/snippets/fsharp/lists/snippet19.fs)]

出力は次のようになります。

```console
[5; 7; 9]
```

次の例は、`List.map3` の使用方法を示しています。

[!code-fsharp[Main](~/samples/snippets/fsharp/lists/snippet20.fs)]

出力は次のようになります。

```console
[7; 10; 13]
```

次の例は、`List.mapi` の使用方法を示しています。

[!code-fsharp[Main](~/samples/snippets/fsharp/lists/snippet21.fs)]

出力は次のようになります。

```console
[1; 3; 5]
```

次の例は、`List.mapi2` の使用方法を示しています。

[!code-fsharp[Main](~/samples/snippets/fsharp/lists/snippet22.fs)]

出力は次のようになります。

```console
[0; 7; 18]
```

[List. collect](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#collect) はと似ていますが `List.map` 、各要素によってリストが生成され、これらのすべてのリストが最終的な一覧に連結される点が異なります。 次のコードでは、リストの各要素が 3 つの値を生成します。 これらすべてが 1 つのリストに集約されます。

[!code-fsharp[Main](~/samples/snippets/fsharp/lists/snippet23.fs)]

出力は次のようになります。

```console
[1; 2; 3; 2; 4; 6; 3; 6; 9]
```

また、 [list. filter](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#filter)を使用することもできます。これはブール条件を受け取り、指定された条件を満たす要素だけで構成される新しいリストを生成します。

[!code-fsharp[Main](~/samples/snippets/fsharp/lists/snippet24.fs)]

結果のリストは `[2; 4; 6]` です。

[マップ] と [フィルター] の組み合わせで、[ [選択]](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#choose) を使用すると、複数の要素を同時に変換および選択できます。 `List.choose` は、オプションを返す関数をリストの各要素に適用し、関数がオプション値 `Some` を返す要素の結果から成る新しいリストを返します。

次のコードでは、`List.choose` を使用して、最初の文字が大文字の単語を単語のリストから選択しています。

[!code-fsharp[Main](~/samples/snippets/fsharp/lists/snippet25.fs)]

出力は次のようになります。

```console
["Rome's"; "Bob's"]
```

### <a name="operating-on-multiple-lists"></a>複数のリストに対する操作

複数のリストを結合できます。 2つのリストを1つに結合するには、 [List. append](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#append)を使用します。 3つ以上のリストを結合するには、 [concat](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#concat)を使用します。

[!code-fsharp[Main](~/samples/snippets/fsharp/lists/snippet26.fs)]

### <a name="fold-and-scan-operations"></a>フォールド操作とスキャン操作

リストの操作の中には、リストのすべての要素間の依存関係を伴うものがあります。 フォールド操作とスキャン操作は `List.iter` 、 `List.map` 各要素に対して関数を呼び出すのと似ていますが、これらの操作には、計算を通じて情報を伝達する *アキュムレータ* と呼ばれる追加のパラメーターが用意されています。

リストに対して計算を実行するには、`List.fold` を使用します。

次のコード例では、 [リスト](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#fold) を使用してさまざまな操作を実行する方法を示します。

 リストが走査されます。アキュムレータ `acc`は、計算の進行に伴って渡される値です。 1 番目の引数はアキュムレータとリスト要素を受け取り、そのリスト要素に対する計算の中間結果を返します。 2 番目の引数はアキュムレータの初期値です。

[!code-fsharp[Main](~/samples/snippets/fsharp/lists/snippet27.fs)]

関数名に数字が付いている関数は、複数のリストを操作するバージョンです。 たとえば、 [list.fold2](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#fold2) は2つのリストに対して計算を実行します。

次の例は、`List.fold2` の使い方を示しています。

[!code-fsharp[Main](~/samples/snippets/fsharp/lists/snippet28.fs)]

`List.fold` および [List. scan](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#scan) は、 `List.fold` 余分なパラメーターの最後の値を返すのと異なりますが、 `List.scan` 余分なパラメーターの中間値 (最終的な値と共に) のリストを返します。

これらの各関数には、 [array.foldback](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#foldBack)などの逆のバリエーションが含まれています。これは、リストが走査される順序と引数の順序によって異なります。 また、 `List.fold` とに `List.foldBack` は、 [list.fold2](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#fold2) と [array.foldback2](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#foldBack2)というバリエーションがあります。これは、同じ長さの2つのリストを受け取ります。 各要素に対して実行される関数では、両方のリストの対応する要素を使用して操作を実行できます。 2 つのリストの要素の型が同じである必要はありません。たとえば、次の例では、一方のリストには銀行口座の取引金額が格納され、もう一方のリストには取引の種類 (預け入れまたは引き出し) が格納されています。

[!code-fsharp[Main](~/samples/snippets/fsharp/lists/snippet29.fs)]

合計のような計算の場合は、結果が走査の順序に依存しないため、`List.fold` と `List.foldBack` のどちらを使用しても、同じ結果になります。 次の例では、`List.foldBack` を使用してリストの要素を追加します。

[!code-fsharp[Main](~/samples/snippets/fsharp/lists/snippet30.fs)]

次の例では、銀行口座の例に戻ります。 今度は、利息を計算する新しい取引の種類が追加されています。 取引の順序によって期末残高が異なります。

[!code-fsharp[Main](~/samples/snippets/fsharp/lists/snippet34.fs)]

関数の [一覧の縮小](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#reduce) は、およびと似ていますが、 `List.fold` 別の `List.scan` アキュムレータを渡すのではなく、 `List.reduce` 1 つだけではなく要素型の2つの引数を受け取る関数を受け取ります。これらの引数の1つはアキュムレータとして機能します。つまり、計算の中間結果が格納されます。 `List.reduce` は、初めに最初の 2 つのリスト要素に対して演算を実行し、次にその演算の結果と次の要素を合わせて使用します。 独自の型を持つ別のアキュムレータがないため、`List.reduce` を `List.fold` の代わりに使用できるのは、アキュムレータと要素が同じ型を持つ場合だけです。 `List.reduce` を使用したコードの例を次に示します。 指定されたリストに要素がない場合、`List.reduce` は例外をスローします。

次のコードでは、ラムダ式の最初の呼び出しで引数 2 と 4 を受け取って 6 を返し、次の呼び出しで引数 6 と 10 を受け取るので、結果が 16 になります。

[!code-fsharp[Main](~/samples/snippets/fsharp/lists/snippet33.fs)]

### <a name="converting-between-lists-and-other-collection-types"></a>リストと他のコレクション型との変換

`List` モジュールには、シーケンスと配列との間で両方向の変換を行うための関数が用意されています。 シーケンスとの間で変換を行うには、 [list. toseq](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#toSeq) または [List. ofseq](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#ofSeq)を使用します。 配列との間で変換を行うには、 [list. toArray](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#toArray) または [List. ofarray](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#ofArray)を使用します。

### <a name="additional-operations"></a>その他の操作

リストに対するその他の操作の詳細については、ライブラリリファレンストピック [リストモジュール](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html)を参照してください。

## <a name="see-also"></a>関連項目

- [F# 言語リファレンス](index.md)
- [F# の型](fsharp-types.md)
- [シーケンス](sequences.md)
- [配列](arrays.md)
- [[オプション]](options.md)
