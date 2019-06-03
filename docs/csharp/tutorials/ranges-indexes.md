---
title: インデックスと範囲を使用してデータの範囲を調べる
description: この高度なチュートリアルでは、インデックスと範囲を使用してデータを調べ、シーケンシャル データ セットのスライスを調べる方法について説明します。
ms.date: 04/19/2019
ms.custom: mvc
ms.openlocfilehash: 118d3c9ccad98ec02195c2b5e26a2ca203990adf
ms.sourcegitcommit: 682c64df0322c7bda016f8bfea8954e9b31f1990
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/13/2019
ms.locfileid: "65557184"
---
# <a name="indices-and-ranges"></a><span data-ttu-id="d7d5c-103">インデックスと範囲</span><span class="sxs-lookup"><span data-stu-id="d7d5c-103">Indices and ranges</span></span>

<span data-ttu-id="d7d5c-104">範囲とインデックスには、<xref:System.Array>、<xref:System.Span%601>、または <xref:System.ReadOnlySpan%601> 内の 1 つの要素または範囲にアクセスできる簡潔な構文が用意されています。</span><span class="sxs-lookup"><span data-stu-id="d7d5c-104">Ranges and indices provide a succinct syntax for accessing single elements or ranges in an <xref:System.Array>, <xref:System.Span%601>, or <xref:System.ReadOnlySpan%601>.</span></span> <span data-ttu-id="d7d5c-105">これらの機能を使用すると、簡潔でわかりやすい構文でシーケンス内の各要素または要素の範囲にアクセスできるようになります。</span><span class="sxs-lookup"><span data-stu-id="d7d5c-105">These features enable more concise, clear syntax to access single elements or ranges of elements in a sequence.</span></span>

<span data-ttu-id="d7d5c-106">このチュートリアルでは、次の作業を行う方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="d7d5c-106">In this tutorial, you'll learn how to:</span></span>

> [!div class="checklist"]
> * <span data-ttu-id="d7d5c-107">シーケンス内の範囲に構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="d7d5c-107">Use the syntax for ranges in a sequence.</span></span>
> * <span data-ttu-id="d7d5c-108">各シーケンスの開始と終了に関する設計上の決定について説明します。</span><span class="sxs-lookup"><span data-stu-id="d7d5c-108">Understand the design decisions for the start and end of each sequence.</span></span>
> * <span data-ttu-id="d7d5c-109"><xref:System.Index> 型と <xref:System.Range> 型のシナリオについて説明します。</span><span class="sxs-lookup"><span data-stu-id="d7d5c-109">Learn scenarios for the <xref:System.Index> and <xref:System.Range> types.</span></span>

## <a name="language-support-for-indices-and-ranges"></a><span data-ttu-id="d7d5c-110">インデックスと範囲の言語サポート</span><span class="sxs-lookup"><span data-stu-id="d7d5c-110">Language support for indices and ranges</span></span>

<span data-ttu-id="d7d5c-111">この言語のサポートでは、2 つの新しい型と 2 つの新しい演算子を使用しています。</span><span class="sxs-lookup"><span data-stu-id="d7d5c-111">This language support relies on two new types and two new operators.</span></span>
- <span data-ttu-id="d7d5c-112"><xref:System.Index?displayProperty=nameWithType> はシーケンスとしてインデックスを表します。</span><span class="sxs-lookup"><span data-stu-id="d7d5c-112"><xref:System.Index?displayProperty=nameWithType> represents an index into a sequence.</span></span>
- <span data-ttu-id="d7d5c-113">`^` 演算子。シーケンスの末尾から相対的なインデックスを指定します。</span><span class="sxs-lookup"><span data-stu-id="d7d5c-113">The `^` operator, which specifies that an index is relative to the end of a sequence.</span></span>
- <span data-ttu-id="d7d5c-114"><xref:System.Range?displayProperty=nameWithType> はシーケンスのサブ範囲を表します。</span><span class="sxs-lookup"><span data-stu-id="d7d5c-114"><xref:System.Range?displayProperty=nameWithType> represents a sub range of a sequence.</span></span>
- <span data-ttu-id="d7d5c-115">範囲演算子 (`..`)。範囲の先頭と末尾をそのオペランドとして指定します。</span><span class="sxs-lookup"><span data-stu-id="d7d5c-115">The Range operator (`..`), which specifies the start and end of a range as its operands.</span></span>

