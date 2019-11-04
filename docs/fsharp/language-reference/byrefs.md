---
title: Byrefs
description: 下位レベルのプログラミングに使用される、 F#の byref および byref に似た型について説明します。
ms.date: 09/02/2018
ms.openlocfilehash: 453de2a5f30dc532dcd7f873b7f5defefdc814cd
ms.sourcegitcommit: 14ad34f7c4564ee0f009acb8bfc0ea7af3bc9541
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/01/2019
ms.locfileid: "73424776"
---
# <a name="byrefs"></a><span data-ttu-id="6823e-103">Byrefs</span><span class="sxs-lookup"><span data-stu-id="6823e-103">Byrefs</span></span>

<span data-ttu-id="6823e-104">F#には、低レベルのプログラミングの領域を処理する2つの主要な機能領域があります。</span><span class="sxs-lookup"><span data-stu-id="6823e-104">F# has two major feature areas that deal in the space of low-level programming:</span></span>

* <span data-ttu-id="6823e-105">`byref`は、マネージポインターである `outref` 型 /`inref`/ます。</span><span class="sxs-lookup"><span data-stu-id="6823e-105">The `byref`/`inref`/`outref` types, which are a managed pointers.</span></span> <span data-ttu-id="6823e-106">実行時に無効なプログラムをコンパイルできないように、使用方法に制限があります。</span><span class="sxs-lookup"><span data-stu-id="6823e-106">They have restrictions on usage so that you cannot compile a program that is invalid at runtime.</span></span>
* <span data-ttu-id="6823e-107">`byref`に似た構造体。これは、`byref<'T>`と同じセマンティクスとコンパイル時の制限を持つ[構造体](structures.md)です。</span><span class="sxs-lookup"><span data-stu-id="6823e-107">A `byref`-like struct, which is a [structure](structures.md) that has similar semantics and the same compile-time restrictions as `byref<'T>`.</span></span> <span data-ttu-id="6823e-108">一例として、<xref:System.Span%601>があります。</span><span class="sxs-lookup"><span data-stu-id="6823e-108">One example is <xref:System.Span%601>.</span></span>

## <a name="syntax"></a><span data-ttu-id="6823e-109">構文</span><span class="sxs-lookup"><span data-stu-id="6823e-109">Syntax</span></span>

```fsharp
// Byref types as parameters
let f (x: byref<'T>) = ()
let g (x: inref<'T>) = ()
let h (x: outref<'T>) = ()

// Calling a function with a byref parameter
let mutable x = 3
f &x

// Declaring a byref-like struct
open System.Runtime.CompilerServices

[<Struct; IsByRefLike>]
type S(count1: int, count2: int) =
    member x.Count1 = count1
    member x.Count2 = count2
```

## <a name="byref-inref-and-outref"></a><span data-ttu-id="6823e-110">Byref、inref、および outref</span><span class="sxs-lookup"><span data-stu-id="6823e-110">Byref, inref, and outref</span></span>

<span data-ttu-id="6823e-111">`byref`には、次の3つの形式があります。</span><span class="sxs-lookup"><span data-stu-id="6823e-111">There are three forms of `byref`:</span></span>

* <span data-ttu-id="6823e-112">`inref<'T>`、基になる値を読み取るためのマネージポインターです。</span><span class="sxs-lookup"><span data-stu-id="6823e-112">`inref<'T>`, a managed pointer for reading the underlying value.</span></span>
* <span data-ttu-id="6823e-113">`outref<'T>`、基になる値に書き込むためのマネージポインターです。</span><span class="sxs-lookup"><span data-stu-id="6823e-113">`outref<'T>`, a managed pointer for writing to the underlying value.</span></span>
* <span data-ttu-id="6823e-114">`byref<'T>`、基になる値の読み取りと書き込みを行うためのマネージポインターです。</span><span class="sxs-lookup"><span data-stu-id="6823e-114">`byref<'T>`, a managed pointer for reading and writing the underlying value.</span></span>

