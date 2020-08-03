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
# <a name="foreach-in-c-reference"></a><span data-ttu-id="c78fe-102">foreach、in (C# リファレンス)</span><span class="sxs-lookup"><span data-stu-id="c78fe-102">foreach, in (C# reference)</span></span>

<span data-ttu-id="c78fe-103">`foreach` ステートメントは、次の例のように、<xref:System.Collections.IEnumerable?displayProperty=nameWithType> または <xref:System.Collections.Generic.IEnumerable%601?displayProperty=nameWithType> インターフェイスを実装している型のインスタンス内の要素ごとに、ステートメントまたはステートメントのブロックを実行します。</span><span class="sxs-lookup"><span data-stu-id="c78fe-103">The `foreach` statement executes a statement or a block of statements for each element in an instance of the type that implements the <xref:System.Collections.IEnumerable?displayProperty=nameWithType> or <xref:System.Collections.Generic.IEnumerable%601?displayProperty=nameWithType> interface, as the following example shows:</span></span>

:::code language="csharp" source="snippets/IterationKeywordsExamples.cs" id="1" interactive="try-dotnet-method" :::

<span data-ttu-id="c78fe-104">`foreach` ステートメントは、これらの型に制限されません。</span><span class="sxs-lookup"><span data-stu-id="c78fe-104">The `foreach` statement isn't limited to those types.</span></span> <span data-ttu-id="c78fe-105">これは次の条件を満たす任意の型のインスタンスと共に使用できます。</span><span class="sxs-lookup"><span data-stu-id="c78fe-105">You can use it with an instance of any type that satisfies the following conditions:</span></span>

- <span data-ttu-id="c78fe-106">戻り値の型がクラス、構造体、インターフェイス型のいずれかである、パラメーターなしのパブリック メソッド `GetEnumerator` がある型。</span><span class="sxs-lookup"><span data-stu-id="c78fe-106">a type has the public parameterless `GetEnumerator` method whose return type is either class, struct, or interface type,</span></span>
- <span data-ttu-id="c78fe-107">`GetEnumerator` メソッドの戻り値の型が、パブリック プロパティ `Current` と、戻り値の型が <xref:System.Boolean> であるパラメーターなしのパブリック メソッド `MoveNext` を持っている。</span><span class="sxs-lookup"><span data-stu-id="c78fe-107">the return type of the `GetEnumerator` method has the public `Current` property and the public parameterless `MoveNext` method whose return type is <xref:System.Boolean>.</span></span>

<span data-ttu-id="c78fe-108">次の例では、何のインターフェイスも実装していない <xref:System.Span%601?displayProperty=nameWithType> 型のインスタンスを使用して、`foreach` ステートメントを使用します。</span><span class="sxs-lookup"><span data-stu-id="c78fe-108">The following example uses the `foreach` statement with an instance of the <xref:System.Span%601?displayProperty=nameWithType> type, which doesn't implement any interfaces:</span></span>

:::code language="csharp" source="snippets/IterationKeywordsExamples.cs" id="2" :::

<span data-ttu-id="c78fe-109">C# 7.3 以降、列挙子の `Current` プロパティによって、[参照戻り値](ref.md#reference-return-values) (`ref T`。この場合、`T` はコレクション要素の型です) が返される場合、次の例のように、`ref` または `ref readonly` 修飾子を使用して繰り返し変数を宣言することができます。</span><span class="sxs-lookup"><span data-stu-id="c78fe-109">Beginning with C# 7.3, if the enumerator's `Current` property returns a [reference return value](ref.md#reference-return-values) (`ref T` where `T` is the type of a collection element), you can declare an iteration variable with the `ref` or `ref readonly` modifier, as the following example shows:</span></span>

:::code language="csharp" source="snippets/IterationKeywordsExamples.cs" id="RefSpan" :::