<span data-ttu-id="d7d5c-116">インデックスのルールから始めましょう。</span><span class="sxs-lookup"><span data-stu-id="d7d5c-116">Let's start with the rules for indices.</span></span> <span data-ttu-id="d7d5c-117">配列 `sequence` を考えます。</span><span class="sxs-lookup"><span data-stu-id="d7d5c-117">Consider an array `sequence`.</span></span> <span data-ttu-id="d7d5c-118">`0` インデックスは `sequence[0]` と同じです。</span><span class="sxs-lookup"><span data-stu-id="d7d5c-118">The `0` index is the same as `sequence[0]`.</span></span> <span data-ttu-id="d7d5c-119">`^0` インデックスは `sequence[sequence.Length]` と同じです。</span><span class="sxs-lookup"><span data-stu-id="d7d5c-119">The `^0` index is the same as `sequence[sequence.Length]`.</span></span> <span data-ttu-id="d7d5c-120">`sequence[sequence.Length]` と同様に、`sequence[^0]` は例外をスローすることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="d7d5c-120">Note that `sequence[^0]` does throw an exception, just as `sequence[sequence.Length]` does.</span></span> <span data-ttu-id="d7d5c-121">任意の数値 `n` の場合、インデックス `^n` は `sequence[sequence.Length - n]` と同じです。</span><span class="sxs-lookup"><span data-stu-id="d7d5c-121">For any number `n`, the index `^n` is the same as `sequence[sequence.Length - n]`.</span></span>

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

<span data-ttu-id="d7d5c-122">末尾の単語は `^1` インデックスで取得できます。</span><span class="sxs-lookup"><span data-stu-id="d7d5c-122">You can retrieve the last word with the `^1` index.</span></span> <span data-ttu-id="d7d5c-123">初期化の下に次のコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="d7d5c-123">Add the following code below the initialization:</span></span>

