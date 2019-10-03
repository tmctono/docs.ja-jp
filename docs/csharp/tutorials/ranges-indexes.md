---
title: インデックスと範囲を使用してデータの範囲を調べる
description: この高度なチュートリアルでは、インデックスと範囲を使用してデータを調べ、シーケンシャル データ セットのスライスを調べる方法について説明します。
ms.date: 09/20/2019
ms.custom: mvc
ms.openlocfilehash: a879601e1358f72e80983992a3cd96ba1fb06a38
ms.sourcegitcommit: da2dd2772fcf32b44eb18b1cbe8affd17b1753c9
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/27/2019
ms.locfileid: "71391970"
---
# <a name="indices-and-ranges"></a><span data-ttu-id="235b7-103">インデックスと範囲</span><span class="sxs-lookup"><span data-stu-id="235b7-103">Indices and ranges</span></span>

<span data-ttu-id="235b7-104">範囲とインデックスには、シーケンス内の 1 つの要素または範囲にアクセスできる簡潔な構文が用意されています。</span><span class="sxs-lookup"><span data-stu-id="235b7-104">Ranges and indices provide a succinct syntax for accessing single elements or ranges in a sequence.</span></span>

<span data-ttu-id="235b7-105">このチュートリアルでは、次の作業を行う方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="235b7-105">In this tutorial, you'll learn how to:</span></span>

> [!div class="checklist"]
>
> - <span data-ttu-id="235b7-106">シーケンス内の範囲に構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="235b7-106">Use the syntax for ranges in a sequence.</span></span>
> - <span data-ttu-id="235b7-107">各シーケンスの開始と終了に関する設計上の決定について説明します。</span><span class="sxs-lookup"><span data-stu-id="235b7-107">Understand the design decisions for the start and end of each sequence.</span></span>
> - <span data-ttu-id="235b7-108"><xref:System.Index> 型と <xref:System.Range> 型のシナリオについて説明します。</span><span class="sxs-lookup"><span data-stu-id="235b7-108">Learn scenarios for the <xref:System.Index> and <xref:System.Range> types.</span></span>

## <a name="language-support-for-indices-and-ranges"></a><span data-ttu-id="235b7-109">インデックスと範囲の言語サポート</span><span class="sxs-lookup"><span data-stu-id="235b7-109">Language support for indices and ranges</span></span>

<span data-ttu-id="235b7-110">この言語のサポートでは、次の 2 つの新しい型と 2 つの新しい演算子が使用されています。</span><span class="sxs-lookup"><span data-stu-id="235b7-110">This language support relies on two new types and two new operators:</span></span>

- <span data-ttu-id="235b7-111"><xref:System.Index?displayProperty=nameWithType> はシーケンスとしてインデックスを表します。</span><span class="sxs-lookup"><span data-stu-id="235b7-111"><xref:System.Index?displayProperty=nameWithType> represents an index into a sequence.</span></span>
- <span data-ttu-id="235b7-112">index from end 演算子の `^`。シーケンスの末尾から相対的なインデックスを指定します。</span><span class="sxs-lookup"><span data-stu-id="235b7-112">The index from end operator `^`, which specifies that an index is relative to the end of a sequence.</span></span>
- <span data-ttu-id="235b7-113"><xref:System.Range?displayProperty=nameWithType> はシーケンスのサブ範囲を表します。</span><span class="sxs-lookup"><span data-stu-id="235b7-113"><xref:System.Range?displayProperty=nameWithType> represents a sub range of a sequence.</span></span>
- <span data-ttu-id="235b7-114">範囲演算子の `..`。範囲の先頭と末尾をそのオペランドとして指定します。</span><span class="sxs-lookup"><span data-stu-id="235b7-114">The range operator `..`, which specifies the start and end of a range as its operands.</span></span>

