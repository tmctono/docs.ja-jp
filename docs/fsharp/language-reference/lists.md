---
title: 表示内容
description: についてF#、同じ型の要素の順序付けされた不変の系列を一覧表示します。
ms.date: 05/16/2016
ms.openlocfilehash: cc4e292280cca0dca37f69cf5a46ec2822d08d5c
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61904125"
---
# <a name="lists"></a><span data-ttu-id="f6941-103">表示内容</span><span class="sxs-lookup"><span data-stu-id="f6941-103">Lists</span></span>

> [!NOTE]
> <span data-ttu-id="f6941-104">この記事の API リファレンスのリンクをクリックすると MSDN に移動します。</span><span class="sxs-lookup"><span data-stu-id="f6941-104">The API reference links in this article will take you to MSDN.</span></span>  <span data-ttu-id="f6941-105">docs.microsoft.com API リファレンスは完全ではありません。</span><span class="sxs-lookup"><span data-stu-id="f6941-105">The docs.microsoft.com API reference is not complete.</span></span>

<span data-ttu-id="f6941-106">F# のリストは、順序が指定されており変更できない一連の同じ型の要素です。</span><span class="sxs-lookup"><span data-stu-id="f6941-106">A list in F# is an ordered, immutable series of elements of the same type.</span></span> <span data-ttu-id="f6941-107">リストに対する基本操作を実行するには、内の関数を使用して、 [List モジュール](https://msdn.microsoft.com/library/a2264ba3-2d45-40dd-9040-4f7aa2ad9788)します。</span><span class="sxs-lookup"><span data-stu-id="f6941-107">To perform basic operations on lists, use the functions in the [List module](https://msdn.microsoft.com/library/a2264ba3-2d45-40dd-9040-4f7aa2ad9788).</span></span>

## <a name="creating-and-initializing-lists"></a><span data-ttu-id="f6941-108">リストの作成と初期化</span><span class="sxs-lookup"><span data-stu-id="f6941-108">Creating and Initializing Lists</span></span>

<span data-ttu-id="f6941-109">リストを定義するには、次のコード行に示すように、セミコロンで区切って明示的にリストした要素を角かっこで囲みます。</span><span class="sxs-lookup"><span data-stu-id="f6941-109">You can define a list by explicitly listing out the elements, separated by semicolons and enclosed in square brackets, as shown in the following line of code.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1301.fs)]

<span data-ttu-id="f6941-110">要素間に改行を挿入することもできます。その場合はセミコロンの区切り記号を省略できます。</span><span class="sxs-lookup"><span data-stu-id="f6941-110">You can also put line breaks between elements, in which case the semicolons are optional.</span></span> <span data-ttu-id="f6941-111">要素の初期化式が長い場合、各要素にコメントを含める場合は、改行の構文を使用するとコードが読みやすくなります。</span><span class="sxs-lookup"><span data-stu-id="f6941-111">The latter syntax can result in more readable code when the element initialization expressions are longer, or when you want to include a comment for each element.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet13011.fs)]

<span data-ttu-id="f6941-112">通常、リストの要素はすべて同じ型である必要があります。</span><span class="sxs-lookup"><span data-stu-id="f6941-112">Normally, all list elements must be the same type.</span></span> <span data-ttu-id="f6941-113">例外として、要素が基本型として指定されているリストには、派生型の要素を含めることができます。</span><span class="sxs-lookup"><span data-stu-id="f6941-113">An exception is that a list in which the elements are specified to be a base type can have elements that are derived types.</span></span> <span data-ttu-id="f6941-114">したがって次に示す例は、`Button` と `CheckBox` の両方が `Control` から派生しているため、受け入れられます。</span><span class="sxs-lookup"><span data-stu-id="f6941-114">Thus the following is acceptable, because both `Button` and `CheckBox` derive from `Control`.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet13012.fs)]

<span data-ttu-id="f6941-115">また、次のコードで示すように、整数を範囲演算子 (`..`) で区切って示した範囲を使用して、リストの要素を定義することもできます。</span><span class="sxs-lookup"><span data-stu-id="f6941-115">You can also define list elements by using a range indicated by integers separated by the range operator (`..`), as shown in the following code.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1302.fs)]

<span data-ttu-id="f6941-116">空のリストは、間に何も含まない 1 組の角かっこで示します。</span><span class="sxs-lookup"><span data-stu-id="f6941-116">An empty list is specified by a pair of square brackets with nothing in between them.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1304.fs)]

<span data-ttu-id="f6941-117">シーケンス式を使用してリストを作成することもできます。</span><span class="sxs-lookup"><span data-stu-id="f6941-117">You can also use a sequence expression to create a list.</span></span> <span data-ttu-id="f6941-118">参照してください[シーケンス式](sequences.md#sequence-expressions)詳細についてはします。</span><span class="sxs-lookup"><span data-stu-id="f6941-118">See [Sequence Expressions](sequences.md#sequence-expressions) for more information.</span></span> <span data-ttu-id="f6941-119">たとえば、次のコードでは 1 から 10 までの整数の 2 乗のリストが作成されます。</span><span class="sxs-lookup"><span data-stu-id="f6941-119">For example, the following code creates a list of squares of integers from 1 to 10.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1303.fs)]

## <a name="operators-for-working-with-lists"></a><span data-ttu-id="f6941-120">リストの操作に使用する演算子</span><span class="sxs-lookup"><span data-stu-id="f6941-120">Operators for Working with Lists</span></span>

<span data-ttu-id="f6941-121">リストに要素を付加するには、`::` (cons) 演算子を使用します。</span><span class="sxs-lookup"><span data-stu-id="f6941-121">You can attach elements to a list by using the `::` (cons) operator.</span></span> <span data-ttu-id="f6941-122">`list1` が `[2; 3; 4]` の場合、次のコードでは `list2` が `[100; 2; 3; 4]` として作成されます。</span><span class="sxs-lookup"><span data-stu-id="f6941-122">If `list1` is `[2; 3; 4]`, the following code creates `list2` as `[100; 2; 3; 4]`.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1305.fs)]

<span data-ttu-id="f6941-123">互換性のある型を含むリストを連結するには、次のコードに示すように `@` 演算子を使用します。</span><span class="sxs-lookup"><span data-stu-id="f6941-123">You can concatenate lists that have compatible types by using the `@` operator, as in the following code.</span></span> <span data-ttu-id="f6941-124">`list1` が `[2; 3; 4]` であり、`list2` が `[100; 2; 3; 4]` の場合、このコードでは `list3` が `[2; 3; 4; 100; 2; 3; 4]` として作成されます。</span><span class="sxs-lookup"><span data-stu-id="f6941-124">If `list1` is `[2; 3; 4]` and `list2` is `[100; 2; 3; 4]`, this code creates `list3` as `[2; 3; 4; 100; 2; 3; 4]`.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1306.fs)]

