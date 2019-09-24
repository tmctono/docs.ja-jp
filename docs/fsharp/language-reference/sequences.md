---
title: シーケンス
description: シーケンスを使用F#する方法について説明します。データの大きな順序で並べ替えられたコレクションがあり、必ずしもすべての要素を使用するとは限りません。
ms.date: 02/19/2019
ms.openlocfilehash: 63e878c2c11db25a08d449070ab779a6e6a2c2eb
ms.sourcegitcommit: 56f1d1203d0075a461a10a301459d3aa452f4f47
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/24/2019
ms.locfileid: "71216762"
---
# <a name="sequences"></a><span data-ttu-id="5f247-103">シーケンス</span><span class="sxs-lookup"><span data-stu-id="5f247-103">Sequences</span></span>

> [!NOTE]
> <span data-ttu-id="5f247-104">この記事の API リファレンスのリンクをクリックすると MSDN に移動します。</span><span class="sxs-lookup"><span data-stu-id="5f247-104">The API reference links in this article will take you to MSDN.</span></span>  <span data-ttu-id="5f247-105">docs.microsoft.com API リファレンスは完全ではありません。</span><span class="sxs-lookup"><span data-stu-id="5f247-105">The docs.microsoft.com API reference is not complete.</span></span>

<span data-ttu-id="5f247-106">*シーケンス*は、すべて1つの型からなる論理的な一連の要素です。</span><span class="sxs-lookup"><span data-stu-id="5f247-106">A *sequence* is a logical series of elements all of one type.</span></span> <span data-ttu-id="5f247-107">シーケンスは、大量の順序付けられたデータのコレクションがあり、すべての要素を使用するとは限らない場合に特に便利です。</span><span class="sxs-lookup"><span data-stu-id="5f247-107">Sequences are particularly useful when you have a large, ordered collection of data but do not necessarily expect to use all of the elements.</span></span> <span data-ttu-id="5f247-108">個々のシーケンス要素は必要に応じてのみ計算されるので、すべての要素が使用されるわけではありません。</span><span class="sxs-lookup"><span data-stu-id="5f247-108">Individual sequence elements are computed only as required, so a sequence can provide better performance than a list in situations in which not all the elements are used.</span></span> <span data-ttu-id="5f247-109">シーケンスは、の`seq<'T>` `System.Collections.Generic.IEnumerable`エイリアスである型によって表されます。</span><span class="sxs-lookup"><span data-stu-id="5f247-109">Sequences are represented by the `seq<'T>` type, which is an alias for `System.Collections.Generic.IEnumerable`.</span></span> <span data-ttu-id="5f247-110">したがって、を実装`System.IEnumerable`するすべての .NET Framework 型をシーケンスとして使用できます。</span><span class="sxs-lookup"><span data-stu-id="5f247-110">Therefore, any .NET Framework type that implements `System.IEnumerable` can be used as a sequence.</span></span> <span data-ttu-id="5f247-111">[Seq モジュール](https://msdn.microsoft.com/library/54e8f059-ca52-4632-9ae9-49685ee9b684)は、シーケンスに関連する操作のサポートを提供します。</span><span class="sxs-lookup"><span data-stu-id="5f247-111">The [Seq module](https://msdn.microsoft.com/library/54e8f059-ca52-4632-9ae9-49685ee9b684) provides support for manipulations involving sequences.</span></span>

## <a name="sequence-expressions"></a><span data-ttu-id="5f247-112">シーケンス式</span><span class="sxs-lookup"><span data-stu-id="5f247-112">Sequence Expressions</span></span>

<span data-ttu-id="5f247-113">*シーケンス式*は、シーケンスに評価される式です。</span><span class="sxs-lookup"><span data-stu-id="5f247-113">A *sequence expression* is an expression that evaluates to a sequence.</span></span> <span data-ttu-id="5f247-114">シーケンス式は、さまざまな形式を取ることができます。</span><span class="sxs-lookup"><span data-stu-id="5f247-114">Sequence expressions can take a number of forms.</span></span> <span data-ttu-id="5f247-115">最も単純な形式は範囲を指定します。</span><span class="sxs-lookup"><span data-stu-id="5f247-115">The simplest form specifies a range.</span></span> <span data-ttu-id="5f247-116">たとえば、は`seq { 1 . 5 }` 、エンドポイント1と5を含む5つの要素を含むシーケンスを作成します。</span><span class="sxs-lookup"><span data-stu-id="5f247-116">For example, `seq { 1 .. 5 }` creates a sequence that contains five elements, including the endpoints 1 and 5.</span></span> <span data-ttu-id="5f247-117">2つの2つの期間の間にインクリメント (またはデクリメント) を指定することもできます。</span><span class="sxs-lookup"><span data-stu-id="5f247-117">You can also specify an increment (or decrement) between two double periods.</span></span> <span data-ttu-id="5f247-118">たとえば、次のコードでは、10の倍数のシーケンスが作成されます。</span><span class="sxs-lookup"><span data-stu-id="5f247-118">For example, the following code creates the sequence of multiples of 10.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1502.fs)]

<span data-ttu-id="5f247-119">シーケンス式は、シーケンスのF#値を生成する式で構成されます。</span><span class="sxs-lookup"><span data-stu-id="5f247-119">Sequence expressions are made up of F# expressions that produce values of the sequence.</span></span> <span data-ttu-id="5f247-120">`yield`キーワードを使用して、シーケンスの一部となる値を生成できます。</span><span class="sxs-lookup"><span data-stu-id="5f247-120">They can use the `yield` keyword to produce values that become part of the sequence.</span></span>

<span data-ttu-id="5f247-121">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="5f247-121">Following is an example.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1503.fs)]

<span data-ttu-id="5f247-122">次の例に`->`示すように`yield`、の代わりに演算子を使用する`do`ことができます。その場合は、キーワードを省略できます。</span><span class="sxs-lookup"><span data-stu-id="5f247-122">You can use the `->` operator instead of `yield`, in which case you can omit the `do` keyword, as shown in the following example.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1504.fs)]

<span data-ttu-id="5f247-123">次のコードでは、グリッドを表す配列へのインデックスと共に、座標ペアのリストが生成されます。</span><span class="sxs-lookup"><span data-stu-id="5f247-123">The following code generates a list of coordinate pairs along with an index into an array that represents the grid.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1505.fs)]

<span data-ttu-id="5f247-124">シーケンスで使用される式は、フィルターです。`if`</span><span class="sxs-lookup"><span data-stu-id="5f247-124">An `if` expression used in a sequence is a filter.</span></span> <span data-ttu-id="5f247-125">たとえば、型`isprime` `int -> bool`の関数があると仮定して、素数だけのシーケンスを生成するには、次のようにシーケンスを作成します。</span><span class="sxs-lookup"><span data-stu-id="5f247-125">For example, to generate a sequence of only prime numbers, assuming that you have a function `isprime` of type `int -> bool`, construct the sequence as follows.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1506.fs)]

