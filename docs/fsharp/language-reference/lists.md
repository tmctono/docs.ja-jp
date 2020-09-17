---
title: リスト
description: 'F # のリストについて説明します。同じ型の順序付けられ、変更できない一連の要素です。'
ms.date: 08/13/2020
ms.openlocfilehash: 567731eb57b77d60d3dd847630d5676e8d047d09
ms.sourcegitcommit: fe8877e564deb68d77fa4b79f55584ac8d7e8997
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/17/2020
ms.locfileid: "90720349"
---
# <a name="lists"></a><span data-ttu-id="520dc-103">リスト</span><span class="sxs-lookup"><span data-stu-id="520dc-103">Lists</span></span>

<span data-ttu-id="520dc-104">F# のリストは、順序が指定されており変更できない一連の同じ型の要素です。</span><span class="sxs-lookup"><span data-stu-id="520dc-104">A list in F# is an ordered, immutable series of elements of the same type.</span></span> <span data-ttu-id="520dc-105">リストに対して基本的な操作を実行するには、 [List モジュール](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html)の関数を使用します。</span><span class="sxs-lookup"><span data-stu-id="520dc-105">To perform basic operations on lists, use the functions in the [List module](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html).</span></span>

## <a name="creating-and-initializing-lists"></a><span data-ttu-id="520dc-106">リストの作成と初期化</span><span class="sxs-lookup"><span data-stu-id="520dc-106">Creating and Initializing Lists</span></span>

<span data-ttu-id="520dc-107">リストを定義するには、次のコード行に示すように、セミコロンで区切って明示的にリストした要素を角かっこで囲みます。</span><span class="sxs-lookup"><span data-stu-id="520dc-107">You can define a list by explicitly listing out the elements, separated by semicolons and enclosed in square brackets, as shown in the following line of code.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1301.fs)]

<span data-ttu-id="520dc-108">要素間に改行を挿入することもできます。その場合はセミコロンの区切り記号を省略できます。</span><span class="sxs-lookup"><span data-stu-id="520dc-108">You can also put line breaks between elements, in which case the semicolons are optional.</span></span> <span data-ttu-id="520dc-109">要素の初期化式が長い場合、各要素にコメントを含める場合は、改行の構文を使用するとコードが読みやすくなります。</span><span class="sxs-lookup"><span data-stu-id="520dc-109">The latter syntax can result in more readable code when the element initialization expressions are longer, or when you want to include a comment for each element.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet13011.fs)]

<span data-ttu-id="520dc-110">通常、リストの要素はすべて同じ型である必要があります。</span><span class="sxs-lookup"><span data-stu-id="520dc-110">Normally, all list elements must be the same type.</span></span> <span data-ttu-id="520dc-111">例外として、要素が基本型として指定されているリストには、派生型の要素を含めることができます。</span><span class="sxs-lookup"><span data-stu-id="520dc-111">An exception is that a list in which the elements are specified to be a base type can have elements that are derived types.</span></span> <span data-ttu-id="520dc-112">したがって次に示す例は、`Button` と `CheckBox` の両方が `Control` から派生しているため、受け入れられます。</span><span class="sxs-lookup"><span data-stu-id="520dc-112">Thus the following is acceptable, because both `Button` and `CheckBox` derive from `Control`.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet13012.fs)]

<span data-ttu-id="520dc-113">また、次のコードで示すように、整数を範囲演算子 (`..`) で区切って示した範囲を使用して、リストの要素を定義することもできます。</span><span class="sxs-lookup"><span data-stu-id="520dc-113">You can also define list elements by using a range indicated by integers separated by the range operator (`..`), as shown in the following code.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1302.fs)]

<span data-ttu-id="520dc-114">空のリストは、間に何も含まない 1 組の角かっこで示します。</span><span class="sxs-lookup"><span data-stu-id="520dc-114">An empty list is specified by a pair of square brackets with nothing in between them.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1304.fs)]

<span data-ttu-id="520dc-115">シーケンス式を使用してリストを作成することもできます。</span><span class="sxs-lookup"><span data-stu-id="520dc-115">You can also use a sequence expression to create a list.</span></span> <span data-ttu-id="520dc-116">詳細については、「 [シーケンス式](sequences.md#sequence-expressions) 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="520dc-116">See [Sequence Expressions](sequences.md#sequence-expressions) for more information.</span></span> <span data-ttu-id="520dc-117">たとえば、次のコードでは 1 から 10 までの整数の 2 乗のリストが作成されます。</span><span class="sxs-lookup"><span data-stu-id="520dc-117">For example, the following code creates a list of squares of integers from 1 to 10.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1303.fs)]

## <a name="operators-for-working-with-lists"></a><span data-ttu-id="520dc-118">リストの操作に使用する演算子</span><span class="sxs-lookup"><span data-stu-id="520dc-118">Operators for Working with Lists</span></span>

<span data-ttu-id="520dc-119">リストに要素を付加するには、`::` (cons) 演算子を使用します。</span><span class="sxs-lookup"><span data-stu-id="520dc-119">You can attach elements to a list by using the `::` (cons) operator.</span></span> <span data-ttu-id="520dc-120">`list1` が `[2; 3; 4]` の場合、次のコードでは `list2` が `[100; 2; 3; 4]` として作成されます。</span><span class="sxs-lookup"><span data-stu-id="520dc-120">If `list1` is `[2; 3; 4]`, the following code creates `list2` as `[100; 2; 3; 4]`.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1305.fs)]

<span data-ttu-id="520dc-121">互換性のある型を含むリストを連結するには、次のコードに示すように `@` 演算子を使用します。</span><span class="sxs-lookup"><span data-stu-id="520dc-121">You can concatenate lists that have compatible types by using the `@` operator, as in the following code.</span></span> <span data-ttu-id="520dc-122">`list1` が `[2; 3; 4]` であり、`list2` が `[100; 2; 3; 4]` の場合、このコードでは `list3` が `[2; 3; 4; 100; 2; 3; 4]` として作成されます。</span><span class="sxs-lookup"><span data-stu-id="520dc-122">If `list1` is `[2; 3; 4]` and `list2` is `[100; 2; 3; 4]`, this code creates `list3` as `[2; 3; 4; 100; 2; 3; 4]`.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1306.fs)]

<span data-ttu-id="520dc-123">リストに対する操作を実行する関数は、 [List モジュール](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html)で使用できます。</span><span class="sxs-lookup"><span data-stu-id="520dc-123">Functions for performing operations on lists are available in the [List module](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html).</span></span>

<span data-ttu-id="520dc-124">F# のリストは変更できないため、変更操作を行うと、既存のリストが変更されるのではなく、新しいリストが生成されます。</span><span class="sxs-lookup"><span data-stu-id="520dc-124">Because lists in F# are immutable, any modifying operations generate new lists instead of modifying existing lists.</span></span>

<span data-ttu-id="520dc-125">F # のリストは、シングルリンクリストとして実装されます。これは、リストの先頭にのみアクセスする操作が O (1) であり、要素アクセスが O (*n*) であることを意味します。</span><span class="sxs-lookup"><span data-stu-id="520dc-125">Lists in F# are implemented as singly linked lists, which means that operations that access only the head of the list are O(1), and element access is O(*n*).</span></span>

## <a name="properties"></a><span data-ttu-id="520dc-126">Properties</span><span class="sxs-lookup"><span data-stu-id="520dc-126">Properties</span></span>