<span data-ttu-id="6823e-115">`inref<'T>` が必要な場所で `byref<'T>` を渡すことができます。</span><span class="sxs-lookup"><span data-stu-id="6823e-115">A `byref<'T>` can be passed where an `inref<'T>` is expected.</span></span> <span data-ttu-id="6823e-116">同様に、`outref<'T>` が想定されている場所で `byref<'T>` を渡すことができます。</span><span class="sxs-lookup"><span data-stu-id="6823e-116">Similarly, a `byref<'T>` can be passed where an `outref<'T>` is expected.</span></span>

## <a name="using-byrefs"></a><span data-ttu-id="6823e-117">Byref の使用</span><span class="sxs-lookup"><span data-stu-id="6823e-117">Using byrefs</span></span>

<span data-ttu-id="6823e-118">`inref<'T>`を使用するには、`&`でポインター値を取得する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6823e-118">To use a `inref<'T>`, you need to get a pointer value with `&`:</span></span>

```fsharp
open System

let f (dt: inref<DateTime>) =
    printfn "Now: %s" (dt.ToString())

let usage =
    let dt = DateTime.Now
    f &dt // Pass a pointer to 'dt'
```

<span data-ttu-id="6823e-119">`outref<'T>` または `byref<'T>`を使用してポインターに書き込むには、ポインターを取得する値も `mutable`に設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6823e-119">To write to the pointer by using an `outref<'T>` or `byref<'T>`, you must also make the value you grab a pointer to `mutable`.</span></span>

```fsharp
open System

let f (dt: byref<DateTime>) =
    printfn "Now: %s" (dt.ToString())
    dt <- DateTime.Now

// Make 'dt' mutable
let mutable dt = DateTime.Now

// Now you can pass the pointer to 'dt'
f &dt
```

<span data-ttu-id="6823e-120">ポインターを読み取る代わりに作成するだけの場合は、`byref<'T>`ではなく `outref<'T>` を使用することを検討してください。</span><span class="sxs-lookup"><span data-stu-id="6823e-120">If you are only writing the pointer instead of reading it, consider using `outref<'T>` instead of `byref<'T>`.</span></span>

### <a name="inref-semantics"></a><span data-ttu-id="6823e-121">Inref セマンティクス</span><span class="sxs-lookup"><span data-stu-id="6823e-121">Inref semantics</span></span>

<span data-ttu-id="6823e-122">次のコードがあるとします。</span><span class="sxs-lookup"><span data-stu-id="6823e-122">Consider the following code:</span></span>

```fsharp
let f (x: inref<SomeStruct>) = x.SomeField
```

<span data-ttu-id="6823e-123">意味的には、これは次のことを意味します。</span><span class="sxs-lookup"><span data-stu-id="6823e-123">Semantically, this means the following:</span></span>

* <span data-ttu-id="6823e-124">`x` ポインターの所有者は、それを使用して値を読み取ることしかできません。</span><span class="sxs-lookup"><span data-stu-id="6823e-124">The holder of the `x` pointer may only use it to read the value.</span></span>
* <span data-ttu-id="6823e-125">`SomeStruct` 内で入れ子になって `struct` フィールドに対して取得されたポインターには、型 `inref<_>`が指定されます。</span><span class="sxs-lookup"><span data-stu-id="6823e-125">Any pointer acquired to `struct` fields nested within `SomeStruct` are given type `inref<_>`.</span></span>

<span data-ttu-id="6823e-126">次のような場合もあります。</span><span class="sxs-lookup"><span data-stu-id="6823e-126">The following is also true:</span></span>

* <span data-ttu-id="6823e-127">他のスレッドまたは別名には、`x`への書き込みアクセス権がないという意味はありません。</span><span class="sxs-lookup"><span data-stu-id="6823e-127">There is no implication that other threads or aliases do not have write access to `x`.</span></span>
* <span data-ttu-id="6823e-128">`inref`で `x` ことによって `SomeStruct` が不変であるという意味はありません。</span><span class="sxs-lookup"><span data-stu-id="6823e-128">There is no implication that `SomeStruct` is immutable by virtue of `x` being an `inref`.</span></span>

<span data-ttu-id="6823e-129">ただし、変更F#できない値型の**場合は、** `this` ポインターが `inref`と推測されます。</span><span class="sxs-lookup"><span data-stu-id="6823e-129">However, for F# value types that **are** immutable, the `this` pointer is inferred to be an `inref`.</span></span>

