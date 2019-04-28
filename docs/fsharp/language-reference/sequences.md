---
title: シーケンス
description: 大規模な順序付けられたデータのコレクションを持っていてもすべての要素を使用すると必ずしも期待しないときに、F# シーケンスを使用する方法について説明します。
ms.date: 02/19/2019
ms.openlocfilehash: a7791be5e8bd07d81fe9e890fc5896b181f0cb39
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61770475"
---
# <a name="sequences"></a><span data-ttu-id="94770-103">シーケンス</span><span class="sxs-lookup"><span data-stu-id="94770-103">Sequences</span></span>

> [!NOTE]
> <span data-ttu-id="94770-104">この記事の API リファレンスのリンクをクリックすると MSDN に移動します。</span><span class="sxs-lookup"><span data-stu-id="94770-104">The API reference links in this article will take you to MSDN.</span></span>  <span data-ttu-id="94770-105">docs.microsoft.com API リファレンスは完全ではありません。</span><span class="sxs-lookup"><span data-stu-id="94770-105">The docs.microsoft.com API reference is not complete.</span></span>

<span data-ttu-id="94770-106">A*シーケンス*論理的な一連の要素は、すべて 1 つの型。</span><span class="sxs-lookup"><span data-stu-id="94770-106">A *sequence* is a logical series of elements all of one type.</span></span> <span data-ttu-id="94770-107">シーケンスは、大規模な順序付けられたデータのコレクションがあるが、すべての要素を使用する予定がない場合に特に便利です。</span><span class="sxs-lookup"><span data-stu-id="94770-107">Sequences are particularly useful when you have a large, ordered collection of data but do not necessarily expect to use all of the elements.</span></span> <span data-ttu-id="94770-108">シーケンスは、すべての要素を使用ない状況で一覧よりも優れたパフォーマンスを提供できるように、シーケンスの個々 の要素としてのみ計算が必要です。</span><span class="sxs-lookup"><span data-stu-id="94770-108">Individual sequence elements are computed only as required, so a sequence can provide better performance than a list in situations in which not all the elements are used.</span></span> <span data-ttu-id="94770-109">シーケンスがによって表される、`seq<'T>`エイリアスである型の`System.Collections.Generic.IEnumerable`します。</span><span class="sxs-lookup"><span data-stu-id="94770-109">Sequences are represented by the `seq<'T>` type, which is an alias for `System.Collections.Generic.IEnumerable`.</span></span> <span data-ttu-id="94770-110">そのため、実装する .NET Framework 型`System.IEnumerable`シーケンスとして使用できます。</span><span class="sxs-lookup"><span data-stu-id="94770-110">Therefore, any .NET Framework type that implements `System.IEnumerable` can be used as a sequence.</span></span> <span data-ttu-id="94770-111">[Seq モジュール](https://msdn.microsoft.com/library/54e8f059-ca52-4632-9ae9-49685ee9b684)シーケンスに関する操作のサポートを提供します。</span><span class="sxs-lookup"><span data-stu-id="94770-111">The [Seq module](https://msdn.microsoft.com/library/54e8f059-ca52-4632-9ae9-49685ee9b684) provides support for manipulations involving sequences.</span></span>

## <a name="sequence-expressions"></a><span data-ttu-id="94770-112">シーケンス式</span><span class="sxs-lookup"><span data-stu-id="94770-112">Sequence Expressions</span></span>

<span data-ttu-id="94770-113">A*シーケンス式*シーケンスに評価される式を指定します。</span><span class="sxs-lookup"><span data-stu-id="94770-113">A *sequence expression* is an expression that evaluates to a sequence.</span></span> <span data-ttu-id="94770-114">シーケンス式は、いくつかの形式にかかります。</span><span class="sxs-lookup"><span data-stu-id="94770-114">Sequence expressions can take a number of forms.</span></span> <span data-ttu-id="94770-115">最も単純な形式では、範囲を指定します。</span><span class="sxs-lookup"><span data-stu-id="94770-115">The simplest form specifies a range.</span></span> <span data-ttu-id="94770-116">たとえば、 `seq { 1 .. 5 }` 1 と 5 のエンドポイントを含む 5 つの要素を含むシーケンスを作成します。</span><span class="sxs-lookup"><span data-stu-id="94770-116">For example, `seq { 1 .. 5 }` creates a sequence that contains five elements, including the endpoints 1 and 5.</span></span> <span data-ttu-id="94770-117">指定され、増分 (したりデクリメント) 2 つの二重ピリオドの間。</span><span class="sxs-lookup"><span data-stu-id="94770-117">You can also specify an increment (or decrement) between two double periods.</span></span> <span data-ttu-id="94770-118">たとえば、次のコードは、10 の倍数のシーケンスを作成します。</span><span class="sxs-lookup"><span data-stu-id="94770-118">For example, the following code creates the sequence of multiples of 10.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1502.fs)]

<span data-ttu-id="94770-119">シーケンス式、順序の値を生成する F# 式で構成されます。</span><span class="sxs-lookup"><span data-stu-id="94770-119">Sequence expressions are made up of F# expressions that produce values of the sequence.</span></span> <span data-ttu-id="94770-120">使用できる、`yield`キーワード、シーケンスの一部となる値を生成します。</span><span class="sxs-lookup"><span data-stu-id="94770-120">They can use the `yield` keyword to produce values that become part of the sequence.</span></span>

<span data-ttu-id="94770-121">例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="94770-121">Following is an example.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1503.fs)]

<span data-ttu-id="94770-122">使用することができます、`->`演算子の代わりに`yield`を省略した場合、`do`キーワードは、次の例に示すようにします。</span><span class="sxs-lookup"><span data-stu-id="94770-122">You can use the `->` operator instead of `yield`, in which case you can omit the `do` keyword, as shown in the following example.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1504.fs)]

<span data-ttu-id="94770-123">次のコードでは、グリッドを表す配列にインデックスと共に座標ペアの一覧を生成します。</span><span class="sxs-lookup"><span data-stu-id="94770-123">The following code generates a list of coordinate pairs along with an index into an array that represents the grid.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1505.fs)]

<span data-ttu-id="94770-124">`if`シーケンスで使用される式はフィルターです。</span><span class="sxs-lookup"><span data-stu-id="94770-124">An `if` expression used in a sequence is a filter.</span></span> <span data-ttu-id="94770-125">たとえば、関数がある場合、唯一の素数のシーケンスを生成する`isprime`型の`int -> bool`、次のように、シーケンスを作成します。</span><span class="sxs-lookup"><span data-stu-id="94770-125">For example, to generate a sequence of only prime numbers, assuming that you have a function `isprime` of type `int -> bool`, construct the sequence as follows.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1506.fs)]

