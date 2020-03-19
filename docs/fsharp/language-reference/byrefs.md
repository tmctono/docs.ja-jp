---
title: Byrefs
description: 低レベルプログラミングに使用される f# で byref 型と byref 型について説明します。
ms.date: 11/04/2019
ms.openlocfilehash: 527f465ee87fe153a2deae1306b6730531dc4123
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2020
ms.locfileid: "79187048"
---
# <a name="byrefs"></a><span data-ttu-id="b9d33-103">Byrefs</span><span class="sxs-lookup"><span data-stu-id="b9d33-103">Byrefs</span></span>

<span data-ttu-id="b9d33-104">F# には、低レベルプログラミングの領域を扱う主な機能が 2 つ用意されています。</span><span class="sxs-lookup"><span data-stu-id="b9d33-104">F# has two major feature areas that deal in the space of low-level programming:</span></span>

* <span data-ttu-id="b9d33-105">`byref`/マネージ`outref`ポインターである型。 `inref` /</span><span class="sxs-lookup"><span data-stu-id="b9d33-105">The `byref`/`inref`/`outref` types, which are managed pointers.</span></span> <span data-ttu-id="b9d33-106">これらのプログラムには使用法に制限があるため、実行時に無効なプログラムをコンパイルすることはできません。</span><span class="sxs-lookup"><span data-stu-id="b9d33-106">They have restrictions on usage so that you cannot compile a program that is invalid at run time.</span></span>
* <span data-ttu-id="b9d33-107">類似`byref`のセマンティクスとコンパイル時の制限を持つ[構造体](structures.md)である -like 構造体 。 `byref<'T>`</span><span class="sxs-lookup"><span data-stu-id="b9d33-107">A `byref`-like struct, which is a [structure](structures.md) that has similar semantics and the same compile-time restrictions as `byref<'T>`.</span></span> <span data-ttu-id="b9d33-108">その一例<xref:System.Span%601>が です。</span><span class="sxs-lookup"><span data-stu-id="b9d33-108">One example is <xref:System.Span%601>.</span></span>

## <a name="syntax"></a><span data-ttu-id="b9d33-109">構文</span><span class="sxs-lookup"><span data-stu-id="b9d33-109">Syntax</span></span>

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

## <a name="byref-inref-and-outref"></a><span data-ttu-id="b9d33-110">バイレフ、インレフ、およびアウトレフ</span><span class="sxs-lookup"><span data-stu-id="b9d33-110">Byref, inref, and outref</span></span>

<span data-ttu-id="b9d33-111">の 3 つの`byref`形式があります。</span><span class="sxs-lookup"><span data-stu-id="b9d33-111">There are three forms of `byref`:</span></span>

* <span data-ttu-id="b9d33-112">`inref<'T>`基になる値を読み取るためのマネージ ポインター。</span><span class="sxs-lookup"><span data-stu-id="b9d33-112">`inref<'T>`, a managed pointer for reading the underlying value.</span></span>
* <span data-ttu-id="b9d33-113">`outref<'T>`の基になる値に書き込むマネージ ポインター。</span><span class="sxs-lookup"><span data-stu-id="b9d33-113">`outref<'T>`, a managed pointer for writing to the underlying value.</span></span>
* <span data-ttu-id="b9d33-114">`byref<'T>`の読み取りと書き込みのマネージ ポインター。</span><span class="sxs-lookup"><span data-stu-id="b9d33-114">`byref<'T>`, a managed pointer for reading and writing the underlying value.</span></span>

<span data-ttu-id="b9d33-115">が`byref<'T>`期待されるところで`inref<'T>`渡すことができます。</span><span class="sxs-lookup"><span data-stu-id="b9d33-115">A `byref<'T>` can be passed where an `inref<'T>` is expected.</span></span> <span data-ttu-id="b9d33-116">同様に、`byref<'T>`が必要な場所`outref<'T>`に a を渡すことができます。</span><span class="sxs-lookup"><span data-stu-id="b9d33-116">Similarly, a `byref<'T>` can be passed where an `outref<'T>` is expected.</span></span>

