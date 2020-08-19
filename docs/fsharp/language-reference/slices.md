---
title: スライス
description: '既存の F # データ型にスライスを使用する方法、およびその他のデータ型用に独自のスライスを定義する方法について説明します。'
ms.date: 12/23/2019
ms.openlocfilehash: d3ddb2c247c36a85842f565f051372c5f2c9a9e9
ms.sourcegitcommit: 8bfeb5930ca48b2ee6053f16082dcaf24d46d221
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/18/2020
ms.locfileid: "88559012"
---
# <a name="slices"></a><span data-ttu-id="5095c-103">スライス</span><span class="sxs-lookup"><span data-stu-id="5095c-103">Slices</span></span>

<span data-ttu-id="5095c-104">F # では、スライスは、その `GetSlice` 定義またはスコープ内の [型拡張](type-extensions.md)でメソッドを持つ任意のデータ型のサブセットです。</span><span class="sxs-lookup"><span data-stu-id="5095c-104">In F#, a slice is a subset of any data type that has a `GetSlice` method in its definition or in an in-scope [type extension](type-extensions.md).</span></span> <span data-ttu-id="5095c-105">これは、F # の配列とリストで最もよく使用されます。</span><span class="sxs-lookup"><span data-stu-id="5095c-105">It is most commonly used with F# arrays and lists.</span></span> <span data-ttu-id="5095c-106">この記事では、既存の F # 型からスライスを取得する方法と、独自のスライスを定義する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="5095c-106">This article explains how to take slices from existing F# types and how to define your own slices.</span></span>

<span data-ttu-id="5095c-107">スライスは [インデクサー](./members/indexed-properties.md)に似ていますが、基になるデータ構造から1つの値を生成するのではなく、複数の値を生成します。</span><span class="sxs-lookup"><span data-stu-id="5095c-107">Slices are similar to [indexers](./members/indexed-properties.md), but instead of yielding a single value from the underlying data structure, they yield multiple ones.</span></span>

<span data-ttu-id="5095c-108">現在、F # には、文字列、リスト、配列、および2D 配列をスライスするための組み込みサポートがあります。</span><span class="sxs-lookup"><span data-stu-id="5095c-108">F# currently has intrinsic support for slicing strings, lists, arrays, and 2D arrays.</span></span>

## <a name="basic-slicing-with-f-lists-and-arrays"></a><span data-ttu-id="5095c-109">F # リストと配列を使用した基本的なスライス</span><span class="sxs-lookup"><span data-stu-id="5095c-109">Basic slicing with F# lists and arrays</span></span>

<span data-ttu-id="5095c-110">スライスされる最も一般的なデータ型は、F # のリストと配列です。</span><span class="sxs-lookup"><span data-stu-id="5095c-110">The most common data types that are sliced are F# lists and arrays.</span></span> <span data-ttu-id="5095c-111">次の例では、リストを使用してこれを行う方法を示します。</span><span class="sxs-lookup"><span data-stu-id="5095c-111">The following example demonstrates how to do this with lists:</span></span>

```fsharp
// Generate a list of 100 integers
let fullList = [ 1 .. 100 ]

// Create a slice from indices 1-5 (inclusive)
let smallSlice = fullList.[1..5]
printfn "Small slice: %A" smallSlice

// Create a slice from the beginning to index 5 (inclusive)
let unboundedBeginning = fullList.[..5]
printfn "Unbounded beginning slice: %A" unboundedBeginning

// Create a slice from an index to the end of the list
let unboundedEnd = fullList.[94..]
printfn "Unbounded end slice: %A" unboundedEnd
```

<span data-ttu-id="5095c-112">配列のスライスは、スライスリストと同じです。</span><span class="sxs-lookup"><span data-stu-id="5095c-112">Slicing arrays is just like slicing lists:</span></span>

```fsharp
// Generate an array of 100 integers
let fullArray = [| 1 .. 100 |]

// Create a slice from indices 1-5 (inclusive)
let smallSlice = fullArray.[1..5]
printfn "Small slice: %A" smallSlice

// Create a slice from the beginning to index 5 (inclusive)
let unboundedBeginning = fullArray.[..5]
printfn "Unbounded beginning slice: %A" unboundedBeginning

// Create a slice from an index to the end of the list
let unboundedEnd = fullArray.[94..]
printfn "Unbounded end slice: %A" unboundedEnd
```

## <a name="slicing-multidimensional-arrays"></a><span data-ttu-id="5095c-113">多次元配列のスライス</span><span class="sxs-lookup"><span data-stu-id="5095c-113">Slicing multidimensional arrays</span></span>

<span data-ttu-id="5095c-114">F # は、F # コアライブラリの多次元配列をサポートしています。</span><span class="sxs-lookup"><span data-stu-id="5095c-114">F# supports multidimensional arrays in the F# core library.</span></span> <span data-ttu-id="5095c-115">1次元配列の場合と同様に、多次元配列のスライスも役に立ちます。</span><span class="sxs-lookup"><span data-stu-id="5095c-115">As with one-dimensional arrays, slices of multidimensional arrays can also be useful.</span></span> <span data-ttu-id="5095c-116">ただし、追加のディメンションの導入では、特定の行と列のスライスを取得できるように、若干異なる構文が必要になります。</span><span class="sxs-lookup"><span data-stu-id="5095c-116">However, the introduction of additional dimensions mandates a slightly different syntax so that you can take slices of specific rows and columns.</span></span>

<span data-ttu-id="5095c-117">次の例は、2D 配列をスライスする方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="5095c-117">The following examples demonstrate how to slice a 2D array:</span></span>