<span data-ttu-id="235b7-115">インデックスのルールから始めましょう。</span><span class="sxs-lookup"><span data-stu-id="235b7-115">Let's start with the rules for indices.</span></span> <span data-ttu-id="235b7-116">配列 `sequence` を考えます。</span><span class="sxs-lookup"><span data-stu-id="235b7-116">Consider an array `sequence`.</span></span> <span data-ttu-id="235b7-117">`0` インデックスは `sequence[0]` と同じです。</span><span class="sxs-lookup"><span data-stu-id="235b7-117">The `0` index is the same as `sequence[0]`.</span></span> <span data-ttu-id="235b7-118">`^0` インデックスは `sequence[sequence.Length]` と同じです。</span><span class="sxs-lookup"><span data-stu-id="235b7-118">The `^0` index is the same as `sequence[sequence.Length]`.</span></span> <span data-ttu-id="235b7-119">`sequence[sequence.Length]` と同様に、`sequence[^0]` は例外をスローすることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="235b7-119">Note that `sequence[^0]` does throw an exception, just as `sequence[sequence.Length]` does.</span></span> <span data-ttu-id="235b7-120">任意の数値 `n` の場合、インデックス `^n` は `sequence[sequence.Length - n]` と同じです。</span><span class="sxs-lookup"><span data-stu-id="235b7-120">For any number `n`, the index `^n` is the same as `sequence[sequence.Length - n]`.</span></span>

```csharp-interactive
string[] words = new string[]
{
                // index from start    index from end
    "The",      // 0                   ^9
    "quick",    // 1                   ^8
    "brown",    // 2                   ^7
    "fox",      // 3                   ^6
    "jumped",   // 4                   ^5
    "over",     // 5                   ^4
    "the",      // 6                   ^3
    "lazy",     // 7                   ^2
    "dog"       // 8                   ^1
};              // 9 (or words.Length) ^0
```

<span data-ttu-id="235b7-121">末尾の単語は `^1` インデックスで取得できます。</span><span class="sxs-lookup"><span data-stu-id="235b7-121">You can retrieve the last word with the `^1` index.</span></span> <span data-ttu-id="235b7-122">初期化の下に次のコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="235b7-122">Add the following code below the initialization:</span></span>