## <a name="using-byrefs"></a><span data-ttu-id="b9d33-117">参照の使用</span><span class="sxs-lookup"><span data-stu-id="b9d33-117">Using byrefs</span></span>

<span data-ttu-id="b9d33-118">を`inref<'T>`使用するには、 を使用してポインター値を取得`&`する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b9d33-118">To use a `inref<'T>`, you need to get a pointer value with `&`:</span></span>

```fsharp
open System

let f (dt: inref<DateTime>) =
    printfn "Now: %s" (dt.ToString())

let usage =
    let dt = DateTime.Now
    f &dt // Pass a pointer to 'dt'
```

<span data-ttu-id="b9d33-119">または を使用してポインターに書き込むには、 へのポインターを取得する値を`mutable`作成する必要もあります。 `byref<'T>` `outref<'T>`</span><span class="sxs-lookup"><span data-stu-id="b9d33-119">To write to the pointer by using an `outref<'T>` or `byref<'T>`, you must also make the value you grab a pointer to `mutable`.</span></span>

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

<span data-ttu-id="b9d33-120">ポインタを読む代わりに書くだけの場合は、`outref<'T>``byref<'T>`の代わりに を使用することを検討してください。</span><span class="sxs-lookup"><span data-stu-id="b9d33-120">If you are only writing the pointer instead of reading it, consider using `outref<'T>` instead of `byref<'T>`.</span></span>

### <a name="inref-semantics"></a><span data-ttu-id="b9d33-121">インレフセマンティクス</span><span class="sxs-lookup"><span data-stu-id="b9d33-121">Inref semantics</span></span>

<span data-ttu-id="b9d33-122">次のコードについて考えてみましょう。</span><span class="sxs-lookup"><span data-stu-id="b9d33-122">Consider the following code:</span></span>

```fsharp
let f (x: inref<SomeStruct>) = x.SomeField
```

<span data-ttu-id="b9d33-123">意味的には、これは次の意味を意味します。</span><span class="sxs-lookup"><span data-stu-id="b9d33-123">Semantically, this means the following:</span></span>

* <span data-ttu-id="b9d33-124">ポインターのホルダーは`x`、値の読み取りにのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="b9d33-124">The holder of the `x` pointer may only use it to read the value.</span></span>
* <span data-ttu-id="b9d33-125">内`struct``SomeStruct`にネストされたフィールドに取得されたポインタには、 `inref<_>`type が与えられます。</span><span class="sxs-lookup"><span data-stu-id="b9d33-125">Any pointer acquired to `struct` fields nested within `SomeStruct` are given type `inref<_>`.</span></span>

<span data-ttu-id="b9d33-126">次のことも当てはまります。</span><span class="sxs-lookup"><span data-stu-id="b9d33-126">The following is also true:</span></span>

* <span data-ttu-id="b9d33-127">他のスレッドまたはエイリアスに対する`x`書き込みアクセス権が与えないことを意味するわけではありません。</span><span class="sxs-lookup"><span data-stu-id="b9d33-127">There is no implication that other threads or aliases do not have write access to `x`.</span></span>
* <span data-ttu-id="b9d33-128">あるというのは、`SomeStruct`不変の`x`意味はありません`inref`。</span><span class="sxs-lookup"><span data-stu-id="b9d33-128">There is no implication that `SomeStruct` is immutable by virtue of `x` being an `inref`.</span></span>

<span data-ttu-id="b9d33-129">ただし、不**変の**F# 値型の`this`場合、ポインターは`inref`.</span><span class="sxs-lookup"><span data-stu-id="b9d33-129">However, for F# value types that **are** immutable, the `this` pointer is inferred to be an `inref`.</span></span>

<span data-ttu-id="b9d33-130">これらの規則はすべて、`inref`ポインタの所有者が、指しているメモリの直接の内容を変更しないことを意味します。</span><span class="sxs-lookup"><span data-stu-id="b9d33-130">All of these rules together mean that the holder of an `inref` pointer may not modify the immediate contents of the memory being pointed to.</span></span>