<span data-ttu-id="f6941-125">リストに対する操作を実行するための関数では使用、 [List モジュール](https://msdn.microsoft.com/library/a2264ba3-2d45-40dd-9040-4f7aa2ad9788)します。</span><span class="sxs-lookup"><span data-stu-id="f6941-125">Functions for performing operations on lists are available in the [List module](https://msdn.microsoft.com/library/a2264ba3-2d45-40dd-9040-4f7aa2ad9788).</span></span>

<span data-ttu-id="f6941-126">F# のリストは変更できないため、変更操作を行うと、既存のリストが変更されるのではなく、新しいリストが生成されます。</span><span class="sxs-lookup"><span data-stu-id="f6941-126">Because lists in F# are immutable, any modifying operations generate new lists instead of modifying existing lists.</span></span>

<span data-ttu-id="f6941-127">リストF#、つまり要素へのアクセスは O とリストの先頭のみにアクセスする操作は o (1)、シングル リンク リストとして実装されます (*n*)。</span><span class="sxs-lookup"><span data-stu-id="f6941-127">Lists in F# are implemented as singly linked lists, which means that operations that access only the head of the list are O(1), and element access is O(*n*).</span></span>

## <a name="properties"></a><span data-ttu-id="f6941-128">プロパティ</span><span class="sxs-lookup"><span data-stu-id="f6941-128">Properties</span></span>

<span data-ttu-id="f6941-129">リスト型では次のプロパティがサポートされています。</span><span class="sxs-lookup"><span data-stu-id="f6941-129">The list type supports the following properties:</span></span>

|<span data-ttu-id="f6941-130">プロパティ</span><span class="sxs-lookup"><span data-stu-id="f6941-130">Property</span></span>|<span data-ttu-id="f6941-131">型</span><span class="sxs-lookup"><span data-stu-id="f6941-131">Type</span></span>|<span data-ttu-id="f6941-132">説明</span><span class="sxs-lookup"><span data-stu-id="f6941-132">Description</span></span>|
|--------|----|-----------|
|[<span data-ttu-id="f6941-133">ヘッド</span><span class="sxs-lookup"><span data-stu-id="f6941-133">Head</span></span>](https://msdn.microsoft.com/library/5f9414fd-6bdb-470a-8b72-40016db30740)|`'T`|<span data-ttu-id="f6941-134">1 番目の要素。</span><span class="sxs-lookup"><span data-stu-id="f6941-134">The first element.</span></span>|
|[<span data-ttu-id="f6941-135">空</span><span class="sxs-lookup"><span data-stu-id="f6941-135">Empty</span></span>](https://msdn.microsoft.com/library/44406ecb-1918-4d32-b32a-ca1f69840386)|`'T list`|<span data-ttu-id="f6941-136">該当する型の空のリストを返す静的プロパティ。</span><span class="sxs-lookup"><span data-stu-id="f6941-136">A static property that returns an empty list of the appropriate type.</span></span>|
|[<span data-ttu-id="f6941-137">IsEmpty</span><span class="sxs-lookup"><span data-stu-id="f6941-137">IsEmpty</span></span>](https://msdn.microsoft.com/library/3ba087b2-2fc2-406d-b10a-cff6a19322da)|`bool`|<span data-ttu-id="f6941-138">リストに要素がない場合は `true` です。</span><span class="sxs-lookup"><span data-stu-id="f6941-138">`true` if the list has no elements.</span></span>|
|[<span data-ttu-id="f6941-139">Item</span><span class="sxs-lookup"><span data-stu-id="f6941-139">Item</span></span>](https://msdn.microsoft.com/library/bdb2553a-0e54-4ff8-baed-ab1aac8f5dae)|`'T`|<span data-ttu-id="f6941-140">指定したインデックスの要素 (起点を 0 とする)。</span><span class="sxs-lookup"><span data-stu-id="f6941-140">The element at the specified index (zero-based).</span></span>|
|[<span data-ttu-id="f6941-141">長さ</span><span class="sxs-lookup"><span data-stu-id="f6941-141">Length</span></span>](https://msdn.microsoft.com/library/25f715c8-9daa-4c4d-a6c7-26772f9dab4d)|`int`|<span data-ttu-id="f6941-142">要素の数。</span><span class="sxs-lookup"><span data-stu-id="f6941-142">The number of elements.</span></span>|
|[<span data-ttu-id="f6941-143">末尾</span><span class="sxs-lookup"><span data-stu-id="f6941-143">Tail</span></span>](https://msdn.microsoft.com/library/2a6f8eb9-dc32-41aa-8b62-2baffaface91)|`'T list`|<span data-ttu-id="f6941-144">1 番目の要素を除いたリスト。</span><span class="sxs-lookup"><span data-stu-id="f6941-144">The list without the first element.</span></span>|

<span data-ttu-id="f6941-145">これらのプロパティを使用したいくつかの例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="f6941-145">Following are some examples of using these properties.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1307.fs)]

## <a name="using-lists"></a><span data-ttu-id="f6941-146">リストの使用</span><span class="sxs-lookup"><span data-stu-id="f6941-146">Using Lists</span></span>

<span data-ttu-id="f6941-147">リストを使用してプログラミングを行うと、少量のコードで複雑な操作を実行できます。</span><span class="sxs-lookup"><span data-stu-id="f6941-147">Programming with lists enables you to perform complex operations with a small amount of code.</span></span> <span data-ttu-id="f6941-148">このセクションでは、関数型プログラミングにおいて重要なリストに対する一般的な操作について説明します。</span><span class="sxs-lookup"><span data-stu-id="f6941-148">This section describes common operations on lists that are important to functional programming.</span></span>

### <a name="recursion-with-lists"></a><span data-ttu-id="f6941-149">リストを使用した再帰</span><span class="sxs-lookup"><span data-stu-id="f6941-149">Recursion with Lists</span></span>

<span data-ttu-id="f6941-150">リストは、再帰的なプログラミング技法に非常に適しています。</span><span class="sxs-lookup"><span data-stu-id="f6941-150">Lists are uniquely suited to recursive programming techniques.</span></span> <span data-ttu-id="f6941-151">リストのすべての要素に対して実行する必要がある操作があるとします。</span><span class="sxs-lookup"><span data-stu-id="f6941-151">Consider an operation that must be performed on every element of a list.</span></span> <span data-ttu-id="f6941-152">この操作を再帰的に実行するには、リストの先頭に対して処理を行った後にリストの後部 (元のリストの最初の要素を除いた要素で構成される、元のリストより小さいリスト) を次の再帰レベルに戻します。</span><span class="sxs-lookup"><span data-stu-id="f6941-152">You can do this recursively by operating on the head of the list and then passing the tail of the list, which is a smaller list that consists of the original list without the first element, back again to the next level of recursion.</span></span>

<span data-ttu-id="f6941-153">このような再帰関数を記述するには、パターン マッチで cons 演算子 (`::`) を使用します。これによって、リストの先頭を末尾から分離できます。</span><span class="sxs-lookup"><span data-stu-id="f6941-153">To write such a recursive function, you use the cons operator (`::`) in pattern matching, which enables you to separate the head of a list from the tail.</span></span>

<span data-ttu-id="f6941-154">パターン マッチを使用して、リストに対する操作を実行する再帰関数を実装する方法を次のコード例に示します。</span><span class="sxs-lookup"><span data-stu-id="f6941-154">The following code example shows how to use pattern matching to implement a recursive function that performs operations on a list.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet13071.fs)]

<span data-ttu-id="f6941-155">このコードは小さいリストでは問題なく動作しますが、リストが大きくなると、スタックがオーバーフローする可能性があります。</span><span class="sxs-lookup"><span data-stu-id="f6941-155">The previous code works well for small lists, but for larger lists, it could overflow the stack.</span></span> <span data-ttu-id="f6941-156">次に示すコードは、再帰関数の処理では標準的な技法であるアキュムレータ引数を使用して、このコードを改善したものです。</span><span class="sxs-lookup"><span data-stu-id="f6941-156">The following code improves on this code by using an accumulator argument, a standard technique for working with recursive functions.</span></span> <span data-ttu-id="f6941-157">アキュムレータ引数を使用すると、関数の後部が再帰的になり、スタック領域を節約できます。</span><span class="sxs-lookup"><span data-stu-id="f6941-157">The use of the accumulator argument makes the function tail recursive, which saves stack space.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet13072.fs)]

<span data-ttu-id="f6941-158">関数 `RemoveAllMultiples` は、2 つのリストを受け取る再帰関数です。</span><span class="sxs-lookup"><span data-stu-id="f6941-158">The function `RemoveAllMultiples` is a recursive function that takes two lists.</span></span> <span data-ttu-id="f6941-159">1 番目のリストは、倍数を削除する数値が格納されたリストで、2 番目のリストは、数値を削除する元のリストです。</span><span class="sxs-lookup"><span data-stu-id="f6941-159">The first list contains the numbers whose multiples will be removed, and the second list is the list from which to remove the numbers.</span></span> <span data-ttu-id="f6941-160">次の例のコードでは、この再帰関数を使用してリストから素数以外をすべて削除します。その結果、素数のリストが残ります。</span><span class="sxs-lookup"><span data-stu-id="f6941-160">The code in the following example uses this recursive function to eliminate all the non-prime numbers from a list, leaving a list of prime numbers as the result.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1308.fs)]

<span data-ttu-id="f6941-161">出力は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="f6941-161">The output is as follows:</span></span>

```
Primes Up To 100:
[2; 3; 5; 7; 11; 13; 17; 19; 23; 29; 31; 37; 41; 43; 47; 53; 59; 61; 67; 71; 73; 79; 83; 89; 97]
```

## <a name="module-functions"></a><span data-ttu-id="f6941-162">モジュール関数</span><span class="sxs-lookup"><span data-stu-id="f6941-162">Module Functions</span></span>