<span data-ttu-id="94770-126">使用すると`yield`または`->`シーケンスの 1 つの要素を生成する、イテレーションの各反復処理が必要です。</span><span class="sxs-lookup"><span data-stu-id="94770-126">When you use `yield` or `->` in an iteration, each iteration is expected to generate a single element of the sequence.</span></span> <span data-ttu-id="94770-127">各イテレーションが要素のシーケンスを生成した場合を使用して、`yield!`します。</span><span class="sxs-lookup"><span data-stu-id="94770-127">If each iteration produces a sequence of elements, use `yield!`.</span></span> <span data-ttu-id="94770-128">その場合は、各反復処理で生成された要素は、最後のシーケンスを生成するために連結されます。</span><span class="sxs-lookup"><span data-stu-id="94770-128">In that case, the elements generated on each iteration are concatenated to produce the final sequence.</span></span>

<span data-ttu-id="94770-129">シーケンス式で複数の式を組み合わせることができます。</span><span class="sxs-lookup"><span data-stu-id="94770-129">You can combine multiple expressions together in a sequence expression.</span></span> <span data-ttu-id="94770-130">それぞれの式によって生成された要素が連結されます。</span><span class="sxs-lookup"><span data-stu-id="94770-130">The elements generated by each expression are concatenated together.</span></span> <span data-ttu-id="94770-131">例については、このトピックの「例」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="94770-131">For an example, see the "Examples" section of this topic.</span></span>

## <a name="examples"></a><span data-ttu-id="94770-132">使用例</span><span class="sxs-lookup"><span data-stu-id="94770-132">Examples</span></span>

<span data-ttu-id="94770-133">最初の例では、イテレーション、フィルター、および配列を生成する yield を含むシーケンス式を使用します。</span><span class="sxs-lookup"><span data-stu-id="94770-133">The first example uses a sequence expression that contains an iteration, a filter, and a yield to generate an array.</span></span> <span data-ttu-id="94770-134">このコードは、1 ~ 100 のコンソールに素数のシーケンスを出力します。</span><span class="sxs-lookup"><span data-stu-id="94770-134">This code prints a sequence of prime numbers between 1 and 100 to the console.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1507.fs)]

<span data-ttu-id="94770-135">次のコードでは`yield`それぞれ 2 つの要素と、製品で構成される 3 つの要素の組で構成される乗算テーブルを作成します。</span><span class="sxs-lookup"><span data-stu-id="94770-135">The following code uses `yield` to create a multiplication table that consists of tuples of three elements, each consisting of two factors and the product.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1508.fs)]

<span data-ttu-id="94770-136">使用例を次に示します`yield!`を個々 のシーケンスを 1 つの最終的なシーケンスに結合します。</span><span class="sxs-lookup"><span data-stu-id="94770-136">The following example demonstrates the use of `yield!` to combine individual sequences into a single final sequence.</span></span> <span data-ttu-id="94770-137">この場合、バイナリ ツリーの各サブツリーのシーケンスは、最後のシーケンスを生成するために、再帰関数で連結されます。</span><span class="sxs-lookup"><span data-stu-id="94770-137">In this case, the sequences for each subtree in a binary tree are concatenated in a recursive function to produce the final sequence.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1509.fs)]

## <a name="using-sequences"></a><span data-ttu-id="94770-138">シーケンスの使用</span><span class="sxs-lookup"><span data-stu-id="94770-138">Using Sequences</span></span>

<span data-ttu-id="94770-139">シーケンスと同じ機能の多くをサポートして[一覧](lists.md)します。</span><span class="sxs-lookup"><span data-stu-id="94770-139">Sequences support many of the same functions as [lists](lists.md).</span></span> <span data-ttu-id="94770-140">シーケンスは、グループ化し、キー生成関数を使用してカウントなどの操作もサポートします。</span><span class="sxs-lookup"><span data-stu-id="94770-140">Sequences also support operations such as grouping and counting by using key-generating functions.</span></span> <span data-ttu-id="94770-141">シーケンスは、サブシーケンスを抽出するためもさまざまな関数をサポートします。</span><span class="sxs-lookup"><span data-stu-id="94770-141">Sequences also support more diverse functions for extracting subsequences.</span></span>

<span data-ttu-id="94770-142">リスト、配列、セット、およびマップなど、多くのデータ型はシーケンスでは暗黙的に列挙可能なコレクションであるためです。</span><span class="sxs-lookup"><span data-stu-id="94770-142">Many data types, such as lists, arrays, sets, and maps are implicitly sequences because they are enumerable collections.</span></span> <span data-ttu-id="94770-143">実装する任意の .NET Framework データ型をさらに、引数が動作との共通の F# データ型では、シーケンスを受け取る関数`System.Collections.Generic.IEnumerable<'T>`します。</span><span class="sxs-lookup"><span data-stu-id="94770-143">A function that takes a sequence as an argument works with any of the common F# data types, in addition to any .NET Framework data type that implements `System.Collections.Generic.IEnumerable<'T>`.</span></span> <span data-ttu-id="94770-144">リスト、リストを受け取ることができるを引数として関数には、この操作を比較します。</span><span class="sxs-lookup"><span data-stu-id="94770-144">Contrast this to a function that takes a list as an argument, which can only take lists.</span></span> <span data-ttu-id="94770-145">型`seq<'T>`の型の省略形は、`IEnumerable<'T>`します。</span><span class="sxs-lookup"><span data-stu-id="94770-145">The type `seq<'T>` is a type abbreviation for `IEnumerable<'T>`.</span></span> <span data-ttu-id="94770-146">つまり、任意の型を実装するジェネリック`System.Collections.Generic.IEnumerable<'T>`、設定を含む配列、リスト、および F#、およびもほとんど、.NET Framework コレクション型のマップと互換性のある、`seq`を入力し、シーケンスが必要とされる場所に使用することができます。</span><span class="sxs-lookup"><span data-stu-id="94770-146">This means that any type that implements the generic `System.Collections.Generic.IEnumerable<'T>`, which includes arrays, lists, sets, and maps in F#, and also most .NET Framework collection types, is compatible with the `seq` type and can be used wherever a sequence is expected.</span></span>

## <a name="module-functions"></a><span data-ttu-id="94770-147">モジュール関数</span><span class="sxs-lookup"><span data-stu-id="94770-147">Module Functions</span></span>