### <a name="outref-semantics"></a><span data-ttu-id="b9d33-131">アウトレフセマンティクス</span><span class="sxs-lookup"><span data-stu-id="b9d33-131">Outref semantics</span></span>

<span data-ttu-id="b9d33-132">の目的`outref<'T>`は、ポインタの書き込みのみを指示することです。</span><span class="sxs-lookup"><span data-stu-id="b9d33-132">The purpose of `outref<'T>` is to indicate that the pointer should only be written to.</span></span> <span data-ttu-id="b9d33-133">予期せず、`outref<'T>`その名前にもかかわらず、基になる値を読み取ることができます。</span><span class="sxs-lookup"><span data-stu-id="b9d33-133">Unexpectedly, `outref<'T>` permits reading the underlying value despite its name.</span></span> <span data-ttu-id="b9d33-134">これは互換性を目的としています。</span><span class="sxs-lookup"><span data-stu-id="b9d33-134">This is for compatibility purposes.</span></span> <span data-ttu-id="b9d33-135">意味的には`outref<'T>`、 と`byref<'T>`同じではありません。</span><span class="sxs-lookup"><span data-stu-id="b9d33-135">Semantically, `outref<'T>` is no different than `byref<'T>`.</span></span>

### <a name="interop-with-c"></a><span data-ttu-id="b9d33-136">C との相互運用性\#</span><span class="sxs-lookup"><span data-stu-id="b9d33-136">Interop with C\#</span></span>

<span data-ttu-id="b9d33-137">C# では`in ref`、`out ref`および キーワードをサポート`ref`し、さらに、リターンもサポートします。</span><span class="sxs-lookup"><span data-stu-id="b9d33-137">C# supports the `in ref` and `out ref` keywords, in addition to `ref` returns.</span></span> <span data-ttu-id="b9d33-138">次の表は、F# が C# の出力を解釈する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="b9d33-138">The following table shows how F# interprets what C# emits:</span></span>

|<span data-ttu-id="b9d33-139">C# コンストラクト</span><span class="sxs-lookup"><span data-stu-id="b9d33-139">C# construct</span></span>|<span data-ttu-id="b9d33-140">F# の推論</span><span class="sxs-lookup"><span data-stu-id="b9d33-140">F# infers</span></span>|
|------------|---------|
|<span data-ttu-id="b9d33-141">`ref`戻り値</span><span class="sxs-lookup"><span data-stu-id="b9d33-141">`ref` return value</span></span>|`outref<'T>`|
|<span data-ttu-id="b9d33-142">`ref readonly`戻り値</span><span class="sxs-lookup"><span data-stu-id="b9d33-142">`ref readonly` return value</span></span>|`inref<'T>`|
|<span data-ttu-id="b9d33-143">`in ref` パラメーター</span><span class="sxs-lookup"><span data-stu-id="b9d33-143">`in ref` parameter</span></span>|`inref<'T>`|
|<span data-ttu-id="b9d33-144">`out ref` パラメーター</span><span class="sxs-lookup"><span data-stu-id="b9d33-144">`out ref` parameter</span></span>|`outref<'T>`|

<span data-ttu-id="b9d33-145">次の表は、F# の出力を示しています。</span><span class="sxs-lookup"><span data-stu-id="b9d33-145">The following table shows what F# emits:</span></span>

