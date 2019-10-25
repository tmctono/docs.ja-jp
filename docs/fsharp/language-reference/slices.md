---
title: Slice (F#)
description: 既存F#のデータ型にスライスを使用する方法、およびその他のデータ型用に独自のスライスを定義する方法について説明します。
ms.date: 01/22/2019
ms.openlocfilehash: cbff1b055ea99ef708f9db191be49275e630ee90
ms.sourcegitcommit: 9bd1c09128e012b6e34bdcbdf3576379f58f3137
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/23/2019
ms.locfileid: "72798909"
---
# <a name="slices"></a><span data-ttu-id="dfc32-103">スライス</span><span class="sxs-lookup"><span data-stu-id="dfc32-103">Slices</span></span>

<span data-ttu-id="dfc32-104">でF#は、スライスはデータ型のサブセットです。</span><span class="sxs-lookup"><span data-stu-id="dfc32-104">In F#, a slice is a subset of a data type.</span></span> <span data-ttu-id="dfc32-105">データ型からスライスを取得できるようにするには、データ型で `GetSlice` メソッドを定義するか、スコープ内にある[型拡張機能](type-extensions.md)を定義する必要があります。</span><span class="sxs-lookup"><span data-stu-id="dfc32-105">To be able to take a slice from a data type, the data type must either define a `GetSlice` method or in a [type extension](type-extensions.md) that is in scope.</span></span> <span data-ttu-id="dfc32-106">この記事では、既存F#の型からスライスを取得する方法と、独自の型を定義する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="dfc32-106">This article explains how to take slices from existing F# types and how to define your own.</span></span>

<span data-ttu-id="dfc32-107">スライスは[インデクサー](./members/indexed-properties.md)に似ていますが、基になるデータ構造から1つの値を生成するのではなく、複数の値を生成します。</span><span class="sxs-lookup"><span data-stu-id="dfc32-107">Slices are similar to [indexers](./members/indexed-properties.md), but instead of yielding a single value from the underlying data structure, they yield multiple ones.</span></span>

<span data-ttu-id="dfc32-108">F#には、現在、文字列、リスト、配列、および2D 配列のスライスのサポートが組み込まれています。</span><span class="sxs-lookup"><span data-stu-id="dfc32-108">F# currently has intrinsic support for slicing strings, lists, arrays, and 2D arrays.</span></span>

## <a name="basic-slicing-with-f-lists-and-arrays"></a><span data-ttu-id="dfc32-109">リストと配列F#を使用した基本的なスライス</span><span class="sxs-lookup"><span data-stu-id="dfc32-109">Basic slicing with F# lists and arrays</span></span>

<span data-ttu-id="dfc32-110">スライスされる最も一般的なデータ型はF# 、リストと配列です。</span><span class="sxs-lookup"><span data-stu-id="dfc32-110">The most common data types that are sliced are F# lists and arrays.</span></span> <span data-ttu-id="dfc32-111">次の例では、リストを使用してこれを行う方法を示します。</span><span class="sxs-lookup"><span data-stu-id="dfc32-111">The following example demonstrates how to do this with lists:</span></span>

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

<span data-ttu-id="dfc32-112">配列のスライスは、スライスリストと同じです。</span><span class="sxs-lookup"><span data-stu-id="dfc32-112">Slicing arrays is just like slicing lists:</span></span>

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

## <a name="slicing-multidimensional-arrays"></a><span data-ttu-id="dfc32-113">多次元配列のスライス</span><span class="sxs-lookup"><span data-stu-id="dfc32-113">Slicing multidimensional arrays</span></span>

<span data-ttu-id="dfc32-114">F#は、コアライブラリのF#多次元配列をサポートしています。</span><span class="sxs-lookup"><span data-stu-id="dfc32-114">F# supports multidimensional arrays in the F# core library.</span></span> <span data-ttu-id="dfc32-115">1次元配列の場合と同様に、多次元配列のスライスも役に立ちます。</span><span class="sxs-lookup"><span data-stu-id="dfc32-115">As with one-dimensional arrays, slices of multidimensional arrays can also be useful.</span></span> <span data-ttu-id="dfc32-116">ただし、追加のディメンションの導入では、特定の行と列のスライスを取得できるように、若干異なる構文が必要になります。</span><span class="sxs-lookup"><span data-stu-id="dfc32-116">However, the introduction of additional dimensions mandates a slightly different syntax so that you can take slices of specific rows and columns.</span></span>

<span data-ttu-id="dfc32-117">次の例は、2D 配列をスライスする方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="dfc32-117">The following examples demonstrate how to slice a 2D array:</span></span>

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

<span data-ttu-id="dfc32-118">コアF#ライブラリでは、3d 配列の`GetSlice`が定義されていません。</span><span class="sxs-lookup"><span data-stu-id="dfc32-118">The F# core library does not define `GetSlice`for 3D arrays.</span></span> <span data-ttu-id="dfc32-119">その他の次元の配列をスライスする場合は、`GetSlice` メンバーを自分で定義する必要があります。</span><span class="sxs-lookup"><span data-stu-id="dfc32-119">If you wish to slice those or other arrays of more dimensions, you must define the `GetSlice` member yourself.</span></span>

## <a name="defining-slices-for-other-data-structures"></a><span data-ttu-id="dfc32-120">他のデータ構造のスライスの定義</span><span class="sxs-lookup"><span data-stu-id="dfc32-120">Defining slices for other data structures</span></span>

<span data-ttu-id="dfc32-121">コアF#ライブラリでは、型の限られたセットのスライスが定義されています。</span><span class="sxs-lookup"><span data-stu-id="dfc32-121">The F# core library defines slices for a limited set of types.</span></span> <span data-ttu-id="dfc32-122">より多くのデータ型に対してスライスを定義する場合は、型定義自体または型拡張機能のいずれかを使用できます。</span><span class="sxs-lookup"><span data-stu-id="dfc32-122">If you wish to define slices for more data types, you can do so either in the type definition itself or in a type extension.</span></span>

<span data-ttu-id="dfc32-123">たとえば、<xref:System.ArraySegment%601> クラスのスライスを定義して、便利なデータ操作を可能にする方法を次に示します。</span><span class="sxs-lookup"><span data-stu-id="dfc32-123">For example, here's how you might define slices for the <xref:System.ArraySegment%601> class to allow for convenient data manipulation:</span></span>

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

### <a name="use-inlining-to-avoid-boxing-if-it-is-necessary"></a><span data-ttu-id="dfc32-124">インライン展開を使用して、必要に応じてボックス化を回避する</span><span class="sxs-lookup"><span data-stu-id="dfc32-124">Use inlining to avoid boxing if it is necessary</span></span>

<span data-ttu-id="dfc32-125">実際に構造体である型のスライスを定義する場合は、`GetSlice` メンバーを `inline` することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="dfc32-125">If you are defining slices for a type that is actually a struct, we recommend that you `inline` the `GetSlice` member.</span></span> <span data-ttu-id="dfc32-126">コンパイラF#はオプションの引数を最適化し、スライスの結果としてヒープの割り当てを回避します。</span><span class="sxs-lookup"><span data-stu-id="dfc32-126">The F# compiler optimizes away the optional arguments, avoiding any heap allocations as a result of slicing.</span></span> <span data-ttu-id="dfc32-127">これは、ヒープに割り当てることができない <xref:System.Span%601> などのスライス構成の場合に非常に重要です。</span><span class="sxs-lookup"><span data-stu-id="dfc32-127">This is critically important for slicing constructs such as <xref:System.Span%601> that cannot be allocated on the heap.</span></span>

```fsharp
open System

type Span<'T> with
    // Note the 'inline' in the member definition
    member inline sp.GetSlice(startIdx, endIdx) =
        let s = defaultArg startIdx 0
        let e = defaultArg endIdx sp.Length
        sp.Slice(s, e)

let printSpan (sp: Span<int>) =
    let arr = sp.ToArray()
    printfn "%A" arr

let sp = [| 1; 2; 3; 4; 5 |].AsSpan()
printSpan sp.[0..] // [|1; 2; 3; 4; 5|]
printSpan sp.[..5] // [|1; 2; 3; 4; 5|]
printSpan sp.[0..3] // [|1; 2; 3|]
printSpan sp.[1..2] // |2; 3|]
```

## <a name="see-also"></a><span data-ttu-id="dfc32-128">関連項目</span><span class="sxs-lookup"><span data-stu-id="dfc32-128">See also</span></span>

- [<span data-ttu-id="dfc32-129">インデックス付きプロパティ</span><span class="sxs-lookup"><span data-stu-id="dfc32-129">Indexed properties</span></span>](./members/indexed-properties.md)