<span data-ttu-id="5f247-126">反復処理で`yield`また`->`はを使用する場合、各反復処理では、シーケンスの1つの要素が生成されます。</span><span class="sxs-lookup"><span data-stu-id="5f247-126">When you use `yield` or `->` in an iteration, each iteration is expected to generate a single element of the sequence.</span></span> <span data-ttu-id="5f247-127">各反復処理で要素のシーケンスが生成さ`yield!`れる場合は、を使用します。</span><span class="sxs-lookup"><span data-stu-id="5f247-127">If each iteration produces a sequence of elements, use `yield!`.</span></span> <span data-ttu-id="5f247-128">その場合、各反復処理で生成された要素が連結され、最終的なシーケンスが生成されます。</span><span class="sxs-lookup"><span data-stu-id="5f247-128">In that case, the elements generated on each iteration are concatenated to produce the final sequence.</span></span>

<span data-ttu-id="5f247-129">シーケンス式では、複数の式を組み合わせることができます。</span><span class="sxs-lookup"><span data-stu-id="5f247-129">You can combine multiple expressions together in a sequence expression.</span></span> <span data-ttu-id="5f247-130">各式によって生成される要素は、連結されます。</span><span class="sxs-lookup"><span data-stu-id="5f247-130">The elements generated by each expression are concatenated together.</span></span> <span data-ttu-id="5f247-131">例については、このトピックの「例」のセクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="5f247-131">For an example, see the "Examples" section of this topic.</span></span>

## <a name="examples"></a><span data-ttu-id="5f247-132">使用例</span><span class="sxs-lookup"><span data-stu-id="5f247-132">Examples</span></span>

<span data-ttu-id="5f247-133">最初の例では、反復処理、フィルター、および yield を含むシーケンス式を使用して、配列を生成します。</span><span class="sxs-lookup"><span data-stu-id="5f247-133">The first example uses a sequence expression that contains an iteration, a filter, and a yield to generate an array.</span></span> <span data-ttu-id="5f247-134">このコードは、1から100までの一連の素数をコンソールに出力します。</span><span class="sxs-lookup"><span data-stu-id="5f247-134">This code prints a sequence of prime numbers between 1 and 100 to the console.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1507.fs)]

<span data-ttu-id="5f247-135">次のコードで`yield`は、を使用して、3つの要素の組で構成される乗算テーブルを作成します。各要素は2つの要素と製品で構成されています。</span><span class="sxs-lookup"><span data-stu-id="5f247-135">The following code uses `yield` to create a multiplication table that consists of tuples of three elements, each consisting of two factors and the product.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1508.fs)]

<span data-ttu-id="5f247-136">次の例では、を`yield!`使用して個々のシーケンスを1つの最終シーケンスに結合する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="5f247-136">The following example demonstrates the use of `yield!` to combine individual sequences into a single final sequence.</span></span> <span data-ttu-id="5f247-137">この場合、バイナリツリー内の各サブツリーのシーケンスは、最後のシーケンスを生成するために再帰関数で連結されます。</span><span class="sxs-lookup"><span data-stu-id="5f247-137">In this case, the sequences for each subtree in a binary tree are concatenated in a recursive function to produce the final sequence.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1509.fs)]

## <a name="using-sequences"></a><span data-ttu-id="5f247-138">シーケンスの使用</span><span class="sxs-lookup"><span data-stu-id="5f247-138">Using Sequences</span></span>

<span data-ttu-id="5f247-139">シーケンスは、[リスト](lists.md)と同じ機能の多くをサポートします。</span><span class="sxs-lookup"><span data-stu-id="5f247-139">Sequences support many of the same functions as [lists](lists.md).</span></span> <span data-ttu-id="5f247-140">シーケンスは、キー生成関数を使用したグループ化やカウントなどの操作もサポートします。</span><span class="sxs-lookup"><span data-stu-id="5f247-140">Sequences also support operations such as grouping and counting by using key-generating functions.</span></span> <span data-ttu-id="5f247-141">シーケンスは、サブシーケンスを抽出するためのさまざまな関数もサポートします。</span><span class="sxs-lookup"><span data-stu-id="5f247-141">Sequences also support more diverse functions for extracting subsequences.</span></span>

<span data-ttu-id="5f247-142">リスト、配列、セット、マップなどの多くのデータ型は、列挙可能なコレクションであるため、暗黙的にシーケンスされます。</span><span class="sxs-lookup"><span data-stu-id="5f247-142">Many data types, such as lists, arrays, sets, and maps are implicitly sequences because they are enumerable collections.</span></span> <span data-ttu-id="5f247-143">シーケンスを引数として受け取る関数は、を実装F# `System.Collections.Generic.IEnumerable<'T>`する任意の .NET Framework データ型に加えて、任意の共通データ型に対して機能します。</span><span class="sxs-lookup"><span data-stu-id="5f247-143">A function that takes a sequence as an argument works with any of the common F# data types, in addition to any .NET Framework data type that implements `System.Collections.Generic.IEnumerable<'T>`.</span></span> <span data-ttu-id="5f247-144">リストを引数として受け取る関数と比較します。この関数はリストを受け取ることしかできません。</span><span class="sxs-lookup"><span data-stu-id="5f247-144">Contrast this to a function that takes a list as an argument, which can only take lists.</span></span> <span data-ttu-id="5f247-145">型`seq<'T>`は、の`IEnumerable<'T>`型略称です。</span><span class="sxs-lookup"><span data-stu-id="5f247-145">The type `seq<'T>` is a type abbreviation for `IEnumerable<'T>`.</span></span> <span data-ttu-id="5f247-146">これは、ジェネリック`System.Collections.Generic.IEnumerable<'T>`を実装する任意の型 (配列、リスト、セット、マップF#など) と、.NET Framework コレクション型のほとんどが`seq`型と互換性があり、シーケンスが必要な場合に使用できることを意味します.</span><span class="sxs-lookup"><span data-stu-id="5f247-146">This means that any type that implements the generic `System.Collections.Generic.IEnumerable<'T>`, which includes arrays, lists, sets, and maps in F#, and also most .NET Framework collection types, is compatible with the `seq` type and can be used wherever a sequence is expected.</span></span>

## <a name="module-functions"></a><span data-ttu-id="5f247-147">モジュール関数</span><span class="sxs-lookup"><span data-stu-id="5f247-147">Module Functions</span></span>

