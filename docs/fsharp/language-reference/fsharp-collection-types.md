---
title: コレクション型
description: 'F # コレクション型と、それらがコレクション型 .NET とどのように異なるかについて説明します。'
ms.date: 08/14/2020
ms.openlocfilehash: 0b5be8f656d6728fe382b1944bda0a410a94d226
ms.sourcegitcommit: fe8877e564deb68d77fa4b79f55584ac8d7e8997
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/17/2020
ms.locfileid: "90720336"
---
# <a name="f-collection-types"></a>F # コレクション型

このトピックを確認することで、特定のニーズに最も適した F # コレクション型を特定できます。 これらのコレクション型は、.NET のコレクション型 (名前空間など) とは異なり `System.Collections.Generic` ます。 F # コレクション型は、オブジェクト指向の観点ではなく関数型プログラミングの観点から設計されています。 具体的には、配列コレクションのみに変更可能な要素があります。 したがって、コレクションを変更する場合は、元のコレクションを変更するのではなく、変更されたコレクションのインスタンスを作成します。

また、コレクション型は、オブジェクトが格納されているデータ構造の型によって異なります。 ハッシュテーブル、リンクリスト、配列などのデータ構造のパフォーマンス特性と使用可能な操作のセットは異なります。

## <a name="table-of-collection-types"></a>コレクション型の表

F # のコレクション型を次の表に示します。

|Type|説明|関連リンク|
|----|-----------|-------------|
|[一覧](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-fsharplist-1.html)|同じ型の順序付けられ、変更できない一連の要素。 リンクリストとして実装されます。|[リスト](lists.md)<br /><br />[List モジュール](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html)|
|[配列](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-core-array-1.html)|同じ型の連続するデータ要素の、固定サイズの、0から始まる変更可能なコレクション。|[配列](arrays.md)<br /><br />[Array モジュール](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html)<br /><br />[Array2D モジュール](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-array2dmodule.html)<br /><br />[Array3D モジュール](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-array3dmodule.html)|
|[seq](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-seq-1.html)|すべてが1つの型である、要素の論理系列。 シーケンスは、大量の順序付けられたデータのコレクションがあり、必ずしもすべての要素を使用するとは限らない場合に特に便利です。 個々のシーケンス要素は必要に応じてのみ計算されるので、すべての要素が使用されていない場合、シーケンスはリストよりもパフォーマンスが向上します。 シーケンスは、のエイリアスである型によって表され `seq<'T>` `IEnumerable<T>` ます。 したがって、を実装するすべての .NET Framework 型を `System.Collections.Generic.IEnumerable<'T>` シーケンスとして使用できます。|[シーケンス](sequences.md)<br /><br />[Seq モジュール](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-seqmodule.html)|
|[Map](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-fsharpmap-2.html)|要素の変更できないディクショナリ。 要素は、キーによってアクセスされます。|[マップモジュール](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-mapmodule.html)|
|[SET](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-fsharpset-1.html)|バイナリツリーに基づく変更できないセット。比較は F # の構造的な比較関数であり、 `System.IComparable` キー値に対するインターフェイスの実装を使用する可能性があります。|[モジュールの設定](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-setmodule.html)|

### <a name="table-of-functions"></a>関数の表

このセクションでは、F # コレクション型で使用できる関数を比較します。 関数の計算の複雑さが与えられます。ここで、N は最初のコレクションのサイズ、M は2番目のコレクションのサイズ (存在する場合) です。 ダッシュ (-) は、この関数がコレクションで使用できないことを示します。 シーケンスは遅延評価されるので、のような関数は `Seq.distinct` 直ちに返されるため、O (1) になることがありますが、列挙された場合でもシーケンスのパフォーマンスに影響します。