<span data-ttu-id="6823e-130">これらのルールはすべて、`inref` ポインターの所有者が、ポイントされているメモリの直接の内容を変更しない可能性があることを意味します。</span><span class="sxs-lookup"><span data-stu-id="6823e-130">All of these rules together mean that the holder of an `inref` pointer may not modify the immediate contents of the memory being pointed to.</span></span>

### <a name="outref-semantics"></a><span data-ttu-id="6823e-131">Outref セマンティクス</span><span class="sxs-lookup"><span data-stu-id="6823e-131">Outref semantics</span></span>

<span data-ttu-id="6823e-132">`outref<'T>` の目的は、ポインターを読み取り専用にする必要があることを示すことです。</span><span class="sxs-lookup"><span data-stu-id="6823e-132">The purpose of `outref<'T>` is to indicate that the pointer should only be read from.</span></span> <span data-ttu-id="6823e-133">予期しない `outref<'T>` は、名前に関係なく、基になる値の読み取りを許可します。</span><span class="sxs-lookup"><span data-stu-id="6823e-133">Unexpectedly, `outref<'T>` permits reading the underlying value despite its name.</span></span> <span data-ttu-id="6823e-134">これは、互換性のためのものです。</span><span class="sxs-lookup"><span data-stu-id="6823e-134">This is for compatibility purposes.</span></span> <span data-ttu-id="6823e-135">意味的には、`outref<'T>` は `byref<'T>`とは異なります。</span><span class="sxs-lookup"><span data-stu-id="6823e-135">Semantically, `outref<'T>` is no different than `byref<'T>`.</span></span>

### <a name="interop-with-c"></a><span data-ttu-id="6823e-136">C\# との相互運用</span><span class="sxs-lookup"><span data-stu-id="6823e-136">Interop with C\#</span></span>

<span data-ttu-id="6823e-137">C#では、`ref` が返すだけでなく、`in ref` キーワードと `out ref` キーワードもサポートされています。</span><span class="sxs-lookup"><span data-stu-id="6823e-137">C# supports the `in ref` and `out ref` keywords, in addition to `ref` returns.</span></span> <span data-ttu-id="6823e-138">次の表は、 F#がC#出力を解釈する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="6823e-138">The following table shows how F# interprets what C# emits:</span></span>

|<span data-ttu-id="6823e-139">C#構築</span><span class="sxs-lookup"><span data-stu-id="6823e-139">C# construct</span></span>|<span data-ttu-id="6823e-140">F#推論</span><span class="sxs-lookup"><span data-stu-id="6823e-140">F# infers</span></span>|
|------------|---------|
|<span data-ttu-id="6823e-141">戻り値の `ref`</span><span class="sxs-lookup"><span data-stu-id="6823e-141">`ref` return value</span></span>|`outref<'T>`|
|<span data-ttu-id="6823e-142">戻り値の `ref readonly`</span><span class="sxs-lookup"><span data-stu-id="6823e-142">`ref readonly` return value</span></span>|`inref<'T>`|
|<span data-ttu-id="6823e-143">`in ref` パラメーター</span><span class="sxs-lookup"><span data-stu-id="6823e-143">`in ref` parameter</span></span>|`inref<'T>`|
|<span data-ttu-id="6823e-144">`out ref` パラメーター</span><span class="sxs-lookup"><span data-stu-id="6823e-144">`out ref` parameter</span></span>|`outref<'T>`|

<span data-ttu-id="6823e-145">次の表は、 F#が出力する内容を示しています。</span><span class="sxs-lookup"><span data-stu-id="6823e-145">The following table shows what F# emits:</span></span>