<span data-ttu-id="94770-148">[Seq モジュール](https://msdn.microsoft.com/library/54e8f059-ca52-4632-9ae9-49685ee9b684)で、 [Microsoft.FSharp.Collections 名前空間](https://msdn.microsoft.com/library/24f64e5f-5030-47d0-9759-8d3e398ed13f)シーケンスを操作するための関数が含まれています。</span><span class="sxs-lookup"><span data-stu-id="94770-148">The [Seq module](https://msdn.microsoft.com/library/54e8f059-ca52-4632-9ae9-49685ee9b684) in the [Microsoft.FSharp.Collections namespace](https://msdn.microsoft.com/library/24f64e5f-5030-47d0-9759-8d3e398ed13f) contains functions for working with sequences.</span></span> <span data-ttu-id="94770-149">これらの関数は、すべてこれらの型の列挙可能なしたがって、シーケンスとして扱うことができますのでに、リスト、配列、マップ、およびセット同様を使用します。</span><span class="sxs-lookup"><span data-stu-id="94770-149">These functions work with lists, arrays, maps, and sets as well, because all of those types are enumerable, and therefore can be treated as sequences.</span></span>

## <a name="creating-sequences"></a><span data-ttu-id="94770-150">シーケンスの作成</span><span class="sxs-lookup"><span data-stu-id="94770-150">Creating Sequences</span></span>

<span data-ttu-id="94770-151">前述のように、シーケンス式を使用して、または特定の関数を使用してシーケンスを作成できます。</span><span class="sxs-lookup"><span data-stu-id="94770-151">You can create sequences by using sequence expressions, as described previously, or by using certain functions.</span></span>

<span data-ttu-id="94770-152">使用して空のシーケンスを作成する[Seq.empty](https://msdn.microsoft.com/library/3c7f1c69-6117-4782-b2da-0e04d6854f59)を使用して 1 つだけ指定した要素のシーケンスを作成することも[Seq.singleton](https://msdn.microsoft.com/library/9b8cc460-a282-4ec5-b29a-630ab17e9de7)します。</span><span class="sxs-lookup"><span data-stu-id="94770-152">You can create an empty sequence by using [Seq.empty](https://msdn.microsoft.com/library/3c7f1c69-6117-4782-b2da-0e04d6854f59), or you can create a sequence of just one specified element by using [Seq.singleton](https://msdn.microsoft.com/library/9b8cc460-a282-4ec5-b29a-630ab17e9de7).</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/fssequences/snippet9.fs)]

<span data-ttu-id="94770-153">使用することができます[Seq.init](https://msdn.microsoft.com/library/059de69d-812c-4f8e-be86-88aa72101576)を要素が指定した関数を使用して作成されたシーケンスを作成します。</span><span class="sxs-lookup"><span data-stu-id="94770-153">You can use [Seq.init](https://msdn.microsoft.com/library/059de69d-812c-4f8e-be86-88aa72101576) to create a sequence for which the elements are created by using a function that you provide.</span></span> <span data-ttu-id="94770-154">シーケンスのサイズを指定します。</span><span class="sxs-lookup"><span data-stu-id="94770-154">You also provide a size for the sequence.</span></span> <span data-ttu-id="94770-155">この関数と同じように[List.init](https://msdn.microsoft.com/library/dd38c096-0ea8-4858-be6b-794b90418b83)要素は、シーケンスの反復処理が完了するまでは作成されません。</span><span class="sxs-lookup"><span data-stu-id="94770-155">This function is just like [List.init](https://msdn.microsoft.com/library/dd38c096-0ea8-4858-be6b-794b90418b83), except that the elements are not created until you iterate through the sequence.</span></span> <span data-ttu-id="94770-156">次のコードは、`Seq.init` の使用例です。</span><span class="sxs-lookup"><span data-stu-id="94770-156">The following code illustrates the use of `Seq.init`.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/fssequences/snippet10.fs)]

<span data-ttu-id="94770-157">出力は次のようになります。</span><span class="sxs-lookup"><span data-stu-id="94770-157">The output is</span></span>

```
0 10 20 30 40
```

<span data-ttu-id="94770-158">使用して[Seq.ofArray](https://msdn.microsoft.com/library/299cd4d9-be72-4511-aac8-089e1ddaac99)と[Seq.ofList&#60;' T&#62;関数](https://msdn.microsoft.com/visualfsharpdocs/conceptual/seq.oflist%5b%27t%5d-function-%5bfsharp%5d)、配列とリストからシーケンスを作成することができます。</span><span class="sxs-lookup"><span data-stu-id="94770-158">By using [Seq.ofArray](https://msdn.microsoft.com/library/299cd4d9-be72-4511-aac8-089e1ddaac99) and [Seq.ofList&#60;'T&#62; Function](https://msdn.microsoft.com/visualfsharpdocs/conceptual/seq.oflist%5b%27t%5d-function-%5bfsharp%5d), you can create sequences from arrays and lists.</span></span> <span data-ttu-id="94770-159">ただし、変換することも配列とリストのシーケンスにキャスト演算子を使用しています。</span><span class="sxs-lookup"><span data-stu-id="94770-159">However, you can also convert arrays and lists to sequences by using a cast operator.</span></span> <span data-ttu-id="94770-160">両方の手法は、次のコードに表示されます。</span><span class="sxs-lookup"><span data-stu-id="94770-160">Both techniques are shown in the following code.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/fssequences/snippet11.fs)]

<span data-ttu-id="94770-161">使用して[Seq.cast](https://msdn.microsoft.com/library/1d087db3-a8b2-41dd-8ddc-227544529334)、シーケンスを作成するには、弱く型指定されたコレクションで定義されているものなどから`System.Collections`します。</span><span class="sxs-lookup"><span data-stu-id="94770-161">By using [Seq.cast](https://msdn.microsoft.com/library/1d087db3-a8b2-41dd-8ddc-227544529334), you can create a sequence from a weakly typed collection, such as those defined in `System.Collections`.</span></span> <span data-ttu-id="94770-162">このような弱く型指定されたコレクションの要素型である`System.Object`非ジェネリックを使用して列挙と`System.Collections.Generic.IEnumerable&#96;1`型。</span><span class="sxs-lookup"><span data-stu-id="94770-162">Such weakly typed collections have the element type `System.Object` and are enumerated by using the non-generic `System.Collections.Generic.IEnumerable&#96;1` type.</span></span> <span data-ttu-id="94770-163">次のコードの使用を示します`Seq.cast`に変換する、`System.Collections.ArrayList`シーケンスにします。</span><span class="sxs-lookup"><span data-stu-id="94770-163">The following code illustrates the use of `Seq.cast` to convert an `System.Collections.ArrayList` into a sequence.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/fssequences/snippet12.fs)]

<span data-ttu-id="94770-164">無限のシーケンスを使用して定義することができます、 [Seq.initInfinite](https://msdn.microsoft.com/library/d1804e53-da92-48ec-8d6e-57eaf4c62bef)関数。</span><span class="sxs-lookup"><span data-stu-id="94770-164">You can define infinite sequences by using the [Seq.initInfinite](https://msdn.microsoft.com/library/d1804e53-da92-48ec-8d6e-57eaf4c62bef) function.</span></span> <span data-ttu-id="94770-165">このようなシーケンスは、要素のインデックスから各要素を生成する関数を提供します。</span><span class="sxs-lookup"><span data-stu-id="94770-165">For such a sequence, you provide a function that generates each element from the index of the element.</span></span> <span data-ttu-id="94770-166">レイジー評価; のため、無限のシーケンスが可能指定した関数を呼び出すことによって、必要に応じて、要素が作成されます。</span><span class="sxs-lookup"><span data-stu-id="94770-166">Infinite sequences are possible because of lazy evaluation; elements are created as needed by calling the function that you specify.</span></span> <span data-ttu-id="94770-167">次のコード例では、浮動小数点、ここでは、代替の一連の連続した整数の 2 乗の逆数の無限のシーケンスを生成します。</span><span class="sxs-lookup"><span data-stu-id="94770-167">The following code example produces an infinite sequence of floating point numbers, in this case the alternating series of reciprocals of squares of successive integers.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/fssequences/snippet13.fs)]

<span data-ttu-id="94770-168">[Seq.unfold](https://msdn.microsoft.com/library/7d9232fc-742e-42bc-bdf7-6f130f0eff21)状態を受け取り、シーケンスの後続の各要素を生成するためにそれを変換する計算関数からシーケンスを生成します。</span><span class="sxs-lookup"><span data-stu-id="94770-168">[Seq.unfold](https://msdn.microsoft.com/library/7d9232fc-742e-42bc-bdf7-6f130f0eff21) generates a sequence from a computation function that takes a state and transforms it to produce each subsequent element in the sequence.</span></span> <span data-ttu-id="94770-169">状態は、値は、各要素の計算に使用し、各要素の計算を変更できます。</span><span class="sxs-lookup"><span data-stu-id="94770-169">The state is just a value that is used to compute each element, and can change as each element is computed.</span></span> <span data-ttu-id="94770-170">2 番目の引数`Seq.unfold`シーケンスを開始するために使用される初期値です。</span><span class="sxs-lookup"><span data-stu-id="94770-170">The second argument to `Seq.unfold` is the initial value that is used to start the sequence.</span></span> <span data-ttu-id="94770-171">`Seq.unfold` 返すことによって、シーケンスを終了することができます、状態のオプションの種類を使用して、`None`値。</span><span class="sxs-lookup"><span data-stu-id="94770-171">`Seq.unfold` uses an option type for the state, which enables you to terminate the sequence by returning the `None` value.</span></span> <span data-ttu-id="94770-172">次のコードは、シーケンスの 2 つの例を示しています。`seq1`と`fib`、によって生成される、`unfold`操作。</span><span class="sxs-lookup"><span data-stu-id="94770-172">The following code shows two examples of sequences, `seq1` and `fib`, that are generated by an `unfold` operation.</span></span> <span data-ttu-id="94770-173">まず、`seq1`は最大 20 の番号を持つ単純なシーケンスだけです。</span><span class="sxs-lookup"><span data-stu-id="94770-173">The first, `seq1`, is just a simple sequence with numbers up to 20.</span></span> <span data-ttu-id="94770-174">次に、`fib`を使用して`unfold`フィボナッチ シーケンスを計算します。</span><span class="sxs-lookup"><span data-stu-id="94770-174">The second, `fib`, uses `unfold` to compute the Fibonacci sequence.</span></span> <span data-ttu-id="94770-175">フィボナッチ シーケンス内の各要素は、前の 2 つのフィボナッチ数の合計であるために、状態値は、前の 2 つの数値のシーケンスで構成される組になります。</span><span class="sxs-lookup"><span data-stu-id="94770-175">Because each element in the Fibonacci sequence is the sum of the previous two Fibonacci numbers, the state value is a tuple that consists of the previous two numbers in the sequence.</span></span> <span data-ttu-id="94770-176">初期値は`(1,1)`シーケンス内の最初の 2 つの数値。</span><span class="sxs-lookup"><span data-stu-id="94770-176">The initial value is `(1,1)`, the first two numbers in the sequence.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/fssequences/snippet14.fs)]

<span data-ttu-id="94770-177">出力は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="94770-177">The output is as follows:</span></span>

```
The sequence seq1 contains numbers from 0 to 20.

0 1 2 3 4 5 6 7 8 9 10 11 12 13 14 15 16 17 18 19 20

The sequence fib contains Fibonacci numbers.

2 3 5 8 13 21 34 55 89 144 233 377 610 987 1597
```

<span data-ttu-id="94770-178">次のコードでは、ここで説明されているを生成し、無限のシーケンスの値を計算するシーケンス モジュールの関数の多くを使用する例を示します。</span><span class="sxs-lookup"><span data-stu-id="94770-178">The following code is an example that uses many of the sequence module functions described here to generate and compute the values of infinite sequences.</span></span> <span data-ttu-id="94770-179">コードは、実行に数分をかかります。</span><span class="sxs-lookup"><span data-stu-id="94770-179">The code might take a few minutes to run.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/fssequences/snippet15.fs)]

## <a name="searching-and-finding-elements"></a><span data-ttu-id="94770-180">検索して、要素の検索</span><span class="sxs-lookup"><span data-stu-id="94770-180">Searching and Finding Elements</span></span>

<span data-ttu-id="94770-181">シーケンスは、リストで使用できる機能をサポートします。[Seq.exists](https://msdn.microsoft.com/library/428c97bf-599d-4c39-a5b9-f8717c198ad1)、 [Seq.exists2](https://msdn.microsoft.com/library/efdf14a4-27f7-4dc1-9281-52639e66d565)、 [Seq.find](https://msdn.microsoft.com/library/02c21ecd-97e5-4e99-a4c1-b4d0b730b7d8)、 [Seq.findIndex](https://msdn.microsoft.com/library/96dfe86b-df15-4d92-8316-7cd6055e09f3)、 [Seq.pick](https://msdn.microsoft.com/library/a87bc771-55f7-43f9-94f9-33d8f9bf325d)、 [Seq.tryFind](https://msdn.microsoft.com/library/ac43c6f5-4dc7-4e9a-a222-00b5736aee47)、および[Seq.tryFindIndex](https://msdn.microsoft.com/library/c357b221-edf6-4f68-bf40-82a3156d945a)します。</span><span class="sxs-lookup"><span data-stu-id="94770-181">Sequences support functionality available with lists: [Seq.exists](https://msdn.microsoft.com/library/428c97bf-599d-4c39-a5b9-f8717c198ad1), [Seq.exists2](https://msdn.microsoft.com/library/efdf14a4-27f7-4dc1-9281-52639e66d565), [Seq.find](https://msdn.microsoft.com/library/02c21ecd-97e5-4e99-a4c1-b4d0b730b7d8), [Seq.findIndex](https://msdn.microsoft.com/library/96dfe86b-df15-4d92-8316-7cd6055e09f3), [Seq.pick](https://msdn.microsoft.com/library/a87bc771-55f7-43f9-94f9-33d8f9bf325d), [Seq.tryFind](https://msdn.microsoft.com/library/ac43c6f5-4dc7-4e9a-a222-00b5736aee47), and [Seq.tryFindIndex](https://msdn.microsoft.com/library/c357b221-edf6-4f68-bf40-82a3156d945a).</span></span> <span data-ttu-id="94770-182">シーケンスの使用可能なこれらの関数のバージョンの検索対象の要素に達するまでのシーケンスを評価します。</span><span class="sxs-lookup"><span data-stu-id="94770-182">The versions of these functions that are available for sequences evaluate the sequence only up to the element that is being searched for.</span></span> <span data-ttu-id="94770-183">例については、次を参照してください。[一覧](https://msdn.microsoft.com/library/83102799-f251-42e1-93ef-64232e8c5b1d)します。</span><span class="sxs-lookup"><span data-stu-id="94770-183">For examples, see [Lists](https://msdn.microsoft.com/library/83102799-f251-42e1-93ef-64232e8c5b1d).</span></span>

## <a name="obtaining-subsequences"></a><span data-ttu-id="94770-184">サブシーケンスの取得</span><span class="sxs-lookup"><span data-stu-id="94770-184">Obtaining Subsequences</span></span>

<span data-ttu-id="94770-185">[Seq.filter](https://msdn.microsoft.com/library/7f2e9850-a660-460c-9831-3bbff5613770)と[Seq.choose](https://msdn.microsoft.com/library/63b83b06-4b24-4239-bf69-a2c12d891395)はシーケンスの要素が評価されるまで、フィルタ リングと選択が発生しない点を除いて、一覧については、使用できる対応する関数のようにします。</span><span class="sxs-lookup"><span data-stu-id="94770-185">[Seq.filter](https://msdn.microsoft.com/library/7f2e9850-a660-460c-9831-3bbff5613770) and [Seq.choose](https://msdn.microsoft.com/library/63b83b06-4b24-4239-bf69-a2c12d891395) are like the corresponding functions that are available for lists, except that the filtering and choosing does not occur until the sequence elements are evaluated.</span></span>

<span data-ttu-id="94770-186">[Seq.truncate](https://msdn.microsoft.com/library/1892dfeb-308e-45e2-857a-3c3405d02244)から別のシーケンスをシーケンスを作成しますが、シーケンスの指定した要素数に制限します。</span><span class="sxs-lookup"><span data-stu-id="94770-186">[Seq.truncate](https://msdn.microsoft.com/library/1892dfeb-308e-45e2-857a-3c3405d02244) creates a sequence from another sequence, but limits the sequence to a specified number of elements.</span></span> <span data-ttu-id="94770-187">[Seq.take](https://msdn.microsoft.com/library/6e75f701-640b-4c4a-9d63-4313fc090596)指定の数のシーケンスの先頭からの要素のみを含む新しいシーケンスを作成します。</span><span class="sxs-lookup"><span data-stu-id="94770-187">[Seq.take](https://msdn.microsoft.com/library/6e75f701-640b-4c4a-9d63-4313fc090596) creates a new sequence that contains only a specified number of elements from the start of a sequence.</span></span> <span data-ttu-id="94770-188">指定するためより少ないシーケンスの要素がある場合`Seq.take`スロー、`System.InvalidOperationException`します。</span><span class="sxs-lookup"><span data-stu-id="94770-188">If there are fewer elements in the sequence than you specify to take, `Seq.take` throws a `System.InvalidOperationException`.</span></span> <span data-ttu-id="94770-189">間の差`Seq.take`と`Seq.truncate`される`Seq.truncate`要素の数が指定した数よりも少ない場合、エラーは発生しません。</span><span class="sxs-lookup"><span data-stu-id="94770-189">The difference between `Seq.take` and `Seq.truncate` is that `Seq.truncate` does not produce an error if the number of elements is fewer than the number you specify.</span></span>

<span data-ttu-id="94770-190">次のコードの動作を示します点と相違`Seq.truncate`と`Seq.take`します。</span><span class="sxs-lookup"><span data-stu-id="94770-190">The following code shows the behavior of and differences between `Seq.truncate` and `Seq.take`.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/fssequences/snippet16.fs)]

<span data-ttu-id="94770-191">出力では、エラーが発生する前に次に示します。</span><span class="sxs-lookup"><span data-stu-id="94770-191">The output, before the error occurs, is as follows.</span></span>

```
1 4 9 16 25 
1 4 9 16 25 36 49 64 81 100 
1 4 9 16 25 
1 4 9 16 25 36 49 64 81 100
```

<span data-ttu-id="94770-192">使用して[Seq.takeWhile](https://msdn.microsoft.com/library/19eea4ce-66e0-4353-b015-72eb03421d92)、述語関数 (ブール関数) を指定し、述語は、元のシーケンスの要素から成る別のシーケンスからシーケンスの作成`true`が終了します。述語を返す最初の要素の前に`false`します。</span><span class="sxs-lookup"><span data-stu-id="94770-192">By using [Seq.takeWhile](https://msdn.microsoft.com/library/19eea4ce-66e0-4353-b015-72eb03421d92), you can specify a predicate function (a Boolean function) and create a sequence from another sequence made up of those elements of the original sequence for which the predicate is `true`, but stop before the first element for which the predicate returns `false`.</span></span> <span data-ttu-id="94770-193">[Seq.skip](https://msdn.microsoft.com/library/b4eb3f08-8594-4d17-8180-852c6c688bf1)指定したもう 1 つのシーケンスの最初の要素数をスキップし、残りの要素を返すシーケンスを返します。</span><span class="sxs-lookup"><span data-stu-id="94770-193">[Seq.skip](https://msdn.microsoft.com/library/b4eb3f08-8594-4d17-8180-852c6c688bf1) returns a sequence that skips a specified number of the first elements of another sequence and returns the remaining elements.</span></span> <span data-ttu-id="94770-194">[Seq.skipWhile](https://msdn.microsoft.com/library/fb729021-2a3c-430f-83c3-0b37526f1a16)述語を返す限り、別のシーケンスの最初の要素をスキップしてシーケンスを返します`true`、述語がを返す最初の要素で始まる残りの要素を返します`false`.</span><span class="sxs-lookup"><span data-stu-id="94770-194">[Seq.skipWhile](https://msdn.microsoft.com/library/fb729021-2a3c-430f-83c3-0b37526f1a16) returns a sequence that skips the first elements of another sequence as long as the predicate returns `true`, and then returns the remaining elements, starting with the first element for which the predicate returns `false`.</span></span>

<span data-ttu-id="94770-195">次のコード例の動作を示しています点と相違`Seq.takeWhile`、 `Seq.skip`、および`Seq.skipWhile`します。</span><span class="sxs-lookup"><span data-stu-id="94770-195">The following code example illustrates the behavior of and differences between `Seq.takeWhile`, `Seq.skip`, and `Seq.skipWhile`.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/fssequences/snippet17.fs)]

<span data-ttu-id="94770-196">出力は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="94770-196">The output is as follows.</span></span>

```
1 4 9 
36 49 64 81 100 
16 25 36 49 64 81 100
```

## <a name="transforming-sequences"></a><span data-ttu-id="94770-197">シーケンスに変換します。</span><span class="sxs-lookup"><span data-stu-id="94770-197">Transforming Sequences</span></span>

<span data-ttu-id="94770-198">[Seq.pairwise](https://msdn.microsoft.com/library/210dcf26-4e24-4d83-af6d-a8288b2ae4b1)入力シーケンスの一連の要素がタプルにグループ化する新しいシーケンスを作成します。</span><span class="sxs-lookup"><span data-stu-id="94770-198">[Seq.pairwise](https://msdn.microsoft.com/library/210dcf26-4e24-4d83-af6d-a8288b2ae4b1) creates a new sequence in which successive elements of the input sequence are grouped into tuples.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/fssequences/snippet18.fs)]

<span data-ttu-id="94770-199">[Seq.windowed](https://msdn.microsoft.com/library/8b565b8f-d645-4dba-be22-099075fe4744)などは`Seq.pairwise`タプルのシーケンスを生成するには、代わりに、隣接する要素のコピーを格納する配列のシーケンスを生成する点を除いて、(、*ウィンドウ*) シーケンスから。</span><span class="sxs-lookup"><span data-stu-id="94770-199">[Seq.windowed](https://msdn.microsoft.com/library/8b565b8f-d645-4dba-be22-099075fe4744) is like `Seq.pairwise`, except that instead of producing a sequence of tuples, it produces a sequence of arrays that contain copies of adjacent elements (a *window*) from the sequence.</span></span> <span data-ttu-id="94770-200">各配列内には、隣接する要素の数を指定します。</span><span class="sxs-lookup"><span data-stu-id="94770-200">You specify the number of adjacent elements you want in each array.</span></span>

<span data-ttu-id="94770-201">次のコード例は、`Seq.windowed` の使用方法を示します。</span><span class="sxs-lookup"><span data-stu-id="94770-201">The following code example demonstrates the use of `Seq.windowed`.</span></span> <span data-ttu-id="94770-202">この場合、ウィンドウ内の要素の数は 3 です。</span><span class="sxs-lookup"><span data-stu-id="94770-202">In this case the number of elements in the window is 3.</span></span> <span data-ttu-id="94770-203">この例では`printSeq`、上記のコード例で定義されています。</span><span class="sxs-lookup"><span data-stu-id="94770-203">The example uses `printSeq`, which is defined in the previous code example.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/fssequences/snippet180.fs)]

<span data-ttu-id="94770-204">出力は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="94770-204">The output is as follows.</span></span>

<span data-ttu-id="94770-205">最初のシーケンス。</span><span class="sxs-lookup"><span data-stu-id="94770-205">Initial sequence:</span></span>

```
1.0 1.5 2.0 1.5 1.0 1.5 

Windows of length 3: 
[|1.0; 1.5; 2.0|] [|1.5; 2.0; 1.5|] [|2.0; 1.5; 1.0|] [|1.5; 1.0; 1.5|] 

Moving average: 
1.5 1.666666667 1.5 1.333333333
```

## <a name="operations-with-multiple-sequences"></a><span data-ttu-id="94770-206">複数のシーケンスでの操作</span><span class="sxs-lookup"><span data-stu-id="94770-206">Operations with Multiple Sequences</span></span>

<span data-ttu-id="94770-207">[Seq.zip](https://msdn.microsoft.com/library/0a5df8bf-0d48-44ce-bff4-e8ef1df5bca4)と[Seq.zip3](https://msdn.microsoft.com/library/ef13bebb-22ae-4eb9-873b-87dd29154d16) 2 または 3 つのシーケンスを受け取り、タプルのシーケンスを生成します。</span><span class="sxs-lookup"><span data-stu-id="94770-207">[Seq.zip](https://msdn.microsoft.com/library/0a5df8bf-0d48-44ce-bff4-e8ef1df5bca4) and [Seq.zip3](https://msdn.microsoft.com/library/ef13bebb-22ae-4eb9-873b-87dd29154d16) take two or three sequences and produce a sequence of tuples.</span></span> <span data-ttu-id="94770-208">これらの関数は、対応する関数を使用できるようには[一覧](https://msdn.microsoft.com/library/83102799-f251-42e1-93ef-64232e8c5b1d)します。</span><span class="sxs-lookup"><span data-stu-id="94770-208">These functions are like the corresponding functions available for [lists](https://msdn.microsoft.com/library/83102799-f251-42e1-93ef-64232e8c5b1d).</span></span> <span data-ttu-id="94770-209">2 つ以上のシーケンスに 1 つのシーケンスを分離する対応する機能はありません。</span><span class="sxs-lookup"><span data-stu-id="94770-209">There is no corresponding functionality to separate one sequence into two or more sequences.</span></span> <span data-ttu-id="94770-210">シーケンスのこの機能を必要がある場合、リストに、シーケンスを変換し、使用して[List.unzip](https://msdn.microsoft.com/library/639db80c-41b5-45bb-a6b4-1eaa04d61d21)します。</span><span class="sxs-lookup"><span data-stu-id="94770-210">If you need this functionality for a sequence, convert the sequence to a list and use [List.unzip](https://msdn.microsoft.com/library/639db80c-41b5-45bb-a6b4-1eaa04d61d21).</span></span>

## <a name="sorting-comparing-and-grouping"></a><span data-ttu-id="94770-211">並べ替え、比較、およびグループ化</span><span class="sxs-lookup"><span data-stu-id="94770-211">Sorting, Comparing, and Grouping</span></span>

<span data-ttu-id="94770-212">リストの並べ替え関数は、シーケンスでも動作します。</span><span class="sxs-lookup"><span data-stu-id="94770-212">The sorting functions supported for lists also work with sequences.</span></span> <span data-ttu-id="94770-213">これが含まれています[Seq.sort](https://msdn.microsoft.com/library/327ea595-e77c-4529-b61e-8c6cbf5ec92e)と[Seq.sortBy](https://msdn.microsoft.com/library/4f8b4fb9-bf20-49d9-b4ee-dcc906c8208f)します。</span><span class="sxs-lookup"><span data-stu-id="94770-213">This includes [Seq.sort](https://msdn.microsoft.com/library/327ea595-e77c-4529-b61e-8c6cbf5ec92e) and [Seq.sortBy](https://msdn.microsoft.com/library/4f8b4fb9-bf20-49d9-b4ee-dcc906c8208f).</span></span> <span data-ttu-id="94770-214">これらの関数は、シーケンス全体を反復処理します。</span><span class="sxs-lookup"><span data-stu-id="94770-214">These functions iterate through the whole sequence.</span></span>

<span data-ttu-id="94770-215">使用して 2 つのシーケンスを比較する、 [Seq.compareWith](https://msdn.microsoft.com/library/5a740135-0b3a-4545-816f-8f91cc31290f)関数。</span><span class="sxs-lookup"><span data-stu-id="94770-215">You compare two sequences by using the [Seq.compareWith](https://msdn.microsoft.com/library/5a740135-0b3a-4545-816f-8f91cc31290f) function.</span></span> <span data-ttu-id="94770-216">関数は、さらに、一連の要素を比較し、最初の等しくないペアを見つけたときに停止します。</span><span class="sxs-lookup"><span data-stu-id="94770-216">The function compares successive elements in turn, and stops when it encounters the first unequal pair.</span></span> <span data-ttu-id="94770-217">追加の要素は、比較には影響しません。</span><span class="sxs-lookup"><span data-stu-id="94770-217">Any additional elements do not contribute to the comparison.</span></span>

<span data-ttu-id="94770-218">`Seq.compareWith` の使用方法を次のコードに示します。</span><span class="sxs-lookup"><span data-stu-id="94770-218">The following code shows the use of `Seq.compareWith`.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/fssequences/snippet19.fs)]

<span data-ttu-id="94770-219">前のコードでは、最初の要素のみが計算され、検査すると、し、結果は-1。</span><span class="sxs-lookup"><span data-stu-id="94770-219">In the previous code, only the first element is computed and examined, and the result is -1.</span></span>

<span data-ttu-id="94770-220">[Seq.countBy](https://msdn.microsoft.com/library/721702a5-150e-4fe8-81cd-ffbf8476cc1f)という値を生成する関数を受け取り、*キー*要素ごとにします。</span><span class="sxs-lookup"><span data-stu-id="94770-220">[Seq.countBy](https://msdn.microsoft.com/library/721702a5-150e-4fe8-81cd-ffbf8476cc1f) takes a function that generates a value called a *key* for each element.</span></span> <span data-ttu-id="94770-221">各要素に対してこの関数を呼び出すことによって各要素のキーが生成されます。</span><span class="sxs-lookup"><span data-stu-id="94770-221">A key is generated for each element by calling this function on each element.</span></span> <span data-ttu-id="94770-222">`Seq.countBy` キーの値とキーの各値を生成する要素の数を含むシーケンスを返します。</span><span class="sxs-lookup"><span data-stu-id="94770-222">`Seq.countBy` then returns a sequence that contains the key values, and a count of the number of elements that generated each value of the key.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/fssequences/snippet201.fs)]

<span data-ttu-id="94770-223">出力は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="94770-223">The output is as follows.</span></span>

```
(1, 34) (2, 33) (0, 33)
```

<span data-ttu-id="94770-224">前の出力は、2、キーを生成する 33 の値と 0 キーを生成した 33 値 34 1、キーの生成元のシーケンスの要素があったことを示しています。</span><span class="sxs-lookup"><span data-stu-id="94770-224">The previous output shows that there were 34 elements of the original sequence that produced the key 1, 33 values that produced the key 2, and 33 values that produced the key 0.</span></span>

<span data-ttu-id="94770-225">呼び出すことによって、シーケンスの要素をグループ化できます[Seq.groupBy](https://msdn.microsoft.com/library/d46a04df-1a42-40cc-a368-058c9c5806fd)します。</span><span class="sxs-lookup"><span data-stu-id="94770-225">You can group elements of a sequence by calling [Seq.groupBy](https://msdn.microsoft.com/library/d46a04df-1a42-40cc-a368-058c9c5806fd).</span></span> <span data-ttu-id="94770-226">`Seq.groupBy` シーケンスと要素からキーを生成する関数を受け取ります。</span><span class="sxs-lookup"><span data-stu-id="94770-226">`Seq.groupBy` takes a sequence and a function that generates a key from an element.</span></span> <span data-ttu-id="94770-227">関数は、シーケンスの各要素に対して実行されます。</span><span class="sxs-lookup"><span data-stu-id="94770-227">The function is executed on each element of the sequence.</span></span> <span data-ttu-id="94770-228">`Seq.groupBy` それぞれの組の最初の要素がキーで、2 つ目は、そのキーを生成する要素のシーケンスは、タプルのシーケンスを返します。</span><span class="sxs-lookup"><span data-stu-id="94770-228">`Seq.groupBy` returns a sequence of tuples, where the first element of each tuple is the key and the second is a sequence of elements that produce that key.</span></span>

<span data-ttu-id="94770-229">次のコード例は、の使用を示しています。`Seq.groupBy`を 0、1、および 2 は、個別のキー値を持つ 3 つのグループに 1 から 100 の数値のシーケンスをパーティション分割します。</span><span class="sxs-lookup"><span data-stu-id="94770-229">The following code example shows the use of `Seq.groupBy` to partition the sequence of numbers from 1 to 100 into three groups that have the distinct key values 0, 1, and 2.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/fssequences/snippet202.fs)]

<span data-ttu-id="94770-230">出力は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="94770-230">The output is as follows.</span></span>

```
(1, seq [1; 4; 7; 10; ...]) (2, seq [2; 5; 8; 11; ...]) (0, seq [3; 6; 9; 12; ...])
```

<span data-ttu-id="94770-231">呼び出すことによって、重複する要素を排除するシーケンスを作成する[Seq.distinct](https://msdn.microsoft.com/library/99d01014-7e0e-4e7b-9d0a-41a61d93f401)します。</span><span class="sxs-lookup"><span data-stu-id="94770-231">You can create a sequence that eliminates duplicate elements by calling [Seq.distinct](https://msdn.microsoft.com/library/99d01014-7e0e-4e7b-9d0a-41a61d93f401).</span></span> <span data-ttu-id="94770-232">使用することもできます[Seq.distinctBy](https://msdn.microsoft.com/library/9293293b-9420-49c8-848f-401a9cd49b75)、各要素に対して呼び出されるキー生成関数を受け取ります。</span><span class="sxs-lookup"><span data-stu-id="94770-232">Or you can use [Seq.distinctBy](https://msdn.microsoft.com/library/9293293b-9420-49c8-848f-401a9cd49b75), which takes a key-generating function to be called on each element.</span></span> <span data-ttu-id="94770-233">結果のシーケンスに固有のキーのある、元のシーケンスの要素が含まれています以前の要素に重複するキーの生成後の要素は破棄されます。</span><span class="sxs-lookup"><span data-stu-id="94770-233">The resulting sequence contains elements of the original sequence that have unique keys; later elements that produce a duplicate key to an earlier element are discarded.</span></span>

<span data-ttu-id="94770-234">`Seq.distinct` の使用方法を次のコード例に示します。</span><span class="sxs-lookup"><span data-stu-id="94770-234">The following code example illustrates the use of `Seq.distinct`.</span></span> <span data-ttu-id="94770-235">`Seq.distinct` バイナリの数値を表すシーケンスを生成して、表示のみの個別の要素には 0 と 1 で示されます。</span><span class="sxs-lookup"><span data-stu-id="94770-235">`Seq.distinct` is demonstrated by generating sequences that represent binary numbers, and then showing that the only distinct elements are 0 and 1.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/fssequences/snippet22.fs)]

<span data-ttu-id="94770-236">次のコード例`Seq.distinctBy`負と正の数値を含むシーケンスを開始し、キー生成関数と絶対値関数を使用します。</span><span class="sxs-lookup"><span data-stu-id="94770-236">The following code demonstrates `Seq.distinctBy` by starting with a sequence that contains negative and positive numbers and using the absolute value function as the key-generating function.</span></span> <span data-ttu-id="94770-237">結果のシーケンスには負の数値がシーケンスの前表示され、したがって、同じ絶対値が正の数値ではなく、選択するために、シーケンス内の負の数値に対応するすべての正の数値がありません。値、またはキー。</span><span class="sxs-lookup"><span data-stu-id="94770-237">The resulting sequence is missing all the positive numbers that correspond to the negative numbers in the sequence, because the negative numbers appear earlier in the sequence and therefore are selected instead of the positive numbers that have the same absolute value, or key.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/fssequences/snippet23.fs)]

## <a name="readonly-and-cached-sequences"></a><span data-ttu-id="94770-238">読み取り専用とキャッシュされたシーケンス</span><span class="sxs-lookup"><span data-stu-id="94770-238">Readonly and Cached Sequences</span></span>

<span data-ttu-id="94770-239">[Seq.readonly](https://msdn.microsoft.com/library/88059cb4-3bb0-4126-9448-fbcd48fe13a7)シーケンスの読み取り専用コピーを作成します。</span><span class="sxs-lookup"><span data-stu-id="94770-239">[Seq.readonly](https://msdn.microsoft.com/library/88059cb4-3bb0-4126-9448-fbcd48fe13a7) creates a read-only copy of a sequence.</span></span> <span data-ttu-id="94770-240">`Seq.readonly` 配列などの読み取り/書き込みコレクションがあるし、元のコレクションを変更したくない場合に役立ちます。</span><span class="sxs-lookup"><span data-stu-id="94770-240">`Seq.readonly` is useful when you have a read-write collection, such as an array, and you do not want to modify the original collection.</span></span> <span data-ttu-id="94770-241">この関数は、データのカプセル化を保持するために使用できます。</span><span class="sxs-lookup"><span data-stu-id="94770-241">This function can be used to preserve data encapsulation.</span></span> <span data-ttu-id="94770-242">次のコード例では、配列を含む型が作成されます。</span><span class="sxs-lookup"><span data-stu-id="94770-242">In the following code example, a type that contains an array is created.</span></span> <span data-ttu-id="94770-243">プロパティは、配列を公開しますが、配列を返す代わりを使用して、配列から作成されたシーケンスを返します`Seq.readonly`します。</span><span class="sxs-lookup"><span data-stu-id="94770-243">A property exposes the array, but instead of returning an array, it returns a sequence that is created from the array by using `Seq.readonly`.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/fssequences/snippet24.fs)]

<span data-ttu-id="94770-244">[Seq.cache](https://msdn.microsoft.com/library/d197f9cc-08bf-4986-9869-246e72ca73f0)シーケンスの保存されているバージョンを作成します。</span><span class="sxs-lookup"><span data-stu-id="94770-244">[Seq.cache](https://msdn.microsoft.com/library/d197f9cc-08bf-4986-9869-246e72ca73f0) creates a stored version of a sequence.</span></span> <span data-ttu-id="94770-245">使用して、`Seq.cache`を避けるために再評価シーケンス、または、シーケンスを使用して複数のスレッドが、各要素は、1 回だけに機能を確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="94770-245">Use `Seq.cache` to avoid reevaluation of a sequence, or when you have multiple threads that use a sequence, but you must make sure that each element is acted upon only one time.</span></span> <span data-ttu-id="94770-246">複数のスレッドによって使用されているシーケンスがある場合は、する 1 つのスレッドを列挙し、元のシーケンスの値を計算することができ、残りのスレッドは、キャッシュされたシーケンスを使用できます。</span><span class="sxs-lookup"><span data-stu-id="94770-246">When you have a sequence that is being used by multiple threads, you can have one thread that enumerates and computes the values for the original sequence, and remaining threads can use the cached sequence.</span></span>

## <a name="performing-computations-on-sequences"></a><span data-ttu-id="94770-247">シーケンスに対する計算の実行</span><span class="sxs-lookup"><span data-stu-id="94770-247">Performing Computations on Sequences</span></span>

<span data-ttu-id="94770-248">などは、一覧のような単純な算術演算[Seq.average](https://msdn.microsoft.com/library/609d793b-c70f-4e36-9ab4-d928056d65b8)、 [Seq.sum](https://msdn.microsoft.com/library/01208515-4880-4358-91f5-af34f66dc77a)、 [Seq.averageBy](https://msdn.microsoft.com/library/47c855c1-2dbd-415a-885e-b909d9d3e4f8)、 [Seq.sumBy](https://msdn.microsoft.com/library/68cca78c-94ed-4a45-9b8d-34d2c5f2b1b1)など。</span><span class="sxs-lookup"><span data-stu-id="94770-248">Simple arithmetic operations are like those of lists, such as [Seq.average](https://msdn.microsoft.com/library/609d793b-c70f-4e36-9ab4-d928056d65b8), [Seq.sum](https://msdn.microsoft.com/library/01208515-4880-4358-91f5-af34f66dc77a), [Seq.averageBy](https://msdn.microsoft.com/library/47c855c1-2dbd-415a-885e-b909d9d3e4f8), [Seq.sumBy](https://msdn.microsoft.com/library/68cca78c-94ed-4a45-9b8d-34d2c5f2b1b1), and so on.</span></span>

<span data-ttu-id="94770-249">[Seq.fold](https://msdn.microsoft.com/library/30c4c95a-9563-4c96-bbe1-f7aacfd026e3)、 [Seq.reduce](https://msdn.microsoft.com/library/a2ad4f64-ac69-47d2-92f0-7173d9dfeae9)、および[Seq.scan](https://msdn.microsoft.com/library/7e2d23e9-f153-4411-a884-b6d415ff627e)はリストの使用できる対応する関数のようにします。</span><span class="sxs-lookup"><span data-stu-id="94770-249">[Seq.fold](https://msdn.microsoft.com/library/30c4c95a-9563-4c96-bbe1-f7aacfd026e3), [Seq.reduce](https://msdn.microsoft.com/library/a2ad4f64-ac69-47d2-92f0-7173d9dfeae9), and [Seq.scan](https://msdn.microsoft.com/library/7e2d23e9-f153-4411-a884-b6d415ff627e) are like the corresponding functions that are available for lists.</span></span> <span data-ttu-id="94770-250">シーケンスは、リストをサポートするこれらの関数の完全なバリエーションのサブセットをサポートします。</span><span class="sxs-lookup"><span data-stu-id="94770-250">Sequences support a subset of the full variations of these functions that lists support.</span></span> <span data-ttu-id="94770-251">詳細と例については、次を参照してください。[一覧](lists.md)します。</span><span class="sxs-lookup"><span data-stu-id="94770-251">For more information and examples, see [Lists](lists.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="94770-252">関連項目</span><span class="sxs-lookup"><span data-stu-id="94770-252">See also</span></span>

- [<span data-ttu-id="94770-253">F# 言語リファレンス</span><span class="sxs-lookup"><span data-stu-id="94770-253">F# Language Reference</span></span>](index.md)
- [<span data-ttu-id="94770-254">F# の型</span><span class="sxs-lookup"><span data-stu-id="94770-254">F# Types</span></span>](fsharp-types.md)
