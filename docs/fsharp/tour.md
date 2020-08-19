---
title: F# のツアー
description: 'このツアーの F # プログラミング言語の主な機能のいくつかを、コードサンプルで確認します。'
ms.date: 08/14/2020
ms.openlocfilehash: b115317e1f47ef7e18333cae4145b99e11645579
ms.sourcegitcommit: 8bfeb5930ca48b2ee6053f16082dcaf24d46d221
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/18/2020
ms.locfileid: "88558596"
---
# <a name="tour-of-f"></a>F のツアー\#

F # について学習する最善の方法は、F # コードの読み取りと書き込みです。 この記事では、F # 言語の主な機能をいくつか紹介し、お使いのコンピューターで実行できるコードスニペットをいくつか紹介します。 開発環境の設定の詳細については、「 [はじめに](get-started/index.md)」を参照してください。

F # には、関数と型という2つの主要な概念があります。  このツアーでは、この2つの概念に分類される言語の機能に重点を置いています。

## <a name="executing-the-code-online"></a>コードをオンラインで実行する

コンピューターに F # がインストールされていない場合は、ブラウザーですべてのサンプルを実行し [てみてください](https://tryfsharp.fsbolero.io/)。 Fable は、ブラウザーで直接実行される F # の言語です。 REPL の後に続くサンプルを確認するには、Fable REPL の左側のメニューバーにある **F # の > ツアーの >** を参照してください。

## <a name="functions-and-modules"></a>関数とモジュール

F # プログラムの最も基本的な部分は、***モジュール***に編成された***関数***です。  [関数](./language-reference/functions/index.md) は、入力に対する処理を実行して出力を生成し、モジュールの下に編成されます。 [モジュール](./language-reference/modules.md)は、F # で項目をグループ化する主な方法です。  これらは、 [ `let` バインディング](./language-reference/functions/let-bindings.md)を使用して定義されます。これにより、関数に名前を付け、引数を定義します。