<span data-ttu-id="f6941-163">[List モジュール](https://msdn.microsoft.com/library/a2264ba3-2d45-40dd-9040-4f7aa2ad9788)リストの要素にアクセスする機能を提供します。</span><span class="sxs-lookup"><span data-stu-id="f6941-163">The [List module](https://msdn.microsoft.com/library/a2264ba3-2d45-40dd-9040-4f7aa2ad9788) provides functions that access the elements of a list.</span></span> <span data-ttu-id="f6941-164">先頭の要素には、最も迅速かつ簡単にアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="f6941-164">The head element is the fastest and easiest to access.</span></span> <span data-ttu-id="f6941-165">プロパティを使用して[ヘッド](https://msdn.microsoft.com/library/5f9414fd-6bdb-470a-8b72-40016db30740)またはモジュール関数[List.head](https://msdn.microsoft.com/library/22514cc5-0511-498b-a2cc-837b688a6da2)します。</span><span class="sxs-lookup"><span data-stu-id="f6941-165">Use the property [Head](https://msdn.microsoft.com/library/5f9414fd-6bdb-470a-8b72-40016db30740) or the module function [List.head](https://msdn.microsoft.com/library/22514cc5-0511-498b-a2cc-837b688a6da2).</span></span> <span data-ttu-id="f6941-166">リストの末尾を使用してアクセスすることができます、[末尾](https://msdn.microsoft.com/library/2a6f8eb9-dc32-41aa-8b62-2baffaface91)プロパティまたは[List.tail](https://msdn.microsoft.com/library/da0a0638-4420-4571-84b6-d09ae601f601)関数。</span><span class="sxs-lookup"><span data-stu-id="f6941-166">You can access the tail of a list by using the [Tail](https://msdn.microsoft.com/library/2a6f8eb9-dc32-41aa-8b62-2baffaface91) property or the [List.tail](https://msdn.microsoft.com/library/da0a0638-4420-4571-84b6-d09ae601f601) function.</span></span> <span data-ttu-id="f6941-167">インデックスを使用して要素を検索するには使用、 [List.nth](https://msdn.microsoft.com/library/1f717d57-89be-4007-a971-9cf5a28d83b1)関数。</span><span class="sxs-lookup"><span data-stu-id="f6941-167">To find an element by index, use the [List.nth](https://msdn.microsoft.com/library/1f717d57-89be-4007-a971-9cf5a28d83b1) function.</span></span> <span data-ttu-id="f6941-168">`List.nth` はリストを走査します。</span><span class="sxs-lookup"><span data-stu-id="f6941-168">`List.nth` traverses the list.</span></span> <span data-ttu-id="f6941-169">そのため、これは O (*n*)。</span><span class="sxs-lookup"><span data-stu-id="f6941-169">Therefore, it is O(*n*).</span></span> <span data-ttu-id="f6941-170">コードで `List.nth` を頻繁に使用する場合は、リストの代わりに配列を使用すると、効果的である可能性があります。</span><span class="sxs-lookup"><span data-stu-id="f6941-170">If your code uses `List.nth` frequently, you might want to consider using an array instead of a list.</span></span> <span data-ttu-id="f6941-171">配列での要素のアクセスは O(1) です。</span><span class="sxs-lookup"><span data-stu-id="f6941-171">Element access in arrays is O(1).</span></span>

### <a name="boolean-operations-on-lists"></a><span data-ttu-id="f6941-172">リストに対するブール演算</span><span class="sxs-lookup"><span data-stu-id="f6941-172">Boolean Operations on Lists</span></span>

<span data-ttu-id="f6941-173">[List.isEmpty](https://msdn.microsoft.com/library/a7941d44-9e92-427c-b806-c378f4558107)関数が一覧にすべての要素があるかどうかを判断します。</span><span class="sxs-lookup"><span data-stu-id="f6941-173">The [List.isEmpty](https://msdn.microsoft.com/library/a7941d44-9e92-427c-b806-c378f4558107) function determines whether a list has any elements.</span></span>

<span data-ttu-id="f6941-174">[List.exists](https://msdn.microsoft.com/library/15a3ebd5-98f0-44c0-8220-7dedec3e68a8)関数に適用されるブール値の一覧を返します要素にテスト`true`任意の要素は、テストを満たしている場合。</span><span class="sxs-lookup"><span data-stu-id="f6941-174">The [List.exists](https://msdn.microsoft.com/library/15a3ebd5-98f0-44c0-8220-7dedec3e68a8) function applies a Boolean test to elements of a list and returns `true` if any element satisfies the test.</span></span> <span data-ttu-id="f6941-175">[List.exists2](https://msdn.microsoft.com/library/7532b39e-3f4f-4534-a60b-d7721dc6fa7e)と似ていますが、一連の 2 つのリスト内の要素のペアで動作します。</span><span class="sxs-lookup"><span data-stu-id="f6941-175">[List.exists2](https://msdn.microsoft.com/library/7532b39e-3f4f-4534-a60b-d7721dc6fa7e) is similar but operates on successive pairs of elements in two lists.</span></span>

<span data-ttu-id="f6941-176">`List.exists` を使用したコードの例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="f6941-176">The following code demonstrates the use of `List.exists`.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lists/snippet1.fs)]

<span data-ttu-id="f6941-177">出力は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="f6941-177">The output is as follows:</span></span>

```
For list [0; 1; 2; 3], contains zero is true
```

<span data-ttu-id="f6941-178">次の例は、`List.exists2` の使い方を示しています。</span><span class="sxs-lookup"><span data-stu-id="f6941-178">The following example demonstrates the use of `List.exists2`.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lists/snippet2.fs)]

<span data-ttu-id="f6941-179">出力は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="f6941-179">The output is as follows:</span></span>

```
Lists [1; 2; 3; 4; 5] and [5; 4; 3; 2; 1] have at least one equal element at the same position.
```

