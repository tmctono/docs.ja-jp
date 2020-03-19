---
title: F# 4.5 の新機能 - F# ガイド
description: F# 4.5 で利用可能な新機能の概要を確認します。
ms.date: 11/27/2019
ms.openlocfilehash: 560e3dd941f79b76d3b864ba0f6560be154ebc1a
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2020
ms.locfileid: "79186136"
---
# <a name="whats-new-in-f-45"></a><span data-ttu-id="96667-103">F# 4.5 の新機能</span><span class="sxs-lookup"><span data-stu-id="96667-103">What's new in F# 4.5</span></span>

<span data-ttu-id="96667-104">F# 4.5 では、F# 言語に複数の改良が加えました。</span><span class="sxs-lookup"><span data-stu-id="96667-104">F# 4.5 adds multiple improvements to the F# language.</span></span> <span data-ttu-id="96667-105">これらの機能の多くは、F# で効率的なコードを記述できる一方で、このコードの安全性を確保するために組み合わせて追加されました。</span><span class="sxs-lookup"><span data-stu-id="96667-105">Many of these features were added together to enable you to write efficient code in F# while also ensuring this code is safe.</span></span> <span data-ttu-id="96667-106">この場合、これらの構成要素を使用する場合、言語にいくつかの概念を追加し、コンパイラ分析の量を大幅に増やします。</span><span class="sxs-lookup"><span data-stu-id="96667-106">Doing so means adding a few concepts to the language and a significant amount of compiler analysis when using these constructs.</span></span>

## <a name="get-started"></a><span data-ttu-id="96667-107">はじめに</span><span class="sxs-lookup"><span data-stu-id="96667-107">Get started</span></span>

<span data-ttu-id="96667-108">F# 4.5 は、すべての .NET コアディストリビューションと Visual Studio ツールで使用できます。</span><span class="sxs-lookup"><span data-stu-id="96667-108">F# 4.5 is available in all .NET Core distributions and Visual Studio tooling.</span></span> <span data-ttu-id="96667-109">[F# の使用を開始](../get-started/index.md)して、詳細を確認してください。</span><span class="sxs-lookup"><span data-stu-id="96667-109">[Get started with F#](../get-started/index.md) to learn more.</span></span>

## <a name="span-and-byref-like-structs"></a><span data-ttu-id="96667-110">スパンとバイレフのような構造体</span><span class="sxs-lookup"><span data-stu-id="96667-110">Span and byref-like structs</span></span>

<span data-ttu-id="96667-111">NET <xref:System.Span%601> Core で導入された型では、厳密に型指定された方法でメモリ内のバッファーを表すことができます。</span><span class="sxs-lookup"><span data-stu-id="96667-111">The <xref:System.Span%601> type introduced in .NET Core allows you to represent buffers in memory in a strongly-typed manner, which is now allowed in F# starting with F# 4.5.</span></span> <span data-ttu-id="96667-112">次の例は、異なるバッファー表現を持つ 関数<xref:System.Span%601>を使用して再利用する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="96667-112">The following example shows how you can re-use a function operating on a <xref:System.Span%601> with different buffer representations:</span></span>

```fsharp
let safeSum (bytes: Span<byte>) =
    let mutable sum = 0
    for i in 0 .. bytes.Length - 1 do
        sum <- sum + int bytes.[i]
    sum

// managed memory
let arrayMemory = Array.zeroCreate<byte>(100)
let arraySpan = new Span<byte>(arrayMemory)

safeSum(arraySpan) |> printfn "res = %d"

// native memory
let nativeMemory = Marshal.AllocHGlobal(100);
let nativeSpan = new Span<byte>(nativeMemory.ToPointer(), 100)

safeSum(nativeSpan) |> printfn "res = %d"
Marshal.FreeHGlobal(nativeMemory)

// stack memory
let mem = NativePtr.stackalloc<byte>(100)
let mem2 = mem |> NativePtr.toVoidPtr
let stackSpan = Span<byte>(mem2, 100)

safeSum(stackSpan) |> printfn "res = %d"
```

