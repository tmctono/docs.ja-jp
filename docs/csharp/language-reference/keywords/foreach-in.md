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
ms.openlocfilehash: 7a1508db23f60cac487e0171c3db7756bc228fd2
ms.sourcegitcommit: c4e9d05644c9cb89de5ce6002723de107ea2e2c4
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/19/2019
ms.locfileid: "65880538"
---
# <a name="foreach-in-c-reference"></a><span data-ttu-id="6960e-102">foreach、in (C# リファレンス)</span><span class="sxs-lookup"><span data-stu-id="6960e-102">foreach, in (C# reference)</span></span>

<span data-ttu-id="6960e-103">`foreach` ステートメントは、<xref:System.Collections.IEnumerable?displayProperty=nameWithType> または <xref:System.Collections.Generic.IEnumerable%601?displayProperty=nameWithType> インターフェイスを実装している型のインスタンス内の要素ごとに、ステートメントまたはステートメントのブロックを実行します。</span><span class="sxs-lookup"><span data-stu-id="6960e-103">The `foreach` statement executes a statement or a block of statements for each element in an instance of the type that implements the <xref:System.Collections.IEnumerable?displayProperty=nameWithType> or <xref:System.Collections.Generic.IEnumerable%601?displayProperty=nameWithType> interface.</span></span> <span data-ttu-id="6960e-104">`foreach` ステートメントはこのような型にのみ限定されるものではありません。次の条件を満たす任意の型のインスタンスに適用できます。</span><span class="sxs-lookup"><span data-stu-id="6960e-104">The `foreach` statement is not limited to those types and can be applied to an instance of any type that satisfies the following conditions:</span></span>

- <span data-ttu-id="6960e-105">戻り値の型がクラス、構造体、インターフェイス型のいずれかである、パラメーターなしのパブリック メソッド `GetEnumerator` を持っている。</span><span class="sxs-lookup"><span data-stu-id="6960e-105">has the public parameterless `GetEnumerator` method whose return type is either class, struct, or interface type,</span></span>
- <span data-ttu-id="6960e-106">`GetEnumerator` メソッドの戻り値の型が、パブリック プロパティ `Current` と、戻り値の型が <xref:System.Boolean> であるパラメーターなしのパブリック メソッド `MoveNext` を持っている。</span><span class="sxs-lookup"><span data-stu-id="6960e-106">the return type of the `GetEnumerator` method has the public `Current` property and the public parameterless `MoveNext` method whose return type is <xref:System.Boolean>.</span></span>

<span data-ttu-id="6960e-107">C# 7.3 以降、列挙子の `Current` プロパティが、[参照戻り値](ref.md#reference-return-values) (`ref T``T` はコレクション要素の種類です) を返す場合、`ref` または `ref readonly` 修飾子を使用して繰り返し変数を宣言することができます。</span><span class="sxs-lookup"><span data-stu-id="6960e-107">Beginning with C# 7.3, if the enumerator's `Current` property returns a [reference return value](ref.md#reference-return-values) (`ref T` where `T` is the type of the collection element), you can declare the iteration variable with the `ref` or `ref readonly` modifier.</span></span>

<span data-ttu-id="6960e-108">`foreach` ステートメント ブロック内の任意の位置で、[break](break.md) ステートメントを使ってループから抜けることができます。または、[continue](continue.md) ステートメントを使って、ループ内の次の繰り返しにスキップできます。</span><span class="sxs-lookup"><span data-stu-id="6960e-108">At any point within the `foreach` statement block, you can break out of the loop by using the [break](break.md) statement, or step to the next iteration in the loop by using the [continue](continue.md) statement.</span></span> <span data-ttu-id="6960e-109">また、[goto](goto.md)、[return](return.md)、[throw](throw.md) ステートメントのいずれかを使って `foreach` ループを終了することもできます。</span><span class="sxs-lookup"><span data-stu-id="6960e-109">You also can exit a `foreach` loop by the [goto](goto.md), [return](return.md), or [throw](throw.md) statements.</span></span>

<span data-ttu-id="6960e-110">`foreach` ステートメントを `null` に適用した場合、<xref:System.NullReferenceException> がスローされます。</span><span class="sxs-lookup"><span data-stu-id="6960e-110">If the `foreach` statement is applied to `null`, a <xref:System.NullReferenceException> is thrown.</span></span> <span data-ttu-id="6960e-111">`foreach` ステートメントのソース コレクションが空の場合、`foreach` ループの本体は実行されず、スキップされます。</span><span class="sxs-lookup"><span data-stu-id="6960e-111">If the source collection of the `foreach` statement is empty, the body of the `foreach` loop is not executed and skipped.</span></span>