|<span data-ttu-id="b9d33-146">F# コンストラクト</span><span class="sxs-lookup"><span data-stu-id="b9d33-146">F# construct</span></span>|<span data-ttu-id="b9d33-147">放出されたコンストラクト</span><span class="sxs-lookup"><span data-stu-id="b9d33-147">Emitted construct</span></span>|
|------------|-----------------|
|<span data-ttu-id="b9d33-148">`inref<'T>` 引数</span><span class="sxs-lookup"><span data-stu-id="b9d33-148">`inref<'T>` argument</span></span>|<span data-ttu-id="b9d33-149">`[In]`引数の属性</span><span class="sxs-lookup"><span data-stu-id="b9d33-149">`[In]` attribute on argument</span></span>|
|<span data-ttu-id="b9d33-150">`inref<'T>`返す</span><span class="sxs-lookup"><span data-stu-id="b9d33-150">`inref<'T>` return</span></span>|<span data-ttu-id="b9d33-151">`modreq`値の属性</span><span class="sxs-lookup"><span data-stu-id="b9d33-151">`modreq` attribute on value</span></span>|
|<span data-ttu-id="b9d33-152">`inref<'T>`抽象的なスロットまたは実装で</span><span class="sxs-lookup"><span data-stu-id="b9d33-152">`inref<'T>` in abstract slot or implementation</span></span>|<span data-ttu-id="b9d33-153">`modreq`引数または戻り値の場合</span><span class="sxs-lookup"><span data-stu-id="b9d33-153">`modreq` on argument or return</span></span>|
|<span data-ttu-id="b9d33-154">`outref<'T>` 引数</span><span class="sxs-lookup"><span data-stu-id="b9d33-154">`outref<'T>` argument</span></span>|<span data-ttu-id="b9d33-155">`[Out]`引数の属性</span><span class="sxs-lookup"><span data-stu-id="b9d33-155">`[Out]` attribute on argument</span></span>|

### <a name="type-inference-and-overloading-rules"></a><span data-ttu-id="b9d33-156">型の推論とオーバーロードの規則</span><span class="sxs-lookup"><span data-stu-id="b9d33-156">Type inference and overloading rules</span></span>

<span data-ttu-id="b9d33-157">型`inref<'T>`は、次の場合に F# コンパイラによって推論されます。</span><span class="sxs-lookup"><span data-stu-id="b9d33-157">An `inref<'T>` type is inferred by the F# compiler in the following cases:</span></span>

1. <span data-ttu-id="b9d33-158">属性を持つ .NET パラメータまたは`IsReadOnly`戻り値の型。</span><span class="sxs-lookup"><span data-stu-id="b9d33-158">A .NET parameter or return type that has an `IsReadOnly` attribute.</span></span>
2. <span data-ttu-id="b9d33-159">変更`this`可能なフィールドを持たない構造体型のポインター。</span><span class="sxs-lookup"><span data-stu-id="b9d33-159">The `this` pointer on a struct type that has no mutable fields.</span></span>
3. <span data-ttu-id="b9d33-160">別`inref<_>`のポインターから派生したメモリ位置のアドレス。</span><span class="sxs-lookup"><span data-stu-id="b9d33-160">The address of a memory location derived from another `inref<_>` pointer.</span></span>

<span data-ttu-id="b9d33-161">の暗黙のアドレスを`inref`取る場合、型の引数を持つオーバーロードは`SomeType`、 type の引数を持つオーバーロード`inref<SomeType>`より優先されます。</span><span class="sxs-lookup"><span data-stu-id="b9d33-161">When an implicit address of an `inref` is being taken, an overload with an argument of type `SomeType` is preferred to an overload with an argument of type `inref<SomeType>`.</span></span> <span data-ttu-id="b9d33-162">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="b9d33-162">For example:</span></span>

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

<span data-ttu-id="b9d33-163">どちらの場合も、オーバーロードを取るのではなく`System.DateTime`、オーバーロードを取る代わりに、`inref<System.DateTime>`取るオーバーロードが解決されます。</span><span class="sxs-lookup"><span data-stu-id="b9d33-163">In both cases, the overloads taking `System.DateTime` are resolved rather than the overloads taking `inref<System.DateTime>`.</span></span>

## <a name="byref-like-structs"></a><span data-ttu-id="b9d33-164">バイレフのような構造体</span><span class="sxs-lookup"><span data-stu-id="b9d33-164">Byref-like structs</span></span>