[!code-csharp[LastIndex](~/samples/csharp/tutorials/RangesIndexes/IndicesAndRanges.cs#IndicesAndRanges_LastIndex)]

<span data-ttu-id="d7d5c-124">範囲は、範囲の*先頭*と*末尾*を指定します。</span><span class="sxs-lookup"><span data-stu-id="d7d5c-124">A range specifies the *start* and *end* of a range.</span></span> <span data-ttu-id="d7d5c-125">範囲は排他的です。つまり、*末尾*は範囲に含まれません。</span><span class="sxs-lookup"><span data-stu-id="d7d5c-125">Ranges are exclusive, meaning the *end* is not included in the range.</span></span> <span data-ttu-id="d7d5c-126">範囲 `[0..^0]` は、`[0..sequence.Length]` が範囲全体を表すのと同じように、範囲全体を表します。</span><span class="sxs-lookup"><span data-stu-id="d7d5c-126">The range `[0..^0]` represents the entire range, just as `[0..sequence.Length]` represents the entire range.</span></span> 

<span data-ttu-id="d7d5c-127">次のコードでは、単語 "quick"、"brown"、"fox" から成る部分範囲が作成されます。</span><span class="sxs-lookup"><span data-stu-id="d7d5c-127">The following code creates a subrange with the words "quick", "brown", and "fox".</span></span> <span data-ttu-id="d7d5c-128">それには、`words[1]` から `words[3]` までが含まれます。</span><span class="sxs-lookup"><span data-stu-id="d7d5c-128">It includes `words[1]` through `words[3]`.</span></span> <span data-ttu-id="d7d5c-129">要素 `words[4]` が範囲内にありません。</span><span class="sxs-lookup"><span data-stu-id="d7d5c-129">The element `words[4]` isn't in the range.</span></span> <span data-ttu-id="d7d5c-130">同じメソッドに次のコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="d7d5c-130">Add the following code to the same method.</span></span> <span data-ttu-id="d7d5c-131">それをコピーして、対話型ウィンドウの下部に貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="d7d5c-131">Copy and paste it at the bottom of the interactive window.</span></span>

[!code-csharp[Range](~/samples/csharp/tutorials/RangesIndexes/IndicesAndRanges.cs#IndicesAndRanges_Range)]

<span data-ttu-id="d7d5c-132">次のコードでは、"lazy" と "dog" の部分範囲が作成されます。</span><span class="sxs-lookup"><span data-stu-id="d7d5c-132">The following code creates a subrange with "lazy" and "dog".</span></span> <span data-ttu-id="d7d5c-133">それには、`words[^2]` と `words[^1]` が含まれます。</span><span class="sxs-lookup"><span data-stu-id="d7d5c-133">It includes `words[^2]` and `words[^1]`.</span></span> <span data-ttu-id="d7d5c-134">末尾インデックス `words[^0]` は含まれません。</span><span class="sxs-lookup"><span data-stu-id="d7d5c-134">The end index `words[^0]` isn't included.</span></span> <span data-ttu-id="d7d5c-135">次のコードも追加します。</span><span class="sxs-lookup"><span data-stu-id="d7d5c-135">Add the following code as well:</span></span>

[!code-csharp[LastRange](~/samples/csharp/tutorials/RangesIndexes/IndicesAndRanges.cs#IndicesAndRanges_LastRange)]

<span data-ttu-id="d7d5c-136">次の例では、先頭と末尾の一方または両方が開いている範囲が作成されます。</span><span class="sxs-lookup"><span data-stu-id="d7d5c-136">The following examples create ranges that are open ended for the start, end, or both:</span></span>

[!code-csharp[PartialRange](~/samples/csharp/tutorials/RangesIndexes/IndicesAndRanges.cs#IndicesAndRanges_PartialRanges)]

<span data-ttu-id="d7d5c-137">範囲やインデックスを変数として宣言することもできます。</span><span class="sxs-lookup"><span data-stu-id="d7d5c-137">You can also declare ranges or indices as variables.</span></span> <span data-ttu-id="d7d5c-138">この変数は、文字 `[` と `]` の内側で使用できます。</span><span class="sxs-lookup"><span data-stu-id="d7d5c-138">The variable can then be used inside the `[` and `]` characters:</span></span>

[!code-csharp[IndexRangeTypes](~/samples/csharp/tutorials/RangesIndexes/IndicesAndRanges.cs#IndicesAndRanges_RangeIndexTypes)]

<span data-ttu-id="d7d5c-139">次のサンプルは、こうした選択肢の理由の多くを示しています。</span><span class="sxs-lookup"><span data-stu-id="d7d5c-139">The following sample shows many of the reasons for those choices.</span></span> <span data-ttu-id="d7d5c-140">`x`、`y`、`z` を変更してさまざまな組み合わせを試してください。</span><span class="sxs-lookup"><span data-stu-id="d7d5c-140">Modify `x`, `y`, and `z` to try different combinations.</span></span> <span data-ttu-id="d7d5c-141">実験するときには、有効な組み合わせになるように `x` が `y` 未満の値、`y` が `z` 未満の値を使用します。</span><span class="sxs-lookup"><span data-stu-id="d7d5c-141">When you experiment, use values where `x` is less than `y`, and `y` is less than `z` for valid combinations.</span></span> <span data-ttu-id="d7d5c-142">新しいメソッドに次のコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="d7d5c-142">Add the following code in a new method.</span></span> <span data-ttu-id="d7d5c-143">さまざまな組み合わせを試してください。</span><span class="sxs-lookup"><span data-stu-id="d7d5c-143">Try different combinations:</span></span>

[!code-csharp[SemanticsExamples](~/samples/csharp/tutorials/RangesIndexes/IndicesAndRanges.cs#IndicesAndRanges_Semantics)]

## <a name="scenarios-for-indices-and-ranges"></a><span data-ttu-id="d7d5c-144">インデックスと範囲のシナリオ</span><span class="sxs-lookup"><span data-stu-id="d7d5c-144">Scenarios for Indices and Ranges</span></span>

<span data-ttu-id="d7d5c-145">シーケンス全体の一部の範囲について何らかの分析を行う場合は、範囲とインデックスを使用することがよくあります。</span><span class="sxs-lookup"><span data-stu-id="d7d5c-145">You'll often use ranges and indices when you want to perform some analysis on subrange of an entire sequence.</span></span> <span data-ttu-id="d7d5c-146">どの部分の範囲が関係しているかを正確に読み取る場合に、この新しい構文の方が明確です。</span><span class="sxs-lookup"><span data-stu-id="d7d5c-146">The new syntax is clearer in reading exactly what subrange is involved.</span></span> <span data-ttu-id="d7d5c-147">ローカル関数 `MovingAverage` は、引数として <xref:System.Range> を受け取ります。</span><span class="sxs-lookup"><span data-stu-id="d7d5c-147">The local function `MovingAverage` takes a <xref:System.Range> as its argument.</span></span> <span data-ttu-id="d7d5c-148">このメソッドでは、最小値、最大値、および平均値を計算するときに、その範囲のみが列挙されます。</span><span class="sxs-lookup"><span data-stu-id="d7d5c-148">The method then enumerates just that range when calculating the min, max, and average.</span></span> <span data-ttu-id="d7d5c-149">プロジェクトで次のコードを試してみてください。</span><span class="sxs-lookup"><span data-stu-id="d7d5c-149">Try the following code in your project:</span></span>

[!code-csharp[MovingAverages](~/samples/csharp/tutorials/RangesIndexes/IndicesAndRanges.cs#IndicesAndRanges_MovingAverage)]

<span data-ttu-id="d7d5c-150">完成したコードは [dotnet/samples](https://github.com/dotnet/samples/tree/master/csharp/tutorials/RangesIndexes) リポジトリからダウンロードできます。</span><span class="sxs-lookup"><span data-stu-id="d7d5c-150">You can download the completed code from the [dotnet/samples](https://github.com/dotnet/samples/tree/master/csharp/tutorials/RangesIndexes) repository.</span></span>