<span data-ttu-id="f6941-180">使用することができます[List.forall](https://msdn.microsoft.com/library/e11a5233-d612-40ac-833b-d5cf496900b7)一覧のすべての要素が条件を満たすかどうかをテストするかどうか。</span><span class="sxs-lookup"><span data-stu-id="f6941-180">You can use [List.forall](https://msdn.microsoft.com/library/e11a5233-d612-40ac-833b-d5cf496900b7) if you want to test whether all the elements of a list meet a condition.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lists/snippet3.fs)]

<span data-ttu-id="f6941-181">出力は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="f6941-181">The output is as follows:</span></span>

```
true
false
```

<span data-ttu-id="f6941-182">同様に、 [List.forall2](https://msdn.microsoft.com/library/bb611f02-8277-48f5-9af3-6194ae27d07e) 2 つのリスト内の対応する位置のすべての要素が要素の各ペアを含むブール式を満たすかどうかを決定します。</span><span class="sxs-lookup"><span data-stu-id="f6941-182">Similarly, [List.forall2](https://msdn.microsoft.com/library/bb611f02-8277-48f5-9af3-6194ae27d07e) determines whether all elements in the corresponding positions in two lists satisfy a Boolean expression that involves each pair of elements.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lists/snippet4.fs)]

<span data-ttu-id="f6941-183">出力は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="f6941-183">The output is as follows:</span></span>

```
true
false
```

### <a name="sort-operations-on-lists"></a><span data-ttu-id="f6941-184">リストに対する並べ替え操作</span><span class="sxs-lookup"><span data-stu-id="f6941-184">Sort Operations on Lists</span></span>

<span data-ttu-id="f6941-185">[List.sort](https://msdn.microsoft.com/library/17f1030e-aa7e-41dd-94ea-72cb6c04fd3d)、 [List.sortBy](https://msdn.microsoft.com/library/955bfc5f-ad9c-4f2d-a7ab-91e43eb21359)、および[List.sortWith](https://msdn.microsoft.com/library/1d806a54-9166-4198-906d-15101f7916c7)関数は、リストを並べ替えます。</span><span class="sxs-lookup"><span data-stu-id="f6941-185">The [List.sort](https://msdn.microsoft.com/library/17f1030e-aa7e-41dd-94ea-72cb6c04fd3d), [List.sortBy](https://msdn.microsoft.com/library/955bfc5f-ad9c-4f2d-a7ab-91e43eb21359), and [List.sortWith](https://msdn.microsoft.com/library/1d806a54-9166-4198-906d-15101f7916c7) functions sort lists.</span></span> <span data-ttu-id="f6941-186">並べ替え関数は、これら 3 つの関数のどれを使用するかを判断します。</span><span class="sxs-lookup"><span data-stu-id="f6941-186">The sorting function determines which of these three functions to use.</span></span> <span data-ttu-id="f6941-187">`List.sort` は、既定の一般的な比較を使用します。</span><span class="sxs-lookup"><span data-stu-id="f6941-187">`List.sort` uses default generic comparison.</span></span> <span data-ttu-id="f6941-188">一般的な比較は、汎用の比較関数に基づくグローバル演算子を使用して、値を比較します。</span><span class="sxs-lookup"><span data-stu-id="f6941-188">Generic comparison uses global operators based on the generic compare function to compare values.</span></span> <span data-ttu-id="f6941-189">この比較は、単純な数値型、タプル、レコード、判別共用体、リスト、配列、および `System.IComparable` を実装する任意の型など、広範な要素型で効率的に動作します。</span><span class="sxs-lookup"><span data-stu-id="f6941-189">It works efficiently with a wide variety of element types, such as simple numeric types, tuples, records, discriminated unions, lists, arrays, and any type that implements `System.IComparable`.</span></span> <span data-ttu-id="f6941-190">`System.IComparable` を実装する型の場合は、汎用的な比較で `System.IComparable.CompareTo()` 関数が使用されます。</span><span class="sxs-lookup"><span data-stu-id="f6941-190">For types that implement `System.IComparable`, generic comparison uses the `System.IComparable.CompareTo()` function.</span></span> <span data-ttu-id="f6941-191">また、汎用的な比較は文字列にも使用できますが、カルチャに依存しない並べ替え順序が使用されます。</span><span class="sxs-lookup"><span data-stu-id="f6941-191">Generic comparison also works with strings, but uses a culture-independent sorting order.</span></span> <span data-ttu-id="f6941-192">関数型のようなサポートされない型には、汎用的な比較を使用できません。</span><span class="sxs-lookup"><span data-stu-id="f6941-192">Generic comparison should not be used on unsupported types, such as function types.</span></span> <span data-ttu-id="f6941-193">また、既定の汎用的な比較は、小さい構造の型の場合に最高のパフォーマンスを示します。比較と並べ替えが頻繁に必要な大きい構造の型の場合は、`System.IComparable` を実装し、`System.IComparable.CompareTo()` メソッドを効率的に実装することを考慮してください。</span><span class="sxs-lookup"><span data-stu-id="f6941-193">Also, the performance of the default generic comparison is best for small structured types; for larger structured types that need to be compared and sorted frequently, consider implementing `System.IComparable` and providing an efficient implementation of the `System.IComparable.CompareTo()` method.</span></span>

<span data-ttu-id="f6941-194">`List.sortBy` 関数は、並べ替え基準として使用される値を返す関数を受け取り、`List.sortWith` 関数は、比較関数を引数として受け取ります。</span><span class="sxs-lookup"><span data-stu-id="f6941-194">`List.sortBy` takes a function that returns a value that is used as the sort criterion, and `List.sortWith` takes a comparison function as an argument.</span></span> <span data-ttu-id="f6941-195">これら 2 つの関数は、比較をサポートしない型を使用するとき、またはカルチャを認識する文字列の場合のように複雑な比較セマンティクスを必要とする比較の場合に役立ちます。</span><span class="sxs-lookup"><span data-stu-id="f6941-195">These latter two functions are useful when you are working with types that do not support comparison, or when the comparison requires more complex comparison semantics, as in the case of culture-aware strings.</span></span>

<span data-ttu-id="f6941-196">次の例は、`List.sort` の使い方を示しています。</span><span class="sxs-lookup"><span data-stu-id="f6941-196">The following example demonstrates the use of `List.sort`.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lists/snippet5.fs)]

<span data-ttu-id="f6941-197">出力は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="f6941-197">The output is as follows:</span></span>

```
[-2; 1; 4; 5; 8]
```

<span data-ttu-id="f6941-198">次の例は、`List.sortBy` の使い方を示しています。</span><span class="sxs-lookup"><span data-stu-id="f6941-198">The following example demonstrates the use of `List.sortBy`.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lists/snippet6.fs)]

<span data-ttu-id="f6941-199">出力は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="f6941-199">The output is as follows:</span></span>

```
[1; -2; 4; 5; 8]
```

<span data-ttu-id="f6941-200">次の例は、`List.sortWith` の使い方を示しています。</span><span class="sxs-lookup"><span data-stu-id="f6941-200">The next example demonstrates the use of `List.sortWith`.</span></span> <span data-ttu-id="f6941-201">この例では、カスタムの比較関数 `compareWidgets` を使用して、まず、カスタム型の 1 つのフィールドを比較し、最初のフィールドの値が同じである場合は、さらに別のフィールドを比較しています。</span><span class="sxs-lookup"><span data-stu-id="f6941-201">In this example, the custom comparison function `compareWidgets` is used to first compare one field of a custom type, and then another when the values of the first field are equal.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lists/snippet7.fs)]

<span data-ttu-id="f6941-202">出力は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="f6941-202">The output is as follows:</span></span>

```
[{ID = 92;
Rev = 1;}; {ID = 92;
Rev = 1;}; {ID = 100;
Rev = 2;}; {ID = 100;
Rev = 5;}; {ID = 110;
Rev = 1;}]
```

### <a name="search-operations-on-lists"></a><span data-ttu-id="f6941-203">リストに対する検索操作</span><span class="sxs-lookup"><span data-stu-id="f6941-203">Search Operations on Lists</span></span>

<span data-ttu-id="f6941-204">リストに対するさまざまな検索操作がサポートされています。</span><span class="sxs-lookup"><span data-stu-id="f6941-204">Numerous search operations are supported for lists.</span></span> <span data-ttu-id="f6941-205">最も簡単な[List.find](https://msdn.microsoft.com/library/0594593e-9c75-44c1-8f5a-a37b2e561c06)、特定の条件に一致する最初の要素を検索することができます。</span><span class="sxs-lookup"><span data-stu-id="f6941-205">The simplest, [List.find](https://msdn.microsoft.com/library/0594593e-9c75-44c1-8f5a-a37b2e561c06), enables you to find the first element that matches a given condition.</span></span>

<span data-ttu-id="f6941-206">次のコード例では、`List.find` を使用して、5 で割り切れる最初の数をリストから検索する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="f6941-206">The following code example demonstrates the use of `List.find` to find the first number that is divisible by 5 in a list.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lists/snippet8.fs)]

<span data-ttu-id="f6941-207">The result is 5.</span><span class="sxs-lookup"><span data-stu-id="f6941-207">The result is 5.</span></span>