[!code-fsharp[BasicFunctions](~/samples/snippets/fsharp/tour.fs#L101-L133)]

`let` バインドは、他の言語の変数と同様に、値を名前にバインドする方法でもあります。  `let` 既定では、バインドは変更できません。つまり、値または関数が名前に ***バインドされる*** と、その場で変更することはできません。  これは、変更可能な他の言語の変数と ***は対照的***です。つまり、値は任意の時点で変更できます。  変更可能なバインドが必要な場合は、構文を使用でき `let mutable ...` ます。

[!code-fsharp[Immutability](~/samples/snippets/fsharp/tour.fs#L75-L94)]

## <a name="numbers-booleans-and-strings"></a>数値、ブール値、および文字列

.NET 言語として、F # では .NET に存在する基になる [プリミティブ型](language-reference/basic-types.md) と同じものがサポートされています。

F # では、さまざまな数値型がどのように表されるかを次に示します。

[!code-fsharp[Numbers](~/samples/snippets/fsharp/tour.fs#L49-L68)]

次に、ブール値と基本的な条件ロジックの実行例を示します。

[!code-fsharp[Bools](~/samples/snippets/fsharp/tour.fs#L142-L152)]

基本的な [文字列](./language-reference/strings.md) 操作は次のようになります。

[!code-fsharp[Strings](~/samples/snippets/fsharp/tour.fs#L158-L180)]

## <a name="tuples"></a>タプル

F # では、[タプル](./language-reference/tuples.md)は大きな問題です。  これらは名前のない、順序付けされた値をグループ化したもので、値自体として扱うことができます。  これらは、他の値から集計された値と考えることができます。  多くの用途があります。たとえば、関数から複数の値を返すことができるようにしたり、特別な便宜を行うために値をグループ化したりします。

[!code-fsharp[Tuples](~/samples/snippets/fsharp/tour.fs#L186-L203)]

組を作成することもでき `struct` ます。  これらは、C# 7/Visual Basic 15 組 (タプル) と完全に相互運用することもでき `struct` ます。

[!code-fsharp[Tuples](~/samples/snippets/fsharp/tour.fs#L205-L218)]

`struct`タプルは値型であるため、暗黙的に参照タプルに変換することはできず、逆の場合もあります。  参照と構造体の組の間で明示的に変換する必要があります。

## <a name="pipelines-and-composition"></a>パイプラインとコンポジション

などのパイプ演算子 `|>` は、F # でデータを処理するときに広く使用されます。 これらの演算子は、関数の "パイプライン" を柔軟な方法で確立できるようにする関数です。 次の例では、これらの演算子を利用して単純な機能パイプラインを構築する方法について説明します。

[!code-fsharp[Pipelines](~/samples/snippets/fsharp/tour.fs#L227-L282)]

前のサンプルでは、リスト処理関数、ファーストクラス関数、 [部分アプリケーション](./language-reference/functions/index.md#partial-application-of-arguments)など、F # の多くの機能が使用されていました。 これらの概念を深く理解することは少し高度になる可能性がありますが、パイプラインを構築するときに、簡単に関数を使用してデータを処理する方法を明確にする必要があります。

## <a name="lists-arrays-and-sequences"></a>リスト、配列、およびシーケンス

リスト、配列、およびシーケンスは、F # コアライブラリの3つのプライマリコレクション型です。

[リスト](./language-reference/lists.md) は、同じ型の要素の順序付けられ、変更できないコレクションです。  これらはシングルリンクリストです。つまり、列挙型であることを意味しますが、サイズが大きい場合はランダムアクセスと連結には適していません。  これは、一般的には、リストを表すために単一リンクリストを使用しない他の一般的な言語の一覧とは対照的です。

[!code-fsharp[Lists](~/samples/snippets/fsharp/tour.fs#L309-L359)]

[配列](./language-reference/arrays.md) は、同じ型の要素の固定 *サイズの変更可能なコレクションです* 。  要素の高速なランダムアクセスをサポートしています。 F # リストは、連続したメモリブロックであるため、F # リストより高速です。

[!code-fsharp[Arrays](~/samples/snippets/fsharp/tour.fs#L368-L407)]

[シーケンス](./language-reference/sequences.md) は、すべて同じ型の論理的な一連の要素です。  これらは、リストや配列よりも一般的な型であり、任意の論理シリーズの要素に "表示" できるようになっています。  また、 ***遅延***がある可能性があるため、このような場合もあります。これは、要素が必要な場合にのみ計算できることを意味します。

[!code-fsharp[Sequences](~/samples/snippets/fsharp/tour.fs#L418-L452)]

## <a name="recursive-functions"></a>再帰関数

コレクションまたは要素のシーケンスの処理は、通常、F # の [再帰](./language-reference/functions/index.md#recursive-functions) を使用して行われます。  F # では、ループと命令型プログラミングがサポートされていますが、正確性を保証するのが簡単であるため、再帰が推奨されています。

> [!NOTE]
> 次の例では、式を使用してパターンマッチングを使用し `match` ます。  この基本的な構成要素については、この記事の後半で説明します。

[!code-fsharp[RecursiveFunctions](~/samples/snippets/fsharp/tour.fs#L461-L500)]

F # では、末尾呼び出しの最適化も完全にサポートされています。これは、再帰呼び出しを最適化して、ループ構造と同じ速度にすることができるようにするための方法です。

## <a name="record-and-discriminated-union-types"></a>レコードと判別共用体型

レコード型と共用体型は、F # コードで使用される2つの基本データ型であり、一般に F # プログラムでデータを表現する最良の方法です。  これは他の言語のクラスと似ていますが、主な違いの1つは、構造上の等価性があることです。  つまり、これらは "ネイティブな" 比較可能であり、等価性が簡単であることを意味します。一方が等しいかどうかを確認するだけです。

[レコード](./language-reference/records.md) は、名前付きの値の集合であり、オプションのメンバー (メソッドなど) が含まれます。  C# または Java に慣れていれば、これらは、構造的な等価性と少ない手続きを持つ POCOs や Pojo に似ています。

[!code-fsharp[Records](~/samples/snippets/fsharp/tour.fs#L507-L559)]

レコードを構造体として表すこともできます。 これは、属性を使用して行い `[<Struct>]` ます。

[!code-fsharp[Records](~/samples/snippets/fsharp/tour.fs#L561-L568)]

[判別共用体 (du)](./language-reference/discriminated-unions.md) は、多数の名前付きフォームまたはケースである可能性がある値です。  型に格納されるデータは、複数の個別の値のいずれかになります。

[!code-fsharp[Unions](~/samples/snippets/fsharp/tour.fs#L575-L631)]

また、Du を *シングルケース判別共用体*として使用して、プリミティブ型に対するドメインモデリングを支援することもできます。  多くの場合、文字列やその他のプリミティブ型を使用して何かを表しているため、特定の意味が与えられます。  ただし、データのプリミティブ表現のみを使用すると、誤った値が誤って割り当てられる可能性があります。  このシナリオでは、各種類の情報を個別の単一ケース共用体として表すことができます。

[!code-fsharp[Unions](~/samples/snippets/fsharp/tour.fs#L633-L654)]

上の例で示すように、単一ケースの判別共用体の基になる値を取得するには、明示的にラップ解除する必要があります。

また、Du は再帰的な定義もサポートしているので、ツリーや本質的に再帰的なデータを簡単に表すことができます。  たとえば、関数と関数を使用してバイナリ検索ツリーを表現する方法を次に示し `exists` `insert` ます。

[!code-fsharp[Unions](~/samples/snippets/fsharp/tour.fs#L656-L683)]

Du では、データ型のツリーの再帰構造を表すことができるため、この再帰構造での操作は簡単で、正確性が保証されます。  次に示すように、パターンマッチングでもサポートされています。

また、次の属性を使用して、の Du をとして表すことができ `struct` `[<Struct>]` ます。

[!code-fsharp[Unions](~/samples/snippets/fsharp/tour.fs#L685-L696)]

ただし、その場合は、次の2つの点に注意する必要があります。

1. Struct DU を再帰的に定義することはできません。
2. Struct DU は、それぞれのケースに対して一意の名前を持つ必要があります。

上記に従わないと、コンパイルエラーが発生します。

## <a name="pattern-matching"></a>パターン マッチ

[パターンマッチング](./language-reference/pattern-matching.md) は f # 言語機能で、f # の型を操作するための正確さを有効にします。  上記のサンプルでは、非常に多くの構文に気付き `match x with ...` ます。  このコンストラクトを使用すると、コンパイラはデータ型の "形状" を理解でき、完全なパターンマッチングとして知られているデータ型を使用する場合に、すべてのケースを考慮する必要があります。  これは、正確さを実現するために非常に強力であり、通常はランタイムの問題としてコンパイル時に巧妙を "リフト" するために使用できます。

[!code-fsharp[PatternMatching](~/samples/snippets/fsharp/tour.fs#L705-L742)]

ご存知かもしれませんが、パターンを使用してい `_` ます。  これは、 [ワイルドカードパターン](./language-reference/pattern-matching.md#wildcard-pattern)と呼ばれます。これは、"何が何であるかを気にしない" と言うことができます。  便利ですが、を使用するのが十分でない場合は、完全なパターンマッチングを誤ってバイパスし、コンパイル時の実施の恩恵を受けることができなくなり `_` ます。  パターンマッチングの際に分解された型の特定の部分を気にしない場合、またはパターン一致式ですべての意味のあるケースを列挙した場合は final 句を使用することをお勧めします。

次の例では、 `_` 解析操作が失敗したときにケースが使用されます。

[!code-fsharp[PatternMatching](~/samples/snippets/fsharp/tour.fs#L744-L762)]

[アクティブパターン](./language-reference/active-patterns.md) は、パターンマッチングで使用するもう1つの強力な構成要素です。  これにより、入力データをカスタムフォームに分割し、パターンマッチ呼び出しサイトで分解することができます。  また、パラメーター化して、がパーティションを関数として定義できるようにすることもできます。  アクティブなパターンをサポートするために前の例を拡張すると、次のようになります。

[!code-fsharp[ActivePatterns](~/samples/snippets/fsharp/tour.fs#L764-L786)]

## <a name="optional-types"></a>省略可能な型

判別共用体型の1つの特殊なケースとして、オプションの型があります。これは、F # コアライブラリの一部であることを意味します。

[オプションの種類](./language-reference/options.md) は、値または nothing の2つのケースのいずれかを表す型です。  このメソッドは、特定の操作の結果として値が異なる可能性がある場合に、どのようなシナリオでも使用されます。  これにより、実行時の問題ではなく、コンパイル時の問題になるように、両方のケースを考慮する必要があります。  これらは多くの場合、 `null` が "nothing" を表すために使用される api で使用されるため、多くの状況では心配する必要があり `NullReferenceException` ません。

[!code-fsharp[Options](~/samples/snippets/fsharp/tour.fs#L789-L814)]

## <a name="units-of-measure"></a>測定単位

F # の型システムの固有の機能の1つに、測定単位を使用して数値リテラルのコンテキストを提供する機能があります。

[測定単位](./language-reference/units-of-measure.md) を使用すると、数値型をメートル単位に関連付けることができます。また、関数は数値リテラルではなく単位で作業を実行します。  これにより、コンパイラは、渡された数値リテラルの型が特定のコンテキストで意味を持つかどうかを検証できるため、そのような作業に関連するランタイムエラーを回避できます。

[!code-fsharp[UnitsOfMeasure](~/samples/snippets/fsharp/tour.fs#L817-L842)]

F # コアライブラリでは、さまざまな SI 単位の型と単位の変換が定義されています。  詳細については、 [Fsharp.core 名前空間](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-data-unitsystems-si-unitsymbols.html)に関するページを参照してください。

## <a name="classes-and-interfaces"></a>クラスとインターフェイス

F # では、.NET クラス、 [インターフェイス](./language-reference/interfaces.md)、 [抽象クラス](./language-reference/abstract-classes.md)、 [継承](./language-reference/inheritance.md)なども完全にサポートされています。

[クラス](./language-reference/classes.md) は、プロパティ、メソッド、およびイベントを [メンバー](./language-reference/members/index.md)として持つことができる .net オブジェクトを表す型です。

[!code-fsharp[Classes](~/samples/snippets/fsharp/tour.fs#L845-L880)]

ジェネリッククラスを定義することも、非常に簡単です。

[!code-fsharp[Classes](~/samples/snippets/fsharp/tour.fs#L883-L908)]

インターフェイスを実装するには、 `interface ... with` 構文または [オブジェクト式](./language-reference/object-expressions.md)のいずれかを使用します。

[!code-fsharp[Classes](~/samples/snippets/fsharp/tour.fs#L911-L934)]

## <a name="which-types-to-use"></a>使用する型

クラス、レコード、判別共用体、および組が存在すると、重要な質問につながります。  多くの場合、その答えは状況によって異なります。

組は、関数から複数の値を返す場合や、値のアドホック集計を値自体として使用する場合に適しています。

レコードは組からの "ステップアップ" であり、名前付きラベルとオプションメンバーのサポートがあります。  プログラムを通じて転送中のデータをより詳細に表現する場合に適しています。  これらは構造的に等価であるため、比較で簡単に使用できます。

判別共用体には多くの用途がありますが、主な利点は、データに含まれる可能性のあるすべての "形状" を考慮して、それらをパターンマッチングと組み合わせて使用できることです。  

クラスは、情報を表す必要がある場合や、その情報を機能に関連付けている場合など、膨大な数の理由で非常に優れています。  経験則として、概念的に一部のデータに関連付けられている機能がある場合は、クラスとオブジェクト指向プログラミングの原則を使用することが大きな利点です。  クラスは C# および Visual Basic と相互運用する場合にも、ほぼすべての言語でクラスを使用するため、推奨されるデータ型です。

## <a name="next-steps"></a>次の手順

言語の主な機能をいくつか紹介したので、最初の F # プログラムを作成する準備ができました。  開発環境を設定してコードを記述する方法については、 [はじめに](get-started/index.md) を参照してください。

さらに学習するための次の手順は任意のものにすることができますが、コア関数型プログラミングの概念を理解するには、 [F # での関数型プログラミングの概要](./introduction-to-functional-programming/index.md) をお勧めします。  これらは、F # で堅牢なプログラムを構築する際に不可欠です。

また、f # の概念コンテンツの包括的なコレクションを確認するには、 [f # 言語リファレンス](./language-reference/index.md) を参照してください。
