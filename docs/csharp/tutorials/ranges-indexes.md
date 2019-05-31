---
title: インデックスと範囲を使用してデータの範囲を調べる
description: この高度なチュートリアルでは、インデックスと範囲を使用してデータを調べ、シーケンシャル データ セットのスライスを調べる方法について説明します。
ms.date: 04/19/2019
ms.custom: mvc
ms.openlocfilehash: 64fae4581e265d4f70b8356d5c651b4fdaca3fe9
ms.sourcegitcommit: dd3b897feb5c4ac39732bb165848e37a344b0765
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/25/2019
ms.locfileid: "64431500"
---
# <a name="indices-and-ranges"></a><span data-ttu-id="eee23-103">インデックスと範囲</span><span class="sxs-lookup"><span data-stu-id="eee23-103">Indices and ranges</span></span>

<span data-ttu-id="eee23-104">範囲とインデックスには、<xref:System.Array>、<xref:System.Span%601>、または <xref:System.ReadOnlySpan%601> 内の 1 つの要素または範囲にアクセスできる簡潔な構文が用意されています。</span><span class="sxs-lookup"><span data-stu-id="eee23-104">Ranges and indices provide a succinct syntax for accessing single elements or ranges in an <xref:System.Array>, <xref:System.Span%601>, or <xref:System.ReadOnlySpan%601>.</span></span> <span data-ttu-id="eee23-105">これらの機能を使用すると、簡潔でわかりやすい構文でシーケンス内の各要素または要素の範囲にアクセスできるようになります。</span><span class="sxs-lookup"><span data-stu-id="eee23-105">These features enable more concise, clear syntax to access single elements or ranges of elements in a sequence.</span></span>

<span data-ttu-id="eee23-106">このチュートリアルでは、次の作業を行う方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="eee23-106">In this tutorial, you'll learn how to:</span></span>

> [!div class="checklist"]
> * <span data-ttu-id="eee23-107">シーケンス内の範囲に構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="eee23-107">Use the syntax for ranges in a sequence.</span></span>
> * <span data-ttu-id="eee23-108">各シーケンスの開始と終了に関する設計上の決定について説明します。</span><span class="sxs-lookup"><span data-stu-id="eee23-108">Understand the design decisions for the start and end of each sequence.</span></span>
> * <span data-ttu-id="eee23-109"><xref:System.Index> 型と <xref:System.Range> 型のシナリオについて説明します。</span><span class="sxs-lookup"><span data-stu-id="eee23-109">Learn scenarios for the <xref:System.Index> and <xref:System.Range> types.</span></span>

## <a name="language-support-for-indices-and-ranges"></a><span data-ttu-id="eee23-110">インデックスと範囲の言語サポート</span><span class="sxs-lookup"><span data-stu-id="eee23-110">Language support for indices and ranges</span></span>

<span data-ttu-id="eee23-111">インデックスの前に `^` 文字を使用すると、**末尾から**インデックスを指定できます。</span><span class="sxs-lookup"><span data-stu-id="eee23-111">You can specify an index **from the end** using the `^` character before the index.</span></span> <span data-ttu-id="eee23-112">末尾からのインデックス付けは、`0..^0` で範囲全体を指定するという規則から始まります。</span><span class="sxs-lookup"><span data-stu-id="eee23-112">Indexing from the end starts from the rule that `0..^0` specifies the entire range.</span></span> <span data-ttu-id="eee23-113">配列全体を列挙するには、"*最初の要素*" から開始し、"*最後の要素を過ぎる*" まで続けます。</span><span class="sxs-lookup"><span data-stu-id="eee23-113">To enumerate an entire array, you start *at the first element*, and continue until you are *past the last element*.</span></span> <span data-ttu-id="eee23-114">列挙子に対する `MoveNext` メソッドの動作を考えてみてください。列挙子から末尾の要素が渡されると、メソッドから false が返されます。</span><span class="sxs-lookup"><span data-stu-id="eee23-114">Think of the behavior of the `MoveNext` method on an enumerator: it returns false when the enumeration passes the last element.</span></span> <span data-ttu-id="eee23-115">インデックス `^0` は、"末尾"、`array[array.Length]`、つまり末尾の要素の後のインデックスを意味します。</span><span class="sxs-lookup"><span data-stu-id="eee23-115">The index `^0` means "the end", `array[array.Length]`, or the index that follows the last element.</span></span> <span data-ttu-id="eee23-116">`array[2]` が "先頭から 2 番目" の要素を意味することには慣れているでしょう。</span><span class="sxs-lookup"><span data-stu-id="eee23-116">You are familiar with `array[2]` meaning the element "2 from the start".</span></span> <span data-ttu-id="eee23-117">今後、`array[^2]` は "末尾から 2 番目" の要素を意味するようになります。</span><span class="sxs-lookup"><span data-stu-id="eee23-117">Now, `array[^2]` means the element "2 from the end".</span></span> 