<span data-ttu-id="520dc-127">リスト型では次のプロパティがサポートされています。</span><span class="sxs-lookup"><span data-stu-id="520dc-127">The list type supports the following properties:</span></span>

|<span data-ttu-id="520dc-128">プロパティ</span><span class="sxs-lookup"><span data-stu-id="520dc-128">Property</span></span>|<span data-ttu-id="520dc-129">Type</span><span class="sxs-lookup"><span data-stu-id="520dc-129">Type</span></span>|<span data-ttu-id="520dc-130">説明</span><span class="sxs-lookup"><span data-stu-id="520dc-130">Description</span></span>|
|--------|----|-----------|
|[<span data-ttu-id="520dc-131">Head</span><span class="sxs-lookup"><span data-stu-id="520dc-131">Head</span></span>](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-list-1.html#Head)|`'T`|<span data-ttu-id="520dc-132">1 番目の要素。</span><span class="sxs-lookup"><span data-stu-id="520dc-132">The first element.</span></span>|
|[<span data-ttu-id="520dc-133">空</span><span class="sxs-lookup"><span data-stu-id="520dc-133">Empty</span></span>](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-list-1.html#Empty)|`'T list`|<span data-ttu-id="520dc-134">該当する型の空のリストを返す静的プロパティ。</span><span class="sxs-lookup"><span data-stu-id="520dc-134">A static property that returns an empty list of the appropriate type.</span></span>|
|[<span data-ttu-id="520dc-135">IsEmpty</span><span class="sxs-lookup"><span data-stu-id="520dc-135">IsEmpty</span></span>](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-list-1.html#IsEmpty)|`bool`|<span data-ttu-id="520dc-136">リストに要素がない場合は `true` です。</span><span class="sxs-lookup"><span data-stu-id="520dc-136">`true` if the list has no elements.</span></span>|
|[<span data-ttu-id="520dc-137">Item</span><span class="sxs-lookup"><span data-stu-id="520dc-137">Item</span></span>](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-list-1.html#Item)|`'T`|<span data-ttu-id="520dc-138">指定したインデックスの要素 (起点を 0 とする)。</span><span class="sxs-lookup"><span data-stu-id="520dc-138">The element at the specified index (zero-based).</span></span>|
|<span data-ttu-id="520dc-139">[[データ型]](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-list-1.html#Length)</span><span class="sxs-lookup"><span data-stu-id="520dc-139">[Length](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-list-1.html#Length)</span></span>|`int`|<span data-ttu-id="520dc-140">要素の数。</span><span class="sxs-lookup"><span data-stu-id="520dc-140">The number of elements.</span></span>|
|[<span data-ttu-id="520dc-141">Tail</span><span class="sxs-lookup"><span data-stu-id="520dc-141">Tail</span></span>](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-list-1.html#Tail)|`'T list`|<span data-ttu-id="520dc-142">1 番目の要素を除いたリスト。</span><span class="sxs-lookup"><span data-stu-id="520dc-142">The list without the first element.</span></span>|

<span data-ttu-id="520dc-143">これらのプロパティを使用したいくつかの例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="520dc-143">Following are some examples of using these properties.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1307.fs)]

## <a name="using-lists"></a><span data-ttu-id="520dc-144">リストの使用</span><span class="sxs-lookup"><span data-stu-id="520dc-144">Using Lists</span></span>

<span data-ttu-id="520dc-145"> リストを使用してプログラミングを行うと、少量のコードで複雑な操作を実行できます。</span><span class="sxs-lookup"><span data-stu-id="520dc-145">Programming with lists enables you to perform complex operations with a small amount of code.</span></span> <span data-ttu-id="520dc-146">このセクションでは、関数型プログラミングにおいて重要なリストに対する一般的な操作について説明します。</span><span class="sxs-lookup"><span data-stu-id="520dc-146">This section describes common operations on lists that are important to functional programming.</span></span>

### <a name="recursion-with-lists"></a><span data-ttu-id="520dc-147">リストを使用した再帰</span><span class="sxs-lookup"><span data-stu-id="520dc-147">Recursion with Lists</span></span>

<span data-ttu-id="520dc-148">リストは、再帰的なプログラミング技法に非常に適しています。</span><span class="sxs-lookup"><span data-stu-id="520dc-148">Lists are uniquely suited to recursive programming techniques.</span></span> <span data-ttu-id="520dc-149">リストのすべての要素に対して実行する必要がある操作があるとします。</span><span class="sxs-lookup"><span data-stu-id="520dc-149">Consider an operation that must be performed on every element of a list.</span></span> <span data-ttu-id="520dc-150">この操作を再帰的に実行するには、リストの先頭に対して処理を行った後にリストの後部 (元のリストの最初の要素を除いた要素で構成される、元のリストより小さいリスト) を次の再帰レベルに戻します。</span><span class="sxs-lookup"><span data-stu-id="520dc-150">You can do this recursively by operating on the head of the list and then passing the tail of the list, which is a smaller list that consists of the original list without the first element, back again to the next level of recursion.</span></span>

<span data-ttu-id="520dc-151">このような再帰関数を記述するには、パターン マッチで cons 演算子 (`::`) を使用します。これによって、リストの先頭を末尾から分離できます。</span><span class="sxs-lookup"><span data-stu-id="520dc-151">To write such a recursive function, you use the cons operator (`::`) in pattern matching, which enables you to separate the head of a list from the tail.</span></span>

<span data-ttu-id="520dc-152">パターン マッチを使用して、リストに対する操作を実行する再帰関数を実装する方法を次のコード例に示します。</span><span class="sxs-lookup"><span data-stu-id="520dc-152">The following code example shows how to use pattern matching to implement a recursive function that performs operations on a list.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet13071.fs)]

<span data-ttu-id="520dc-153">このコードは小さいリストでは問題なく動作しますが、リストが大きくなると、スタックがオーバーフローする可能性があります。</span><span class="sxs-lookup"><span data-stu-id="520dc-153">The previous code works well for small lists, but for larger lists, it could overflow the stack.</span></span> <span data-ttu-id="520dc-154">次に示すコードは、再帰関数の処理では標準的な技法であるアキュムレータ引数を使用して、このコードを改善したものです。</span><span class="sxs-lookup"><span data-stu-id="520dc-154">The following code improves on this code by using an accumulator argument, a standard technique for working with recursive functions.</span></span> <span data-ttu-id="520dc-155">アキュムレータ引数を使用すると、関数の後部が再帰的になり、スタック領域を節約できます。</span><span class="sxs-lookup"><span data-stu-id="520dc-155">The use of the accumulator argument makes the function tail recursive, which saves stack space.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet13072.fs)]

<span data-ttu-id="520dc-156">関数 `RemoveAllMultiples` は、2 つのリストを受け取る再帰関数です。</span><span class="sxs-lookup"><span data-stu-id="520dc-156">The function `RemoveAllMultiples` is a recursive function that takes two lists.</span></span> <span data-ttu-id="520dc-157">1 番目のリストは、倍数を削除する数値が格納されたリストで、2 番目のリストは、数値を削除する元のリストです。</span><span class="sxs-lookup"><span data-stu-id="520dc-157">The first list contains the numbers whose multiples will be removed, and the second list is the list from which to remove the numbers.</span></span> <span data-ttu-id="520dc-158">次の例のコードでは、この再帰関数を使用してリストから素数以外をすべて削除します。その結果、素数のリストが残ります。</span><span class="sxs-lookup"><span data-stu-id="520dc-158">The code in the following example uses this recursive function to eliminate all the non-prime numbers from a list, leaving a list of prime numbers as the result.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1308.fs)]