<span data-ttu-id="b9d33-165">`byref`/`inref`トリオ/に`outref`加えて、-like セマンティクスに従うことができる独自の構造体を`byref`定義できます。</span><span class="sxs-lookup"><span data-stu-id="b9d33-165">In addition to the `byref`/`inref`/`outref` trio, you can define your own structs that can adhere to `byref`-like semantics.</span></span> <span data-ttu-id="b9d33-166">これは<xref:System.Runtime.CompilerServices.IsByRefLikeAttribute>属性で行われます。</span><span class="sxs-lookup"><span data-stu-id="b9d33-166">This is done with the <xref:System.Runtime.CompilerServices.IsByRefLikeAttribute> attribute:</span></span>

```fsharp
open System
open System.Runtime.CompilerServices

[<IsByRefLike; Struct>]
type S(count1: Span<int>, count2: Span<int>) =
    member x.Count1 = count1
    member x.Count2 = count2
```

<span data-ttu-id="b9d33-167">`IsByRefLike`は を`Struct`意味しません。</span><span class="sxs-lookup"><span data-stu-id="b9d33-167">`IsByRefLike` does not imply `Struct`.</span></span> <span data-ttu-id="b9d33-168">両方とも型に存在する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b9d33-168">Both must be present on the type.</span></span>

<span data-ttu-id="b9d33-169">F#`byref`の "-like" 構造体は、スタックにバインドされた値型です。</span><span class="sxs-lookup"><span data-stu-id="b9d33-169">A "`byref`-like" struct in F# is a stack-bound value type.</span></span> <span data-ttu-id="b9d33-170">マネージ ヒープには割り当てが行きまとい。</span><span class="sxs-lookup"><span data-stu-id="b9d33-170">It is never allocated on the managed heap.</span></span> <span data-ttu-id="b9d33-171">`byref`-like 構造体は、有効期間と非キャプチャに関する強力なチェックのセットで実施される、高性能プログラミングに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="b9d33-171">A `byref`-like struct is useful for high-performance programming, as it is enforced with set of strong checks about lifetime and non-capture.</span></span> <span data-ttu-id="b9d33-172">ルールは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="b9d33-172">The rules are:</span></span>

* <span data-ttu-id="b9d33-173">関数パラメーター、メソッドパラメーター、ローカル変数、メソッドの戻り値として使用できます。</span><span class="sxs-lookup"><span data-stu-id="b9d33-173">They can be used as function parameters, method parameters, local variables, method returns.</span></span>
* <span data-ttu-id="b9d33-174">クラスの静的メンバーまたはインスタンス メンバー、または通常の構造体にはできません。</span><span class="sxs-lookup"><span data-stu-id="b9d33-174">They cannot be static or instance members of a class or normal struct.</span></span>
* <span data-ttu-id="b9d33-175">これらの関数は、どのクロージャ構造`async`(メソッドまたはラムダ式) でもキャプチャできません。</span><span class="sxs-lookup"><span data-stu-id="b9d33-175">They cannot be captured by any closure construct (`async` methods or lambda expressions).</span></span>
* <span data-ttu-id="b9d33-176">ジェネリック パラメーターとして使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="b9d33-176">They cannot be used as a generic parameter.</span></span>

<span data-ttu-id="b9d33-177">この最後のポイントは、F# パイプライン スタイルのプログラミングでは`|>`重要です。</span><span class="sxs-lookup"><span data-stu-id="b9d33-177">This last point is crucial for F# pipeline-style programming, as `|>` is a generic function that parameterizes its input types.</span></span> <span data-ttu-id="b9d33-178">この制限は、インラインであり`|>`、その本体のインライン化されていないジェネリック関数を呼び出さないため、将来的には緩和される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="b9d33-178">This restriction may be relaxed for `|>` in the future, as it is inline and does not make any calls to non-inlined generic functions in its body.</span></span>

<span data-ttu-id="b9d33-179">これらの規則は使用を強く制限しますが、安全な方法で高性能コンピューティングの約束を果たすために行います。</span><span class="sxs-lookup"><span data-stu-id="b9d33-179">Although these rules strongly restrict usage, they do so to fulfill the promise of high-performance computing in a safe manner.</span></span>