<span data-ttu-id="f6941-208">呼び出す場合は、要素は、最初に変換する必要があります、 [List.pick](https://msdn.microsoft.com/library/0430b515-7fe4-49a1-a616-d2286d8b08b2)オプションを返します関数を受け取るが、値の最初のオプションを検索、`Some(x)`します。</span><span class="sxs-lookup"><span data-stu-id="f6941-208">If the elements must be transformed first, call [List.pick](https://msdn.microsoft.com/library/0430b515-7fe4-49a1-a616-d2286d8b08b2), which takes a function that returns an option, and looks for the first option value that is `Some(x)`.</span></span> <span data-ttu-id="f6941-209">`List.pick` は要素を返す代わりに、結果 `x` を返します。</span><span class="sxs-lookup"><span data-stu-id="f6941-209">Instead of returning the element, `List.pick` returns the result `x`.</span></span> <span data-ttu-id="f6941-210">一致する要素が見つからない場合、`List.pick` は `System.Collections.Generic.KeyNotFoundException` をスローします。</span><span class="sxs-lookup"><span data-stu-id="f6941-210">If no matching element is found, `List.pick` throws `System.Collections.Generic.KeyNotFoundException`.</span></span> <span data-ttu-id="f6941-211">`List.pick` の使用方法を次のコードに示します。</span><span class="sxs-lookup"><span data-stu-id="f6941-211">The following code shows the use of `List.pick`.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lists/snippet9.fs)]

<span data-ttu-id="f6941-212">出力は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="f6941-212">The output is as follows:</span></span>

```
"b"
```

<span data-ttu-id="f6941-213">検索操作の別のグループ[List.tryFind](https://msdn.microsoft.com/library/37f4532e-9fd0-4802-8bbd-e1aa2380287d)関連関数は、オプションの値を返します。</span><span class="sxs-lookup"><span data-stu-id="f6941-213">Another group of search operations, [List.tryFind](https://msdn.microsoft.com/library/37f4532e-9fd0-4802-8bbd-e1aa2380287d) and related functions, return an option value.</span></span> <span data-ttu-id="f6941-214">`List.tryFind` 関数は、条件を満たす要素がリストにある場合は、その最初の要素を返します。条件を満たす要素がない場合は、オプション値 `None` を返します。</span><span class="sxs-lookup"><span data-stu-id="f6941-214">The `List.tryFind` function returns the first element of a list that satisfies a condition if such an element exists, but the option value `None` if not.</span></span> <span data-ttu-id="f6941-215">バリエーション[List.tryFindIndex](https://msdn.microsoft.com/library/5e31968c-c3d3-43d2-859a-0526825895ec)が見つかった場合、要素自体ではなく、要素のインデックスを返します。</span><span class="sxs-lookup"><span data-stu-id="f6941-215">The variation [List.tryFindIndex](https://msdn.microsoft.com/library/5e31968c-c3d3-43d2-859a-0526825895ec) returns the index of the element, if one is found, rather than the element itself.</span></span> <span data-ttu-id="f6941-216">これらの関数を次のコードに示します。</span><span class="sxs-lookup"><span data-stu-id="f6941-216">These functions are illustrated in the following code.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lists/snippet10.fs)]

<span data-ttu-id="f6941-217">出力は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="f6941-217">The output is as follows:</span></span>

```
The first even value is 22.
The first even value is at position 8.
```

### <a name="arithmetic-operations-on-lists"></a><span data-ttu-id="f6941-218">リストに対する算術演算</span><span class="sxs-lookup"><span data-stu-id="f6941-218">Arithmetic Operations on Lists</span></span>

<span data-ttu-id="f6941-219">Sum や average などの一般的な算術演算に組み込まれている、 [List モジュール](https://msdn.microsoft.com/library/a2264ba3-2d45-40dd-9040-4f7aa2ad9788)します。</span><span class="sxs-lookup"><span data-stu-id="f6941-219">Common arithmetic operations such as sum and average are built into the [List module](https://msdn.microsoft.com/library/a2264ba3-2d45-40dd-9040-4f7aa2ad9788).</span></span> <span data-ttu-id="f6941-220">使用する[List.sum](https://msdn.microsoft.com/library/54d47fe3-5ecf-4883-beb5-e915342a17f9)、リストの要素の型をサポートする必要があります、`+`演算子と 0 個の値。</span><span class="sxs-lookup"><span data-stu-id="f6941-220">To work with [List.sum](https://msdn.microsoft.com/library/54d47fe3-5ecf-4883-beb5-e915342a17f9), the list element type must support the `+` operator and have a zero value.</span></span> <span data-ttu-id="f6941-221">すべての組み込み数値型はこの条件を満たしています。</span><span class="sxs-lookup"><span data-stu-id="f6941-221">All built-in arithmetic types satisfy these conditions.</span></span> <span data-ttu-id="f6941-222">使用する[List.average](https://msdn.microsoft.com/library/2b9a627b-106d-4548-8c4c-ab5058b8f8e1)要素の型は、除算、剰余は整数型は除外されますが、浮動小数点型では、なしをサポートする必要があります。</span><span class="sxs-lookup"><span data-stu-id="f6941-222">To work with [List.average](https://msdn.microsoft.com/library/2b9a627b-106d-4548-8c4c-ab5058b8f8e1), the element type must support division without a remainder, which excludes integral types but allows for floating point types.</span></span> <span data-ttu-id="f6941-223">[List.sumBy](https://msdn.microsoft.com/library/b7623389-0fe1-4762-9c67-51079903ab7d)と[List.averageBy](https://msdn.microsoft.com/library/936cc9ec-62af-464d-8726-7999c2f48403)関数をパラメーターとして関数を実行して、この関数の結果は、合計または平均値の計算に使用されます。</span><span class="sxs-lookup"><span data-stu-id="f6941-223">The [List.sumBy](https://msdn.microsoft.com/library/b7623389-0fe1-4762-9c67-51079903ab7d) and [List.averageBy](https://msdn.microsoft.com/library/936cc9ec-62af-464d-8726-7999c2f48403) functions take a function as a parameter, and this function's results are used to calculate the values for the sum or average.</span></span>

<span data-ttu-id="f6941-224">次のコードは、`List.sum`、 `List.sumBy`、および `List.average` の使用方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="f6941-224">The following code demonstrates the use of `List.sum`, `List.sumBy`, and `List.average`.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lists/snippet11.fs)]

<span data-ttu-id="f6941-225">出力は `1.000000`になります。</span><span class="sxs-lookup"><span data-stu-id="f6941-225">The output is `1.000000`.</span></span>

<span data-ttu-id="f6941-226">`List.averageBy` の使用方法を次のコードに示します。</span><span class="sxs-lookup"><span data-stu-id="f6941-226">The following code shows the use of `List.averageBy`.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lists/snippet12.fs)]

<span data-ttu-id="f6941-227">出力は `5.5`になります。</span><span class="sxs-lookup"><span data-stu-id="f6941-227">The output is `5.5`.</span></span>

### <a name="lists-and-tuples"></a><span data-ttu-id="f6941-228">リストとタプル</span><span class="sxs-lookup"><span data-stu-id="f6941-228">Lists and Tuples</span></span>

<span data-ttu-id="f6941-229">タプルを含むリストは、zip 関数および unzip 関数で操作できます。</span><span class="sxs-lookup"><span data-stu-id="f6941-229">Lists that contain tuples can be manipulated by zip and unzip functions.</span></span> <span data-ttu-id="f6941-230">これらの関数は、単一値の 2 つのリストを結合してタプルのリストを 1 つ生成したり、タプルの 1 つのリストを分割して単一の値のリストを 2 つ生成したりします。</span><span class="sxs-lookup"><span data-stu-id="f6941-230">These functions combine two lists of single values into one list of tuples or separate one list of tuples into two lists of single values.</span></span> <span data-ttu-id="f6941-231">最も単純な[List.zip](https://msdn.microsoft.com/library/3028d790-8f48-4c94-bf08-b058bec3689c)関数が 1 つの要素の 2 つのリストを受け取り、タプルのペアの 1 つのリストを生成します。</span><span class="sxs-lookup"><span data-stu-id="f6941-231">The simplest [List.zip](https://msdn.microsoft.com/library/3028d790-8f48-4c94-bf08-b058bec3689c) function takes two lists of single elements and produces a single list of tuple pairs.</span></span> <span data-ttu-id="f6941-232">別のバージョン、 [List.zip3](https://msdn.microsoft.com/library/003cc28e-0de3-4d99-89ed-cb19028e3c5b)1 つの要素の 3 つのリストを受け取り、3 つの要素の組の 1 つのリストを生成します。</span><span class="sxs-lookup"><span data-stu-id="f6941-232">Another version, [List.zip3](https://msdn.microsoft.com/library/003cc28e-0de3-4d99-89ed-cb19028e3c5b), takes three lists of single elements and produces a single list of tuples that have three elements.</span></span> <span data-ttu-id="f6941-233">次のコード例は、`List.zip` の使用方法を示します。</span><span class="sxs-lookup"><span data-stu-id="f6941-233">The following code example demonstrates the use of `List.zip`.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lists/snippet13.fs)]

<span data-ttu-id="f6941-234">出力は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="f6941-234">The output is as follows:</span></span>

```
[(1, -1); (2, -2); (3; -3)]
```

<span data-ttu-id="f6941-235">次のコード例は、`List.zip3` の使用方法を示します。</span><span class="sxs-lookup"><span data-stu-id="f6941-235">The following code example demonstrates the use of `List.zip3`.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lists/snippet14.fs)]

<span data-ttu-id="f6941-236">出力は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="f6941-236">The output is as follows:</span></span>

```
[(1, -1, 0); (2, -2, 0); (3, -3, 0)]
```