<span data-ttu-id="520dc-159">出力は次のようになります。</span><span class="sxs-lookup"><span data-stu-id="520dc-159">The output is as follows:</span></span>

```console
Primes Up To 100:
[2; 3; 5; 7; 11; 13; 17; 19; 23; 29; 31; 37; 41; 43; 47; 53; 59; 61; 67; 71; 73; 79; 83; 89; 97]
```

## <a name="module-functions"></a><span data-ttu-id="520dc-160">モジュール関数</span><span class="sxs-lookup"><span data-stu-id="520dc-160">Module Functions</span></span>

<span data-ttu-id="520dc-161">[List モジュール](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html)には、リストの要素にアクセスする関数が用意されています。</span><span class="sxs-lookup"><span data-stu-id="520dc-161">The [List module](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html) provides functions that access the elements of a list.</span></span> <span data-ttu-id="520dc-162">先頭の要素には、最も迅速かつ簡単にアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="520dc-162">The head element is the fastest and easiest to access.</span></span> <span data-ttu-id="520dc-163">プロパティ [head](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-list-1.html#Head) またはモジュール関数リストを使用します [。 head](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#head).</span><span class="sxs-lookup"><span data-stu-id="520dc-163">Use the property [Head](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-list-1.html#Head) or the module function [List.head](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#head).</span></span> <span data-ttu-id="520dc-164">[Tail プロパティまた](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-list-1.html#Tail)は[tail 関数を](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#tail)使用して、リストの末尾にアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="520dc-164">You can access the tail of a list by using the [Tail](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-list-1.html#Tail) property or the [List.tail](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#tail) function.</span></span> <span data-ttu-id="520dc-165">インデックスによって要素を検索するには、 [List. n](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#nth) 関数を使用します。</span><span class="sxs-lookup"><span data-stu-id="520dc-165">To find an element by index, use the [List.nth](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#nth) function.</span></span> <span data-ttu-id="520dc-166">`List.nth` はリストを走査します。</span><span class="sxs-lookup"><span data-stu-id="520dc-166">`List.nth` traverses the list.</span></span> <span data-ttu-id="520dc-167">そのため、O (*n*) です。</span><span class="sxs-lookup"><span data-stu-id="520dc-167">Therefore, it is O(*n*).</span></span> <span data-ttu-id="520dc-168">コードで `List.nth` を頻繁に使用する場合は、リストの代わりに配列を使用すると、効果的である可能性があります。</span><span class="sxs-lookup"><span data-stu-id="520dc-168">If your code uses `List.nth` frequently, you might want to consider using an array instead of a list.</span></span> <span data-ttu-id="520dc-169">配列での要素のアクセスは O(1) です。</span><span class="sxs-lookup"><span data-stu-id="520dc-169">Element access in arrays is O(1).</span></span>

### <a name="boolean-operations-on-lists"></a><span data-ttu-id="520dc-170">リストに対するブール演算</span><span class="sxs-lookup"><span data-stu-id="520dc-170">Boolean Operations on Lists</span></span>

<span data-ttu-id="520dc-171">[IsEmpty](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#isEmpty)関数は、リストに要素があるかどうかを判断します。</span><span class="sxs-lookup"><span data-stu-id="520dc-171">The [List.isEmpty](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#isEmpty) function determines whether a list has any elements.</span></span>

<span data-ttu-id="520dc-172">[List. exists](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#exists)関数は、ブール値のテストをリストの要素に適用し、 `true` いずれかの要素がテストに適合する場合はを返します。</span><span class="sxs-lookup"><span data-stu-id="520dc-172">The [List.exists](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#exists) function applies a Boolean test to elements of a list and returns `true` if any element satisfies the test.</span></span> <span data-ttu-id="520dc-173">[List.exists2](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#exists2) は似ていますが、2つのリストの要素の連続するペアで動作します。</span><span class="sxs-lookup"><span data-stu-id="520dc-173">[List.exists2](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#exists2) is similar but operates on successive pairs of elements in two lists.</span></span>

<span data-ttu-id="520dc-174">`List.exists` を使用したコードの例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="520dc-174">The following code demonstrates the use of `List.exists`.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lists/snippet1.fs)]

<span data-ttu-id="520dc-175">出力は次のようになります。</span><span class="sxs-lookup"><span data-stu-id="520dc-175">The output is as follows:</span></span>

```console
For list [0; 1; 2; 3], contains zero is true
```

<span data-ttu-id="520dc-176">次の例は、`List.exists2` の使い方を示しています。</span><span class="sxs-lookup"><span data-stu-id="520dc-176">The following example demonstrates the use of `List.exists2`.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lists/snippet2.fs)]

<span data-ttu-id="520dc-177">出力は次のようになります。</span><span class="sxs-lookup"><span data-stu-id="520dc-177">The output is as follows:</span></span>

```console
Lists [1; 2; 3; 4; 5] and [5; 4; 3; 2; 1] have at least one equal element at the same position.
```