<span data-ttu-id="eee23-118">**範囲**は、**範囲演算子** `..` を使用して指定できます。</span><span class="sxs-lookup"><span data-stu-id="eee23-118">You can specify a **range** with the **range operator**: `..`.</span></span> <span data-ttu-id="eee23-119">たとえば、`0..^0` は配列の範囲全体を指定します。0 は先頭からですが、末尾の 0 は含まれません。</span><span class="sxs-lookup"><span data-stu-id="eee23-119">For example, `0..^0` specifies the entire range of the array: 0 from the start up to, but not including 0 from the end.</span></span> <span data-ttu-id="eee23-120">どちらのオペランドでも、"先頭から" または "末尾から" を使用できます。</span><span class="sxs-lookup"><span data-stu-id="eee23-120">Either operand may use "from the start" or "from the end".</span></span> <span data-ttu-id="eee23-121">さらに、どちらのオペランドも省略できます。</span><span class="sxs-lookup"><span data-stu-id="eee23-121">Furthermore, either operand may be omitted.</span></span> <span data-ttu-id="eee23-122">先頭インデックスの既定値は `0`、末尾インデックスの既定値は `^0` です。</span><span class="sxs-lookup"><span data-stu-id="eee23-122">The defaults are `0` for the start index, and `^0` for the end index.</span></span>

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

<span data-ttu-id="eee23-123">各要素のインデックスによって "先頭から" と "末尾から" の概念が強調されており、その範囲では範囲の末尾が除外されています。</span><span class="sxs-lookup"><span data-stu-id="eee23-123">The index of each element reinforces the concept of "from the start", and "from the end", and that ranges are exclusive of the end of the range.</span></span> <span data-ttu-id="eee23-124">配列全体の "先頭" は最初の要素です。</span><span class="sxs-lookup"><span data-stu-id="eee23-124">The "start" of the entire array is the first element.</span></span> <span data-ttu-id="eee23-125">配列全体の "末尾" は、最後の要素の "*後*" です。</span><span class="sxs-lookup"><span data-stu-id="eee23-125">The "end" of the entire array is *past* the last element.</span></span>

<span data-ttu-id="eee23-126">末尾の単語は `^1` インデックスで取得できます。</span><span class="sxs-lookup"><span data-stu-id="eee23-126">You can retrieve the last word with the `^1` index.</span></span> <span data-ttu-id="eee23-127">初期化の下に次のコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="eee23-127">Add the following code below the initialization:</span></span>