<span data-ttu-id="c78fe-110">C# 8.0 以降、`await foreach` ステートメントを使用して、データの非同期ストリーム、つまり、<xref:System.Collections.Generic.IAsyncEnumerable%601> インターフェイスを実装するコレクション型を使用できます。</span><span class="sxs-lookup"><span data-stu-id="c78fe-110">Beginning with C# 8.0, you can use the `await foreach` statement to consume an asynchronous stream of data, that is, the collection type that implements the <xref:System.Collections.Generic.IAsyncEnumerable%601> interface.</span></span> <span data-ttu-id="c78fe-111">次の要素が非同期で取得されている限り、ループの各反復は中断される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="c78fe-111">Each iteration of the loop may be suspended while the next element is retrieved asynchronously.</span></span> <span data-ttu-id="c78fe-112">`await foreach` ステートメントを使用する方法の例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="c78fe-112">The following example shows how to use the `await foreach` statement:</span></span>

:::code language="csharp" source="snippets/IterationKeywordsExamples.cs" id="AwaitForeach" :::

<span data-ttu-id="c78fe-113">既定では、ストリーム要素はキャプチャされたコンテキストで処理されます。</span><span class="sxs-lookup"><span data-stu-id="c78fe-113">By default, stream elements are processed in the captured context.</span></span> <span data-ttu-id="c78fe-114">コンテキストのキャプチャを無効にする場合は、<xref:System.Threading.Tasks.TaskAsyncEnumerableExtensions.ConfigureAwait%2A?displayProperty=nameWithType> 拡張メソッドを使用します。</span><span class="sxs-lookup"><span data-stu-id="c78fe-114">If you want to disable capturing of the context, use the <xref:System.Threading.Tasks.TaskAsyncEnumerableExtensions.ConfigureAwait%2A?displayProperty=nameWithType> extension method.</span></span> <span data-ttu-id="c78fe-115">同期コンテキストおよび現在のコンテキストのキャプチャについての詳細は、「[タスク ベースの非同期パターンの利用](../../../standard/asynchronous-programming-patterns/consuming-the-task-based-asynchronous-pattern.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c78fe-115">For more information about synchronization contexts and capturing the current context, see [Consuming the Task-based asynchronous pattern](../../../standard/asynchronous-programming-patterns/consuming-the-task-based-asynchronous-pattern.md).</span></span> <span data-ttu-id="c78fe-116">非同期ストリームの詳細については、「[C# 8.0 の新機能](../../whats-new/csharp-8.md)」の記事の「[非同期ストリーム](../../whats-new/csharp-8.md#asynchronous-streams)」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="c78fe-116">For more information about asynchronous streams, see the [Asynchronous streams](../../whats-new/csharp-8.md#asynchronous-streams) section of the [What's new in C# 8.0](../../whats-new/csharp-8.md) article.</span></span>

<span data-ttu-id="c78fe-117">`foreach` ステートメント ブロック内の任意の位置で、[break](break.md) ステートメントを使ってループから抜けることができます。または、[continue](continue.md) ステートメントを使って、ループ内の次の繰り返しにスキップできます。</span><span class="sxs-lookup"><span data-stu-id="c78fe-117">At any point within the `foreach` statement block, you can break out of the loop by using the [break](break.md) statement, or step to the next iteration in the loop by using the [continue](continue.md) statement.</span></span> <span data-ttu-id="c78fe-118">また、[goto](goto.md)、[return](return.md)、[throw](throw.md) ステートメントのいずれかを使って `foreach` ループを終了することもできます。</span><span class="sxs-lookup"><span data-stu-id="c78fe-118">You can also exit a `foreach` loop by the [goto](goto.md), [return](return.md), or [throw](throw.md) statements.</span></span>

<span data-ttu-id="c78fe-119">`foreach` ステートメントを `null` に適用した場合、<xref:System.NullReferenceException> がスローされます。</span><span class="sxs-lookup"><span data-stu-id="c78fe-119">If the `foreach` statement is applied to `null`, a <xref:System.NullReferenceException> is thrown.</span></span> <span data-ttu-id="c78fe-120">`foreach` ステートメントのソース コレクションが空の場合、`foreach` ループの本体は実行されず、スキップされます。</span><span class="sxs-lookup"><span data-stu-id="c78fe-120">If the source collection of the `foreach` statement is empty, the body of the `foreach` loop isn't executed and skipped.</span></span>

## <a name="type-of-an-iteration-variable"></a><span data-ttu-id="c78fe-121">繰り返し変数の型</span><span class="sxs-lookup"><span data-stu-id="c78fe-121">Type of an iteration variable</span></span>

<span data-ttu-id="c78fe-122">次のコードに示すように、`var` キーワードを使用して、コンパイラによって `foreach` ステートメントで繰り返し変数の型が推論されるようにすることができます。</span><span class="sxs-lookup"><span data-stu-id="c78fe-122">You can use the `var` keyword to let the compiler infer the type of an iteration variable in the `foreach` statement, as the following code shows:</span></span>

```csharp
foreach (var item in collection) { }
```

<span data-ttu-id="c78fe-123">次のコードに示すように、繰り返し変数の型を明示的に指定することもできます。</span><span class="sxs-lookup"><span data-stu-id="c78fe-123">You can also explicitly specify the type of an iteration variable, as the following code shows:</span></span>

```csharp
IEnumerable<T> collection = new T[5];
foreach (V item in collection) { }
```

<span data-ttu-id="c78fe-124">前の形式では、コレクション要素の型 `T` は、繰り返し変数の型 `V` に暗黙的または明示的に変換できる必要があります。</span><span class="sxs-lookup"><span data-stu-id="c78fe-124">In the preceding form, type `T` of a collection element must be implicitly or explicitly convertible to type `V` of an iteration variable.</span></span> <span data-ttu-id="c78fe-125">`T` から `V` への明示的な変換が実行時に失敗した場合、`foreach` ステートメントから <xref:System.InvalidCastException> がスローされます。</span><span class="sxs-lookup"><span data-stu-id="c78fe-125">If an explicit conversion from `T` to `V` fails at run time, the `foreach` statement throws an <xref:System.InvalidCastException>.</span></span> <span data-ttu-id="c78fe-126">たとえば、`T` が非シール クラス型の場合、`V` は任意のインターフェイス型にすることができ、`T` で実装されないものにすることもできます。</span><span class="sxs-lookup"><span data-stu-id="c78fe-126">For example, if `T` is a non-sealed class type, `V` can be any interface type, even the one that `T` doesn't implement.</span></span> <span data-ttu-id="c78fe-127">実行時に、コレクション要素の型は `T` から派生したものである可能性があり、実際には `V` を実装します。</span><span class="sxs-lookup"><span data-stu-id="c78fe-127">At run time, the type of a collection element may be the one that derives from `T` and actually implements `V`.</span></span> <span data-ttu-id="c78fe-128">そうでない場合は、<xref:System.InvalidCastException> がスローされます。</span><span class="sxs-lookup"><span data-stu-id="c78fe-128">If that's not the case, an <xref:System.InvalidCastException> is thrown.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="c78fe-129">C# 言語仕様</span><span class="sxs-lookup"><span data-stu-id="c78fe-129">C# language specification</span></span>

<span data-ttu-id="c78fe-130">詳細については、「[C# 言語仕様](~/_csharplang/spec/introduction.md)」の [foreach ステートメント](~/_csharplang/spec/statements.md#the-foreach-statement)に関するセクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="c78fe-130">For more information, see [The foreach statement](~/_csharplang/spec/statements.md#the-foreach-statement) section of the [C# language specification](~/_csharplang/spec/introduction.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="c78fe-131">関連項目</span><span class="sxs-lookup"><span data-stu-id="c78fe-131">See also</span></span>

- [<span data-ttu-id="c78fe-132">C# リファレンス</span><span class="sxs-lookup"><span data-stu-id="c78fe-132">C# reference</span></span>](../index.md)
- [<span data-ttu-id="c78fe-133">C# キーワード</span><span class="sxs-lookup"><span data-stu-id="c78fe-133">C# keywords</span></span>](index.md)
- [<span data-ttu-id="c78fe-134">配列での foreach の使用</span><span class="sxs-lookup"><span data-stu-id="c78fe-134">Using foreach with arrays</span></span>](../../programming-guide/arrays/using-foreach-with-arrays.md)
- [<span data-ttu-id="c78fe-135">for ステートメント</span><span class="sxs-lookup"><span data-stu-id="c78fe-135">for statement</span></span>](for.md)