<span data-ttu-id="520dc-178">リストのすべての要素が条件を満たしているかどうかをテストする場合は、forall を使用できます[。](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#forall)</span><span class="sxs-lookup"><span data-stu-id="520dc-178">You can use [List.forall](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#forall) if you want to test whether all the elements of a list meet a condition.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lists/snippet3.fs)]

<span data-ttu-id="520dc-179">出力は次のようになります。</span><span class="sxs-lookup"><span data-stu-id="520dc-179">The output is as follows:</span></span>

```console
true
false
```

<span data-ttu-id="520dc-180">同様に、 [array.forall2](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#forall2) は、2つのリスト内の対応する位置にあるすべての要素が、要素の各ペアに関係するブール式を満たすかどうかを判断します。</span><span class="sxs-lookup"><span data-stu-id="520dc-180">Similarly, [List.forall2](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#forall2) determines whether all elements in the corresponding positions in two lists satisfy a Boolean expression that involves each pair of elements.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lists/snippet4.fs)]

<span data-ttu-id="520dc-181">出力は次のようになります。</span><span class="sxs-lookup"><span data-stu-id="520dc-181">The output is as follows:</span></span>

```console
true
false
```

### <a name="sort-operations-on-lists"></a><span data-ttu-id="520dc-182">リストに対する並べ替え操作</span><span class="sxs-lookup"><span data-stu-id="520dc-182">Sort Operations on Lists</span></span>

<span data-ttu-id="520dc-183">[リスト並べ替え](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#sort)、 [sortBy](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#sortBy)、および関数を使用し[た sortwith](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#sortWith)リスト。</span><span class="sxs-lookup"><span data-stu-id="520dc-183">The [List.sort](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#sort), [List.sortBy](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#sortBy), and [List.sortWith](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#sortWith) functions sort lists.</span></span> <span data-ttu-id="520dc-184">並べ替え関数は、これら 3 つの関数のどれを使用するかを判断します。</span><span class="sxs-lookup"><span data-stu-id="520dc-184">The sorting function determines which of these three functions to use.</span></span> <span data-ttu-id="520dc-185">`List.sort` は、既定の一般的な比較を使用します。</span><span class="sxs-lookup"><span data-stu-id="520dc-185">`List.sort` uses default generic comparison.</span></span> <span data-ttu-id="520dc-186">一般的な比較は、汎用の比較関数に基づくグローバル演算子を使用して、値を比較します。</span><span class="sxs-lookup"><span data-stu-id="520dc-186">Generic comparison uses global operators based on the generic compare function to compare values.</span></span> <span data-ttu-id="520dc-187">この比較は、単純な数値型、タプル、レコード、判別共用体、リスト、配列、および `System.IComparable` を実装する任意の型など、広範な要素型で効率的に動作します。</span><span class="sxs-lookup"><span data-stu-id="520dc-187">It works efficiently with a wide variety of element types, such as simple numeric types, tuples, records, discriminated unions, lists, arrays, and any type that implements `System.IComparable`.</span></span> <span data-ttu-id="520dc-188">`System.IComparable` を実装する型の場合は、汎用的な比較で `System.IComparable.CompareTo()` 関数が使用されます。</span><span class="sxs-lookup"><span data-stu-id="520dc-188">For types that implement `System.IComparable`, generic comparison uses the `System.IComparable.CompareTo()` function.</span></span> <span data-ttu-id="520dc-189">また、汎用的な比較は文字列にも使用できますが、カルチャに依存しない並べ替え順序が使用されます。</span><span class="sxs-lookup"><span data-stu-id="520dc-189">Generic comparison also works with strings, but uses a culture-independent sorting order.</span></span> <span data-ttu-id="520dc-190">関数型のようなサポートされない型には、汎用的な比較を使用できません。</span><span class="sxs-lookup"><span data-stu-id="520dc-190">Generic comparison should not be used on unsupported types, such as function types.</span></span> <span data-ttu-id="520dc-191">また、既定の汎用的な比較は、小さい構造の型の場合に最高のパフォーマンスを示します。比較と並べ替えが頻繁に必要な大きい構造の型の場合は、`System.IComparable` を実装し、`System.IComparable.CompareTo()` メソッドを効率的に実装することを考慮してください。</span><span class="sxs-lookup"><span data-stu-id="520dc-191">Also, the performance of the default generic comparison is best for small structured types; for larger structured types that need to be compared and sorted frequently, consider implementing `System.IComparable` and providing an efficient implementation of the `System.IComparable.CompareTo()` method.</span></span>

<span data-ttu-id="520dc-192">`List.sortBy` 関数は、並べ替え基準として使用される値を返す関数を受け取り、`List.sortWith` 関数は、比較関数を引数として受け取ります。</span><span class="sxs-lookup"><span data-stu-id="520dc-192">`List.sortBy` takes a function that returns a value that is used as the sort criterion, and `List.sortWith` takes a comparison function as an argument.</span></span> <span data-ttu-id="520dc-193">これら 2 つの関数は、比較をサポートしない型を使用するとき、またはカルチャを認識する文字列の場合のように複雑な比較セマンティクスを必要とする比較の場合に役立ちます。</span><span class="sxs-lookup"><span data-stu-id="520dc-193">These latter two functions are useful when you are working with types that do not support comparison, or when the comparison requires more complex comparison semantics, as in the case of culture-aware strings.</span></span>

<span data-ttu-id="520dc-194">次の例は、`List.sort` の使い方を示しています。</span><span class="sxs-lookup"><span data-stu-id="520dc-194">The following example demonstrates the use of `List.sort`.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lists/snippet5.fs)]

<span data-ttu-id="520dc-195">出力は次のようになります。</span><span class="sxs-lookup"><span data-stu-id="520dc-195">The output is as follows:</span></span>

```console
[-2; 1; 4; 5; 8]
```

<span data-ttu-id="520dc-196">次の例は、`List.sortBy` の使い方を示しています。</span><span class="sxs-lookup"><span data-stu-id="520dc-196">The following example demonstrates the use of `List.sortBy`.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lists/snippet6.fs)]

<span data-ttu-id="520dc-197">出力は次のようになります。</span><span class="sxs-lookup"><span data-stu-id="520dc-197">The output is as follows:</span></span>

```console
[1; -2; 4; 5; 8]
```

<span data-ttu-id="520dc-198">次の例は、`List.sortWith` の使い方を示しています。</span><span class="sxs-lookup"><span data-stu-id="520dc-198">The next example demonstrates the use of `List.sortWith`.</span></span> <span data-ttu-id="520dc-199">この例では、カスタムの比較関数 `compareWidgets` を使用して、まず、カスタム型の 1 つのフィールドを比較し、最初のフィールドの値が同じである場合は、さらに別のフィールドを比較しています。</span><span class="sxs-lookup"><span data-stu-id="520dc-199">In this example, the custom comparison function `compareWidgets` is used to first compare one field of a custom type, and then another when the values of the first field are equal.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lists/snippet7.fs)]

<span data-ttu-id="520dc-200">出力は次のようになります。</span><span class="sxs-lookup"><span data-stu-id="520dc-200">The output is as follows:</span></span>

```console
[{ID = 92;
Rev = 1;}; {ID = 92;
Rev = 1;}; {ID = 100;
Rev = 2;}; {ID = 100;
Rev = 5;}; {ID = 110;
Rev = 1;}]
```

### <a name="search-operations-on-lists"></a><span data-ttu-id="520dc-201">リストに対する検索操作</span><span class="sxs-lookup"><span data-stu-id="520dc-201">Search Operations on Lists</span></span>

<span data-ttu-id="520dc-202">リストに対するさまざまな検索操作がサポートされています。</span><span class="sxs-lookup"><span data-stu-id="520dc-202">Numerous search operations are supported for lists.</span></span> <span data-ttu-id="520dc-203">最も単純な [リストです。 find](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#find)を使用すると、特定の条件に一致する最初の要素を検索できます。</span><span class="sxs-lookup"><span data-stu-id="520dc-203">The simplest, [List.find](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#find), enables you to find the first element that matches a given condition.</span></span>

<span data-ttu-id="520dc-204">次のコード例では、`List.find` を使用して、5 で割り切れる最初の数をリストから検索する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="520dc-204">The following code example demonstrates the use of `List.find` to find the first number that is divisible by 5 in a list.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lists/snippet8.fs)]

<span data-ttu-id="520dc-205">The result is 5.</span><span class="sxs-lookup"><span data-stu-id="520dc-205">The result is 5.</span></span>

