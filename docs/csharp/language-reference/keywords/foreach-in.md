---
title: C# foreach ステートメント
ms.date: 05/17/2019
f1_keywords:
- foreach
- foreach_CSharpKeyword
helpviewer_keywords:
- foreach keyword [C#]
- foreach statement [C#]
- in keyword [C#]
ms.assetid: 5a9c5ddc-5fd3-457a-9bb6-9abffcd874ec
ms.openlocfilehash: dbe4f4e95c2b99f1be47885e39d51db81ba3a97d
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/14/2020
ms.locfileid: "79173706"
---
# <a name="foreach-in-c-reference"></a><span data-ttu-id="1c388-102">foreach、in (C# リファレンス)</span><span class="sxs-lookup"><span data-stu-id="1c388-102">foreach, in (C# reference)</span></span>

<span data-ttu-id="1c388-103">`foreach` ステートメントは、<xref:System.Collections.IEnumerable?displayProperty=nameWithType> または <xref:System.Collections.Generic.IEnumerable%601?displayProperty=nameWithType> インターフェイスを実装している型のインスタンス内の要素ごとに、ステートメントまたはステートメントのブロックを実行します。</span><span class="sxs-lookup"><span data-stu-id="1c388-103">The `foreach` statement executes a statement or a block of statements for each element in an instance of the type that implements the <xref:System.Collections.IEnumerable?displayProperty=nameWithType> or <xref:System.Collections.Generic.IEnumerable%601?displayProperty=nameWithType> interface.</span></span> <span data-ttu-id="1c388-104">`foreach` ステートメントはこのような型にのみ限定されるものではありません。次の条件を満たす任意の型のインスタンスに適用できます。</span><span class="sxs-lookup"><span data-stu-id="1c388-104">The `foreach` statement is not limited to those types and can be applied to an instance of any type that satisfies the following conditions:</span></span>

- <span data-ttu-id="1c388-105">戻り値の型がクラス、構造体、インターフェイス型のいずれかである、パラメーターなしのパブリック メソッド `GetEnumerator` を持っている。</span><span class="sxs-lookup"><span data-stu-id="1c388-105">has the public parameterless `GetEnumerator` method whose return type is either class, struct, or interface type,</span></span>
- <span data-ttu-id="1c388-106">`GetEnumerator` メソッドの戻り値の型が、パブリック プロパティ `Current` と、戻り値の型が <xref:System.Boolean> であるパラメーターなしのパブリック メソッド `MoveNext` を持っている。</span><span class="sxs-lookup"><span data-stu-id="1c388-106">the return type of the `GetEnumerator` method has the public `Current` property and the public parameterless `MoveNext` method whose return type is <xref:System.Boolean>.</span></span>

<span data-ttu-id="1c388-107">C# 7.3 以降、列挙子の `Current` プロパティが、[参照戻り値](ref.md#reference-return-values) (`ref T``T` はコレクション要素の種類です) を返す場合、`ref` または `ref readonly` 修飾子を使用して繰り返し変数を宣言することができます。</span><span class="sxs-lookup"><span data-stu-id="1c388-107">Beginning with C# 7.3, if the enumerator's `Current` property returns a [reference return value](ref.md#reference-return-values) (`ref T` where `T` is the type of the collection element), you can declare the iteration variable with the `ref` or `ref readonly` modifier.</span></span>

<span data-ttu-id="1c388-108">C# 8.0 以降では、コレクション型で `await` インターフェイスが実装されている場合、`foreach` 演算子が <xref:System.Collections.Generic.IAsyncEnumerable%601> ステートメントに適用される場合があります。</span><span class="sxs-lookup"><span data-stu-id="1c388-108">Beginning with C# 8.0, the `await` operator may be applied to the `foreach` statement when the collection type implements the <xref:System.Collections.Generic.IAsyncEnumerable%601> interface.</span></span> <span data-ttu-id="1c388-109">次の要素が非同期で取得されている限り、ループの各反復は中断される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="1c388-109">Each iteration of the loop may be suspended while the next element is retrieved asynchronously.</span></span> <span data-ttu-id="1c388-110">既定では、ストリーム要素はキャプチャされたコンテキストで処理されます。</span><span class="sxs-lookup"><span data-stu-id="1c388-110">By default, stream elements are processed in the captured context.</span></span> <span data-ttu-id="1c388-111">コンテキストのキャプチャを無効にする場合は、<xref:System.Threading.Tasks.TaskAsyncEnumerableExtensions.ConfigureAwait%2A?displayProperty=nameWithType> 拡張メソッドを使用します。</span><span class="sxs-lookup"><span data-stu-id="1c388-111">If you want to disable capturing of the context, use the <xref:System.Threading.Tasks.TaskAsyncEnumerableExtensions.ConfigureAwait%2A?displayProperty=nameWithType> extension method.</span></span> <span data-ttu-id="1c388-112">同期コンテキストについて、および現在のコンテキストのキャプチャについての詳細は、「[タスク ベースの非同期パターンの利用](../../../standard/asynchronous-programming-patterns/consuming-the-task-based-asynchronous-pattern.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1c388-112">For more information about synchronization contexts and capturing the current context, see the article on [consuming the Task-based asynchronous pattern](../../../standard/asynchronous-programming-patterns/consuming-the-task-based-asynchronous-pattern.md).</span></span>

<span data-ttu-id="1c388-113">`foreach` ステートメント ブロック内の任意の位置で、[break](break.md) ステートメントを使ってループから抜けることができます。または、[continue](continue.md) ステートメントを使って、ループ内の次の繰り返しにスキップできます。</span><span class="sxs-lookup"><span data-stu-id="1c388-113">At any point within the `foreach` statement block, you can break out of the loop by using the [break](break.md) statement, or step to the next iteration in the loop by using the [continue](continue.md) statement.</span></span> <span data-ttu-id="1c388-114">また、[goto](goto.md)、[return](return.md)、[throw](throw.md) ステートメントのいずれかを使って `foreach` ループを終了することもできます。</span><span class="sxs-lookup"><span data-stu-id="1c388-114">You also can exit a `foreach` loop by the [goto](goto.md), [return](return.md), or [throw](throw.md) statements.</span></span>

<span data-ttu-id="1c388-115">`foreach` ステートメントを `null` に適用した場合、<xref:System.NullReferenceException> がスローされます。</span><span class="sxs-lookup"><span data-stu-id="1c388-115">If the `foreach` statement is applied to `null`, a <xref:System.NullReferenceException> is thrown.</span></span> <span data-ttu-id="1c388-116">`foreach` ステートメントのソース コレクションが空の場合、`foreach` ループの本体は実行されず、スキップされます。</span><span class="sxs-lookup"><span data-stu-id="1c388-116">If the source collection of the `foreach` statement is empty, the body of the `foreach` loop isn't executed and skipped.</span></span>

## <a name="examples"></a><span data-ttu-id="1c388-117">使用例</span><span class="sxs-lookup"><span data-stu-id="1c388-117">Examples</span></span>

[!INCLUDE[interactive-note](~/includes/csharp-interactive-note.md)]

<span data-ttu-id="1c388-118">次の例では、<xref:System.Collections.Generic.IEnumerable%601> インターフェイスを実装する <xref:System.Collections.Generic.List%601> 型のインスタンスを使用して、`foreach` ステートメントの使用方法を示します。</span><span class="sxs-lookup"><span data-stu-id="1c388-118">The following example shows usage of the `foreach` statement with an instance of the <xref:System.Collections.Generic.List%601> type that implements the <xref:System.Collections.Generic.IEnumerable%601> interface:</span></span>

[!code-csharp-interactive[list example](~/samples/snippets/csharp/keywords/IterationKeywordsExamples.cs#1)]

<span data-ttu-id="1c388-119">次の例では、何のインターフェイスも実装していない <xref:System.Span%601?displayProperty=nameWithType> 型のインスタンスを使用して、`foreach` ステートメントを使用します。</span><span class="sxs-lookup"><span data-stu-id="1c388-119">The next example uses the `foreach` statement with an instance of the <xref:System.Span%601?displayProperty=nameWithType> type, which doesn't implement any interfaces:</span></span>

[!code-csharp[span example](~/samples/snippets/csharp/keywords/IterationKeywordsExamples.cs#2)]

<span data-ttu-id="1c388-120">次の例では、stackalloc 配列内の各項目の値を設定するために、`ref` 繰り返し変数を使用します。</span><span class="sxs-lookup"><span data-stu-id="1c388-120">The following example uses a `ref` iteration variable to set the value of each item in a stackalloc array.</span></span> <span data-ttu-id="1c388-121">`ref readonly` バージョンは、すべての値を出力するコレクションを反復処理します。</span><span class="sxs-lookup"><span data-stu-id="1c388-121">The `ref readonly` version iterates the collection to print all the values.</span></span> <span data-ttu-id="1c388-122">`readonly` 宣言では、暗黙のローカル変数宣言を使用します。</span><span class="sxs-lookup"><span data-stu-id="1c388-122">The `readonly` declaration uses an implicit local variable declaration.</span></span> <span data-ttu-id="1c388-123">暗黙の変数宣言は、`ref` または `ref readonly` 宣言で使用でき、変数の宣言を明示的に型指定できます。</span><span class="sxs-lookup"><span data-stu-id="1c388-123">Implicit variable declarations can be used with either `ref` or `ref readonly` declarations, as can explicitly typed variable declarations.</span></span>

[!code-csharp[ref span example](~/samples/snippets/csharp/keywords/IterationKeywordsExamples.cs#RefSpan)]

<span data-ttu-id="1c388-124">次の例では、`await foreach` を使用して、各要素を非同期に生成するコレクションを反復処理します。</span><span class="sxs-lookup"><span data-stu-id="1c388-124">The following example uses `await foreach` to iterate a collection that generates each element asynchronously:</span></span>

[!code-csharp[ref span example](~/samples/snippets/csharp/keywords/IterationKeywordsExamples.cs#AwaitForeach)]

## <a name="c-language-specification"></a><span data-ttu-id="1c388-125">C# 言語仕様</span><span class="sxs-lookup"><span data-stu-id="1c388-125">C# language specification</span></span>

<span data-ttu-id="1c388-126">詳細については、「[C# 言語仕様](/dotnet/csharp/language-reference/language-specification/introduction)」の [foreach ステートメント](~/_csharplang/spec/statements.md#the-foreach-statement)に関するセクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="1c388-126">For more information, see [The foreach statement](~/_csharplang/spec/statements.md#the-foreach-statement) section of the [C# language specification](/dotnet/csharp/language-reference/language-specification/introduction).</span></span>

## <a name="see-also"></a><span data-ttu-id="1c388-127">関連項目</span><span class="sxs-lookup"><span data-stu-id="1c388-127">See also</span></span>

- [<span data-ttu-id="1c388-128">C# リファレンス</span><span class="sxs-lookup"><span data-stu-id="1c388-128">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="1c388-129">C# プログラミング ガイド</span><span class="sxs-lookup"><span data-stu-id="1c388-129">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="1c388-130">C# のキーワード</span><span class="sxs-lookup"><span data-stu-id="1c388-130">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="1c388-131">配列での foreach の使用</span><span class="sxs-lookup"><span data-stu-id="1c388-131">Using foreach with arrays</span></span>](../../programming-guide/arrays/using-foreach-with-arrays.md)
- [<span data-ttu-id="1c388-132">for ステートメント</span><span class="sxs-lookup"><span data-stu-id="1c388-132">for statement</span></span>](for.md)
