---
title: C# foreach ステートメント
ms.date: 07/22/2020
f1_keywords:
- foreach
- foreach_CSharpKeyword
helpviewer_keywords:
- foreach keyword [C#]
- foreach statement [C#]
- in keyword [C#]
ms.assetid: 5a9c5ddc-5fd3-457a-9bb6-9abffcd874ec
ms.openlocfilehash: 4af431d29e538c1516efeaad3008eaa3b2229ece
ms.sourcegitcommit: 04022ca5d00b2074e1b1ffdbd76bec4950697c4c
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/23/2020
ms.locfileid: "87104239"
---
# <a name="foreach-in-c-reference"></a>foreach、in (C# リファレンス)

`foreach` ステートメントは、次の例のように、<xref:System.Collections.IEnumerable?displayProperty=nameWithType> または <xref:System.Collections.Generic.IEnumerable%601?displayProperty=nameWithType> インターフェイスを実装している型のインスタンス内の要素ごとに、ステートメントまたはステートメントのブロックを実行します。

:::code language="csharp" source="snippets/IterationKeywordsExamples.cs" id="1" interactive="try-dotnet-method" :::

`foreach` ステートメントは、これらの型に制限されません。 これは次の条件を満たす任意の型のインスタンスと共に使用できます。

- 戻り値の型がクラス、構造体、インターフェイス型のいずれかである、パラメーターなしのパブリック メソッド `GetEnumerator` がある型。
- `GetEnumerator` メソッドの戻り値の型が、パブリック プロパティ `Current` と、戻り値の型が <xref:System.Boolean> であるパラメーターなしのパブリック メソッド `MoveNext` を持っている。

次の例では、何のインターフェイスも実装していない <xref:System.Span%601?displayProperty=nameWithType> 型のインスタンスを使用して、`foreach` ステートメントを使用します。

:::code language="csharp" source="snippets/IterationKeywordsExamples.cs" id="2" :::

C# 7.3 以降、列挙子の `Current` プロパティによって、[参照戻り値](ref.md#reference-return-values) (`ref T`。この場合、`T` はコレクション要素の型です) が返される場合、次の例のように、`ref` または `ref readonly` 修飾子を使用して繰り返し変数を宣言することができます。

:::code language="csharp" source="snippets/IterationKeywordsExamples.cs" id="RefSpan" :::

C# 8.0 以降、`await foreach` ステートメントを使用して、データの非同期ストリーム、つまり、<xref:System.Collections.Generic.IAsyncEnumerable%601> インターフェイスを実装するコレクション型を使用できます。 次の要素が非同期で取得されている限り、ループの各反復は中断される可能性があります。 `await foreach` ステートメントを使用する方法の例を次に示します。

:::code language="csharp" source="snippets/IterationKeywordsExamples.cs" id="AwaitForeach" :::

既定では、ストリーム要素はキャプチャされたコンテキストで処理されます。 コンテキストのキャプチャを無効にする場合は、<xref:System.Threading.Tasks.TaskAsyncEnumerableExtensions.ConfigureAwait%2A?displayProperty=nameWithType> 拡張メソッドを使用します。 同期コンテキストおよび現在のコンテキストのキャプチャについての詳細は、「[タスク ベースの非同期パターンの利用](../../../standard/asynchronous-programming-patterns/consuming-the-task-based-asynchronous-pattern.md)」を参照してください。 非同期ストリームの詳細については、「[C# 8.0 の新機能](../../whats-new/csharp-8.md)」の記事の「[非同期ストリーム](../../whats-new/csharp-8.md#asynchronous-streams)」セクションを参照してください。

`foreach` ステートメント ブロック内の任意の位置で、[break](break.md) ステートメントを使ってループから抜けることができます。または、[continue](continue.md) ステートメントを使って、ループ内の次の繰り返しにスキップできます。 また、[goto](goto.md)、[return](return.md)、[throw](throw.md) ステートメントのいずれかを使って `foreach` ループを終了することもできます。

`foreach` ステートメントを `null` に適用した場合、<xref:System.NullReferenceException> がスローされます。 `foreach` ステートメントのソース コレクションが空の場合、`foreach` ループの本体は実行されず、スキップされます。

## <a name="type-of-an-iteration-variable"></a>繰り返し変数の型

次のコードに示すように、`var` キーワードを使用して、コンパイラによって `foreach` ステートメントで繰り返し変数の型が推論されるようにすることができます。

```csharp
foreach (var item in collection) { }
```

次のコードに示すように、繰り返し変数の型を明示的に指定することもできます。

```csharp
IEnumerable<T> collection = new T[5];
foreach (V item in collection) { }
```

前の形式では、コレクション要素の型 `T` は、繰り返し変数の型 `V` に暗黙的または明示的に変換できる必要があります。 `T` から `V` への明示的な変換が実行時に失敗した場合、`foreach` ステートメントから <xref:System.InvalidCastException> がスローされます。 たとえば、`T` が非シール クラス型の場合、`V` は任意のインターフェイス型にすることができ、`T` で実装されないものにすることもできます。 実行時に、コレクション要素の型は `T` から派生したものである可能性があり、実際には `V` を実装します。 そうでない場合は、<xref:System.InvalidCastException> がスローされます。

## <a name="c-language-specification"></a>C# 言語仕様

詳細については、「[C# 言語仕様](~/_csharplang/spec/introduction.md)」の [foreach ステートメント](~/_csharplang/spec/statements.md#the-foreach-statement)に関するセクションを参照してください。

## <a name="see-also"></a>関連項目

- [C# リファレンス](../index.md)
- [C# キーワード](index.md)
- [配列での foreach の使用](../../programming-guide/arrays/using-foreach-with-arrays.md)
- [for ステートメント](for.md)
