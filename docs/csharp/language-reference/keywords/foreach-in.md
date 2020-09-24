---
description: foreach、in (C# リファレンス)
title: C# foreach ステートメント
ms.date: 09/18/2020
f1_keywords:
- foreach
- foreach_CSharpKeyword
helpviewer_keywords:
- foreach keyword [C#]
- foreach statement [C#]
- in keyword [C#]
ms.assetid: 5a9c5ddc-5fd3-457a-9bb6-9abffcd874ec
ms.openlocfilehash: ea8a6f86595348a32b707caf9782f84147fefc87
ms.sourcegitcommit: 43ed174f085840ca18a791dc89fe833174da766d
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/21/2020
ms.locfileid: "90828891"
---
# <a name="foreach-in-c-reference"></a><span data-ttu-id="5c20d-103">foreach、in (C# リファレンス)</span><span class="sxs-lookup"><span data-stu-id="5c20d-103">foreach, in (C# reference)</span></span>

<span data-ttu-id="5c20d-104">`foreach` ステートメントは、次の例のように、<xref:System.Collections.IEnumerable?displayProperty=nameWithType> または <xref:System.Collections.Generic.IEnumerable%601?displayProperty=nameWithType> インターフェイスを実装している型のインスタンス内の要素ごとに、ステートメントまたはステートメントのブロックを実行します。</span><span class="sxs-lookup"><span data-stu-id="5c20d-104">The `foreach` statement executes a statement or a block of statements for each element in an instance of the type that implements the <xref:System.Collections.IEnumerable?displayProperty=nameWithType> or <xref:System.Collections.Generic.IEnumerable%601?displayProperty=nameWithType> interface, as the following example shows:</span></span>

:::code language="csharp" source="snippets/IterationKeywordsExamples.cs" id="1" interactive="try-dotnet-method" :::

<span data-ttu-id="5c20d-105">`foreach` ステートメントは、これらの型に制限されません。</span><span class="sxs-lookup"><span data-stu-id="5c20d-105">The `foreach` statement isn't limited to those types.</span></span> <span data-ttu-id="5c20d-106">これは次の条件を満たす任意の型のインスタンスと共に使用できます。</span><span class="sxs-lookup"><span data-stu-id="5c20d-106">You can use it with an instance of any type that satisfies the following conditions:</span></span>

- <span data-ttu-id="5c20d-107">戻り値の型がクラス、構造体、インターフェイス型のいずれかである、パラメーターなしのパブリック メソッド `GetEnumerator` がある型。</span><span class="sxs-lookup"><span data-stu-id="5c20d-107">A type has the public parameterless `GetEnumerator` method whose return type is either class, struct, or interface type.</span></span> <span data-ttu-id="5c20d-108">C# 9.0 以降では、`GetEnumerator` メソッドを型の[拡張メソッド](../../programming-guide/classes-and-structs/extension-methods.md)にすることができます。</span><span class="sxs-lookup"><span data-stu-id="5c20d-108">Beginning with C# 9.0, the `GetEnumerator` method can be a type's [extension method](../../programming-guide/classes-and-structs/extension-methods.md).</span></span>
- <span data-ttu-id="5c20d-109">`GetEnumerator` メソッドの戻り値の型に、パブリック プロパティ `Current` と、戻り値の型が <xref:System.Boolean> であるパラメーターなしのパブリック メソッド `MoveNext` がある。</span><span class="sxs-lookup"><span data-stu-id="5c20d-109">The return type of the `GetEnumerator` method has the public `Current` property and the public parameterless `MoveNext` method whose return type is <xref:System.Boolean>.</span></span>

<span data-ttu-id="5c20d-110">次の例では、何のインターフェイスも実装していない <xref:System.Span%601?displayProperty=nameWithType> 型のインスタンスを使用して、`foreach` ステートメントを使用します。</span><span class="sxs-lookup"><span data-stu-id="5c20d-110">The following example uses the `foreach` statement with an instance of the <xref:System.Span%601?displayProperty=nameWithType> type, which doesn't implement any interfaces:</span></span>

:::code language="csharp" source="snippets/IterationKeywordsExamples.cs" id="2" :::

<span data-ttu-id="5c20d-111">C# 7.3 以降、列挙子の `Current` プロパティによって、[参照戻り値](ref.md#reference-return-values) (`ref T`。この場合、`T` はコレクション要素の型です) が返される場合、次の例のように、`ref` または `ref readonly` 修飾子を使用して繰り返し変数を宣言することができます。</span><span class="sxs-lookup"><span data-stu-id="5c20d-111">Beginning with C# 7.3, if the enumerator's `Current` property returns a [reference return value](ref.md#reference-return-values) (`ref T` where `T` is the type of a collection element), you can declare an iteration variable with the `ref` or `ref readonly` modifier, as the following example shows:</span></span>

:::code language="csharp" source="snippets/IterationKeywordsExamples.cs" id="RefSpan" :::

<span data-ttu-id="5c20d-112">C# 8.0 以降、`await foreach` ステートメントを使用して、データの非同期ストリーム、つまり、<xref:System.Collections.Generic.IAsyncEnumerable%601> インターフェイスを実装するコレクション型を使用できます。</span><span class="sxs-lookup"><span data-stu-id="5c20d-112">Beginning with C# 8.0, you can use the `await foreach` statement to consume an asynchronous stream of data, that is, the collection type that implements the <xref:System.Collections.Generic.IAsyncEnumerable%601> interface.</span></span> <span data-ttu-id="5c20d-113">次の要素が非同期で取得されている限り、ループの各反復は中断される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="5c20d-113">Each iteration of the loop may be suspended while the next element is retrieved asynchronously.</span></span> <span data-ttu-id="5c20d-114">`await foreach` ステートメントを使用する方法の例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="5c20d-114">The following example shows how to use the `await foreach` statement:</span></span>

:::code language="csharp" source="snippets/IterationKeywordsExamples.cs" id="AwaitForeach" :::

<span data-ttu-id="5c20d-115">既定では、ストリーム要素はキャプチャされたコンテキストで処理されます。</span><span class="sxs-lookup"><span data-stu-id="5c20d-115">By default, stream elements are processed in the captured context.</span></span> <span data-ttu-id="5c20d-116">コンテキストのキャプチャを無効にする場合は、<xref:System.Threading.Tasks.TaskAsyncEnumerableExtensions.ConfigureAwait%2A?displayProperty=nameWithType> 拡張メソッドを使用します。</span><span class="sxs-lookup"><span data-stu-id="5c20d-116">If you want to disable capturing of the context, use the <xref:System.Threading.Tasks.TaskAsyncEnumerableExtensions.ConfigureAwait%2A?displayProperty=nameWithType> extension method.</span></span> <span data-ttu-id="5c20d-117">同期コンテキストおよび現在のコンテキストのキャプチャについての詳細は、「[タスク ベースの非同期パターンの利用](../../../standard/asynchronous-programming-patterns/consuming-the-task-based-asynchronous-pattern.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5c20d-117">For more information about synchronization contexts and capturing the current context, see [Consuming the Task-based asynchronous pattern](../../../standard/asynchronous-programming-patterns/consuming-the-task-based-asynchronous-pattern.md).</span></span> <span data-ttu-id="5c20d-118">非同期ストリームの詳細については、「[C# 8.0 の新機能](../../whats-new/csharp-8.md)」の記事の「[非同期ストリーム](../../whats-new/csharp-8.md#asynchronous-streams)」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="5c20d-118">For more information about asynchronous streams, see the [Asynchronous streams](../../whats-new/csharp-8.md#asynchronous-streams) section of the [What's new in C# 8.0](../../whats-new/csharp-8.md) article.</span></span>

<span data-ttu-id="5c20d-119">`foreach` ステートメント ブロック内の任意の位置で、[break](break.md) ステートメントを使ってループから抜けることができます。または、[continue](continue.md) ステートメントを使って、ループ内の次の繰り返しにスキップできます。</span><span class="sxs-lookup"><span data-stu-id="5c20d-119">At any point within the `foreach` statement block, you can break out of the loop by using the [break](break.md) statement, or step to the next iteration in the loop by using the [continue](continue.md) statement.</span></span> <span data-ttu-id="5c20d-120">また、[goto](goto.md)、[return](return.md)、[throw](throw.md) ステートメントのいずれかを使って `foreach` ループを終了することもできます。</span><span class="sxs-lookup"><span data-stu-id="5c20d-120">You can also exit a `foreach` loop by the [goto](goto.md), [return](return.md), or [throw](throw.md) statements.</span></span>

<span data-ttu-id="5c20d-121">`foreach` ステートメントを `null` に適用した場合、<xref:System.NullReferenceException> がスローされます。</span><span class="sxs-lookup"><span data-stu-id="5c20d-121">If the `foreach` statement is applied to `null`, a <xref:System.NullReferenceException> is thrown.</span></span> <span data-ttu-id="5c20d-122">`foreach` ステートメントのソース コレクションが空の場合、`foreach` ループの本体は実行されず、スキップされます。</span><span class="sxs-lookup"><span data-stu-id="5c20d-122">If the source collection of the `foreach` statement is empty, the body of the `foreach` loop isn't executed and skipped.</span></span>

## <a name="type-of-an-iteration-variable"></a><span data-ttu-id="5c20d-123">繰り返し変数の型</span><span class="sxs-lookup"><span data-stu-id="5c20d-123">Type of an iteration variable</span></span>

<span data-ttu-id="5c20d-124">次のコードに示すように、`var` キーワードを使用して、コンパイラによって `foreach` ステートメントで繰り返し変数の型が推論されるようにすることができます。</span><span class="sxs-lookup"><span data-stu-id="5c20d-124">You can use the `var` keyword to let the compiler infer the type of an iteration variable in the `foreach` statement, as the following code shows:</span></span>

```csharp
foreach (var item in collection) { }
```

<span data-ttu-id="5c20d-125">次のコードに示すように、繰り返し変数の型を明示的に指定することもできます。</span><span class="sxs-lookup"><span data-stu-id="5c20d-125">You can also explicitly specify the type of an iteration variable, as the following code shows:</span></span>

```csharp
IEnumerable<T> collection = new T[5];
foreach (V item in collection) { }
```

<span data-ttu-id="5c20d-126">前の形式では、コレクション要素の型 `T` は、繰り返し変数の型 `V` に暗黙的または明示的に変換できる必要があります。</span><span class="sxs-lookup"><span data-stu-id="5c20d-126">In the preceding form, type `T` of a collection element must be implicitly or explicitly convertible to type `V` of an iteration variable.</span></span> <span data-ttu-id="5c20d-127">`T` から `V` への明示的な変換が実行時に失敗した場合、`foreach` ステートメントから <xref:System.InvalidCastException> がスローされます。</span><span class="sxs-lookup"><span data-stu-id="5c20d-127">If an explicit conversion from `T` to `V` fails at run time, the `foreach` statement throws an <xref:System.InvalidCastException>.</span></span> <span data-ttu-id="5c20d-128">たとえば、`T` が非シール クラス型の場合、`V` は任意のインターフェイス型にすることができ、`T` で実装されないものにすることもできます。</span><span class="sxs-lookup"><span data-stu-id="5c20d-128">For example, if `T` is a non-sealed class type, `V` can be any interface type, even the one that `T` doesn't implement.</span></span> <span data-ttu-id="5c20d-129">実行時に、コレクション要素の型は `T` から派生したものである可能性があり、実際には `V` を実装します。</span><span class="sxs-lookup"><span data-stu-id="5c20d-129">At run time, the type of a collection element may be the one that derives from `T` and actually implements `V`.</span></span> <span data-ttu-id="5c20d-130">そうでない場合は、<xref:System.InvalidCastException> がスローされます。</span><span class="sxs-lookup"><span data-stu-id="5c20d-130">If that's not the case, an <xref:System.InvalidCastException> is thrown.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="5c20d-131">C# 言語仕様</span><span class="sxs-lookup"><span data-stu-id="5c20d-131">C# language specification</span></span>

<span data-ttu-id="5c20d-132">詳細については、「[C# 言語仕様](~/_csharplang/spec/introduction.md)」の [foreach ステートメント](~/_csharplang/spec/statements.md#the-foreach-statement)に関するセクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="5c20d-132">For more information, see [The foreach statement](~/_csharplang/spec/statements.md#the-foreach-statement) section of the [C# language specification](~/_csharplang/spec/introduction.md).</span></span>

<span data-ttu-id="5c20d-133">C# 8.0 以降に追加された機能の詳細については、機能の提案に関する次の記述を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5c20d-133">For more information about features added in C# 8.0 and later, see the following feature proposal notes:</span></span>

- [<span data-ttu-id="5c20d-134">非同期ストリーム (C# 8.0)</span><span class="sxs-lookup"><span data-stu-id="5c20d-134">Async streams (C# 8.0)</span></span>](~/_csharplang/proposals/csharp-8.0/async-streams.md)
- [<span data-ttu-id="5c20d-135">`foreach` ループに対する拡張機能 `GetEnumerator` のサポート (C# 9.0)</span><span class="sxs-lookup"><span data-stu-id="5c20d-135">Extension `GetEnumerator` support for `foreach` loops (C# 9.0)</span></span>](~/_csharplang/proposals/csharp-9.0/extension-getenumerator.md)

## <a name="see-also"></a><span data-ttu-id="5c20d-136">関連項目</span><span class="sxs-lookup"><span data-stu-id="5c20d-136">See also</span></span>

- [<span data-ttu-id="5c20d-137">C# リファレンス</span><span class="sxs-lookup"><span data-stu-id="5c20d-137">C# reference</span></span>](../index.md)
- [<span data-ttu-id="5c20d-138">C# キーワード</span><span class="sxs-lookup"><span data-stu-id="5c20d-138">C# keywords</span></span>](index.md)
- [<span data-ttu-id="5c20d-139">配列での foreach の使用</span><span class="sxs-lookup"><span data-stu-id="5c20d-139">Using foreach with arrays</span></span>](../../programming-guide/arrays/using-foreach-with-arrays.md)
- [<span data-ttu-id="5c20d-140">for ステートメント</span><span class="sxs-lookup"><span data-stu-id="5c20d-140">for statement</span></span>](for.md)