<span data-ttu-id="f6941-237">対応するバージョンを解凍[List.unzip](https://msdn.microsoft.com/library/639db80c-41b5-45bb-a6b4-1eaa04d61d21)と[List.unzip3](https://msdn.microsoft.com/library/43078c77-32ec-4342-85b3-c31ccf984db4)組のリストを受け取り、最初のリストがそれぞれの組の最初のすべての要素が含まれている、タプルの一覧を返すと、2 番目のリストには、各タプルの 2 番目の要素が含まれています。</span><span class="sxs-lookup"><span data-stu-id="f6941-237">The corresponding unzip versions, [List.unzip](https://msdn.microsoft.com/library/639db80c-41b5-45bb-a6b4-1eaa04d61d21) and [List.unzip3](https://msdn.microsoft.com/library/43078c77-32ec-4342-85b3-c31ccf984db4), take lists of tuples and return lists in a tuple, where the first list contains all the elements that were first in each tuple, and the second list contains the second element of each tuple, and so on.</span></span>

<span data-ttu-id="f6941-238">次のコード例は、の使用を示します[List.unzip](https://msdn.microsoft.com/library/639db80c-41b5-45bb-a6b4-1eaa04d61d21)します。</span><span class="sxs-lookup"><span data-stu-id="f6941-238">The following code example demonstrates the use of [List.unzip](https://msdn.microsoft.com/library/639db80c-41b5-45bb-a6b4-1eaa04d61d21).</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lists/snippet15.fs)]

<span data-ttu-id="f6941-239">出力は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="f6941-239">The output is as follows:</span></span>

```
([1; 3], [2; 4])
[1; 3] [2; 4]
```

<span data-ttu-id="f6941-240">次のコード例は、の使用を示します[List.unzip3](https://msdn.microsoft.com/library/43078c77-32ec-4342-85b3-c31ccf984db4)します。</span><span class="sxs-lookup"><span data-stu-id="f6941-240">The following code example demonstrates the use of [List.unzip3](https://msdn.microsoft.com/library/43078c77-32ec-4342-85b3-c31ccf984db4).</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lists/snippet16.fs)]

<span data-ttu-id="f6941-241">出力は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="f6941-241">The output is as follows:</span></span>

```
([1; 4], [2; 5], [3; 6])
```

### <a name="operating-on-list-elements"></a><span data-ttu-id="f6941-242">リスト要素に対する操作</span><span class="sxs-lookup"><span data-stu-id="f6941-242">Operating on List Elements</span></span>

<span data-ttu-id="f6941-243">F# は、リストの要素に対するさまざまな操作をサポートしています。</span><span class="sxs-lookup"><span data-stu-id="f6941-243">F# supports a variety of operations on list elements.</span></span> <span data-ttu-id="f6941-244">最も単純な[List.iter](https://msdn.microsoft.com/library/f778d075-81a9-4994-af60-cddcc53a201f)を使用すると、一覧のすべての要素に対して関数を呼び出します。</span><span class="sxs-lookup"><span data-stu-id="f6941-244">The simplest is [List.iter](https://msdn.microsoft.com/library/f778d075-81a9-4994-af60-cddcc53a201f), which enables you to call a function on every element of a list.</span></span> <span data-ttu-id="f6941-245">種類があります[List.iter2](https://msdn.microsoft.com/library/ea3b7761-916c-4016-9bd8-651124c98b40)、2 つのリストの要素に対して演算を実行できます[List.iteri](https://msdn.microsoft.com/library/6dd21ae6-5c00-41cd-8306-821e513d8f60)などは`List.iter`として各要素のインデックスが渡されることを除き、各要素に対して呼び出される関数の引数と[List.iteri2](https://msdn.microsoft.com/library/9658d740-9be5-4bf7-b663-c8ab2b3e196c)の機能の組み合わせである`List.iter2`と`List.iteri`します。</span><span class="sxs-lookup"><span data-stu-id="f6941-245">Variations include [List.iter2](https://msdn.microsoft.com/library/ea3b7761-916c-4016-9bd8-651124c98b40), which enables you to perform an operation on elements of two lists, [List.iteri](https://msdn.microsoft.com/library/6dd21ae6-5c00-41cd-8306-821e513d8f60), which is like `List.iter` except that the index of each element is passed as an argument to the function that is called for each element, and [List.iteri2](https://msdn.microsoft.com/library/9658d740-9be5-4bf7-b663-c8ab2b3e196c), which is a combination of the functionality of `List.iter2` and `List.iteri`.</span></span> <span data-ttu-id="f6941-246">次のコード例にこれらの関数を示します。</span><span class="sxs-lookup"><span data-stu-id="f6941-246">The following code example illustrates these functions.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lists/snippet17.fs)]

<span data-ttu-id="f6941-247">出力は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="f6941-247">The output is as follows:</span></span>

```
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

<span data-ttu-id="f6941-248">リストの要素を変換するもう 1 つの頻繁に使用される関数は[List.map](https://msdn.microsoft.com/library/c6b49c99-d4f3-4ba3-b1d0-85a312683dc6)を使用すると、一覧の各要素に関数を適用して、新しいリストにすべての結果を格納します。</span><span class="sxs-lookup"><span data-stu-id="f6941-248">Another frequently used function that transforms list elements is [List.map](https://msdn.microsoft.com/library/c6b49c99-d4f3-4ba3-b1d0-85a312683dc6), which enables you to apply a function to each element of a list and put all the results into a new list.</span></span> <span data-ttu-id="f6941-249">[List.map2](https://msdn.microsoft.com/library/5f48cce7-6eaf-4e54-8996-2b04d3c31e57)と[List.map3](https://msdn.microsoft.com/library/dd9fb190-6980-4537-be96-5645a64908f8)は複数のリストを受け取るバリエーションです。</span><span class="sxs-lookup"><span data-stu-id="f6941-249">[List.map2](https://msdn.microsoft.com/library/5f48cce7-6eaf-4e54-8996-2b04d3c31e57) and [List.map3](https://msdn.microsoft.com/library/dd9fb190-6980-4537-be96-5645a64908f8) are variations that take multiple lists.</span></span> <span data-ttu-id="f6941-250">使用することもできます[List.mapi](https://msdn.microsoft.com/library/284b9234-3d26-409b-b328-ac79638d9e14)と[List.mapi2](https://msdn.microsoft.com/library/680643af-233c-40a3-82f2-43d5af27ec49)場合、要素だけでなく、関数は各要素のインデックスに渡される必要があります。</span><span class="sxs-lookup"><span data-stu-id="f6941-250">You can also use [List.mapi](https://msdn.microsoft.com/library/284b9234-3d26-409b-b328-ac79638d9e14) and [List.mapi2](https://msdn.microsoft.com/library/680643af-233c-40a3-82f2-43d5af27ec49), if, in addition to the element, the function needs to be passed the index of each element.</span></span> <span data-ttu-id="f6941-251">`List.mapi2` と `List.mapi` の唯一の違いは、`List.mapi2` では 2 つのリストが使用される点です。</span><span class="sxs-lookup"><span data-stu-id="f6941-251">The only difference between `List.mapi2` and `List.mapi` is that `List.mapi2` works with two lists.</span></span> <span data-ttu-id="f6941-252">次の例を示しています[List.map](https://msdn.microsoft.com/library/c6b49c99-d4f3-4ba3-b1d0-85a312683dc6)します。</span><span class="sxs-lookup"><span data-stu-id="f6941-252">The following example illustrates [List.map](https://msdn.microsoft.com/library/c6b49c99-d4f3-4ba3-b1d0-85a312683dc6).</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lists/snippet18.fs)]

<span data-ttu-id="f6941-253">出力は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="f6941-253">The output is as follows:</span></span>

```
[2; 3; 4]
```

<span data-ttu-id="f6941-254">`List.map2` を使用する例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="f6941-254">The following example shows the use of `List.map2`.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lists/snippet19.fs)]

<span data-ttu-id="f6941-255">出力は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="f6941-255">The output is as follows:</span></span>

```
[5; 7; 9]
```

<span data-ttu-id="f6941-256">`List.map3` を使用する例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="f6941-256">The following example shows the use of `List.map3`.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lists/snippet20.fs)]

<span data-ttu-id="f6941-257">出力は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="f6941-257">The output is as follows:</span></span>

```
[7; 10; 13]
```

<span data-ttu-id="f6941-258">`List.mapi` を使用する例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="f6941-258">The following example shows the use of `List.mapi`.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lists/snippet21.fs)]

<span data-ttu-id="f6941-259">出力は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="f6941-259">The output is as follows:</span></span>

```
[1; 3; 5]
```

<span data-ttu-id="f6941-260">`List.mapi2` を使用する例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="f6941-260">The following example shows the use of `List.mapi2`.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lists/snippet22.fs)]

<span data-ttu-id="f6941-261">出力は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="f6941-261">The output is as follows:</span></span>

```
[0; 7; 18]
```

<span data-ttu-id="f6941-262">[List.collect](https://msdn.microsoft.com/library/cd08bbc7-a3b9-40ab-8c20-4e85ec84664f)などは`List.map`, 点が、各要素はリストを生成および最終的な一覧にこれらすべてのリストが連結されます。</span><span class="sxs-lookup"><span data-stu-id="f6941-262">[List.collect](https://msdn.microsoft.com/library/cd08bbc7-a3b9-40ab-8c20-4e85ec84664f) is like `List.map`, except that each element produces a list and all these lists are concatenated into a final list.</span></span> <span data-ttu-id="f6941-263">次のコードでは、リストの各要素が 3 つの値を生成します。</span><span class="sxs-lookup"><span data-stu-id="f6941-263">In the following code, each element of the list generates three numbers.</span></span> <span data-ttu-id="f6941-264">これらすべてが 1 つのリストに集約されます。</span><span class="sxs-lookup"><span data-stu-id="f6941-264">These are all collected into one list.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lists/snippet23.fs)]

<span data-ttu-id="f6941-265">出力は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="f6941-265">The output is as follows:</span></span>

```
[1; 2; 3; 2; 4; 6; 3; 6; 9]
```

<span data-ttu-id="f6941-266">使用することも[List.filter](https://msdn.microsoft.com/library/11a8c926-547b-44dd-bbae-98d44f3dd248)、ブール条件を受け取り、特定の条件を満たす要素のみで構成される新しいリストを生成します。</span><span class="sxs-lookup"><span data-stu-id="f6941-266">You can also use [List.filter](https://msdn.microsoft.com/library/11a8c926-547b-44dd-bbae-98d44f3dd248), which takes a Boolean condition and produces a new list that consists only of elements that satisfy the given condition.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lists/snippet24.fs)]

<span data-ttu-id="f6941-267">結果のリストは `[2; 4; 6]` です。</span><span class="sxs-lookup"><span data-stu-id="f6941-267">The resulting list is `[2; 4; 6]`.</span></span>

<span data-ttu-id="f6941-268">Map と filter を組み合わせた[List.choose](https://msdn.microsoft.com/library/2e21d3fb-ce35-4824-8a57-c4404616093d)変換し、同時に要素を選択することができます。</span><span class="sxs-lookup"><span data-stu-id="f6941-268">A combination of map and filter, [List.choose](https://msdn.microsoft.com/library/2e21d3fb-ce35-4824-8a57-c4404616093d) enables you to transform and select elements at the same time.</span></span> <span data-ttu-id="f6941-269">`List.choose` は、オプションを返す関数をリストの各要素に適用し、関数がオプション値 `Some` を返す要素の結果から成る新しいリストを返します。</span><span class="sxs-lookup"><span data-stu-id="f6941-269">`List.choose` applies a function that returns an option to each element of a list, and returns a new list of the results for elements when the function returns the option value `Some`.</span></span>

<span data-ttu-id="f6941-270">次のコードでは、`List.choose` を使用して、最初の文字が大文字の単語を単語のリストから選択しています。</span><span class="sxs-lookup"><span data-stu-id="f6941-270">The following code demonstrates the use of `List.choose` to select capitalized words out of a list of words.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lists/snippet25.fs)]

<span data-ttu-id="f6941-271">出力は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="f6941-271">The output is as follows:</span></span>

```
["Rome's"; "Bob's"]
```

### <a name="operating-on-multiple-lists"></a><span data-ttu-id="f6941-272">複数のリストに対する操作</span><span class="sxs-lookup"><span data-stu-id="f6941-272">Operating on Multiple Lists</span></span>

<span data-ttu-id="f6941-273">複数のリストを結合できます。</span><span class="sxs-lookup"><span data-stu-id="f6941-273">Lists can be joined together.</span></span> <span data-ttu-id="f6941-274">2 つのリストに 1 つに参加するには、使用[List.append](https://msdn.microsoft.com/library/2954da80-3f4a-4a4b-9371-794645c03426)します。</span><span class="sxs-lookup"><span data-stu-id="f6941-274">To join two lists into one, use [List.append](https://msdn.microsoft.com/library/2954da80-3f4a-4a4b-9371-794645c03426).</span></span> <span data-ttu-id="f6941-275">使用して複数の 2 つのリストを結合する[List.concat](https://msdn.microsoft.com/library/c5afd433-8764-4ea8-a6a8-937fb4d77c4c)します。</span><span class="sxs-lookup"><span data-stu-id="f6941-275">To join more than two lists, use [List.concat](https://msdn.microsoft.com/library/c5afd433-8764-4ea8-a6a8-937fb4d77c4c).</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lists/snippet26.fs)]

### <a name="fold-and-scan-operations"></a><span data-ttu-id="f6941-276">フォールド操作とスキャン操作</span><span class="sxs-lookup"><span data-stu-id="f6941-276">Fold and Scan Operations</span></span>

<span data-ttu-id="f6941-277">リストの操作の中には、リストのすべての要素間の依存関係を伴うものがあります。</span><span class="sxs-lookup"><span data-stu-id="f6941-277">Some list operations involve interdependencies between all of the list elements.</span></span> <span data-ttu-id="f6941-278">フォールド操作とスキャン操作は`List.iter`と`List.map`、各要素に対して関数を呼び出す場合、これらの操作と呼ばれる追加のパラメーターを提供する、*アキュムレータ*情報を保持します。計算。</span><span class="sxs-lookup"><span data-stu-id="f6941-278">The fold and scan operations are like `List.iter` and `List.map` in that you invoke a function on each element, but these operations provide an additional parameter called the *accumulator* that carries information through the computation.</span></span>

<span data-ttu-id="f6941-279">リストに対して計算を実行するには、`List.fold` を使用します。</span><span class="sxs-lookup"><span data-stu-id="f6941-279">Use `List.fold` to perform a calculation on a list.</span></span>

<span data-ttu-id="f6941-280">次のコード例は、の使用を示します[List.fold](https://msdn.microsoft.com/library/c272779e-bae7-4983-8d7f-16b345bb33a0)さまざまな操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="f6941-280">The following code example demonstrates the use of [List.fold](https://msdn.microsoft.com/library/c272779e-bae7-4983-8d7f-16b345bb33a0) to perform various operations.</span></span>

<span data-ttu-id="f6941-281">リストが走査されます。アキュムレータ `acc`は、計算の進行に伴って渡される値です。</span><span class="sxs-lookup"><span data-stu-id="f6941-281">The list is traversed; the accumulator `acc` is a value that is passed along as the calculation proceeds.</span></span> <span data-ttu-id="f6941-282">1 番目の引数はアキュムレータとリスト要素を受け取り、そのリスト要素に対する計算の中間結果を返します。</span><span class="sxs-lookup"><span data-stu-id="f6941-282">The first argument takes the accumulator and the list element, and returns the interim result of the calculation for that list element.</span></span> <span data-ttu-id="f6941-283">2 番目の引数はアキュムレータの初期値です。</span><span class="sxs-lookup"><span data-stu-id="f6941-283">The second argument is the initial value of the accumulator.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lists/snippet27.fs)]

<span data-ttu-id="f6941-284">関数名に数字が付いている関数は、複数のリストを操作するバージョンです。</span><span class="sxs-lookup"><span data-stu-id="f6941-284">The versions of these functions that have a digit in the function name operate on more than one list.</span></span> <span data-ttu-id="f6941-285">たとえば、 [List.fold2](https://msdn.microsoft.com/library/6cfcd043-a65d-4423-805a-2ab234cb5343) 2 つのリストに対して計算を実行します。</span><span class="sxs-lookup"><span data-stu-id="f6941-285">For example, [List.fold2](https://msdn.microsoft.com/library/6cfcd043-a65d-4423-805a-2ab234cb5343) performs computations on two lists.</span></span>

<span data-ttu-id="f6941-286">次の例は、`List.fold2` の使い方を示しています。</span><span class="sxs-lookup"><span data-stu-id="f6941-286">The following example demonstrates the use of `List.fold2`.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lists/snippet28.fs)]

<span data-ttu-id="f6941-287">`List.fold` [List.scan](https://msdn.microsoft.com/library/21f636db-885c-4a72-970e-e3841f33a1b8)を異なる`List.fold`最終的な追加のパラメーターの値を返しますが、`List.scan`追加のパラメーター (最終値) に加え、中間値の一覧を返します。</span><span class="sxs-lookup"><span data-stu-id="f6941-287">`List.fold` and [List.scan](https://msdn.microsoft.com/library/21f636db-885c-4a72-970e-e3841f33a1b8) differ in that `List.fold` returns the final value of the extra parameter, but `List.scan` returns the list of the intermediate values (along with the final value) of the extra parameter.</span></span>

<span data-ttu-id="f6941-288">これらの各関数が含まれていますリバース バリエーションの 1 つ、たとえば、 [List.foldBack](https://msdn.microsoft.com/library/b9a58e66-efe1-445f-a90c-ac9ffb9d40c7)での順序でリストが走査して、引数の順序。</span><span class="sxs-lookup"><span data-stu-id="f6941-288">Each of these functions includes a reverse variation, for example, [List.foldBack](https://msdn.microsoft.com/library/b9a58e66-efe1-445f-a90c-ac9ffb9d40c7), which differs in the order in which the list is traversed and the order of the arguments.</span></span> <span data-ttu-id="f6941-289">また、`List.fold`と`List.foldBack`のバリエーションがある[List.fold2](https://msdn.microsoft.com/library/6cfcd043-a65d-4423-805a-2ab234cb5343)と[List.foldBack2](https://msdn.microsoft.com/library/56371d3e-5271-4183-9e8c-15a02eda9aa2)、同じ長さの 2 つのリストを受け取る。</span><span class="sxs-lookup"><span data-stu-id="f6941-289">Also, `List.fold` and `List.foldBack` have variations, [List.fold2](https://msdn.microsoft.com/library/6cfcd043-a65d-4423-805a-2ab234cb5343) and [List.foldBack2](https://msdn.microsoft.com/library/56371d3e-5271-4183-9e8c-15a02eda9aa2), that take two lists of equal length.</span></span> <span data-ttu-id="f6941-290">各要素に対して実行される関数では、両方のリストの対応する要素を使用して操作を実行できます。</span><span class="sxs-lookup"><span data-stu-id="f6941-290">The function that executes on each element can use corresponding elements of both lists to perform some action.</span></span> <span data-ttu-id="f6941-291">2 つのリストの要素の型が同じである必要はありません。たとえば、次の例では、一方のリストには銀行口座の取引金額が格納され、もう一方のリストには取引の種類 (預け入れまたは引き出し) が格納されています。</span><span class="sxs-lookup"><span data-stu-id="f6941-291">The element types of the two lists can be different, as in the following example, in which one list contains transaction amounts for a bank account, and the other list contains the type of transaction: deposit or withdrawal.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lists/snippet29.fs)]

<span data-ttu-id="f6941-292">合計のような計算の場合は、結果が走査の順序に依存しないため、`List.fold` と `List.foldBack` のどちらを使用しても、同じ結果になります。</span><span class="sxs-lookup"><span data-stu-id="f6941-292">For a calculation like summation, `List.fold` and `List.foldBack` have the same effect because the result does not depend on the order of traversal.</span></span> <span data-ttu-id="f6941-293">次の例では、`List.foldBack` を使用してリストの要素を追加します。</span><span class="sxs-lookup"><span data-stu-id="f6941-293">In the following example, `List.foldBack` is used to add the elements in a list.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lists/snippet30.fs)]

<span data-ttu-id="f6941-294">次の例では、銀行口座の例に戻ります。</span><span class="sxs-lookup"><span data-stu-id="f6941-294">The following example returns to the bank account example.</span></span> <span data-ttu-id="f6941-295">今度は、利息を計算する新しい取引の種類が追加されています。</span><span class="sxs-lookup"><span data-stu-id="f6941-295">This time a new transaction type is added: an interest calculation.</span></span> <span data-ttu-id="f6941-296">取引の順序によって期末残高が異なります。</span><span class="sxs-lookup"><span data-stu-id="f6941-296">The ending balance now depends on the order of transactions.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lists/snippet34.fs)]

<span data-ttu-id="f6941-297">関数は、 [List.reduce](https://msdn.microsoft.com/library/048e1f95-691b-49cb-bb99-fb85f68f3d8b)に似ています`List.fold`と`List.scan`ただし、別のアキュムレータを受け渡すのではなく`List.reduce`の代わりに、要素型の 2 つの引数を受け取る関数には1 つだけ、およびそれらの引数の 1 つは、計算の中間結果を格納することを意味、アキュムレータとして機能します。</span><span class="sxs-lookup"><span data-stu-id="f6941-297">The function [List.reduce](https://msdn.microsoft.com/library/048e1f95-691b-49cb-bb99-fb85f68f3d8b) is somewhat like `List.fold` and `List.scan`, except that instead of passing around a separate accumulator, `List.reduce` takes a function that takes two arguments of the element type instead of just one, and one of those arguments acts as the accumulator, meaning that it stores the intermediate result of the computation.</span></span> <span data-ttu-id="f6941-298">`List.reduce` は、初めに最初の 2 つのリスト要素に対して演算を実行し、次にその演算の結果と次の要素を合わせて使用します。</span><span class="sxs-lookup"><span data-stu-id="f6941-298">`List.reduce` starts by operating on the first two list elements, and then uses the result of the operation along with the next element.</span></span> <span data-ttu-id="f6941-299">独自の型を持つ別のアキュムレータがないため、`List.reduce` を `List.fold` の代わりに使用できるのは、アキュムレータと要素が同じ型を持つ場合だけです。</span><span class="sxs-lookup"><span data-stu-id="f6941-299">Because there is not a separate accumulator that has its own type, `List.reduce` can be used in place of `List.fold` only when the accumulator and the element type have the same type.</span></span> <span data-ttu-id="f6941-300">`List.reduce` を使用したコードの例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="f6941-300">The following code demonstrates the use of `List.reduce`.</span></span> <span data-ttu-id="f6941-301">指定されたリストに要素がない場合、`List.reduce` は例外をスローします。</span><span class="sxs-lookup"><span data-stu-id="f6941-301">`List.reduce` throws an exception if the list provided has no elements.</span></span>

<span data-ttu-id="f6941-302">次のコードでは、ラムダ式の最初の呼び出しで引数 2 と 4 を受け取って 6 を返し、次の呼び出しで引数 6 と 10 を受け取るので、結果が 16 になります。</span><span class="sxs-lookup"><span data-stu-id="f6941-302">In the following code, the first call to the lambda expression is given the arguments 2 and 4, and returns 6, and the next call is given the arguments 6 and 10, so the result is 16.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lists/snippet33.fs)]

### <a name="converting-between-lists-and-other-collection-types"></a><span data-ttu-id="f6941-303">リストと他のコレクション型との変換</span><span class="sxs-lookup"><span data-stu-id="f6941-303">Converting Between Lists and Other Collection Types</span></span>

<span data-ttu-id="f6941-304">`List` モジュールには、シーケンスと配列との間で両方向の変換を行うための関数が用意されています。</span><span class="sxs-lookup"><span data-stu-id="f6941-304">The `List` module provides functions for converting to and from both sequences and arrays.</span></span> <span data-ttu-id="f6941-305">シーケンスとの間に変換する[List.toSeq](https://msdn.microsoft.com/library/7024be4b-ee70-43cc-8d0a-e6564a4ff7c0)または[List.ofSeq](https://msdn.microsoft.com/library/74ab9289-4a59-4433-92eb-3f662d7f7db0)します。</span><span class="sxs-lookup"><span data-stu-id="f6941-305">To convert to or from a sequence, use [List.toSeq](https://msdn.microsoft.com/library/7024be4b-ee70-43cc-8d0a-e6564a4ff7c0) or [List.ofSeq](https://msdn.microsoft.com/library/74ab9289-4a59-4433-92eb-3f662d7f7db0).</span></span> <span data-ttu-id="f6941-306">または配列に変換する[List.toArray](https://msdn.microsoft.com/library/ac87dd82-a0cd-40b3-b1fa-dd3168134547)または[List.ofArray](https://msdn.microsoft.com/library/f4bddc26-8c8f-4307-a6d7-a49dceb97032)します。</span><span class="sxs-lookup"><span data-stu-id="f6941-306">To convert to or from an array, use [List.toArray](https://msdn.microsoft.com/library/ac87dd82-a0cd-40b3-b1fa-dd3168134547) or [List.ofArray](https://msdn.microsoft.com/library/f4bddc26-8c8f-4307-a6d7-a49dceb97032).</span></span>

### <a name="additional-operations"></a><span data-ttu-id="f6941-307">その他の操作</span><span class="sxs-lookup"><span data-stu-id="f6941-307">Additional Operations</span></span>

<span data-ttu-id="f6941-308">リストに対する追加の操作については、ライブラリのリファレンス トピックを参照してください。 [Collections.List モジュール](https://msdn.microsoft.com/visualfsharpdocs/conceptual/collections.list-module-%5bfsharp%5d)します。</span><span class="sxs-lookup"><span data-stu-id="f6941-308">For information about additional operations on lists, see the library reference topic [Collections.List Module](https://msdn.microsoft.com/visualfsharpdocs/conceptual/collections.list-module-%5bfsharp%5d).</span></span>

## <a name="see-also"></a><span data-ttu-id="f6941-309">関連項目</span><span class="sxs-lookup"><span data-stu-id="f6941-309">See also</span></span>

- [<span data-ttu-id="f6941-310">F# 言語リファレンス</span><span class="sxs-lookup"><span data-stu-id="f6941-310">F# Language Reference</span></span>](index.md)
- [<span data-ttu-id="f6941-311">F# の型</span><span class="sxs-lookup"><span data-stu-id="f6941-311">F# Types</span></span>](fsharp-types.md)
- [<span data-ttu-id="f6941-312">シーケンス</span><span class="sxs-lookup"><span data-stu-id="f6941-312">Sequences</span></span>](sequences.md)
- [<span data-ttu-id="f6941-313">配列</span><span class="sxs-lookup"><span data-stu-id="f6941-313">Arrays</span></span>](arrays.md)
- [<span data-ttu-id="f6941-314">オプション</span><span class="sxs-lookup"><span data-stu-id="f6941-314">Options</span></span>](options.md)