|<span data-ttu-id="6823e-146">F#構築</span><span class="sxs-lookup"><span data-stu-id="6823e-146">F# construct</span></span>|<span data-ttu-id="6823e-147">出力されたコンストラクト</span><span class="sxs-lookup"><span data-stu-id="6823e-147">Emitted construct</span></span>|
|------------|-----------------|
|<span data-ttu-id="6823e-148">`inref<'T>` 引数</span><span class="sxs-lookup"><span data-stu-id="6823e-148">`inref<'T>` argument</span></span>|<span data-ttu-id="6823e-149">引数の `[In]` 属性</span><span class="sxs-lookup"><span data-stu-id="6823e-149">`[In]` attribute on argument</span></span>|
|<span data-ttu-id="6823e-150">`inref<'T>` 返す</span><span class="sxs-lookup"><span data-stu-id="6823e-150">`inref<'T>` return</span></span>|<span data-ttu-id="6823e-151">値の `modreq` 属性</span><span class="sxs-lookup"><span data-stu-id="6823e-151">`modreq` attribute on value</span></span>|
|<span data-ttu-id="6823e-152">抽象スロットまたは実装内の `inref<'T>`</span><span class="sxs-lookup"><span data-stu-id="6823e-152">`inref<'T>` in abstract slot or implementation</span></span>|<span data-ttu-id="6823e-153">引数または戻り値の `modreq`</span><span class="sxs-lookup"><span data-stu-id="6823e-153">`modreq` on argument or return</span></span>|
|<span data-ttu-id="6823e-154">`outref<'T>` 引数</span><span class="sxs-lookup"><span data-stu-id="6823e-154">`outref<'T>` argument</span></span>|<span data-ttu-id="6823e-155">引数の `[Out]` 属性</span><span class="sxs-lookup"><span data-stu-id="6823e-155">`[Out]` attribute on argument</span></span>|

### <a name="type-inference-and-overloading-rules"></a><span data-ttu-id="6823e-156">型の推定とオーバーロードの規則</span><span class="sxs-lookup"><span data-stu-id="6823e-156">Type inference and overloading rules</span></span>

<span data-ttu-id="6823e-157">`inref<'T>` 型は、次の場合F#にコンパイラによって推論されます。</span><span class="sxs-lookup"><span data-stu-id="6823e-157">An `inref<'T>` type is inferred by the F# compiler in the following cases:</span></span>

1. <span data-ttu-id="6823e-158">`IsReadOnly` 属性を持つ .NET パラメーターまたは戻り値の型。</span><span class="sxs-lookup"><span data-stu-id="6823e-158">A .NET parameter or return type that has an `IsReadOnly` attribute.</span></span>
2. <span data-ttu-id="6823e-159">変更可能なフィールドを持たない構造体型の `this` ポインター。</span><span class="sxs-lookup"><span data-stu-id="6823e-159">The `this` pointer on a struct type that has no mutable fields.</span></span>
3. <span data-ttu-id="6823e-160">別の `inref<_>` ポインターから派生したメモリ位置のアドレス。</span><span class="sxs-lookup"><span data-stu-id="6823e-160">The address of a memory location derived from another `inref<_>` pointer.</span></span>