<span data-ttu-id="96667-113">この重要な側面は、Span やその他[の byref のような構造体](../language-reference/structures.md#byreflike-structs)が、コンパイラによって非常に厳密な静的分析を実行し、予期しない方法で使用を制限することです。</span><span class="sxs-lookup"><span data-stu-id="96667-113">An important aspect to this is that Span and other [byref-like structs](../language-reference/structures.md#byreflike-structs) have very rigid static analysis performed by the compiler that restrict their usage in ways you might find to be unexpected.</span></span> <span data-ttu-id="96667-114">これは、F# 4.5 で導入されたパフォーマンス、表現力、安全性の基本的なトレードオフです。</span><span class="sxs-lookup"><span data-stu-id="96667-114">This is the fundamental tradeoff between performance, expressiveness, and safety that is introduced in F# 4.5.</span></span>

## <a name="revamped-byrefs"></a><span data-ttu-id="96667-115">改良されたバイレフ</span><span class="sxs-lookup"><span data-stu-id="96667-115">Revamped byrefs</span></span>

<span data-ttu-id="96667-116">F# 4.5 より前のバージョンでは、F# の[Byrefs](../language-reference/byrefs.md)は安全で、多くのアプリケーションでは不音でした。</span><span class="sxs-lookup"><span data-stu-id="96667-116">Prior to F# 4.5, [Byrefs](../language-reference/byrefs.md) in F# were unsafe and unsound for numerous applications.</span></span> <span data-ttu-id="96667-117">byrefs に関するサウンドの問題は F# 4.5 で取り上げられており、span および byref のような構造体に対して行われたのと同じ静的分析も適用されました。</span><span class="sxs-lookup"><span data-stu-id="96667-117">Soundness issues around byrefs have been addressed in F# 4.5 and the same static analysis done for span and byref-like structs was also applied.</span></span>

### <a name="inreft-and-outreft"></a><span data-ttu-id="96667-118">インレフ<>とアウトレフ<></span><span class="sxs-lookup"><span data-stu-id="96667-118">inref<'T> and outref<'T></span></span>

<span data-ttu-id="96667-119">読み取り専用、書き込み専用、および読み取り/書き込みマネージ ポインターの概念`inref<'T>`を`outref<'T>`表すために、F# 4.5 では、それぞれ、読み取り専用ポインターと書き込み専用ポインターを表す型が導入されています。</span><span class="sxs-lookup"><span data-stu-id="96667-119">To represent the notion of a read-only, write-only, and read/write managed pointer, F# 4.5 introduces the `inref<'T>`, `outref<'T>` types to represent read-only and write-only pointers, respectively.</span></span> <span data-ttu-id="96667-120">それぞれに異なるセマンティクスがあります。</span><span class="sxs-lookup"><span data-stu-id="96667-120">Each have different semantics.</span></span> <span data-ttu-id="96667-121">たとえば、`inref<'T>`に書き込むことはできません。</span><span class="sxs-lookup"><span data-stu-id="96667-121">For example, you cannot write to an `inref<'T>`:</span></span>

```fsharp
let f (dt: inref<DateTime>) =
    dt <- DateTime.Now // ERROR - cannot write to an inref!
```

<span data-ttu-id="96667-122">既定では、何か変更可能として宣言されていない限り、型`inref<'T>`の推論は、F# コードの不変の性質に沿ったマネージ ポインターを推論します。</span><span class="sxs-lookup"><span data-stu-id="96667-122">By default, type inference will infer managed pointers as `inref<'T>` to be in line with the immutable nature of F# code, unless something has already been declared as mutable.</span></span> <span data-ttu-id="96667-123">書き込み可能なものにするには、そのアドレスを操作する関数またはメンバー`mutable`に渡す前に、型を宣言する必要があります。</span><span class="sxs-lookup"><span data-stu-id="96667-123">To make something writable, you'll need to declare a type as `mutable` before passing its address to a function or member that manipulates it.</span></span> <span data-ttu-id="96667-124">詳細については[、「Byrefs」](../language-reference/byrefs.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="96667-124">To learn more, see [Byrefs](../language-reference/byrefs.md).</span></span>

## <a name="readonly-structs"></a><span data-ttu-id="96667-125">読み取り専用構造体</span><span class="sxs-lookup"><span data-stu-id="96667-125">Readonly structs</span></span>

<span data-ttu-id="96667-126">F# 4.5 以降では、構造体<xref:System.Runtime.CompilerServices.IsReadOnlyAttribute>に次のようにアポイントを付けることができます。</span><span class="sxs-lookup"><span data-stu-id="96667-126">Starting with F# 4.5, you can annotate a struct with <xref:System.Runtime.CompilerServices.IsReadOnlyAttribute> as such:</span></span>

```fsharp
[<IsReadOnly; Struct>]
type S(count1: int, count2: int) =
    member x.Count1 = count1
    member x.Count2 = count2
```

<span data-ttu-id="96667-127">これにより、構造体で変更可能なメンバーを宣言することを禁止し、F# と C# がアセンブリから読み取り時に読み取り専用として扱うことを可能にするメタデータを出力します。</span><span class="sxs-lookup"><span data-stu-id="96667-127">This disallows you from declaring a mutable member in the struct and emits metadata that allows F# and C# to treat it as readonly when consumed from an assembly.</span></span> <span data-ttu-id="96667-128">詳細については、「 [ReadOnly 構造体](../language-reference/structures.md#readonly-structs)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="96667-128">To learn more, see [ReadOnly structs](../language-reference/structures.md#readonly-structs).</span></span>

## <a name="void-pointers"></a><span data-ttu-id="96667-129">ボイドポインタ</span><span class="sxs-lookup"><span data-stu-id="96667-129">Void pointers</span></span>

<span data-ttu-id="96667-130">型`voidptr`は、次の関数と同様に、F# 4.5 に追加されます。</span><span class="sxs-lookup"><span data-stu-id="96667-130">The `voidptr` type is added to F# 4.5, as are the following functions:</span></span>

* <span data-ttu-id="96667-131">`NativePtr.ofVoidPtr`void ポインタをネイティブの int ポインタに変換するには</span><span class="sxs-lookup"><span data-stu-id="96667-131">`NativePtr.ofVoidPtr` to convert a void pointer into a native int pointer</span></span>
* <span data-ttu-id="96667-132">`NativePtr.toVoidPtr`ネイティブの int ポインターを void ポインターに変換するには</span><span class="sxs-lookup"><span data-stu-id="96667-132">`NativePtr.toVoidPtr` to convert a native int pointer to a void pointer</span></span>

<span data-ttu-id="96667-133">これは、void ポインターを使用するネイティブ コンポーネントと相互運用するときに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="96667-133">This is helpful when interoperating with a native component that makes use of void pointers.</span></span>

## <a name="the-match-keyword"></a><span data-ttu-id="96667-134">`match!` キーワード</span><span class="sxs-lookup"><span data-stu-id="96667-134">The `match!` keyword</span></span>

<span data-ttu-id="96667-135">この`match!`キーワードは、計算式の内部でパターン マッチングを強化します。</span><span class="sxs-lookup"><span data-stu-id="96667-135">The `match!` keyword enhances pattern matching when inside a computation expression:</span></span>

```fsharp
// Code that returns an asynchronous option
let checkBananaAsync (s: string) =
    async {
        if s = "banana" then
            return Some s
        else
            return None
    }

// Now you can use 'match!'
let funcWithString (s: string) =
    async {
        match! checkBananaAsync s with
        | Some bananaString -> printfn "It's banana!"
        | None -> printfn "%s" s
}
```

<span data-ttu-id="96667-136">これにより、多くの場合、オプション (または他の型) と非同期などの計算式を混在させるコードを短くすることができます。</span><span class="sxs-lookup"><span data-stu-id="96667-136">This allows you to shorten code that often involves mixing options (or other types) with computation expressions such as async.</span></span> <span data-ttu-id="96667-137">詳細については[、「match!」](../language-reference/computation-expressions.md#match)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="96667-137">To learn more, see [match!](../language-reference/computation-expressions.md#match).</span></span>

## <a name="relaxed-upcasting-requirements-in-array-list-and-sequence-expressions"></a><span data-ttu-id="96667-138">配列、リスト、シーケンス式での緩和されたアップキャスト要件</span><span class="sxs-lookup"><span data-stu-id="96667-138">Relaxed upcasting requirements in array, list, and sequence expressions</span></span>

<span data-ttu-id="96667-139">配列、リスト、シーケンス式の別の内部から継承する型を混在させる場合は、従来、任意の派生型を親の型にアップキャストする`:>`必要`upcast`があります。</span><span class="sxs-lookup"><span data-stu-id="96667-139">Mixing types where one may inherit from another inside of array, list, and sequence expressions has traditionally required you to upcast any derived type to its parent type with `:>` or `upcast`.</span></span> <span data-ttu-id="96667-140">これは緩和され、次のように示されています。</span><span class="sxs-lookup"><span data-stu-id="96667-140">This is now relaxed, demonstrated as follows:</span></span>

```fsharp
let x0 : obj list  = [ "a" ] // ok pre-F# 4.5
let x1 : obj list  = [ "a"; "b" ] // ok pre-F# 4.5
let x2 : obj list  = [ yield "a" :> obj ] // ok pre-F# 4.5

let x3 : obj list  = [ yield "a" ] // Now ok for F# 4.5, and can replace x2
```

## <a name="indentation-relaxation-for-array-and-list-expressions"></a><span data-ttu-id="96667-141">配列およびリスト式のインデント緩和</span><span class="sxs-lookup"><span data-stu-id="96667-141">Indentation relaxation for array and list expressions</span></span>

<span data-ttu-id="96667-142">F# 4.5 より前のバージョンでは、メソッド呼び出しに引数として渡された場合、配列とリスト式を過度にインデントする必要があった。</span><span class="sxs-lookup"><span data-stu-id="96667-142">Prior to F# 4.5, you needed to excessively indent array and list expressions when passed as arguments to method calls.</span></span> <span data-ttu-id="96667-143">これは不要になりました。</span><span class="sxs-lookup"><span data-stu-id="96667-143">This is no longer required:</span></span>

```fsharp
module NoExcessiveIndenting =
    System.Console.WriteLine(format="{0}", arg = [|
        "hello"
    |])
    System.Console.WriteLine([|
        "hello"
    |])
```