## <a name="examples"></a><span data-ttu-id="6960e-112">使用例</span><span class="sxs-lookup"><span data-stu-id="6960e-112">Examples</span></span>

[!INCLUDE[interactive-note](~/includes/csharp-interactive-note.md)]

<span data-ttu-id="6960e-113">次の例では、<xref:System.Collections.Generic.IEnumerable%601> インターフェイスを実装する <xref:System.Collections.Generic.List%601> 型のインスタンスを使用して、`foreach` ステートメントの使用方法を示します。</span><span class="sxs-lookup"><span data-stu-id="6960e-113">The following example shows usage of the `foreach` statement with an instance of the <xref:System.Collections.Generic.List%601> type that implements the <xref:System.Collections.Generic.IEnumerable%601> interface:</span></span>

[!code-csharp-interactive[list example](~/samples/snippets/csharp/keywords/IterationKeywordsExamples.cs#1)]

<span data-ttu-id="6960e-114">次の例では、何のインターフェイスも実装していない <xref:System.Span%601?displayProperty=nameWithType> 型のインスタンスを使用して、`foreach` ステートメントを使用します。</span><span class="sxs-lookup"><span data-stu-id="6960e-114">The next example uses the `foreach` statement with an instance of the <xref:System.Span%601?displayProperty=nameWithType> type, which doesn't implement any interfaces:</span></span>

[!code-csharp-interactive[span example](~/samples/snippets/csharp/keywords/IterationKeywordsExamples.cs#2)]

<span data-ttu-id="6960e-115">次の例では、stackalloc 配列内の各項目の値を設定するために、`ref` 繰り返し変数を使用します。</span><span class="sxs-lookup"><span data-stu-id="6960e-115">The following example uses a `ref` iteration variable to set the value of each item in a stackalloc array.</span></span> <span data-ttu-id="6960e-116">`ref readonly` バージョンは、すべての値を出力するコレクションを反復処理します。</span><span class="sxs-lookup"><span data-stu-id="6960e-116">The `ref readonly` version iterates the collection to print all the values.</span></span> <span data-ttu-id="6960e-117">`readonly` 宣言では、暗黙のローカル変数宣言を使用します。</span><span class="sxs-lookup"><span data-stu-id="6960e-117">The `readonly` declaration uses an implicit local variable declaration.</span></span> <span data-ttu-id="6960e-118">暗黙の変数宣言は、`ref` または `ref readonly` 宣言で使用でき、変数の宣言を明示的に型指定できます。</span><span class="sxs-lookup"><span data-stu-id="6960e-118">Implicit variable declarations can be used with either `ref` or `ref readonly` declarations, as can explicitly typed variable declarations.</span></span>

[!code-csharp-interactive[ref span example](~/samples/snippets/csharp/keywords/IterationKeywordsExamples.cs#RefSpan)]

## <a name="c-language-specification"></a><span data-ttu-id="6960e-119">C# 言語仕様</span><span class="sxs-lookup"><span data-stu-id="6960e-119">C# language specification</span></span>

<span data-ttu-id="6960e-120">詳細については、「[C# 言語仕様](../language-specification/index.md)」の [foreach ステートメント](~/_csharplang/spec/statements.md#the-foreach-statement)に関するセクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="6960e-120">For more information, see [The foreach statement](~/_csharplang/spec/statements.md#the-foreach-statement) section of the [C# language specification](../language-specification/index.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="6960e-121">関連項目</span><span class="sxs-lookup"><span data-stu-id="6960e-121">See also</span></span>

- [<span data-ttu-id="6960e-122">C# リファレンス</span><span class="sxs-lookup"><span data-stu-id="6960e-122">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="6960e-123">C# プログラミング ガイド</span><span class="sxs-lookup"><span data-stu-id="6960e-123">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="6960e-124">C# のキーワード</span><span class="sxs-lookup"><span data-stu-id="6960e-124">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="6960e-125">繰り返しステートメント</span><span class="sxs-lookup"><span data-stu-id="6960e-125">Iteration Statements</span></span>](iteration-statements.md)
- [<span data-ttu-id="6960e-126">配列での foreach の使用</span><span class="sxs-lookup"><span data-stu-id="6960e-126">Using foreach with arrays</span></span>](../../programming-guide/arrays/using-foreach-with-arrays.md)
- [<span data-ttu-id="6960e-127">for ステートメント</span><span class="sxs-lookup"><span data-stu-id="6960e-127">for statement</span></span>](for.md)