<span data-ttu-id="520dc-206">最初に要素を変換する必要がある場合は、 [List. pick](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#pick)を呼び出します。この関数は、オプションを返す関数を受け取り、である最初のオプション値を検索し `Some(x)` ます。</span><span class="sxs-lookup"><span data-stu-id="520dc-206">If the elements must be transformed first, call [List.pick](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#pick), which takes a function that returns an option, and looks for the first option value that is `Some(x)`.</span></span> <span data-ttu-id="520dc-207">`List.pick` は要素を返す代わりに、結果 `x` を返します。</span><span class="sxs-lookup"><span data-stu-id="520dc-207">Instead of returning the element, `List.pick` returns the result `x`.</span></span> <span data-ttu-id="520dc-208">一致する要素が見つからない場合、`List.pick` は `System.Collections.Generic.KeyNotFoundException` をスローします。</span><span class="sxs-lookup"><span data-stu-id="520dc-208">If no matching element is found, `List.pick` throws `System.Collections.Generic.KeyNotFoundException`.</span></span> <span data-ttu-id="520dc-209">`List.pick` の使用方法を次のコードに示します。</span><span class="sxs-lookup"><span data-stu-id="520dc-209">The following code shows the use of `List.pick`.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lists/snippet9.fs)]

<span data-ttu-id="520dc-210">出力は次のようになります。</span><span class="sxs-lookup"><span data-stu-id="520dc-210">The output is as follows:</span></span>

```console
"b"
```

<span data-ttu-id="520dc-211">別の検索操作のグループである [tryFind](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#tryFind) と関連する関数は、オプション値を返します。</span><span class="sxs-lookup"><span data-stu-id="520dc-211">Another group of search operations, [List.tryFind](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#tryFind) and related functions, return an option value.</span></span> <span data-ttu-id="520dc-212">`List.tryFind` 関数は、条件を満たす要素がリストにある場合は、その最初の要素を返します。条件を満たす要素がない場合は、オプション値 `None` を返します。</span><span class="sxs-lookup"><span data-stu-id="520dc-212">The `List.tryFind` function returns the first element of a list that satisfies a condition if such an element exists, but the option value `None` if not.</span></span> <span data-ttu-id="520dc-213">バリエーション [リスト. tryFindIndex](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#tryFindIndex) は、要素自体ではなく、要素が見つかった場合はそのインデックスを返します。</span><span class="sxs-lookup"><span data-stu-id="520dc-213">The variation [List.tryFindIndex](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#tryFindIndex) returns the index of the element, if one is found, rather than the element itself.</span></span> <span data-ttu-id="520dc-214">これらの関数を次のコードに示します。</span><span class="sxs-lookup"><span data-stu-id="520dc-214">These functions are illustrated in the following code.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lists/snippet10.fs)]

<span data-ttu-id="520dc-215">出力は次のようになります。</span><span class="sxs-lookup"><span data-stu-id="520dc-215">The output is as follows:</span></span>

```console
The first even value is 22.
The first even value is at position 8.
```

### <a name="arithmetic-operations-on-lists"></a><span data-ttu-id="520dc-216">リストに対する算術演算</span><span class="sxs-lookup"><span data-stu-id="520dc-216">Arithmetic Operations on Lists</span></span>

<span data-ttu-id="520dc-217">Sum や average などの一般的な算術演算は、 [List モジュール](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html)に組み込まれています。</span><span class="sxs-lookup"><span data-stu-id="520dc-217">Common arithmetic operations such as sum and average are built into the [List module](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html).</span></span> <span data-ttu-id="520dc-218">[List. sum](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#sum)を使用するには、リスト要素の型が演算子をサポートし、値が0である必要があり `+` ます。</span><span class="sxs-lookup"><span data-stu-id="520dc-218">To work with [List.sum](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#sum), the list element type must support the `+` operator and have a zero value.</span></span> <span data-ttu-id="520dc-219">すべての組み込み数値型はこの条件を満たしています。</span><span class="sxs-lookup"><span data-stu-id="520dc-219">All built-in arithmetic types satisfy these conditions.</span></span> <span data-ttu-id="520dc-220">[List. average](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#average)を使用するには、要素型が剰余のない除算をサポートしている必要があります。これには整数型は含まれませんが、浮動小数点型は許可されます。</span><span class="sxs-lookup"><span data-stu-id="520dc-220">To work with [List.average](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#average), the element type must support division without a remainder, which excludes integral types but allows for floating point types.</span></span> <span data-ttu-id="520dc-221">AverageBy[関数および](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#sumBy)[リスト](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#averageBy)関数は、パラメーターとして関数を受け取ります。この関数の結果は、合計または平均の値を計算するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="520dc-221">The [List.sumBy](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#sumBy) and [List.averageBy](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#averageBy) functions take a function as a parameter, and this function's results are used to calculate the values for the sum or average.</span></span>

<span data-ttu-id="520dc-222">次のコードは、`List.sum`、 `List.sumBy`、および `List.average` の使用方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="520dc-222">The following code demonstrates the use of `List.sum`, `List.sumBy`, and `List.average`.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lists/snippet11.fs)]

<span data-ttu-id="520dc-223">出力は `1.000000` になります。</span><span class="sxs-lookup"><span data-stu-id="520dc-223">The output is `1.000000`.</span></span>

<span data-ttu-id="520dc-224">`List.averageBy` の使用方法を次のコードに示します。</span><span class="sxs-lookup"><span data-stu-id="520dc-224">The following code shows the use of `List.averageBy`.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lists/snippet12.fs)]

<span data-ttu-id="520dc-225">出力は `5.5` になります。</span><span class="sxs-lookup"><span data-stu-id="520dc-225">The output is `5.5`.</span></span>

### <a name="lists-and-tuples"></a><span data-ttu-id="520dc-226">リストとタプル</span><span class="sxs-lookup"><span data-stu-id="520dc-226">Lists and Tuples</span></span>

<span data-ttu-id="520dc-227">タプルを含むリストは、zip 関数および unzip 関数で操作できます。</span><span class="sxs-lookup"><span data-stu-id="520dc-227">Lists that contain tuples can be manipulated by zip and unzip functions.</span></span> <span data-ttu-id="520dc-228">これらの関数は、単一値の 2 つのリストを結合してタプルのリストを 1 つ生成したり、タプルの 1 つのリストを分割して単一の値のリストを 2 つ生成したりします。</span><span class="sxs-lookup"><span data-stu-id="520dc-228">These functions combine two lists of single values into one list of tuples or separate one list of tuples into two lists of single values.</span></span> <span data-ttu-id="520dc-229">最も単純な [List.zip](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#zip) 関数は、1つの要素の2つのリストを受け取り、組のペアのリストを1つ生成します。</span><span class="sxs-lookup"><span data-stu-id="520dc-229">The simplest [List.zip](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#zip) function takes two lists of single elements and produces a single list of tuple pairs.</span></span> <span data-ttu-id="520dc-230">別のバージョン ( [List.zip3](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#zip3)) は、1つの要素の3つのリストを受け取り、3つの要素を持つ組のリストを1つ生成します。</span><span class="sxs-lookup"><span data-stu-id="520dc-230">Another version, [List.zip3](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#zip3), takes three lists of single elements and produces a single list of tuples that have three elements.</span></span> <span data-ttu-id="520dc-231">次のコード例は、`List.zip` の使用方法を示します。</span><span class="sxs-lookup"><span data-stu-id="520dc-231">The following code example demonstrates the use of `List.zip`.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lists/snippet13.fs)]

<span data-ttu-id="520dc-232">出力は次のようになります。</span><span class="sxs-lookup"><span data-stu-id="520dc-232">The output is as follows:</span></span>

```console
[(1, -1); (2, -2); (3; -3)]
```

<span data-ttu-id="520dc-233">次のコード例は、`List.zip3` の使用方法を示します。</span><span class="sxs-lookup"><span data-stu-id="520dc-233">The following code example demonstrates the use of `List.zip3`.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lists/snippet14.fs)]

<span data-ttu-id="520dc-234">出力は次のようになります。</span><span class="sxs-lookup"><span data-stu-id="520dc-234">The output is as follows:</span></span>

```console
[(1, -1, 0); (2, -2, 0); (3, -3, 0)]
```