```fsharp
// Generate a 3x3 2D matrix
let A = array2D [[1;2;3];[4;5;6];[7;8;9]]
printfn "Full matrix:\n %A" A

// Take the first row
let row0 = A.[0,*]
printfn "Row 0: %A" row0

// Take the first column
let col0 = A.[*,0]
printfn "Column 0: %A" col0

// Take all rows but only two columns
let subA = A.[*,0..1]
printfn "%A" subA

// Take two rows and all columns
let subA' = A.[0..1,*]
printfn "%A" subA'

// Slice a 2x2 matrix out of the full 3x3 matrix
let twoByTwo = A.[0..1,0..1]
printfn "%A" twoByTwo
```

<span data-ttu-id="5095c-118">現在、F # コアライブラリでは、 `GetSlice` 3d 配列に対して定義されていません。</span><span class="sxs-lookup"><span data-stu-id="5095c-118">The F# core library does not currently define `GetSlice` for 3D arrays.</span></span> <span data-ttu-id="5095c-119">3D 配列やその他の次元の配列をスライスする場合は、自分でメンバーを定義 `GetSlice` します。</span><span class="sxs-lookup"><span data-stu-id="5095c-119">If you wish to slice 3D arrays or other arrays of more dimensions, define the `GetSlice` member yourself.</span></span>

## <a name="defining-slices-for-other-data-structures"></a><span data-ttu-id="5095c-120">他のデータ構造のスライスの定義</span><span class="sxs-lookup"><span data-stu-id="5095c-120">Defining slices for other data structures</span></span>

<span data-ttu-id="5095c-121">F # コアライブラリでは、型の限られたセットのスライスが定義されています。</span><span class="sxs-lookup"><span data-stu-id="5095c-121">The F# core library defines slices for a limited set of types.</span></span> <span data-ttu-id="5095c-122">より多くのデータ型に対してスライスを定義する場合は、型定義自体または型拡張機能のいずれかを使用できます。</span><span class="sxs-lookup"><span data-stu-id="5095c-122">If you wish to define slices for more data types, you can do so either in the type definition itself or in a type extension.</span></span>

<span data-ttu-id="5095c-123">たとえば、クラスのスライスを定義して、 <xref:System.ArraySegment%601> 便利なデータ操作を可能にする方法を次に示します。</span><span class="sxs-lookup"><span data-stu-id="5095c-123">For example, here's how you might define slices for the <xref:System.ArraySegment%601> class to allow for convenient data manipulation:</span></span>

```fsharp
open System

type ArraySegment<'TItem> with
    member segment.GetSlice(start, finish) =
        let start = defaultArg start 0
        let finish = defaultArg finish segment.Count
        ArraySegment(segment.Array, segment.Offset + start, finish - start)

let arr = ArraySegment [| 1 .. 10 |]
let slice = arr.[2..5] //[ 3; 4; 5]
```

<span data-ttu-id="5095c-124">型と型を使用するもう1つの例を <xref:System.Span%601> <xref:System.ReadOnlySpan%601> 次に示します。</span><span class="sxs-lookup"><span data-stu-id="5095c-124">Another example using the <xref:System.Span%601> and <xref:System.ReadOnlySpan%601> types:</span></span>

```fsharp
open System

type ReadOnlySpan<'T> with
    member sp.GetSlice(startIdx, endIdx) =
        let s = defaultArg startIdx 0
        let e = defaultArg endIdx sp.Length
        sp.Slice(s, e - s)

type Span<'T> with
    member sp.GetSlice(startIdx, endIdx) =
        let s = defaultArg startIdx 0
        let e = defaultArg endIdx sp.Length
        sp.Slice(s, e - s)

let printSpan (sp: Span<int>) =
    let arr = sp.ToArray()
    printfn "%A" arr

let sp = [| 1; 2; 3; 4; 5 |].AsSpan()
printSpan sp.[0..] // [|1; 2; 3; 4; 5|]
printSpan sp.[..5] // [|1; 2; 3; 4; 5|]
printSpan sp.[0..3] // [|1; 2; 3|]
printSpan sp.[1..3] // |2; 3|]
```

## <a name="built-in-f-slices-are-end-inclusive"></a><span data-ttu-id="5095c-125">組み込みの F # スライスは両端を含みます</span><span class="sxs-lookup"><span data-stu-id="5095c-125">Built-in F# slices are end-inclusive</span></span>

<span data-ttu-id="5095c-126">F # のすべての組み込みスライスは、終了します。つまり、上限がスライスに含まれます。</span><span class="sxs-lookup"><span data-stu-id="5095c-126">All intrinsic slices in F# are end-inclusive; that is, the upper bound is included in the slice.</span></span> <span data-ttu-id="5095c-127">開始インデックスと終了インデックスを持つ特定のスライスの場合、結果として得られるスライスには `x` `y` *yth* 値が含まれます。</span><span class="sxs-lookup"><span data-stu-id="5095c-127">For a given slice with starting index `x` and ending index `y`, the resulting slice will include the *yth* value.</span></span>

```fsharp
// Define a new list
let xs = [1 .. 10]

printfn "%A" xs.[2..5] // Includes the 5th index
```

## <a name="see-also"></a><span data-ttu-id="5095c-128">関連項目</span><span class="sxs-lookup"><span data-stu-id="5095c-128">See also</span></span>

- [<span data-ttu-id="5095c-129">インデックス付きプロパティ</span><span class="sxs-lookup"><span data-stu-id="5095c-129">Indexed properties</span></span>](./members/indexed-properties.md)