<span data-ttu-id="6823e-161">`inref` の暗黙的なアドレスを取得するときに、型 `SomeType` の引数を持つオーバーロードは `inref<SomeType>`型の引数を持つオーバーロードに優先されます。</span><span class="sxs-lookup"><span data-stu-id="6823e-161">When an implicit address of an `inref` is being taken, an overload with an argument of type `SomeType` is preferred to an overload with an argument of type `inref<SomeType>`.</span></span> <span data-ttu-id="6823e-162">(例:</span><span class="sxs-lookup"><span data-stu-id="6823e-162">For example:</span></span>

```fsharp
type C() =
    static member M(x: System.DateTime) = x.AddDays(1.0)
    static member M(x: inref<System.DateTime>) = x.AddDays(2.0)
    static member M2(x: System.DateTime, y: int) = x.AddDays(1.0)
    static member M2(x: inref<System.DateTime>, y: int) = x.AddDays(2.0)

let res = System.DateTime.Now
let v =  C.M(res)
let v2 =  C.M2(res, 4)
```

<span data-ttu-id="6823e-163">どちらの場合も、`inref<System.DateTime>`を取るオーバーロードではなく、`System.DateTime` を受け取るオーバーロードが解決されます。</span><span class="sxs-lookup"><span data-stu-id="6823e-163">In both cases, the overloads taking `System.DateTime` are resolved rather than the overloads taking `inref<System.DateTime>`.</span></span>

## <a name="byref-like-structs"></a><span data-ttu-id="6823e-164">Byref に似た構造体</span><span class="sxs-lookup"><span data-stu-id="6823e-164">Byref-like structs</span></span>

<span data-ttu-id="6823e-165">`byref`/`inref`/`outref` trio に加えて、`byref`に似たセマンティクスに従うことができる独自の構造体を定義することもできます。</span><span class="sxs-lookup"><span data-stu-id="6823e-165">In addition to the `byref`/`inref`/`outref` trio, you can define your own structs that can adhere to `byref`-like semantics.</span></span> <span data-ttu-id="6823e-166">これは、<xref:System.Runtime.CompilerServices.IsByRefLikeAttribute> 属性を使用して行います。</span><span class="sxs-lookup"><span data-stu-id="6823e-166">This is done with the <xref:System.Runtime.CompilerServices.IsByRefLikeAttribute> attribute:</span></span>

```fsharp
open System
open System.Runtime.CompilerServices

[<IsByRefLike; Struct>]
type S(count1: Span<int>, count2: Span<int>) =
    member x.Count1 = count1
    member x.Count2 = count2
```

<span data-ttu-id="6823e-167">`IsByRefLike` は `Struct`を意味しません。</span><span class="sxs-lookup"><span data-stu-id="6823e-167">`IsByRefLike` does not imply `Struct`.</span></span> <span data-ttu-id="6823e-168">両方とも型に存在する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6823e-168">Both must be present on the type.</span></span>

<span data-ttu-id="6823e-169">のF# "`byref`に似た" 構造体は、スタックバインド値型です。</span><span class="sxs-lookup"><span data-stu-id="6823e-169">A "`byref`-like" struct in F# is a stack-bound value type.</span></span> <span data-ttu-id="6823e-170">マネージヒープに割り当てられることはありません。</span><span class="sxs-lookup"><span data-stu-id="6823e-170">It is never allocated on the managed heap.</span></span> <span data-ttu-id="6823e-171">`byref`のような構造体は、有効期間と非キャプチャに関する厳密なチェックセットによって適用されるため、高パフォーマンスのプログラミングに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="6823e-171">A `byref`-like struct is useful for high-performance programming, as it is enforced with set of strong checks about lifetime and non-capture.</span></span> <span data-ttu-id="6823e-172">規則は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="6823e-172">The rules are:</span></span>

* <span data-ttu-id="6823e-173">これらは、関数パラメーター、メソッドパラメーター、ローカル変数、メソッドが返す値として使用できます。</span><span class="sxs-lookup"><span data-stu-id="6823e-173">They can be used as function parameters, method parameters, local variables, method returns.</span></span>
* <span data-ttu-id="6823e-174">これらは、クラスまたは通常の構造体の静的メンバーまたはインスタンスメンバーにすることはできません。</span><span class="sxs-lookup"><span data-stu-id="6823e-174">They cannot be static or instance members of a class or normal struct.</span></span>
* <span data-ttu-id="6823e-175">これらは、クロージャコンストラクト (`async` メソッドまたはラムダ式) によってキャプチャすることはできません。</span><span class="sxs-lookup"><span data-stu-id="6823e-175">They cannot be captured by any closure construct (`async` methods or lambda expressions).</span></span>
* <span data-ttu-id="6823e-176">これらは、ジェネリックパラメーターとして使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="6823e-176">They cannot be used as a generic parameter.</span></span>

<span data-ttu-id="6823e-177">この最後の点は、 F#入力の型をパラメーター化するジェネリック関数である `|>` のように、パイプラインスタイルのプログラミングにとって非常に重要です。</span><span class="sxs-lookup"><span data-stu-id="6823e-177">This last point is crucial for F# pipeline-style programming, as `|>` is a generic function that parameterizes its input types.</span></span> <span data-ttu-id="6823e-178">この制限は、インラインであるため、将来の `|>` に対して緩和される可能性があり、その本体で非インラインジェネリック関数を呼び出すことはありません。</span><span class="sxs-lookup"><span data-stu-id="6823e-178">This restriction may be relaxed for `|>` in the future, as it is inline and does not make any calls to non-inlined generic functions in its body.</span></span>

<span data-ttu-id="6823e-179">これらのルールでは使用法が非常に厳密に制限されていますが、高パフォーマンスコンピューティングの約束を安全な方法で実現するために、これらのルールが使用されます。</span><span class="sxs-lookup"><span data-stu-id="6823e-179">Although these rules very strongly restrict usage, they do so to fulfill the promise of high-performance computing in a safe manner.</span></span>

## <a name="byref-returns"></a><span data-ttu-id="6823e-180">Byref の戻り値</span><span class="sxs-lookup"><span data-stu-id="6823e-180">Byref returns</span></span>

<span data-ttu-id="6823e-181">関数またはF#メンバーからの Byref 戻り値は、生成および使用できます。</span><span class="sxs-lookup"><span data-stu-id="6823e-181">Byref returns from F# functions or members can be produced and consumed.</span></span> <span data-ttu-id="6823e-182">`byref`を返すメソッドを使用する場合、値は暗黙的に逆参照されます。</span><span class="sxs-lookup"><span data-stu-id="6823e-182">When consuming a `byref`-returning method, the value is implicitly dereferenced.</span></span> <span data-ttu-id="6823e-183">(例:</span><span class="sxs-lookup"><span data-stu-id="6823e-183">For example:</span></span>

```fsharp
let safeSum(bytes: Span<byte>) =
    let mutable sum = 0
    for i in 0 .. bytes.Length - 1 do
        sum <- sum + int bytes.[i]
    sum

let sum = safeSum(mySpanOfBytes)
printfn "%d" sum // 'sum' is of type 'int'
```

<span data-ttu-id="6823e-184">複数のチェーン呼び出しを通じて参照を渡すなど、暗黙的な逆参照を回避するには、`&x` (`x` は値) を使用します。</span><span class="sxs-lookup"><span data-stu-id="6823e-184">To avoid the implicit dereference, such as passing a reference through multiple chained calls, use `&x` (where `x` is the value).</span></span>

<span data-ttu-id="6823e-185">また、戻り `byref`に直接割り当てることもできます。</span><span class="sxs-lookup"><span data-stu-id="6823e-185">You can also directly assign to a return `byref`.</span></span> <span data-ttu-id="6823e-186">次のような (非常に必須の) プログラムを考えてみましょう。</span><span class="sxs-lookup"><span data-stu-id="6823e-186">Consider the following (highly imperative) program:</span></span>

```fsharp
type C() =
    let mutable nums = [| 1; 3; 7; 15; 31; 63; 127; 255; 511; 1023 |]

    override __.ToString() = String.Join(' ', nums)

    member __.FindLargestSmallerThan(target: int) =
        let mutable ctr = nums.Length - 1

        while ctr > 0 && nums.[ctr] >= target do ctr <- ctr - 1

        if ctr > 0 then &nums.[ctr] else &nums.[0]

[<EntryPoint>]
let main argv =
    let c = C()
    printfn "Original sequence: %s" (c.ToString())

    let v = &c.FindLargestSmallerThan 16

    v <- v*2 // Directly assign to the byref return

    printfn "New sequence:      %s" (c.ToString())

    0 // return an integer exit code
```

<span data-ttu-id="6823e-187">出力結果は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="6823e-187">This is the output:</span></span>

```console
Original sequence: 1 3 7 15 31 63 127 255 511 1023
New sequence:      1 3 7 30 31 63 127 255 511 1023
```

## <a name="scoping-for-byrefs"></a><span data-ttu-id="6823e-188">Byref のスコープ</span><span class="sxs-lookup"><span data-stu-id="6823e-188">Scoping for byrefs</span></span>

<span data-ttu-id="6823e-189">`let`バインドされた値は、その参照が定義されているスコープを超えてはなりません。</span><span class="sxs-lookup"><span data-stu-id="6823e-189">A `let`-bound value cannot have its reference exceed the scope in which it was defined.</span></span> <span data-ttu-id="6823e-190">たとえば、次のような場合は許可されません。</span><span class="sxs-lookup"><span data-stu-id="6823e-190">For example, the following is disallowed:</span></span>

```fsharp
let test2 () =
    let x = 12
    &x // Error: 'x' exceeds its defined scope!

let test () =
    let x =
        let y = 1
        &y // Error: `y` exceeds its defined scope!
    ()
```

<span data-ttu-id="6823e-191">これにより、最適化を使用してコンパイルした場合に、によって異なる結果が得られるのを防ぐことができます。</span><span class="sxs-lookup"><span data-stu-id="6823e-191">This prevents you from getting different results depending on if you compile with optimizations on or off.</span></span>