<span data-ttu-id="520dc-235">対応する unzip のバージョン、array.unzip3、および[リスト](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#unzip3)は、組内の組と戻り値[のリストを](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#unzip)取得します。最初のリストには各組の最初の要素が含まれ、2番目のリストには各組の2番目の要素が含まれます。</span><span class="sxs-lookup"><span data-stu-id="520dc-235">The corresponding unzip versions, [List.unzip](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#unzip) and [List.unzip3](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#unzip3), take lists of tuples and return lists in a tuple, where the first list contains all the elements that were first in each tuple, and the second list contains the second element of each tuple, and so on.</span></span>

<span data-ttu-id="520dc-236">次のコード例は、 [unzip](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#unzip)の使用方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="520dc-236">The following code example demonstrates the use of [List.unzip](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#unzip).</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lists/snippet15.fs)]

<span data-ttu-id="520dc-237">出力は次のようになります。</span><span class="sxs-lookup"><span data-stu-id="520dc-237">The output is as follows:</span></span>

```console
([1; 3], [2; 4])
[1; 3] [2; 4]
```

<span data-ttu-id="520dc-238">次のコード例は、 [array.unzip3](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#unzip3)の使用方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="520dc-238">The following code example demonstrates the use of [List.unzip3](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#unzip3).</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lists/snippet16.fs)]

<span data-ttu-id="520dc-239">出力は次のようになります。</span><span class="sxs-lookup"><span data-stu-id="520dc-239">The output is as follows:</span></span>

```console
([1; 4], [2; 5], [3; 6])
```

### <a name="operating-on-list-elements"></a><span data-ttu-id="520dc-240">リスト要素に対する操作</span><span class="sxs-lookup"><span data-stu-id="520dc-240">Operating on List Elements</span></span>

<span data-ttu-id="520dc-241">F# は、リストの要素に対するさまざまな操作をサポートしています。</span><span class="sxs-lookup"><span data-stu-id="520dc-241">F# supports a variety of operations on list elements.</span></span> <span data-ttu-id="520dc-242">最も単純なのは [iter](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#iter)です。これを使用すると、リストのすべての要素に対して関数を呼び出すことができます。</span><span class="sxs-lookup"><span data-stu-id="520dc-242">The simplest is [List.iter](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#iter), which enables you to call a function on every element of a list.</span></span> <span data-ttu-id="520dc-243">バリエーションには [array.iter2](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#iter2)が含まれてい [ます。これ](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#iteri)により、 `List.iter` 各要素のインデックスは、各要素に対して呼び出される関数に引数として渡され、 [array.iteri2](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#iteri2)はとの機能を組み合わせたものであることを除いて、2つのリストの要素に対して操作を実行でき `List.iter2` `List.iteri` ます。</span><span class="sxs-lookup"><span data-stu-id="520dc-243">Variations include [List.iter2](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#iter2), which enables you to perform an operation on elements of two lists, [List.iteri](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#iteri), which is like `List.iter` except that the index of each element is passed as an argument to the function that is called for each element, and [List.iteri2](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#iteri2), which is a combination of the functionality of `List.iter2` and `List.iteri`.</span></span> <span data-ttu-id="520dc-244">次のコード例にこれらの関数を示します。</span><span class="sxs-lookup"><span data-stu-id="520dc-244">The following code example illustrates these functions.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lists/snippet17.fs)]

<span data-ttu-id="520dc-245">出力は次のようになります。</span><span class="sxs-lookup"><span data-stu-id="520dc-245">The output is as follows:</span></span>

```console
List.iter: element is 1
List.iter: element is 2
List.iter: element is 3
List.iteri: element 0 is 1
List.iteri: element 1 is 2
List.iteri: element 2 is 3
List.iter2: elements are 1 4
List.iter2: elements are 2 5
List.iter2: elements are 3 6
List.iteri2: element 0 of list1 is 1; element 0 of list2 is 4
List.iteri2: element 1 of list1 is 2; element 1 of list2 is 5
List.iteri2: element 2 of list1 is 3; element 2 of list2 is 6
```

<span data-ttu-id="520dc-246">リスト要素を変換する、よく使用されるもう1つの関数は、list [. map です。](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#map)これにより、リストの各要素に関数を適用し、すべての結果を新しいリストに入れることができます。</span><span class="sxs-lookup"><span data-stu-id="520dc-246">Another frequently used function that transforms list elements is [List.map](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#map), which enables you to apply a function to each element of a list and put all the results into a new list.</span></span> <span data-ttu-id="520dc-247">[List.map2](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#map2) と [list.map3](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#map3) は、複数のリストを受け取るバリエーションです。</span><span class="sxs-lookup"><span data-stu-id="520dc-247">[List.map2](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#map2) and [List.map3](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#map3) are variations that take multiple lists.</span></span> <span data-ttu-id="520dc-248">また、 [array.mapi2 とリスト](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#mapi2)を使用することもできます。この場合、要素に[加えて、](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#mapi)関数は各要素のインデックスを渡す必要があります。</span><span class="sxs-lookup"><span data-stu-id="520dc-248">You can also use [List.mapi](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#mapi) and [List.mapi2](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#mapi2), if, in addition to the element, the function needs to be passed the index of each element.</span></span> <span data-ttu-id="520dc-249">`List.mapi2` と `List.mapi` の唯一の違いは、`List.mapi2` では 2 つのリストが使用される点です。</span><span class="sxs-lookup"><span data-stu-id="520dc-249">The only difference between `List.mapi2` and `List.mapi` is that `List.mapi2` works with two lists.</span></span> <span data-ttu-id="520dc-250">次の例は、 [List. map](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#map)を示しています。</span><span class="sxs-lookup"><span data-stu-id="520dc-250">The following example illustrates [List.map](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#map).</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lists/snippet18.fs)]

<span data-ttu-id="520dc-251">出力は次のようになります。</span><span class="sxs-lookup"><span data-stu-id="520dc-251">The output is as follows:</span></span>

```console
[2; 3; 4]
```

<span data-ttu-id="520dc-252">次の例は、`List.map2` の使用方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="520dc-252">The following example shows the use of `List.map2`.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lists/snippet19.fs)]

<span data-ttu-id="520dc-253">出力は次のようになります。</span><span class="sxs-lookup"><span data-stu-id="520dc-253">The output is as follows:</span></span>

```console
[5; 7; 9]
```

<span data-ttu-id="520dc-254">次の例は、`List.map3` の使用方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="520dc-254">The following example shows the use of `List.map3`.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lists/snippet20.fs)]

<span data-ttu-id="520dc-255">出力は次のようになります。</span><span class="sxs-lookup"><span data-stu-id="520dc-255">The output is as follows:</span></span>

```console
[7; 10; 13]
```

<span data-ttu-id="520dc-256">次の例は、`List.mapi` の使用方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="520dc-256">The following example shows the use of `List.mapi`.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lists/snippet21.fs)]

<span data-ttu-id="520dc-257">出力は次のようになります。</span><span class="sxs-lookup"><span data-stu-id="520dc-257">The output is as follows:</span></span>

```console
[1; 3; 5]
```

<span data-ttu-id="520dc-258">次の例は、`List.mapi2` の使用方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="520dc-258">The following example shows the use of `List.mapi2`.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lists/snippet22.fs)]

<span data-ttu-id="520dc-259">出力は次のようになります。</span><span class="sxs-lookup"><span data-stu-id="520dc-259">The output is as follows:</span></span>

```console
[0; 7; 18]
```