|機能|Array|List|シーケンス|マップ|設定|説明|
|--------|-----|----|--------|---|---|-----------|
|append|O (N)|O (N)|O (N)|-|-|最初のコレクションの要素の後に2番目のコレクションの要素を含む新しいコレクションを返します。|
|add|-|-|-|O (log (N))|O (log (N))|要素が追加された新しいコレクションを返します。|
|average|O (N)|O (N)|O (N)|-|-|コレクション内の要素の平均を返します。|
|averageBy|O (N)|O (N)|O (N)|-|-|各要素に適用される指定された関数の結果の平均を返します。|
|array.blit|O (N)|-|-|-|-|配列のセクションをコピーします。|
|cache|-|-|O (N)|-|-|シーケンスの要素を計算して格納します。|
|cast|-|-|O (N)|-|-|要素を指定した型に変換します。|
|choose|O (N)|O (N)|O (N)|-|-|指定された関数 `f` をリストの各要素に適用し `x` ます。 関数がを返す各要素の結果を含むリストを返し `Some(f(x))` ます。|
|collect|O (N)|O (N)|O (N)|-|-|指定された関数をコレクションの各要素に適用し、すべての結果を連結して、結合されたリストを返します。|
|Seq.comparewith|-|-|O (N)|-|-|指定された比較関数を要素ごとに使用して、2つのシーケンスを比較します。|
|concat|O (N)|O (N)|O (N)|-|-|指定した列挙体の列挙体を1つの連結された列挙体として結合します。|
|次の値を含む|-|-|-|-|O (log (N))|指定した要素がセットに含まれている場合に true を返します。|
|containsKey|-|-|-|O (log (N))|-|要素がマップのドメイン内にあるかどうかをテストします。|
|count|-|-|-|-|O (N)|セット内の要素数を返します。|
|countBy|-|-|O (N)|-|-|シーケンスの各要素にキー生成関数を適用し、元のシーケンスで一意のキーとその出現回数を生成するシーケンスを返します。|
|copy|O (N)|-|O (N)|-|-|コレクションをコピーします。|
|create|O (N)|-|-|-|-|最初に指定された値である要素全体の配列を作成します。|
|delay|-|-|O(1)|-|-|シーケンスの指定された遅延指定から構築されたシーケンスを返します。|
|相違点|-|-|-|-|O (M \* ログ (N))|最初のセットから削除された2番目のセットの要素を含む新しいセットを返します。|
|distinct|||O(1)\*|||エントリの汎用ハッシュと等価比較に従って、重複するエントリを含まないシーケンスを返します。 要素がシーケンス内で複数回出現する場合、後で発生する項目は破棄されます。|
|Seq.distinctby|||O(1)\*|||指定されたキー生成関数が返すキーの汎用ハッシュと等価比較に従って、重複するエントリを含まないシーケンスを返します。 要素がシーケンス内で複数回出現する場合、後で発生する項目は破棄されます。|
|empty|O(1)|O(1)|O(1)|O(1)|O(1)|空のコレクションを作成します。|
|exists|O (N)|O (N)|O (N)|O (log (N))|O (log (N))|シーケンスのいずれかの要素が、指定された述語を満たすかどうかをテストします。|
|list.exists2|O (最小 (N, M))|-|O (最小 (N, M))|||入力シーケンスの対応する要素のペアが、指定された述語を満たすかどうかをテストします。|
|fill|O (N)|||||配列の要素の範囲を指定された値に設定します。|
|filter|O (N)|O (N)|O (N)|O (N)|O (N)|指定された述語が返すコレクションの要素のみを含む新しいコレクションを返し `true` ます。|
|検索|O (N)|O (N)|O (N)|O (log (N))|-|指定された関数が返す最初の要素を返し `true` ます。 `System.Collections.Generic.KeyNotFoundException`そのような要素が存在しない場合はを返します。|
|findIndex|O (N)|O (N)|O (N)|-|-|指定された述語を満たす配列内の最初の要素のインデックスを返します。 `System.Collections.Generic.KeyNotFoundException`述語を満たす要素がない場合に、を発生させます。|
|Map.findkey|-|-|-|O (log (N))|-|コレクション内の各マッピングで関数を評価し、関数がを返す最初のマッピングのキーを返し `true` ます。 このような要素が存在しない場合、この関数はを発生させ `System.Collections.Generic.KeyNotFoundException` ます。|
|パンフレット|O (N)|O (N)|O (N)|O (N)|O (N)|計算にアキュムレータ引数を使用して、コレクションの各要素に関数を適用します。 入力関数が f で、要素が i0 の場合では、この関数は f (...(f s i0)...)から.|
|list.fold2|O (N)|O (N)|-|-|-|2つのコレクションの対応する要素に関数を適用し、計算を通じてアキュムレータ引数を処理します。 コレクションのサイズは同じである必要があります。 入力関数が f で、要素が i0 の場合と j0...この関数は、f (...(f s i0 j0)...)の場合。|
|Array.foldback|O (N)|O (N)|-|O (N)|O (N)|計算にアキュムレータ引数を使用して、コレクションの各要素に関数を適用します。 入力関数が f で、要素が i0 の場合では、この関数は f i0 (...(s)。|
|Array.foldback2|O (N)|O (N)|-|-|-|2つのコレクションの対応する要素に関数を適用し、計算を通じてアキュムレータ引数を処理します。 コレクションのサイズは同じである必要があります。 入力関数が f で、要素が i0 の場合と j0...この関数は、f i0 j0 (...(f)。|
|forall|O (N)|O (N)|O (N)|O (N)|O (N)|コレクションのすべての要素が、指定された述語を満たすかどうかをテストします。|
|array.forall2|O (N)|O (N)|O (N)|-|-|コレクションの対応するすべての要素が、指定された述語ペアを満たしているかどうかをテストします。|
|取得/n 番目|O(1)|O (N)|O (N)|-|-|インデックスを指定して、コレクションから要素を返します。|
|head|-|O(1)|O(1)|-|-|コレクションの最初の要素を返します。|
|Init|O (N)|O (N)|O(1)|-|-|ディメンションと、要素を計算するジェネレーター関数を指定して、コレクションを作成します。|
|Seq.initinfinite|-|-|O(1)|-|-|反復処理時に、指定された関数を呼び出すことによって連続する要素を返すシーケンスを生成します。|
|intersect|-|-|-|-|O (log (N) \* log (M))|2つのセットの積集合を計算します。|
|Set.intersectmany|-|-|-|-|O (N1 \* N2...)|セットのシーケンスの積集合を計算します。 シーケンスを空にすることはできません。|
|isEmpty|O(1)|O(1)|O(1)|O(1)|-|`true`コレクションが空の場合は、を返します。|
|Set.ispropersubset|-|-|-|-|O (M \* ログ (N))|`true`最初のセットのすべての要素が2番目のセットに含まれており、2番目のセットの少なくとも1つの要素が1番目のセットに含まれていない場合は、を返します。|
|Set.ispropersuperset|-|-|-|-|O (M \* ログ (N))|`true`2 番目のセットのすべての要素が1番目のセットに含まれていて、1番目のセットの少なくとも1つの要素が2番目のセットに含まれていない場合、を返します。|
|Set.issubset|-|-|-|-|O (M \* ログ (N))|`true`最初のセットのすべての要素が2番目のセットに含まれている場合は、を返します。|
|Set.issuperset|-|-|-|-|O (M \* ログ (N))|`true`2 番目のセットのすべての要素が1番目のセットに含まれている場合は、を返します。|
|iter|O (N)|O (N)|O (N)|O (N)|O (N)|指定された関数をコレクションの各要素に適用します。|
|array.iteri|O (N)|O (N)|O (N)|-|-|指定された関数をコレクションの各要素に適用します。 関数に渡される整数は、要素のインデックスを示します。|
|array.iteri2|O (N)|O (N)|-|-|-|2つの配列内の一致するインデックスから描画された要素のペアに、指定された関数を適用します。 関数に渡される整数は、要素のインデックスを示します。 2つの配列の長さは同じである必要があります。|
|array.iter2|O (N)|O (N)|O (N)|-|-|2つの配列内の一致するインデックスから描画された要素のペアに、指定された関数を適用します。 2つの配列の長さは同じである必要があります。|
|last|O(1)|O (N)|O (N)|-|-|適用可能なコレクション内の最後の項目を返します。|
|length|O(1)|O (N)|O (N)|-|-|コレクション内の要素の数を返します。|
|map|O (N)|O (N)|O(1)|-|-|指定された関数を配列の各要素に適用した結果として得られる要素を含むコレクションを構築します。|
|list.map2|O (N)|O (N)|O(1)|-|-|指定された関数を2つのコレクションのペアの対応する要素に適用した結果を要素として持つコレクションを構築します。 2つの入力配列の長さは同じである必要があります。|
|list.map3|-|O (N)|-|-|-|指定された関数を3つのコレクションの対応する要素に同時に適用した結果として得られる要素を含むコレクションを構築します。|
|経由|O (N)|O (N)|O (N)|-|-|指定された関数を配列の各要素に適用した結果として得られる要素を持つ配列を構築します。 関数に渡される整数インデックスは、変換される要素のインデックスを示します。|
|array.mapi2|O (N)|O (N)|-|-|-|指定された関数を2つのコレクションの対応する要素に適用した結果を要素として持つコレクションを構築します。また、要素のインデックスも渡します。 2つの入力配列の長さは同じである必要があります。|
|max|O (N)|O (N)|O (N)|-|-|[Max](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-core-operators.html#max)演算子を使用した場合と比較して、コレクション内の最大の要素を返します。|
|maxBy|O (N)|O (N)|O (N)|-|-|関数の結果に対して [max](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-core-operators.html#max) を使用することにより、コレクション内の最大の要素を返します。|
|Set.maxelement|-|-|-|-|O (log (N))|セットで使用されている順序に従って、セット内の最大の要素を返します。|
|分|O (N)|O (N)|O (N)|-|-|[Min](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-core-operators.html#min)演算子を使用した場合と比較して、コレクション内の最小の要素を返します。|
|Array.minby|O (N)|O (N)|O (N)|-|-|関数の結果に対して [min](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-core-operators.html#min) 演算子を使用することにより、コレクション内の最小の要素を返します。|
|Set.minelement|-|-|-|-|O (log (N))|セットで使用されている順序に従って、セット内の最も小さい要素を返します。|
|List.ofarray|-|O (N)|O(1)|O (N)|O (N)|指定された配列と同じ要素を含むコレクションを作成します。|
|Array.oflist|O (N)|-|O(1)|O (N)|O (N)|指定されたリストと同じ要素を含むコレクションを作成します。|
|Array.ofseq|O (N)|O (N)|-|O (N)|O (N)|指定されたシーケンスと同じ要素を含むコレクションを作成します。|
|ペアワイズ|-|-|O (N)|-|-|2番目の要素の先行要素としてのみ返される最初の要素を除き、入力シーケンス内の各要素とその先行要素のシーケンスを返します。|
|partition|O (N)|O (N)|-|O (N)|O (N)|コレクションを2つのコレクションに分割します。 最初のコレクションには、指定された述語によって返される要素が含まれ、2番目のコレクションには、指定された述語が返す要素が含まれ `true` `false` ます。|
|permute|O (N)|O (N)|-|-|-|指定された順列に従ってすべての要素を変えるする配列を返します。|
|拾い|O (N)|O (N)|O (N)|O (log (N))|-|指定された関数を一連の要素に適用し、関数が値を返す最初の結果を返します。 関数が何も返さない場合 `System.Collections.Generic.KeyNotFoundException` は、が発生します。|
|readonly|-|-|O (N)|-|-|指定されたシーケンスオブジェクトにデリゲートするシーケンスオブジェクトを作成します。 この操作により、型キャストは元のシーケンスを再検出および再処理できなくなります。 たとえば、配列が指定されている場合、返されるシーケンスは配列の要素を返しますが、返されたシーケンスオブジェクトを配列にキャストすることはできません。|
|reduce|O (N)|O (N)|O (N)|-|-|計算にアキュムレータ引数を使用して、コレクションの各要素に関数を適用します。 この関数は、最初の2つの要素に関数を適用し、3番目の要素と共にこの結果を関数に渡します。以降も同様です。 関数は、最終結果を返します。|
|Array.reduceback|O (N)|O (N)|-|-|-|計算にアキュムレータ引数を使用して、コレクションの各要素に関数を適用します。 入力関数が f で、要素が i0 の場合では、この関数は f i0 (...(では f iN-1)。|
|remove|-|-|-|O (log (N))|O (log (N))|マップのドメインから要素を削除します。 要素が存在しない場合、例外は発生しません。|
|レプリケート|-|O (N)|-|-|-|指定した値に設定されたすべての要素を使用して、指定した長さのリストを作成します。|
|下位|O (N)|O (N)|-|-|-|要素を逆順にした新しいリストを返します。|
|取り込む|O (N)|O (N)|O (N)|-|-|計算にアキュムレータ引数を使用して、コレクションの各要素に関数を適用します。 この操作では、関数を2番目の引数とリストの最初の要素に適用します。 次に、操作は、この結果を2番目の要素と共に関数に渡します。 最後に、操作は中間結果と最終結果のリストを返します。|
|Array.scanback|O (N)|O (N)|-|-|-|は Array.foldback 操作に似ていますが、中間と最終の両方の結果を返します。|
|singleton|-|-|O(1)|-|O(1)|項目を1つだけ生成するシーケンスを返します。|
|set|O(1)|-|-|-|-|配列の要素を指定された値に設定します。|
|skip|-|-|O (N)|-|-|基になるシーケンスの N 個の要素をスキップし、シーケンスの残りの要素を生成するシーケンスを返します。|
|skipWhile|-|-|O (N)|-|-|反復処理時に、指定された述語がを返したときに、基になるシーケンスの要素をスキップし、シーケンスの残りの要素を生成するシーケンスを返し `true` ます。|
|sort|O (N \* ログ (n)) 平均<br /><br />O (N ^ 2) 最悪のケース|O (N \* ログ (n))|O (N \* ログ (n))|-|-|要素の値でコレクションを並べ替えます。 要素は [比較](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-core-operators.html#compare)を使用して比較されます。|
|sortBy|O (N \* ログ (n)) 平均<br /><br />O (N ^ 2) 最悪のケース|O (N \* ログ (n))|O (N \* ログ (n))|-|-|指定されたプロジェクションによって提供されるキーを使用して、指定されたリストを並べ替えます。 キーは [比較](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-core-operators.html#compare)を使用して比較されます。|
|Array.sortinplace|O (N \* ログ (n)) 平均<br /><br />O (N ^ 2) 最悪のケース|-|-|-|-|位置を変更し、指定された比較関数を使用して、配列の要素を並べ替えます。 要素の比較には、 [compare](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-core-operators.html#compare)を使用します。|
|Array.sortinplaceby|O (N \* ログ (n)) 平均<br /><br />O (N ^ 2) 最悪のケース|-|-|-|-|位置を変更し、キーに対して指定された射影を使用して、配列の要素を並べ替えます。 要素の比較には、 [compare](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-core-operators.html#compare)を使用します。|
|Array.sortinplacewith|O (N \* ログ (n)) 平均<br /><br />O (N ^ 2) 最悪のケース|-|-|-|-|位置を変更し、指定された比較関数を順序として使用して、配列の要素を並べ替えます。|
|List.sortwith|O (N \* ログ (n)) 平均<br /><br />O (N ^ 2) 最悪のケース|O (N \* ログ (n))|-|-|-|指定された比較関数を順序として使用し、新しいコレクションを返すコレクションの要素を並べ替えます。|
|sub|O (N)|-|-|-|-|開始インデックスと長さによって指定された指定されたサブ範囲を含む配列を構築します。|
|Sum|O (N)|O (N)|O (N)|-|-|コレクション内の要素の合計を返します。|
|Array.sumby|O (N)|O (N)|O (N)|-|-|関数をコレクションの各要素に適用することによって生成される結果の合計を返します。|
|テイ|-|O(1)|-|-|-|最初の要素を含まないリストを返します。|
|take|-|-|O (N)|-|-|指定された数までシーケンスの要素を返します。|
|takeWhile|-|-|O(1)|-|-|反復処理時に、指定された述語がを返したときに基になるシーケンスの要素を生成 `true` し、それ以上要素を返さないシーケンスを返します。|
|toArray|-|O (N)|O (N)|O (N)|O (N)|指定されたコレクションから配列を作成します。|
|System.linq.enumerable.tolist|O (N)|-|O (N)|O (N)|O (N)|指定されたコレクションからリストを作成します。|
|Array.toseq|O(1)|O(1)|-|O(1)|O(1)|指定されたコレクションからシーケンスを作成します。|
|truncate|-|-|O(1)|-|-|列挙された場合に N 個を超える要素を返さないシーケンスを返します。|
|tryFind|O (N)|O (N)|O (N)|O (log (N))|-|指定された述語を満たす要素を検索します。|
|Array.tryfindindex|O (N)|O (N)|O (N)|-|-|指定された述語を満たす最初の要素を検索し、一致する要素のインデックスを返し `None` ます。そのような要素が存在しない場合はを返します。|
|Map.tryfindkey|-|-|-|O (log (N))|-|指定された述語を満たすコレクション内の最初のマッピングのキーを返し `None` ます。そのような要素が存在しない場合はを返します。|
|Array.trypick|O (N)|O (N)|O (N)|O (log (N))|-|指定された関数を一連の要素に適用し、関数が `Some` 何らかの値に対してを返す最初の結果を返します。 そのような要素が存在しない場合、操作はを返し `None` ます。|
|折り畳み|-|-|O (N)|-|-|指定された計算によって生成される要素を格納しているシーケンスを返します。|
|union|-|-|-|-|O (M \* ログ (N))|2つのセットの和集合を計算します。|
|Set.unionmany|-|-|-|-|O (N1 \* N2...)|セットのシーケンスの和集合を計算します。|
|unzip|O (N)|O (N)|O (N)|-|-|ペアのリストを2つのリストに分割します。|
|array.unzip3|O (N)|O (N)|O (N)|-|-|3要素のリストを3つのリストに分割します。|
|ウィンドウ|-|-|O (N)|-|-|入力シーケンスから描画される、含まれる要素のスライディングウィンドウを生成するシーケンスを返します。 各ウィンドウは、新しい配列として返されます。|
|zip|O (N)|O (N)|O (N)|-|-|2つのコレクションをペアのリストに結合します。 2つのリストの長さは同じである必要があります。|
|array.zip3|O (N)|O (N)|O (N)|-|-|3つのコレクションを3要素のリストに結合します。 リストの長さは同じである必要があります。|

## <a name="see-also"></a>関連項目

- [F# の型](fsharp-types.md)
- [F# 言語リファレンス](index.md)