[!code-csharp[LastIndex](~/samples/csharp/tutorials/RangesIndexes/IndicesAndRanges.cs#IndicesAndRanges_LastIndex)]

<span data-ttu-id="235b7-123">範囲は、範囲の*先頭*と*末尾*を指定します。</span><span class="sxs-lookup"><span data-stu-id="235b7-123">A range specifies the *start* and *end* of a range.</span></span> <span data-ttu-id="235b7-124">範囲は排他的です。つまり、*末尾*は範囲に含まれません。</span><span class="sxs-lookup"><span data-stu-id="235b7-124">Ranges are exclusive, meaning the *end* is not included in the range.</span></span> <span data-ttu-id="235b7-125">範囲 `[0..^0]` は、`[0..sequence.Length]` が範囲全体を表すのと同じように、範囲全体を表します。</span><span class="sxs-lookup"><span data-stu-id="235b7-125">The range `[0..^0]` represents the entire range, just as `[0..sequence.Length]` represents the entire range.</span></span> 

<span data-ttu-id="235b7-126">次のコードでは、単語 "quick"、"brown"、"fox" から成る部分範囲が作成されます。</span><span class="sxs-lookup"><span data-stu-id="235b7-126">The following code creates a subrange with the words "quick", "brown", and "fox".</span></span> <span data-ttu-id="235b7-127">それには、`words[1]` から `words[3]` までが含まれます。</span><span class="sxs-lookup"><span data-stu-id="235b7-127">It includes `words[1]` through `words[3]`.</span></span> <span data-ttu-id="235b7-128">要素 `words[4]` が範囲内にありません。</span><span class="sxs-lookup"><span data-stu-id="235b7-128">The element `words[4]` isn't in the range.</span></span> <span data-ttu-id="235b7-129">同じメソッドに次のコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="235b7-129">Add the following code to the same method.</span></span> <span data-ttu-id="235b7-130">それをコピーして、対話型ウィンドウの下部に貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="235b7-130">Copy and paste it at the bottom of the interactive window.</span></span>

[!code-csharp[Range](~/samples/csharp/tutorials/RangesIndexes/IndicesAndRanges.cs#IndicesAndRanges_Range)]

<span data-ttu-id="235b7-131">次のコードでは、"lazy" と "dog" の部分範囲が作成されます。</span><span class="sxs-lookup"><span data-stu-id="235b7-131">The following code creates a subrange with "lazy" and "dog".</span></span> <span data-ttu-id="235b7-132">それには、`words[^2]` と `words[^1]` が含まれます。</span><span class="sxs-lookup"><span data-stu-id="235b7-132">It includes `words[^2]` and `words[^1]`.</span></span> <span data-ttu-id="235b7-133">末尾インデックス `words[^0]` は含まれません。</span><span class="sxs-lookup"><span data-stu-id="235b7-133">The end index `words[^0]` isn't included.</span></span> <span data-ttu-id="235b7-134">次のコードも追加します。</span><span class="sxs-lookup"><span data-stu-id="235b7-134">Add the following code as well:</span></span>

[!code-csharp[LastRange](~/samples/csharp/tutorials/RangesIndexes/IndicesAndRanges.cs#IndicesAndRanges_LastRange)]

<span data-ttu-id="235b7-135">次の例では、先頭と末尾の一方または両方が開いている範囲が作成されます。</span><span class="sxs-lookup"><span data-stu-id="235b7-135">The following examples create ranges that are open ended for the start, end, or both:</span></span>

[!code-csharp[PartialRange](~/samples/csharp/tutorials/RangesIndexes/IndicesAndRanges.cs#IndicesAndRanges_PartialRanges)]

<span data-ttu-id="235b7-136">範囲やインデックスを変数として宣言することもできます。</span><span class="sxs-lookup"><span data-stu-id="235b7-136">You can also declare ranges or indices as variables.</span></span> <span data-ttu-id="235b7-137">この変数は、文字 `[` と `]` の内側で使用できます。</span><span class="sxs-lookup"><span data-stu-id="235b7-137">The variable can then be used inside the `[` and `]` characters:</span></span>

[!code-csharp[IndexRangeTypes](~/samples/csharp/tutorials/RangesIndexes/IndicesAndRanges.cs#IndicesAndRanges_RangeIndexTypes)]

<span data-ttu-id="235b7-138">次のサンプルは、こうした選択肢の理由の多くを示しています。</span><span class="sxs-lookup"><span data-stu-id="235b7-138">The following sample shows many of the reasons for those choices.</span></span> <span data-ttu-id="235b7-139">`x`、`y`、`z` を変更してさまざまな組み合わせを試してください。</span><span class="sxs-lookup"><span data-stu-id="235b7-139">Modify `x`, `y`, and `z` to try different combinations.</span></span> <span data-ttu-id="235b7-140">実験するときには、有効な組み合わせになるように `x` が `y` 未満の値、`y` が `z` 未満の値を使用します。</span><span class="sxs-lookup"><span data-stu-id="235b7-140">When you experiment, use values where `x` is less than `y`, and `y` is less than `z` for valid combinations.</span></span> <span data-ttu-id="235b7-141">新しいメソッドに次のコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="235b7-141">Add the following code in a new method.</span></span> <span data-ttu-id="235b7-142">さまざまな組み合わせを試してください。</span><span class="sxs-lookup"><span data-stu-id="235b7-142">Try different combinations:</span></span>

[!code-csharp[SemanticsExamples](~/samples/csharp/tutorials/RangesIndexes/IndicesAndRanges.cs#IndicesAndRanges_Semantics)]

## <a name="type-support-for-indices-and-ranges"></a><span data-ttu-id="235b7-143">インデックスと範囲の型のサポート</span><span class="sxs-lookup"><span data-stu-id="235b7-143">Type support for indices and ranges</span></span>

<span data-ttu-id="235b7-144">型に <xref:System.Index> または <xref:System.Range> パラメーターを持つ[インデクサー](../programming-guide/indexers/index.md)が用意されている場合、それぞれ明示的にインデックスまたは範囲をサポートします。</span><span class="sxs-lookup"><span data-stu-id="235b7-144">If a type provides an [indexer](../programming-guide/indexers/index.md) with an <xref:System.Index> or <xref:System.Range> parameter, it explicitly supports indices or ranges respectively.</span></span>

<span data-ttu-id="235b7-145">アクセス可能なゲッターと戻り値の型 `int` を持つ `Length` または `Count` という名前のプロパティがある場合、型は**可算**です。</span><span class="sxs-lookup"><span data-stu-id="235b7-145">A type is **countable** if it has a property named `Length` or `Count` with an accessible getter and a return type of `int`.</span></span> <span data-ttu-id="235b7-146">インデックスまたは範囲を明示的にサポートしていない可算型は、それらを暗黙的にサポートしている可能性があります。</span><span class="sxs-lookup"><span data-stu-id="235b7-146">A countable type that doesn't explicitly support indices or ranges may provide an implicit support for them.</span></span> <span data-ttu-id="235b7-147">詳細については、[機能の提案に関する注記](~/_csharplang/proposals/csharp-8.0/ranges.md)の「[暗黙的なインデックスのサポート](~/_csharplang/proposals/csharp-8.0/ranges.md#implicit-index-support)」と「[暗黙的な範囲のサポート](~/_csharplang/proposals/csharp-8.0/ranges.md#implicit-range-support)」のセクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="235b7-147">For more information, see the [Implicit Index support](~/_csharplang/proposals/csharp-8.0/ranges.md#implicit-index-support) and [Implicit Range support](~/_csharplang/proposals/csharp-8.0/ranges.md#implicit-range-support) sections of the [feature proposal note](~/_csharplang/proposals/csharp-8.0/ranges.md).</span></span>

<span data-ttu-id="235b7-148">たとえば、次の .NET 型は、<xref:System.Array>、<xref:System.String>、<xref:System.Span%601>、および <xref:System.ReadOnlySpan%601> のインデックスと範囲の両方をサポートしています。</span><span class="sxs-lookup"><span data-stu-id="235b7-148">For example, the following .NET types support both indices and ranges: <xref:System.Array>, <xref:System.String>, <xref:System.Span%601>, and <xref:System.ReadOnlySpan%601>.</span></span> <span data-ttu-id="235b7-149"><xref:System.Collections.Generic.List%601> はインデックスをサポートしていますが、範囲はサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="235b7-149">The <xref:System.Collections.Generic.List%601> supports indices but doesn't support ranges.</span></span>

## <a name="scenarios-for-indices-and-ranges"></a><span data-ttu-id="235b7-150">インデックスと範囲のシナリオ</span><span class="sxs-lookup"><span data-stu-id="235b7-150">Scenarios for indices and ranges</span></span>

<span data-ttu-id="235b7-151">シーケンス全体の一部の範囲について何らかの分析を行う場合は、範囲とインデックスを使用することがよくあります。</span><span class="sxs-lookup"><span data-stu-id="235b7-151">You'll often use ranges and indices when you want to perform some analysis on subrange of an entire sequence.</span></span> <span data-ttu-id="235b7-152">どの部分の範囲が関係しているかを正確に読み取る場合に、この新しい構文の方が明確です。</span><span class="sxs-lookup"><span data-stu-id="235b7-152">The new syntax is clearer in reading exactly what subrange is involved.</span></span> <span data-ttu-id="235b7-153">ローカル関数 `MovingAverage` は、引数として <xref:System.Range> を受け取ります。</span><span class="sxs-lookup"><span data-stu-id="235b7-153">The local function `MovingAverage` takes a <xref:System.Range> as its argument.</span></span> <span data-ttu-id="235b7-154">このメソッドでは、最小値、最大値、および平均値を計算するときに、その範囲のみが列挙されます。</span><span class="sxs-lookup"><span data-stu-id="235b7-154">The method then enumerates just that range when calculating the min, max, and average.</span></span> <span data-ttu-id="235b7-155">プロジェクトで次のコードを試してみてください。</span><span class="sxs-lookup"><span data-stu-id="235b7-155">Try the following code in your project:</span></span>

[!code-csharp[MovingAverages](~/samples/csharp/tutorials/RangesIndexes/IndicesAndRanges.cs#IndicesAndRanges_MovingAverage)]

<span data-ttu-id="235b7-156">完成したコードは [dotnet/samples](https://github.com/dotnet/samples/tree/master/csharp/tutorials/RangesIndexes) リポジトリからダウンロードできます。</span><span class="sxs-lookup"><span data-stu-id="235b7-156">You can download the completed code from the [dotnet/samples](https://github.com/dotnet/samples/tree/master/csharp/tutorials/RangesIndexes) repository.</span></span>