<span data-ttu-id="520dc-260">[List. collect](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#collect) はと似ていますが `List.map` 、各要素によってリストが生成され、これらのすべてのリストが最終的な一覧に連結される点が異なります。</span><span class="sxs-lookup"><span data-stu-id="520dc-260">[List.collect](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#collect) is like `List.map`, except that each element produces a list and all these lists are concatenated into a final list.</span></span> <span data-ttu-id="520dc-261">次のコードでは、リストの各要素が 3 つの値を生成します。</span><span class="sxs-lookup"><span data-stu-id="520dc-261">In the following code, each element of the list generates three numbers.</span></span> <span data-ttu-id="520dc-262">これらすべてが 1 つのリストに集約されます。</span><span class="sxs-lookup"><span data-stu-id="520dc-262">These are all collected into one list.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lists/snippet23.fs)]

<span data-ttu-id="520dc-263">出力は次のようになります。</span><span class="sxs-lookup"><span data-stu-id="520dc-263">The output is as follows:</span></span>

```console
[1; 2; 3; 2; 4; 6; 3; 6; 9]
```

<span data-ttu-id="520dc-264">また、 [list. filter](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#filter)を使用することもできます。これはブール条件を受け取り、指定された条件を満たす要素だけで構成される新しいリストを生成します。</span><span class="sxs-lookup"><span data-stu-id="520dc-264">You can also use [List.filter](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#filter), which takes a Boolean condition and produces a new list that consists only of elements that satisfy the given condition.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lists/snippet24.fs)]

<span data-ttu-id="520dc-265">結果のリストは `[2; 4; 6]` です。</span><span class="sxs-lookup"><span data-stu-id="520dc-265">The resulting list is `[2; 4; 6]`.</span></span>

<span data-ttu-id="520dc-266">[マップ] と [フィルター] の組み合わせで、[ [選択]](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#choose) を使用すると、複数の要素を同時に変換および選択できます。</span><span class="sxs-lookup"><span data-stu-id="520dc-266">A combination of map and filter, [List.choose](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#choose) enables you to transform and select elements at the same time.</span></span> <span data-ttu-id="520dc-267">`List.choose` は、オプションを返す関数をリストの各要素に適用し、関数がオプション値 `Some` を返す要素の結果から成る新しいリストを返します。</span><span class="sxs-lookup"><span data-stu-id="520dc-267">`List.choose` applies a function that returns an option to each element of a list, and returns a new list of the results for elements when the function returns the option value `Some`.</span></span>

<span data-ttu-id="520dc-268">次のコードでは、`List.choose` を使用して、最初の文字が大文字の単語を単語のリストから選択しています。</span><span class="sxs-lookup"><span data-stu-id="520dc-268">The following code demonstrates the use of `List.choose` to select capitalized words out of a list of words.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lists/snippet25.fs)]

<span data-ttu-id="520dc-269">出力は次のようになります。</span><span class="sxs-lookup"><span data-stu-id="520dc-269">The output is as follows:</span></span>

```console
["Rome's"; "Bob's"]
```

### <a name="operating-on-multiple-lists"></a><span data-ttu-id="520dc-270">複数のリストに対する操作</span><span class="sxs-lookup"><span data-stu-id="520dc-270">Operating on Multiple Lists</span></span>

<span data-ttu-id="520dc-271">複数のリストを結合できます。</span><span class="sxs-lookup"><span data-stu-id="520dc-271">Lists can be joined together.</span></span> <span data-ttu-id="520dc-272">2つのリストを1つに結合するには、 [List. append](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#append)を使用します。</span><span class="sxs-lookup"><span data-stu-id="520dc-272">To join two lists into one, use [List.append](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#append).</span></span> <span data-ttu-id="520dc-273">3つ以上のリストを結合するには、 [concat](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#concat)を使用します。</span><span class="sxs-lookup"><span data-stu-id="520dc-273">To join more than two lists, use [List.concat](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#concat).</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lists/snippet26.fs)]

### <a name="fold-and-scan-operations"></a><span data-ttu-id="520dc-274">フォールド操作とスキャン操作</span><span class="sxs-lookup"><span data-stu-id="520dc-274">Fold and Scan Operations</span></span>

<span data-ttu-id="520dc-275">リストの操作の中には、リストのすべての要素間の依存関係を伴うものがあります。</span><span class="sxs-lookup"><span data-stu-id="520dc-275">Some list operations involve interdependencies between all of the list elements.</span></span> <span data-ttu-id="520dc-276">フォールド操作とスキャン操作は `List.iter` 、 `List.map` 各要素に対して関数を呼び出すのと似ていますが、これらの操作には、計算を通じて情報を伝達する *アキュムレータ* と呼ばれる追加のパラメーターが用意されています。</span><span class="sxs-lookup"><span data-stu-id="520dc-276">The fold and scan operations are like `List.iter` and `List.map` in that you invoke a function on each element, but these operations provide an additional parameter called the *accumulator* that carries information through the computation.</span></span>

<span data-ttu-id="520dc-277">リストに対して計算を実行するには、`List.fold` を使用します。</span><span class="sxs-lookup"><span data-stu-id="520dc-277">Use `List.fold` to perform a calculation on a list.</span></span>

<span data-ttu-id="520dc-278">次のコード例では、 [リスト](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#fold) を使用してさまざまな操作を実行する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="520dc-278">The following code example demonstrates the use of [List.fold](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#fold) to perform various operations.</span></span>

<span data-ttu-id="520dc-279"> リストが走査されます。アキュムレータ `acc`は、計算の進行に伴って渡される値です。</span><span class="sxs-lookup"><span data-stu-id="520dc-279">The list is traversed; the accumulator `acc` is a value that is passed along as the calculation proceeds.</span></span> <span data-ttu-id="520dc-280">1 番目の引数はアキュムレータとリスト要素を受け取り、そのリスト要素に対する計算の中間結果を返します。</span><span class="sxs-lookup"><span data-stu-id="520dc-280">The first argument takes the accumulator and the list element, and returns the interim result of the calculation for that list element.</span></span> <span data-ttu-id="520dc-281">2 番目の引数はアキュムレータの初期値です。</span><span class="sxs-lookup"><span data-stu-id="520dc-281">The second argument is the initial value of the accumulator.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lists/snippet27.fs)]

<span data-ttu-id="520dc-282">関数名に数字が付いている関数は、複数のリストを操作するバージョンです。</span><span class="sxs-lookup"><span data-stu-id="520dc-282">The versions of these functions that have a digit in the function name operate on more than one list.</span></span> <span data-ttu-id="520dc-283">たとえば、 [list.fold2](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#fold2) は2つのリストに対して計算を実行します。</span><span class="sxs-lookup"><span data-stu-id="520dc-283">For example, [List.fold2](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#fold2) performs computations on two lists.</span></span>

<span data-ttu-id="520dc-284">次の例は、`List.fold2` の使い方を示しています。</span><span class="sxs-lookup"><span data-stu-id="520dc-284">The following example demonstrates the use of `List.fold2`.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lists/snippet28.fs)]