[!code-csharp[LastIndex](~/samples/csharp/tutorials/RangesIndexes/IndicesAndRanges.cs#IndicesAndRanges_LastIndex)]

<span data-ttu-id="eee23-128">次のコードでは、単語 "quick"、"brown"、"fox" から成る部分範囲が作成されます。</span><span class="sxs-lookup"><span data-stu-id="eee23-128">The following code creates a subrange with the words "quick", "brown", and "fox".</span></span> <span data-ttu-id="eee23-129">それには、`words[1]` から `words[3]` までが含まれます。</span><span class="sxs-lookup"><span data-stu-id="eee23-129">It includes `words[1]` through `words[3]`.</span></span> <span data-ttu-id="eee23-130">要素 `words[4]` が範囲内にありません。</span><span class="sxs-lookup"><span data-stu-id="eee23-130">The element `words[4]` isn't in the range.</span></span> <span data-ttu-id="eee23-131">同じメソッドに次のコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="eee23-131">Add the following code to the same method.</span></span> <span data-ttu-id="eee23-132">それをコピーして、対話型ウィンドウの下部に貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="eee23-132">Copy and paste it at the bottom of the interactive window.</span></span>

[!code-csharp[Range](~/samples/csharp/tutorials/RangesIndexes/IndicesAndRanges.cs#IndicesAndRanges_Range)]

<span data-ttu-id="eee23-133">次のコードでは、"lazy" と "dog" の部分範囲が作成されます。</span><span class="sxs-lookup"><span data-stu-id="eee23-133">The following code creates a subrange with "lazy" and "dog".</span></span> <span data-ttu-id="eee23-134">それには、`words[^2]` と `words[^1]` が含まれます。</span><span class="sxs-lookup"><span data-stu-id="eee23-134">It includes `words[^2]` and `words[^1]`.</span></span> <span data-ttu-id="eee23-135">末尾インデックス `words[^0]` は含まれません。</span><span class="sxs-lookup"><span data-stu-id="eee23-135">The end index `words[^0]` isn't included.</span></span> <span data-ttu-id="eee23-136">次のコードも追加します。</span><span class="sxs-lookup"><span data-stu-id="eee23-136">Add the following code as well:</span></span>

[!code-csharp[LastRange](~/samples/csharp/tutorials/RangesIndexes/IndicesAndRanges.cs#IndicesAndRanges_LastRange)]

<span data-ttu-id="eee23-137">次の例では、先頭と末尾の一方または両方が開いている範囲が作成されます。</span><span class="sxs-lookup"><span data-stu-id="eee23-137">The following examples create ranges that are open ended for the start, end, or both:</span></span>

[!code-csharp[PartialRange](~/samples/csharp/tutorials/RangesIndexes/IndicesAndRanges.cs#IndicesAndRanges_PartialRanges)]

<span data-ttu-id="eee23-138">範囲やインデックスを変数として宣言することもできます。</span><span class="sxs-lookup"><span data-stu-id="eee23-138">You can also declare ranges or indices as variables.</span></span> <span data-ttu-id="eee23-139">この変数は、文字 `[` と `]` の内側で使用できます。</span><span class="sxs-lookup"><span data-stu-id="eee23-139">The variable can then be used inside the `[` and `]` characters:</span></span>

[!code-csharp[IndexRangeTypes](~/samples/csharp/tutorials/RangesIndexes/IndicesAndRanges.cs#IndicesAndRanges_RangeIndexTypes)]

<span data-ttu-id="eee23-140">前の例は、さらに説明が必要な 2 つの設計上の決定を示しています。</span><span class="sxs-lookup"><span data-stu-id="eee23-140">The previous examples show two design decisions that require more explanation:</span></span>

- <span data-ttu-id="eee23-141">範囲は*排他*です。つまり、末尾のインデックスの要素が範囲内にありません。</span><span class="sxs-lookup"><span data-stu-id="eee23-141">Ranges are *exclusive*, meaning the element at the last index isn't in the range.</span></span>
- <span data-ttu-id="eee23-142">インデックス `^0` は、コレクションの "*末尾の要素*" ではなく、コレクションの "*末尾*" です。</span><span class="sxs-lookup"><span data-stu-id="eee23-142">The index `^0` is *the end* of the collection, not *the last element* in the collection.</span></span>

<span data-ttu-id="eee23-143">次のサンプルは、こうした選択肢の理由の多くを示しています。</span><span class="sxs-lookup"><span data-stu-id="eee23-143">The following sample shows many of the reasons for those choices.</span></span> <span data-ttu-id="eee23-144">`x`、`y`、`z` を変更してさまざまな組み合わせを試してください。</span><span class="sxs-lookup"><span data-stu-id="eee23-144">Modify `x`, `y`, and `z` to try different combinations.</span></span> <span data-ttu-id="eee23-145">実験するときには、有効な組み合わせになるように `x` が `y` 未満の値、`y` が `z` 未満の値を使用します。</span><span class="sxs-lookup"><span data-stu-id="eee23-145">When you experiment, use values where `x` is less than `y`, and `y` is less than `z` for valid combinations.</span></span> <span data-ttu-id="eee23-146">新しいメソッドに次のコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="eee23-146">Add the following code in a new method.</span></span> <span data-ttu-id="eee23-147">さまざまな組み合わせを試してください。</span><span class="sxs-lookup"><span data-stu-id="eee23-147">Try different combinations:</span></span>

[!code-csharp[SemanticsExamples](~/samples/csharp/tutorials/RangesIndexes/IndicesAndRanges.cs#IndicesAndRanges_Semantics)]

## <a name="scenarios-for-indices-and-ranges"></a><span data-ttu-id="eee23-148">インデックスと範囲のシナリオ</span><span class="sxs-lookup"><span data-stu-id="eee23-148">Scenarios for Indices and Ranges</span></span>

<span data-ttu-id="eee23-149">シーケンス全体の一部の範囲について何らかの分析を行う場合は、範囲とインデックスを使用することがよくあります。</span><span class="sxs-lookup"><span data-stu-id="eee23-149">You'll often use ranges and indices when you want to perform some analysis on subrange of an entire sequence.</span></span> <span data-ttu-id="eee23-150">どの部分の範囲が関係しているかを正確に読み取る場合に、この新しい構文の方が明確です。</span><span class="sxs-lookup"><span data-stu-id="eee23-150">The new syntax is clearer in reading exactly what subrange is involved.</span></span> <span data-ttu-id="eee23-151">ローカル関数 `MovingAverage` は、引数として <xref:System.Range> を受け取ります。</span><span class="sxs-lookup"><span data-stu-id="eee23-151">The local function `MovingAverage` takes a <xref:System.Range> as its argument.</span></span> <span data-ttu-id="eee23-152">このメソッドでは、最小値、最大値、および平均値を計算するときに、その範囲のみが列挙されます。</span><span class="sxs-lookup"><span data-stu-id="eee23-152">The method then enumerates just that range when calculating the min, max, and average.</span></span> <span data-ttu-id="eee23-153">プロジェクトで次のコードを試してみてください。</span><span class="sxs-lookup"><span data-stu-id="eee23-153">Try the following code in your project:</span></span>

[!code-csharp[MovingAverages](~/samples/csharp/tutorials/RangesIndexes/IndicesAndRanges.cs#IndicesAndRanges_MovingAverage)]

<span data-ttu-id="eee23-154">完成したコードは [dotnet/samples](https://github.com/dotnet/samples/tree/master/csharp/tutorials/RangesIndexes) リポジトリからダウンロードできます。</span><span class="sxs-lookup"><span data-stu-id="eee23-154">You can download the completed code from the [dotnet/samples](https://github.com/dotnet/samples/tree/master/csharp/tutorials/RangesIndexes) repository.</span></span>