## <a name="byref-returns"></a><span data-ttu-id="b9d33-180">バイレフが戻る</span><span class="sxs-lookup"><span data-stu-id="b9d33-180">Byref returns</span></span>

<span data-ttu-id="b9d33-181">F# 関数またはメンバーからの Byref 戻り値を生成して使用できます。</span><span class="sxs-lookup"><span data-stu-id="b9d33-181">Byref returns from F# functions or members can be produced and consumed.</span></span> <span data-ttu-id="b9d33-182">戻り値`byref`を使用する場合、値は暗黙的に逆参照されます。</span><span class="sxs-lookup"><span data-stu-id="b9d33-182">When consuming a `byref`-returning method, the value is implicitly dereferenced.</span></span> <span data-ttu-id="b9d33-183">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="b9d33-183">For example:</span></span>

```fsharp
let squareAndPrint (data : byref<int>) =
    let squared = data*data    // data is implicitly dereferenced
    printfn "%d" squared
```

<span data-ttu-id="b9d33-184">値 byref を返すためには、値を含む変数は現在のスコープよりも長く存在する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b9d33-184">To return a value byref, the variable that contains the value must live longer than the current scope.</span></span>
<span data-ttu-id="b9d33-185">また、byref を返すために`&value`は、使用します (値は現在のスコープよりも長く存在する変数です)。</span><span class="sxs-lookup"><span data-stu-id="b9d33-185">Also, to return byref, use `&value` (where value is a variable that lives longer than the current scope).</span></span>

```fsharp
let mutable sum = 0
let safeSum (bytes: Span<byte>) =
    for i in 0 .. bytes.Length - 1 do
        sum <- sum + int bytes.[i]
    &sum  // sum lives longer than the scope of this function.
```

<span data-ttu-id="b9d33-186">複数の連鎖呼び出しを通じて参照を渡すなど、暗黙的な逆`&x`参照を`x`回避するには、(値は場所) を使用します。</span><span class="sxs-lookup"><span data-stu-id="b9d33-186">To avoid the implicit dereference, such as passing a reference through multiple chained calls, use `&x` (where `x` is the value).</span></span>

<span data-ttu-id="b9d33-187">また、直接戻り . `byref`</span><span class="sxs-lookup"><span data-stu-id="b9d33-187">You can also directly assign to a return `byref`.</span></span> <span data-ttu-id="b9d33-188">次の (非常に命令的な) プログラムを検討してください。</span><span class="sxs-lookup"><span data-stu-id="b9d33-188">Consider the following (highly imperative) program:</span></span>

```fsharp
type C() =
    let mutable nums = [| 1; 3; 7; 15; 31; 63; 127; 255; 511; 1023 |]

    override _.ToString() = String.Join(' ', nums)

    member _.FindLargestSmallerThan(target: int) =
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

<span data-ttu-id="b9d33-189">出力結果は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="b9d33-189">This is the output:</span></span>

```console
Original sequence: 1 3 7 15 31 63 127 255 511 1023
New sequence:      1 3 7 30 31 63 127 255 511 1023
```

## <a name="scoping-for-byrefs"></a><span data-ttu-id="b9d33-190">バイ参照のスコープ指定</span><span class="sxs-lookup"><span data-stu-id="b9d33-190">Scoping for byrefs</span></span>

<span data-ttu-id="b9d33-191">バインド`let`された値は、その参照が定義されているスコープを超えることはできません。</span><span class="sxs-lookup"><span data-stu-id="b9d33-191">A `let`-bound value cannot have its reference exceed the scope in which it was defined.</span></span> <span data-ttu-id="b9d33-192">たとえば、次の項目は許可されません。</span><span class="sxs-lookup"><span data-stu-id="b9d33-192">For example, the following is disallowed:</span></span>

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

<span data-ttu-id="b9d33-193">これにより、最適化を使用してコンパイルするかどうかによって、異なる結果が得られるのを防ぐことができます。</span><span class="sxs-lookup"><span data-stu-id="b9d33-193">This prevents you from getting different results depending on if you compile with optimizations or not.</span></span>