<span data-ttu-id="520dc-285">`List.fold` および [List. scan](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#scan) は、 `List.fold` 余分なパラメーターの最後の値を返すのと異なりますが、 `List.scan` 余分なパラメーターの中間値 (最終的な値と共に) のリストを返します。</span><span class="sxs-lookup"><span data-stu-id="520dc-285">`List.fold` and [List.scan](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#scan) differ in that `List.fold` returns the final value of the extra parameter, but `List.scan` returns the list of the intermediate values (along with the final value) of the extra parameter.</span></span>

<span data-ttu-id="520dc-286">これらの各関数には、 [array.foldback](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#foldBack)などの逆のバリエーションが含まれています。これは、リストが走査される順序と引数の順序によって異なります。</span><span class="sxs-lookup"><span data-stu-id="520dc-286">Each of these functions includes a reverse variation, for example, [List.foldBack](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#foldBack), which differs in the order in which the list is traversed and the order of the arguments.</span></span> <span data-ttu-id="520dc-287">また、 `List.fold` とに `List.foldBack` は、 [list.fold2](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#fold2) と [array.foldback2](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#foldBack2)というバリエーションがあります。これは、同じ長さの2つのリストを受け取ります。</span><span class="sxs-lookup"><span data-stu-id="520dc-287">Also, `List.fold` and `List.foldBack` have variations, [List.fold2](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#fold2) and [List.foldBack2](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#foldBack2), that take two lists of equal length.</span></span> <span data-ttu-id="520dc-288">各要素に対して実行される関数では、両方のリストの対応する要素を使用して操作を実行できます。</span><span class="sxs-lookup"><span data-stu-id="520dc-288">The function that executes on each element can use corresponding elements of both lists to perform some action.</span></span> <span data-ttu-id="520dc-289">2 つのリストの要素の型が同じである必要はありません。たとえば、次の例では、一方のリストには銀行口座の取引金額が格納され、もう一方のリストには取引の種類 (預け入れまたは引き出し) が格納されています。</span><span class="sxs-lookup"><span data-stu-id="520dc-289">The element types of the two lists can be different, as in the following example, in which one list contains transaction amounts for a bank account, and the other list contains the type of transaction: deposit or withdrawal.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lists/snippet29.fs)]

<span data-ttu-id="520dc-290">合計のような計算の場合は、結果が走査の順序に依存しないため、`List.fold` と `List.foldBack` のどちらを使用しても、同じ結果になります。</span><span class="sxs-lookup"><span data-stu-id="520dc-290">For a calculation like summation, `List.fold` and `List.foldBack` have the same effect because the result does not depend on the order of traversal.</span></span> <span data-ttu-id="520dc-291">次の例では、`List.foldBack` を使用してリストの要素を追加します。</span><span class="sxs-lookup"><span data-stu-id="520dc-291">In the following example, `List.foldBack` is used to add the elements in a list.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lists/snippet30.fs)]

<span data-ttu-id="520dc-292">次の例では、銀行口座の例に戻ります。</span><span class="sxs-lookup"><span data-stu-id="520dc-292">The following example returns to the bank account example.</span></span> <span data-ttu-id="520dc-293">今度は、利息を計算する新しい取引の種類が追加されています。</span><span class="sxs-lookup"><span data-stu-id="520dc-293">This time a new transaction type is added: an interest calculation.</span></span> <span data-ttu-id="520dc-294">取引の順序によって期末残高が異なります。</span><span class="sxs-lookup"><span data-stu-id="520dc-294">The ending balance now depends on the order of transactions.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lists/snippet34.fs)]

<span data-ttu-id="520dc-295">関数の [一覧の縮小](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#reduce) は、およびと似ていますが、 `List.fold` 別の `List.scan` アキュムレータを渡すのではなく、 `List.reduce` 1 つだけではなく要素型の2つの引数を受け取る関数を受け取ります。これらの引数の1つはアキュムレータとして機能します。つまり、計算の中間結果が格納されます。</span><span class="sxs-lookup"><span data-stu-id="520dc-295">The function [List.reduce](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#reduce) is somewhat like `List.fold` and `List.scan`, except that instead of passing around a separate accumulator, `List.reduce` takes a function that takes two arguments of the element type instead of just one, and one of those arguments acts as the accumulator, meaning that it stores the intermediate result of the computation.</span></span> <span data-ttu-id="520dc-296">`List.reduce` は、初めに最初の 2 つのリスト要素に対して演算を実行し、次にその演算の結果と次の要素を合わせて使用します。</span><span class="sxs-lookup"><span data-stu-id="520dc-296">`List.reduce` starts by operating on the first two list elements, and then uses the result of the operation along with the next element.</span></span> <span data-ttu-id="520dc-297">独自の型を持つ別のアキュムレータがないため、`List.reduce` を `List.fold` の代わりに使用できるのは、アキュムレータと要素が同じ型を持つ場合だけです。</span><span class="sxs-lookup"><span data-stu-id="520dc-297">Because there is not a separate accumulator that has its own type, `List.reduce` can be used in place of `List.fold` only when the accumulator and the element type have the same type.</span></span> <span data-ttu-id="520dc-298">`List.reduce` を使用したコードの例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="520dc-298">The following code demonstrates the use of `List.reduce`.</span></span> <span data-ttu-id="520dc-299">指定されたリストに要素がない場合、`List.reduce` は例外をスローします。</span><span class="sxs-lookup"><span data-stu-id="520dc-299">`List.reduce` throws an exception if the list provided has no elements.</span></span>

<span data-ttu-id="520dc-300">次のコードでは、ラムダ式の最初の呼び出しで引数 2 と 4 を受け取って 6 を返し、次の呼び出しで引数 6 と 10 を受け取るので、結果が 16 になります。</span><span class="sxs-lookup"><span data-stu-id="520dc-300">In the following code, the first call to the lambda expression is given the arguments 2 and 4, and returns 6, and the next call is given the arguments 6 and 10, so the result is 16.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lists/snippet33.fs)]

### <a name="converting-between-lists-and-other-collection-types"></a><span data-ttu-id="520dc-301">リストと他のコレクション型との変換</span><span class="sxs-lookup"><span data-stu-id="520dc-301">Converting Between Lists and Other Collection Types</span></span>

<span data-ttu-id="520dc-302">`List` モジュールには、シーケンスと配列との間で両方向の変換を行うための関数が用意されています。</span><span class="sxs-lookup"><span data-stu-id="520dc-302">The `List` module provides functions for converting to and from both sequences and arrays.</span></span> <span data-ttu-id="520dc-303">シーケンスとの間で変換を行うには、 [list. toseq](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#toSeq) または [List. ofseq](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#ofSeq)を使用します。</span><span class="sxs-lookup"><span data-stu-id="520dc-303">To convert to or from a sequence, use [List.toSeq](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#toSeq) or [List.ofSeq](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#ofSeq).</span></span> <span data-ttu-id="520dc-304">配列との間で変換を行うには、 [list. toArray](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#toArray) または [List. ofarray](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#ofArray)を使用します。</span><span class="sxs-lookup"><span data-stu-id="520dc-304">To convert to or from an array, use [List.toArray](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#toArray) or [List.ofArray](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#ofArray).</span></span>

### <a name="additional-operations"></a><span data-ttu-id="520dc-305">その他の操作</span><span class="sxs-lookup"><span data-stu-id="520dc-305">Additional Operations</span></span>

<span data-ttu-id="520dc-306">リストに対するその他の操作の詳細については、ライブラリリファレンストピック [リストモジュール](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="520dc-306">For information about additional operations on lists, see the library reference topic [List Module](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html).</span></span>

## <a name="see-also"></a><span data-ttu-id="520dc-307">関連項目</span><span class="sxs-lookup"><span data-stu-id="520dc-307">See also</span></span>

- [<span data-ttu-id="520dc-308">F# 言語リファレンス</span><span class="sxs-lookup"><span data-stu-id="520dc-308">F# Language Reference</span></span>](index.md)
- [<span data-ttu-id="520dc-309">F# の型</span><span class="sxs-lookup"><span data-stu-id="520dc-309">F# Types</span></span>](fsharp-types.md)
- [<span data-ttu-id="520dc-310">シーケンス</span><span class="sxs-lookup"><span data-stu-id="520dc-310">Sequences</span></span>](sequences.md)
- [<span data-ttu-id="520dc-311">配列</span><span class="sxs-lookup"><span data-stu-id="520dc-311">Arrays</span></span>](arrays.md)
- <span data-ttu-id="520dc-312">[[オプション]](options.md)</span><span class="sxs-lookup"><span data-stu-id="520dc-312">[Options](options.md)</span></span>