<span data-ttu-id="5f247-148">[Fsharp.core 名前空間](https://msdn.microsoft.com/library/24f64e5f-5030-47d0-9759-8d3e398ed13f)の[Seq モジュール](https://msdn.microsoft.com/library/54e8f059-ca52-4632-9ae9-49685ee9b684)には、シーケンスを操作するための関数が含まれています。</span><span class="sxs-lookup"><span data-stu-id="5f247-148">The [Seq module](https://msdn.microsoft.com/library/54e8f059-ca52-4632-9ae9-49685ee9b684) in the [Microsoft.FSharp.Collections namespace](https://msdn.microsoft.com/library/24f64e5f-5030-47d0-9759-8d3e398ed13f) contains functions for working with sequences.</span></span> <span data-ttu-id="5f247-149">これらの関数は、リスト、配列、マップ、およびセットとも連動します。これらの型はすべて列挙可能であるため、シーケンスとして扱うことができます。</span><span class="sxs-lookup"><span data-stu-id="5f247-149">These functions work with lists, arrays, maps, and sets as well, because all of those types are enumerable, and therefore can be treated as sequences.</span></span>

## <a name="creating-sequences"></a><span data-ttu-id="5f247-150">シーケンスの作成</span><span class="sxs-lookup"><span data-stu-id="5f247-150">Creating Sequences</span></span>

<span data-ttu-id="5f247-151">シーケンス式を使用してシーケンスを作成するには、前に説明したように、または特定の関数を使用します。</span><span class="sxs-lookup"><span data-stu-id="5f247-151">You can create sequences by using sequence expressions, as described previously, or by using certain functions.</span></span>

<span data-ttu-id="5f247-152">空のシーケンスは、 [seq](https://msdn.microsoft.com/library/3c7f1c69-6117-4782-b2da-0e04d6854f59)を使用して作成できます。また、 [seq. シングルトン](https://msdn.microsoft.com/library/9b8cc460-a282-4ec5-b29a-630ab17e9de7)を使用して、指定した要素のシーケンスを1つだけ作成することもできます。</span><span class="sxs-lookup"><span data-stu-id="5f247-152">You can create an empty sequence by using [Seq.empty](https://msdn.microsoft.com/library/3c7f1c69-6117-4782-b2da-0e04d6854f59), or you can create a sequence of just one specified element by using [Seq.singleton](https://msdn.microsoft.com/library/9b8cc460-a282-4ec5-b29a-630ab17e9de7).</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/fssequences/snippet9.fs)]

<span data-ttu-id="5f247-153">[Seq. init](https://msdn.microsoft.com/library/059de69d-812c-4f8e-be86-88aa72101576)を使用して、指定した関数を使用して要素が作成されるシーケンスを作成できます。</span><span class="sxs-lookup"><span data-stu-id="5f247-153">You can use [Seq.init](https://msdn.microsoft.com/library/059de69d-812c-4f8e-be86-88aa72101576) to create a sequence for which the elements are created by using a function that you provide.</span></span> <span data-ttu-id="5f247-154">シーケンスのサイズも指定します。</span><span class="sxs-lookup"><span data-stu-id="5f247-154">You also provide a size for the sequence.</span></span> <span data-ttu-id="5f247-155">この関数は、シーケンスを反復処理するまで要素が作成されない点を除いて、 [List. init](https://msdn.microsoft.com/library/dd38c096-0ea8-4858-be6b-794b90418b83)と同じです。</span><span class="sxs-lookup"><span data-stu-id="5f247-155">This function is just like [List.init](https://msdn.microsoft.com/library/dd38c096-0ea8-4858-be6b-794b90418b83), except that the elements are not created until you iterate through the sequence.</span></span> <span data-ttu-id="5f247-156">次のコードは、`Seq.init` の使用例です。</span><span class="sxs-lookup"><span data-stu-id="5f247-156">The following code illustrates the use of `Seq.init`.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/fssequences/snippet10.fs)]

<span data-ttu-id="5f247-157">出力は次のようになります。</span><span class="sxs-lookup"><span data-stu-id="5f247-157">The output is</span></span>

```console
0 10 20 30 40
```

<span data-ttu-id="5f247-158">[Seq. ofArray](https://msdn.microsoft.com/library/299cd4d9-be72-4511-aac8-089e1ddaac99)と[Seq. ofarray&#60;&#62; t 関数](https://msdn.microsoft.com/visualfsharpdocs/conceptual/seq.oflist%5b%27t%5d-function-%5bfsharp%5d)を使用すると、配列とリストからシーケンスを作成できます。</span><span class="sxs-lookup"><span data-stu-id="5f247-158">By using [Seq.ofArray](https://msdn.microsoft.com/library/299cd4d9-be72-4511-aac8-089e1ddaac99) and [Seq.ofList&#60;'T&#62; Function](https://msdn.microsoft.com/visualfsharpdocs/conceptual/seq.oflist%5b%27t%5d-function-%5bfsharp%5d), you can create sequences from arrays and lists.</span></span> <span data-ttu-id="5f247-159">ただし、キャスト演算子を使用して、配列とリストをシーケンスに変換することもできます。</span><span class="sxs-lookup"><span data-stu-id="5f247-159">However, you can also convert arrays and lists to sequences by using a cast operator.</span></span> <span data-ttu-id="5f247-160">次のコードは、両方の手法を示しています。</span><span class="sxs-lookup"><span data-stu-id="5f247-160">Both techniques are shown in the following code.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/fssequences/snippet11.fs)]

<span data-ttu-id="5f247-161">[Seq. cast](https://msdn.microsoft.com/library/1d087db3-a8b2-41dd-8ddc-227544529334)を使用すると、で`System.Collections`定義されているような、弱く型指定されたコレクションからシーケンスを作成できます。</span><span class="sxs-lookup"><span data-stu-id="5f247-161">By using [Seq.cast](https://msdn.microsoft.com/library/1d087db3-a8b2-41dd-8ddc-227544529334), you can create a sequence from a weakly typed collection, such as those defined in `System.Collections`.</span></span> <span data-ttu-id="5f247-162">このように弱く型指定され`System.Object`たコレクションには要素型があり、 `System.Collections.Generic.IEnumerable&#96;1`非ジェネリック型を使用して列挙されます。</span><span class="sxs-lookup"><span data-stu-id="5f247-162">Such weakly typed collections have the element type `System.Object` and are enumerated by using the non-generic `System.Collections.Generic.IEnumerable&#96;1` type.</span></span> <span data-ttu-id="5f247-163">次の`Seq.cast`コードは、を使用してを`System.Collections.ArrayList`シーケンスに変換する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="5f247-163">The following code illustrates the use of `Seq.cast` to convert an `System.Collections.ArrayList` into a sequence.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/fssequences/snippet12.fs)]

<span data-ttu-id="5f247-164">無限のシーケンスを定義するには、 [Seq. initinfinite](https://msdn.microsoft.com/library/d1804e53-da92-48ec-8d6e-57eaf4c62bef)関数を使用します。</span><span class="sxs-lookup"><span data-stu-id="5f247-164">You can define infinite sequences by using the [Seq.initInfinite](https://msdn.microsoft.com/library/d1804e53-da92-48ec-8d6e-57eaf4c62bef) function.</span></span> <span data-ttu-id="5f247-165">このようなシーケンスでは、要素のインデックスから各要素を生成する関数を指定します。</span><span class="sxs-lookup"><span data-stu-id="5f247-165">For such a sequence, you provide a function that generates each element from the index of the element.</span></span> <span data-ttu-id="5f247-166">無限のシーケンスは、レイジー評価のために可能です。要素は、必要に応じて、指定した関数を呼び出すことによって作成されます。</span><span class="sxs-lookup"><span data-stu-id="5f247-166">Infinite sequences are possible because of lazy evaluation; elements are created as needed by calling the function that you specify.</span></span> <span data-ttu-id="5f247-167">次のコード例では、浮動小数点数の無限のシーケンスが生成されます。この例では、連続した整数の2乗の reciprocals が連続して作成されています。</span><span class="sxs-lookup"><span data-stu-id="5f247-167">The following code example produces an infinite sequence of floating point numbers, in this case the alternating series of reciprocals of squares of successive integers.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/fssequences/snippet13.fs)]

<span data-ttu-id="5f247-168">[Seq](https://msdn.microsoft.com/library/7d9232fc-742e-42bc-bdf7-6f130f0eff21)は、状態を受け取るコンピュテーション関数からシーケンスを生成し、シーケンス内の後続の各要素を生成するように変換します。</span><span class="sxs-lookup"><span data-stu-id="5f247-168">[Seq.unfold](https://msdn.microsoft.com/library/7d9232fc-742e-42bc-bdf7-6f130f0eff21) generates a sequence from a computation function that takes a state and transforms it to produce each subsequent element in the sequence.</span></span> <span data-ttu-id="5f247-169">状態は、各要素を計算するために使用される値であり、各要素が計算されるたびに変更できます。</span><span class="sxs-lookup"><span data-stu-id="5f247-169">The state is just a value that is used to compute each element, and can change as each element is computed.</span></span> <span data-ttu-id="5f247-170">の2番目`Seq.unfold`の引数は、シーケンスを開始するために使用される初期値です。</span><span class="sxs-lookup"><span data-stu-id="5f247-170">The second argument to `Seq.unfold` is the initial value that is used to start the sequence.</span></span> <span data-ttu-id="5f247-171">`Seq.unfold`状態にオプションの種類を使用します。これにより、 `None`値を返すことによってシーケンスを終了できます。</span><span class="sxs-lookup"><span data-stu-id="5f247-171">`Seq.unfold` uses an option type for the state, which enables you to terminate the sequence by returning the `None` value.</span></span> <span data-ttu-id="5f247-172">次のコードは、 `seq1` `unfold`操作によって生成`fib`されるシーケンス (と) の2つの例を示しています。</span><span class="sxs-lookup"><span data-stu-id="5f247-172">The following code shows two examples of sequences, `seq1` and `fib`, that are generated by an `unfold` operation.</span></span> <span data-ttu-id="5f247-173">1つ目`seq1`のは、数が20までの単純なシーケンスです。</span><span class="sxs-lookup"><span data-stu-id="5f247-173">The first, `seq1`, is just a simple sequence with numbers up to 20.</span></span> <span data-ttu-id="5f247-174">2番目`fib`のは`unfold` 、を使用してフィボナッチシーケンスを計算します。</span><span class="sxs-lookup"><span data-stu-id="5f247-174">The second, `fib`, uses `unfold` to compute the Fibonacci sequence.</span></span> <span data-ttu-id="5f247-175">フィボナッチシーケンス内の各要素は前の2つのフィボナッチ数の合計であるため、状態の値は、シーケンス内の前の2つの数値で構成される組になります。</span><span class="sxs-lookup"><span data-stu-id="5f247-175">Because each element in the Fibonacci sequence is the sum of the previous two Fibonacci numbers, the state value is a tuple that consists of the previous two numbers in the sequence.</span></span> <span data-ttu-id="5f247-176">初期値は、 `(1,1)`シーケンスの最初の2つの数値です。</span><span class="sxs-lookup"><span data-stu-id="5f247-176">The initial value is `(1,1)`, the first two numbers in the sequence.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/fssequences/snippet14.fs)]

<span data-ttu-id="5f247-177">出力は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="5f247-177">The output is as follows:</span></span>

```console
The sequence seq1 contains numbers from 0 to 20.

0 1 2 3 4 5 6 7 8 9 10 11 12 13 14 15 16 17 18 19 20

The sequence fib contains Fibonacci numbers.

2 3 5 8 13 21 34 55 89 144 233 377 610 987 1597
```

<span data-ttu-id="5f247-178">次のコードは、ここで説明するシーケンスモジュール関数の多くを使用して無限シーケンスの値を生成および計算する例です。</span><span class="sxs-lookup"><span data-stu-id="5f247-178">The following code is an example that uses many of the sequence module functions described here to generate and compute the values of infinite sequences.</span></span> <span data-ttu-id="5f247-179">コードの実行には数分かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="5f247-179">The code might take a few minutes to run.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/fssequences/snippet15.fs)]

## <a name="searching-and-finding-elements"></a><span data-ttu-id="5f247-180">要素の検索と検索</span><span class="sxs-lookup"><span data-stu-id="5f247-180">Searching and Finding Elements</span></span>

<span data-ttu-id="5f247-181">シーケンスは、リストで使用できる機能をサポートしています。[Seq.exists](https://msdn.microsoft.com/library/428c97bf-599d-4c39-a5b9-f8717c198ad1)、[Seq.exists2](https://msdn.microsoft.com/library/efdf14a4-27f7-4dc1-9281-52639e66d565)、[Seq.find](https://msdn.microsoft.com/library/02c21ecd-97e5-4e99-a4c1-b4d0b730b7d8)、[Seq.findIndex](https://msdn.microsoft.com/library/96dfe86b-df15-4d92-8316-7cd6055e09f3)、[Seq.pick](https://msdn.microsoft.com/library/a87bc771-55f7-43f9-94f9-33d8f9bf325d)、[Seq.tryFind](https://msdn.microsoft.com/library/ac43c6f5-4dc7-4e9a-a222-00b5736aee47)、および [Seq.tryFindIndex](https://msdn.microsoft.com/library/c357b221-edf6-4f68-bf40-82a3156d945a)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5f247-181">Sequences support functionality available with lists: [Seq.exists](https://msdn.microsoft.com/library/428c97bf-599d-4c39-a5b9-f8717c198ad1), [Seq.exists2](https://msdn.microsoft.com/library/efdf14a4-27f7-4dc1-9281-52639e66d565), [Seq.find](https://msdn.microsoft.com/library/02c21ecd-97e5-4e99-a4c1-b4d0b730b7d8), [Seq.findIndex](https://msdn.microsoft.com/library/96dfe86b-df15-4d92-8316-7cd6055e09f3), [Seq.pick](https://msdn.microsoft.com/library/a87bc771-55f7-43f9-94f9-33d8f9bf325d), [Seq.tryFind](https://msdn.microsoft.com/library/ac43c6f5-4dc7-4e9a-a222-00b5736aee47), and [Seq.tryFindIndex](https://msdn.microsoft.com/library/c357b221-edf6-4f68-bf40-82a3156d945a).</span></span> <span data-ttu-id="5f247-182">シーケンスで使用できるこれらの関数のバージョンによって、シーケンスは検索対象の要素までのみ評価されます。</span><span class="sxs-lookup"><span data-stu-id="5f247-182">The versions of these functions that are available for sequences evaluate the sequence only up to the element that is being searched for.</span></span> <span data-ttu-id="5f247-183">例については、「[リスト](https://msdn.microsoft.com/library/83102799-f251-42e1-93ef-64232e8c5b1d)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5f247-183">For examples, see [Lists](https://msdn.microsoft.com/library/83102799-f251-42e1-93ef-64232e8c5b1d).</span></span>

## <a name="obtaining-subsequences"></a><span data-ttu-id="5f247-184">サブシーケンスの取得</span><span class="sxs-lookup"><span data-stu-id="5f247-184">Obtaining Subsequences</span></span>

<span data-ttu-id="5f247-185">[Seq. filter](https://msdn.microsoft.com/library/7f2e9850-a660-460c-9831-3bbff5613770)と[seq. choose](https://msdn.microsoft.com/library/63b83b06-4b24-4239-bf69-a2c12d891395)は、リストで使用できる対応する関数と似ています。ただし、フィルター処理と選択は、シーケンス要素が評価されるまで発生しません。</span><span class="sxs-lookup"><span data-stu-id="5f247-185">[Seq.filter](https://msdn.microsoft.com/library/7f2e9850-a660-460c-9831-3bbff5613770) and [Seq.choose](https://msdn.microsoft.com/library/63b83b06-4b24-4239-bf69-a2c12d891395) are like the corresponding functions that are available for lists, except that the filtering and choosing does not occur until the sequence elements are evaluated.</span></span>

<span data-ttu-id="5f247-186">[Seq. truncate](https://msdn.microsoft.com/library/1892dfeb-308e-45e2-857a-3c3405d02244)は、別のシーケンスからシーケンスを作成しますが、シーケンスは指定した数の要素に制限されます。</span><span class="sxs-lookup"><span data-stu-id="5f247-186">[Seq.truncate](https://msdn.microsoft.com/library/1892dfeb-308e-45e2-857a-3c3405d02244) creates a sequence from another sequence, but limits the sequence to a specified number of elements.</span></span> <span data-ttu-id="5f247-187">[Seq. take](https://msdn.microsoft.com/library/6e75f701-640b-4c4a-9d63-4313fc090596)は、シーケンスの先頭から指定された数の要素のみを含む新しいシーケンスを作成します。</span><span class="sxs-lookup"><span data-stu-id="5f247-187">[Seq.take](https://msdn.microsoft.com/library/6e75f701-640b-4c4a-9d63-4313fc090596) creates a new sequence that contains only a specified number of elements from the start of a sequence.</span></span> <span data-ttu-id="5f247-188">指定した数よりも多い要素がシーケンス内にある場合`Seq.take` 、は`System.InvalidOperationException`をスローします。</span><span class="sxs-lookup"><span data-stu-id="5f247-188">If there are fewer elements in the sequence than you specify to take, `Seq.take` throws a `System.InvalidOperationException`.</span></span> <span data-ttu-id="5f247-189">との違いは`Seq.truncate` 、要素`Seq.truncate`の数が指定した数よりも小さい場合、はエラーを生成しないという点です。 `Seq.take`</span><span class="sxs-lookup"><span data-stu-id="5f247-189">The difference between `Seq.take` and `Seq.truncate` is that `Seq.truncate` does not produce an error if the number of elements is fewer than the number you specify.</span></span>

<span data-ttu-id="5f247-190">次のコードは、との動作との`Seq.truncate`違い`Seq.take`を示しています。</span><span class="sxs-lookup"><span data-stu-id="5f247-190">The following code shows the behavior of and differences between `Seq.truncate` and `Seq.take`.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/fssequences/snippet16.fs)]

<span data-ttu-id="5f247-191">エラーが発生する前の出力は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="5f247-191">The output, before the error occurs, is as follows.</span></span>

```console
1 4 9 16 25 
1 4 9 16 25 36 49 64 81 100 
1 4 9 16 25 
1 4 9 16 25 36 49 64 81 100
```

<span data-ttu-id="5f247-192">Seq を使用することにより、述語関数 (ブール関数) を指定し、述語がある元のシーケンスの要素で構成さ`true`れた別のシーケンスのシーケンスを作成し、最初の要素の前に停止することができ[ます。](https://msdn.microsoft.com/library/19eea4ce-66e0-4353-b015-72eb03421d92)述語が返さ`false`れる。</span><span class="sxs-lookup"><span data-stu-id="5f247-192">By using [Seq.takeWhile](https://msdn.microsoft.com/library/19eea4ce-66e0-4353-b015-72eb03421d92), you can specify a predicate function (a Boolean function) and create a sequence from another sequence made up of those elements of the original sequence for which the predicate is `true`, but stop before the first element for which the predicate returns `false`.</span></span> <span data-ttu-id="5f247-193">[Seq. skip](https://msdn.microsoft.com/library/b4eb3f08-8594-4d17-8180-852c6c688bf1)は、指定された数の別のシーケンスの最初の要素をスキップし、残りの要素を返すシーケンスを返します。</span><span class="sxs-lookup"><span data-stu-id="5f247-193">[Seq.skip](https://msdn.microsoft.com/library/b4eb3f08-8594-4d17-8180-852c6c688bf1) returns a sequence that skips a specified number of the first elements of another sequence and returns the remaining elements.</span></span> <span data-ttu-id="5f247-194">[Seq. skipwhile](https://msdn.microsoft.com/library/fb729021-2a3c-430f-83c3-0b37526f1a16)は、述語がを返し`true`た限り、別のシーケンスの最初の要素をスキップし、残りの要素を返すシーケンスを返します。このシーケンスは、述語が返す`false`最初の要素から始まります.</span><span class="sxs-lookup"><span data-stu-id="5f247-194">[Seq.skipWhile](https://msdn.microsoft.com/library/fb729021-2a3c-430f-83c3-0b37526f1a16) returns a sequence that skips the first elements of another sequence as long as the predicate returns `true`, and then returns the remaining elements, starting with the first element for which the predicate returns `false`.</span></span>

<span data-ttu-id="5f247-195">次のコード例は、の動作と`Seq.takeWhile`、 `Seq.skip`、、および`Seq.skipWhile`の違いを示しています。</span><span class="sxs-lookup"><span data-stu-id="5f247-195">The following code example illustrates the behavior of and differences between `Seq.takeWhile`, `Seq.skip`, and `Seq.skipWhile`.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/fssequences/snippet17.fs)]

<span data-ttu-id="5f247-196">出力は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="5f247-196">The output is as follows.</span></span>

```console
1 4 9 
36 49 64 81 100 
16 25 36 49 64 81 100
```

## <a name="transforming-sequences"></a><span data-ttu-id="5f247-197">シーケンスの変換</span><span class="sxs-lookup"><span data-stu-id="5f247-197">Transforming Sequences</span></span>

<span data-ttu-id="5f247-198">[Seq (ペア](https://msdn.microsoft.com/library/210dcf26-4e24-4d83-af6d-a8288b2ae4b1)) は、入力シーケンスの連続する要素を組にグループ化する新しいシーケンスを作成します。</span><span class="sxs-lookup"><span data-stu-id="5f247-198">[Seq.pairwise](https://msdn.microsoft.com/library/210dcf26-4e24-4d83-af6d-a8288b2ae4b1) creates a new sequence in which successive elements of the input sequence are grouped into tuples.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/fssequences/snippet18.fs)]

<span data-ttu-id="5f247-199">[Seq. ウィンドウ](https://msdn.microsoft.com/library/8b565b8f-d645-4dba-be22-099075fe4744)は似`Seq.pairwise`ていますが、組のシーケンスを生成するのではなく、シーケンスから隣接する要素 (*ウィンドウ*) のコピーを格納する配列のシーケンスを生成します。</span><span class="sxs-lookup"><span data-stu-id="5f247-199">[Seq.windowed](https://msdn.microsoft.com/library/8b565b8f-d645-4dba-be22-099075fe4744) is like `Seq.pairwise`, except that instead of producing a sequence of tuples, it produces a sequence of arrays that contain copies of adjacent elements (a *window*) from the sequence.</span></span> <span data-ttu-id="5f247-200">各配列で隣接する要素の数を指定します。</span><span class="sxs-lookup"><span data-stu-id="5f247-200">You specify the number of adjacent elements you want in each array.</span></span>

<span data-ttu-id="5f247-201">次のコード例は、`Seq.windowed` の使用方法を示します。</span><span class="sxs-lookup"><span data-stu-id="5f247-201">The following code example demonstrates the use of `Seq.windowed`.</span></span> <span data-ttu-id="5f247-202">この場合、ウィンドウ内の要素の数は3です。</span><span class="sxs-lookup"><span data-stu-id="5f247-202">In this case the number of elements in the window is 3.</span></span> <span data-ttu-id="5f247-203">この例で`printSeq`は、前のコード例で定義されているを使用します。</span><span class="sxs-lookup"><span data-stu-id="5f247-203">The example uses `printSeq`, which is defined in the previous code example.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/fssequences/snippet180.fs)]

<span data-ttu-id="5f247-204">出力は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="5f247-204">The output is as follows.</span></span>

<span data-ttu-id="5f247-205">初期シーケンス:</span><span class="sxs-lookup"><span data-stu-id="5f247-205">Initial sequence:</span></span>

```console
1.0 1.5 2.0 1.5 1.0 1.5 

Windows of length 3: 
[|1.0; 1.5; 2.0|] [|1.5; 2.0; 1.5|] [|2.0; 1.5; 1.0|] [|1.5; 1.0; 1.5|] 

Moving average: 
1.5 1.666666667 1.5 1.333333333
```

## <a name="operations-with-multiple-sequences"></a><span data-ttu-id="5f247-206">複数のシーケンスを持つ操作</span><span class="sxs-lookup"><span data-stu-id="5f247-206">Operations with Multiple Sequences</span></span>

<span data-ttu-id="5f247-207">[Seq](https://msdn.microsoft.com/library/0a5df8bf-0d48-44ce-bff4-e8ef1df5bca4)と[array.zip3](https://msdn.microsoft.com/library/ef13bebb-22ae-4eb9-873b-87dd29154d16)は、2つまたは3つのシーケンスを受け取り、組のシーケンスを生成します。</span><span class="sxs-lookup"><span data-stu-id="5f247-207">[Seq.zip](https://msdn.microsoft.com/library/0a5df8bf-0d48-44ce-bff4-e8ef1df5bca4) and [Seq.zip3](https://msdn.microsoft.com/library/ef13bebb-22ae-4eb9-873b-87dd29154d16) take two or three sequences and produce a sequence of tuples.</span></span> <span data-ttu-id="5f247-208">これらの関数は、[リスト](https://msdn.microsoft.com/library/83102799-f251-42e1-93ef-64232e8c5b1d)で使用できる対応する関数に似ています。</span><span class="sxs-lookup"><span data-stu-id="5f247-208">These functions are like the corresponding functions available for [lists](https://msdn.microsoft.com/library/83102799-f251-42e1-93ef-64232e8c5b1d).</span></span> <span data-ttu-id="5f247-209">1つのシーケンスを2つ以上のシーケンスに分割する対応する機能はありません。</span><span class="sxs-lookup"><span data-stu-id="5f247-209">There is no corresponding functionality to separate one sequence into two or more sequences.</span></span> <span data-ttu-id="5f247-210">シーケンスにこの機能が必要な場合は、シーケンスをリストに変換し、 [unzip](https://msdn.microsoft.com/library/639db80c-41b5-45bb-a6b4-1eaa04d61d21)を使用します。</span><span class="sxs-lookup"><span data-stu-id="5f247-210">If you need this functionality for a sequence, convert the sequence to a list and use [List.unzip](https://msdn.microsoft.com/library/639db80c-41b5-45bb-a6b4-1eaa04d61d21).</span></span>

## <a name="sorting-comparing-and-grouping"></a><span data-ttu-id="5f247-211">並べ替え、比較、およびグループ化</span><span class="sxs-lookup"><span data-stu-id="5f247-211">Sorting, Comparing, and Grouping</span></span>

<span data-ttu-id="5f247-212">リストでサポートされている並べ替え関数は、シーケンスでも使用できます。</span><span class="sxs-lookup"><span data-stu-id="5f247-212">The sorting functions supported for lists also work with sequences.</span></span> <span data-ttu-id="5f247-213">これに[は、](https://msdn.microsoft.com/library/327ea595-e77c-4529-b61e-8c6cbf5ec92e) SortBy および[seq](https://msdn.microsoft.com/library/4f8b4fb9-bf20-49d9-b4ee-dcc906c8208f)が含まれます。</span><span class="sxs-lookup"><span data-stu-id="5f247-213">This includes [Seq.sort](https://msdn.microsoft.com/library/327ea595-e77c-4529-b61e-8c6cbf5ec92e) and [Seq.sortBy](https://msdn.microsoft.com/library/4f8b4fb9-bf20-49d9-b4ee-dcc906c8208f).</span></span> <span data-ttu-id="5f247-214">これらの関数は、シーケンス全体を反復処理します。</span><span class="sxs-lookup"><span data-stu-id="5f247-214">These functions iterate through the whole sequence.</span></span>

<span data-ttu-id="5f247-215">2つのシーケンスを比較するには、 [Seq. compareWith](https://msdn.microsoft.com/library/5a740135-0b3a-4545-816f-8f91cc31290f)関数を使用します。</span><span class="sxs-lookup"><span data-stu-id="5f247-215">You compare two sequences by using the [Seq.compareWith](https://msdn.microsoft.com/library/5a740135-0b3a-4545-816f-8f91cc31290f) function.</span></span> <span data-ttu-id="5f247-216">関数は、連続する要素を順番に比較し、最初の等しくないペアが検出されたときに停止します。</span><span class="sxs-lookup"><span data-stu-id="5f247-216">The function compares successive elements in turn, and stops when it encounters the first unequal pair.</span></span> <span data-ttu-id="5f247-217">その他の要素は、比較には関与しません。</span><span class="sxs-lookup"><span data-stu-id="5f247-217">Any additional elements do not contribute to the comparison.</span></span>

<span data-ttu-id="5f247-218">`Seq.compareWith` の使用方法を次のコードに示します。</span><span class="sxs-lookup"><span data-stu-id="5f247-218">The following code shows the use of `Seq.compareWith`.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/fssequences/snippet19.fs)]

<span data-ttu-id="5f247-219">前のコードでは、最初の要素のみが計算され、検査され、結果は-1 になります。</span><span class="sxs-lookup"><span data-stu-id="5f247-219">In the previous code, only the first element is computed and examined, and the result is -1.</span></span>

<span data-ttu-id="5f247-220">[CountBy](https://msdn.microsoft.com/library/721702a5-150e-4fe8-81cd-ffbf8476cc1f)は、各要素の*キー*と呼ばれる値を生成する関数を受け取ります。</span><span class="sxs-lookup"><span data-stu-id="5f247-220">[Seq.countBy](https://msdn.microsoft.com/library/721702a5-150e-4fe8-81cd-ffbf8476cc1f) takes a function that generates a value called a *key* for each element.</span></span> <span data-ttu-id="5f247-221">各要素に対してこの関数を呼び出すことにより、各要素に対してキーが生成されます。</span><span class="sxs-lookup"><span data-stu-id="5f247-221">A key is generated for each element by calling this function on each element.</span></span> <span data-ttu-id="5f247-222">`Seq.countBy`次に、キー値を含むシーケンスと、キーの各値を生成した要素の数を返します。</span><span class="sxs-lookup"><span data-stu-id="5f247-222">`Seq.countBy` then returns a sequence that contains the key values, and a count of the number of elements that generated each value of the key.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/fssequences/snippet201.fs)]

<span data-ttu-id="5f247-223">出力は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="5f247-223">The output is as follows.</span></span>

```console
(1, 34) (2, 33) (0, 33)
```

<span data-ttu-id="5f247-224">前の出力は、キー1、キー2を生成した33値、およびキー0を生成した33値を生成した、元のシーケンスの34要素があることを示しています。</span><span class="sxs-lookup"><span data-stu-id="5f247-224">The previous output shows that there were 34 elements of the original sequence that produced the key 1, 33 values that produced the key 2, and 33 values that produced the key 0.</span></span>

<span data-ttu-id="5f247-225">シーケンスの要素をグループ化するには、 [Seq. groupBy](https://msdn.microsoft.com/library/d46a04df-1a42-40cc-a368-058c9c5806fd)を呼び出します。</span><span class="sxs-lookup"><span data-stu-id="5f247-225">You can group elements of a sequence by calling [Seq.groupBy](https://msdn.microsoft.com/library/d46a04df-1a42-40cc-a368-058c9c5806fd).</span></span> <span data-ttu-id="5f247-226">`Seq.groupBy`は、シーケンスと、要素からキーを生成する関数を受け取ります。</span><span class="sxs-lookup"><span data-stu-id="5f247-226">`Seq.groupBy` takes a sequence and a function that generates a key from an element.</span></span> <span data-ttu-id="5f247-227">関数は、シーケンスの各要素に対して実行されます。</span><span class="sxs-lookup"><span data-stu-id="5f247-227">The function is executed on each element of the sequence.</span></span> <span data-ttu-id="5f247-228">`Seq.groupBy`組のシーケンスを返します。各組の最初の要素はキーで、2番目の要素はそのキーを生成する要素のシーケンスです。</span><span class="sxs-lookup"><span data-stu-id="5f247-228">`Seq.groupBy` returns a sequence of tuples, where the first element of each tuple is the key and the second is a sequence of elements that produce that key.</span></span>

<span data-ttu-id="5f247-229">次のコード例では、 `Seq.groupBy`を使用して、0、1、および2の個別のキー値を持つ3つのグループに、1 ~ 100 の一連の数値を分割しています。</span><span class="sxs-lookup"><span data-stu-id="5f247-229">The following code example shows the use of `Seq.groupBy` to partition the sequence of numbers from 1 to 100 into three groups that have the distinct key values 0, 1, and 2.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/fssequences/snippet202.fs)]

<span data-ttu-id="5f247-230">出力は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="5f247-230">The output is as follows.</span></span>

```console
(1, seq [1; 4; 7; 10; ...]) (2, seq [2; 5; 8; 11; ...]) (0, seq [3; 6; 9; 12; ...])
```

<span data-ttu-id="5f247-231">[Seq](https://msdn.microsoft.com/library/99d01014-7e0e-4e7b-9d0a-41a61d93f401)を呼び出すことで、重複する要素を排除するシーケンスを作成できます。</span><span class="sxs-lookup"><span data-stu-id="5f247-231">You can create a sequence that eliminates duplicate elements by calling [Seq.distinct](https://msdn.microsoft.com/library/99d01014-7e0e-4e7b-9d0a-41a61d93f401).</span></span> <span data-ttu-id="5f247-232">または、 [seq.distinctby](https://msdn.microsoft.com/library/9293293b-9420-49c8-848f-401a9cd49b75)を使用することもできます。この場合、各要素に対して呼び出されるキー生成関数を受け取ります。</span><span class="sxs-lookup"><span data-stu-id="5f247-232">Or you can use [Seq.distinctBy](https://msdn.microsoft.com/library/9293293b-9420-49c8-848f-401a9cd49b75), which takes a key-generating function to be called on each element.</span></span> <span data-ttu-id="5f247-233">結果のシーケンスには、一意のキーを持つ元のシーケンスの要素が含まれます。それより前の要素に対して重複するキーを生成する要素は破棄されます。</span><span class="sxs-lookup"><span data-stu-id="5f247-233">The resulting sequence contains elements of the original sequence that have unique keys; later elements that produce a duplicate key to an earlier element are discarded.</span></span>

<span data-ttu-id="5f247-234">`Seq.distinct` の使用方法を次のコード例に示します。</span><span class="sxs-lookup"><span data-stu-id="5f247-234">The following code example illustrates the use of `Seq.distinct`.</span></span> <span data-ttu-id="5f247-235">`Seq.distinct`は、バイナリ数値を表すシーケンスを生成して、個別の要素だけが0と1であることを示すことによって示されます。</span><span class="sxs-lookup"><span data-stu-id="5f247-235">`Seq.distinct` is demonstrated by generating sequences that represent binary numbers, and then showing that the only distinct elements are 0 and 1.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/fssequences/snippet22.fs)]

<span data-ttu-id="5f247-236">次のコードは`Seq.distinctBy` 、負の数値と正の数値を格納し、キー生成関数として絶対値関数を使用するシーケンスを使用してを開始することで、を示しています。</span><span class="sxs-lookup"><span data-stu-id="5f247-236">The following code demonstrates `Seq.distinctBy` by starting with a sequence that contains negative and positive numbers and using the absolute value function as the key-generating function.</span></span> <span data-ttu-id="5f247-237">結果のシーケンスには、シーケンスの負の数値に対応する正の数値がすべて不足しています。負の数値はシーケンスの前に表示されるため、絶対値が同じ正の数値の代わりに選択されるためです。値、またはキー。</span><span class="sxs-lookup"><span data-stu-id="5f247-237">The resulting sequence is missing all the positive numbers that correspond to the negative numbers in the sequence, because the negative numbers appear earlier in the sequence and therefore are selected instead of the positive numbers that have the same absolute value, or key.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/fssequences/snippet23.fs)]

## <a name="readonly-and-cached-sequences"></a><span data-ttu-id="5f247-238">読み取り専用とキャッシュされたシーケンス</span><span class="sxs-lookup"><span data-stu-id="5f247-238">Readonly and Cached Sequences</span></span>

<span data-ttu-id="5f247-239">[Seq. readonly](https://msdn.microsoft.com/library/88059cb4-3bb0-4126-9448-fbcd48fe13a7)は、シーケンスの読み取り専用コピーを作成します。</span><span class="sxs-lookup"><span data-stu-id="5f247-239">[Seq.readonly](https://msdn.microsoft.com/library/88059cb4-3bb0-4126-9448-fbcd48fe13a7) creates a read-only copy of a sequence.</span></span> <span data-ttu-id="5f247-240">`Seq.readonly`は、配列などの読み取り/書き込みコレクションがあり、元のコレクションを変更しない場合に便利です。</span><span class="sxs-lookup"><span data-stu-id="5f247-240">`Seq.readonly` is useful when you have a read-write collection, such as an array, and you do not want to modify the original collection.</span></span> <span data-ttu-id="5f247-241">この関数は、データのカプセル化を維持するために使用できます。</span><span class="sxs-lookup"><span data-stu-id="5f247-241">This function can be used to preserve data encapsulation.</span></span> <span data-ttu-id="5f247-242">次のコード例では、配列を含む型が作成されます。</span><span class="sxs-lookup"><span data-stu-id="5f247-242">In the following code example, a type that contains an array is created.</span></span> <span data-ttu-id="5f247-243">プロパティは配列を公開しますが、配列を返すのではなく、を使用`Seq.readonly`して配列から作成されたシーケンスを返します。</span><span class="sxs-lookup"><span data-stu-id="5f247-243">A property exposes the array, but instead of returning an array, it returns a sequence that is created from the array by using `Seq.readonly`.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/fssequences/snippet24.fs)]

<span data-ttu-id="5f247-244">[Seq. cache](https://msdn.microsoft.com/library/d197f9cc-08bf-4986-9869-246e72ca73f0)は、シーケンスの格納されているバージョンを作成します。</span><span class="sxs-lookup"><span data-stu-id="5f247-244">[Seq.cache](https://msdn.microsoft.com/library/d197f9cc-08bf-4986-9869-246e72ca73f0) creates a stored version of a sequence.</span></span> <span data-ttu-id="5f247-245">シーケンス`Seq.cache`の再評価を避けるため、またはシーケンスを使用する複数のスレッドがある場合は、を使用して、各要素が1回だけ動作するようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="5f247-245">Use `Seq.cache` to avoid reevaluation of a sequence, or when you have multiple threads that use a sequence, but you must make sure that each element is acted upon only one time.</span></span> <span data-ttu-id="5f247-246">複数のスレッドで使用されているシーケンスがある場合は、元のシーケンスの値を列挙して計算するスレッドを1つ持つことができ、残りのスレッドはキャッシュされたシーケンスを使用できます。</span><span class="sxs-lookup"><span data-stu-id="5f247-246">When you have a sequence that is being used by multiple threads, you can have one thread that enumerates and computes the values for the original sequence, and remaining threads can use the cached sequence.</span></span>

## <a name="performing-computations-on-sequences"></a><span data-ttu-id="5f247-247">シーケンスに対する計算の実行</span><span class="sxs-lookup"><span data-stu-id="5f247-247">Performing Computations on Sequences</span></span>

<span data-ttu-id="5f247-248">単純な算術演算は、 [seq. average](https://msdn.microsoft.com/library/609d793b-c70f-4e36-9ab4-d928056d65b8)、seq. [sum](https://msdn.microsoft.com/library/01208515-4880-4358-91f5-af34f66dc77a)、seq. [AverageBy](https://msdn.microsoft.com/library/47c855c1-2dbd-415a-885e-b909d9d3e4f8)、 [seq. sumby](https://msdn.microsoft.com/library/68cca78c-94ed-4a45-9b8d-34d2c5f2b1b1)などのリストのようなものです。</span><span class="sxs-lookup"><span data-stu-id="5f247-248">Simple arithmetic operations are like those of lists, such as [Seq.average](https://msdn.microsoft.com/library/609d793b-c70f-4e36-9ab4-d928056d65b8), [Seq.sum](https://msdn.microsoft.com/library/01208515-4880-4358-91f5-af34f66dc77a), [Seq.averageBy](https://msdn.microsoft.com/library/47c855c1-2dbd-415a-885e-b909d9d3e4f8), [Seq.sumBy](https://msdn.microsoft.com/library/68cca78c-94ed-4a45-9b8d-34d2c5f2b1b1), and so on.</span></span>

<span data-ttu-id="5f247-249">[Seq](https://msdn.microsoft.com/library/30c4c95a-9563-4c96-bbe1-f7aacfd026e3)、 [Seq](https://msdn.microsoft.com/library/a2ad4f64-ac69-47d2-92f0-7173d9dfeae9)、および[seq. scan](https://msdn.microsoft.com/library/7e2d23e9-f153-4411-a884-b6d415ff627e)は、リストで使用できる対応する関数に似ています。</span><span class="sxs-lookup"><span data-stu-id="5f247-249">[Seq.fold](https://msdn.microsoft.com/library/30c4c95a-9563-4c96-bbe1-f7aacfd026e3), [Seq.reduce](https://msdn.microsoft.com/library/a2ad4f64-ac69-47d2-92f0-7173d9dfeae9), and [Seq.scan](https://msdn.microsoft.com/library/7e2d23e9-f153-4411-a884-b6d415ff627e) are like the corresponding functions that are available for lists.</span></span> <span data-ttu-id="5f247-250">シーケンスは、サポートを一覧表示するこれらの関数の全バリエーションのサブセットをサポートします。</span><span class="sxs-lookup"><span data-stu-id="5f247-250">Sequences support a subset of the full variations of these functions that lists support.</span></span> <span data-ttu-id="5f247-251">詳細と例については、「[リスト](lists.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5f247-251">For more information and examples, see [Lists](lists.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="5f247-252">関連項目</span><span class="sxs-lookup"><span data-stu-id="5f247-252">See also</span></span>

- [<span data-ttu-id="5f247-253">F# 言語リファレンス</span><span class="sxs-lookup"><span data-stu-id="5f247-253">F# Language Reference</span></span>](index.md)
- [<span data-ttu-id="5f247-254">F# の型</span><span class="sxs-lookup"><span data-stu-id="5f247-254">F# Types</span></span>](fsharp-types.md)
