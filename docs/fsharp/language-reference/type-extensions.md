---
title: 型拡張
description: 型拡張F#を使用して、以前に定義したオブジェクト型に新しいメンバーを追加する方法について説明します。
ms.date: 02/08/2019
ms.openlocfilehash: 502b8636052139b39c800447870c6076a8cd2643
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/30/2019
ms.locfileid: "68630203"
---
# <a name="type-extensions"></a><span data-ttu-id="d28fb-103">型拡張</span><span class="sxs-lookup"><span data-stu-id="d28fb-103">Type extensions</span></span>

<span data-ttu-id="d28fb-104">型拡張機能 (_拡張_とも呼ばれます) は、以前に定義されたオブジェクト型に新しいメンバーを追加できるようにするための機能ファミリです。</span><span class="sxs-lookup"><span data-stu-id="d28fb-104">Type extensions (also called _augmentations_) are a family of features that let you add new members to a previously defined object type.</span></span> <span data-ttu-id="d28fb-105">次の3つの機能があります。</span><span class="sxs-lookup"><span data-stu-id="d28fb-105">The three features are:</span></span>

* <span data-ttu-id="d28fb-106">組み込み型拡張機能</span><span class="sxs-lookup"><span data-stu-id="d28fb-106">Intrinsic type extensions</span></span>
* <span data-ttu-id="d28fb-107">省略可能な型拡張</span><span class="sxs-lookup"><span data-stu-id="d28fb-107">Optional type extensions</span></span>
* <span data-ttu-id="d28fb-108">拡張メソッド</span><span class="sxs-lookup"><span data-stu-id="d28fb-108">Extension methods</span></span>

<span data-ttu-id="d28fb-109">各は異なるシナリオで使用でき、トレードオフも異なります。</span><span class="sxs-lookup"><span data-stu-id="d28fb-109">Each can be used in different scenarios and has different tradeoffs.</span></span>

## <a name="syntax"></a><span data-ttu-id="d28fb-110">構文</span><span class="sxs-lookup"><span data-stu-id="d28fb-110">Syntax</span></span>

```fsharp
// Intrinsic and optional extensions
type typename with
    member self-identifier.member-name =
        body
    ...

// Extension methods
open System.Runtime.CompilerServices

[<Extension>]
type Extensions() =
    [static] member self-identifier.extension-name (ty: typename, [args]) =
        body
    ...
```

## <a name="intrinsic-type-extensions"></a><span data-ttu-id="d28fb-111">組み込み型拡張機能</span><span class="sxs-lookup"><span data-stu-id="d28fb-111">Intrinsic type extensions</span></span>

<span data-ttu-id="d28fb-112">組み込み型拡張は、ユーザー定義型を拡張する型の拡張機能です。</span><span class="sxs-lookup"><span data-stu-id="d28fb-112">An intrinsic type extension is a type extension that extends a user-defined type.</span></span>

<span data-ttu-id="d28fb-113">組み込み型拡張は、拡張する型と同じファイル**と**同じ名前空間またはモジュールで定義されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="d28fb-113">Intrinsic type extensions must be defined in the same file **and** in the same namespace or module as the type they're extending.</span></span> <span data-ttu-id="d28fb-114">その他の定義では、[省略可能な型拡張](type-extensions.md#optional-type-extensions)になります。</span><span class="sxs-lookup"><span data-stu-id="d28fb-114">Any other definition will result in them being [optional type extensions](type-extensions.md#optional-type-extensions).</span></span>

<span data-ttu-id="d28fb-115">組み込み型の拡張機能は、型宣言から機能を分離するために、明確な方法である場合があります。</span><span class="sxs-lookup"><span data-stu-id="d28fb-115">Intrinsic type extensions are sometimes a cleaner way to separate functionality from the type declaration.</span></span> <span data-ttu-id="d28fb-116">次の例は、組み込み型拡張を定義する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="d28fb-116">The following example shows how to define an intrinsic type extension:</span></span>

```fsharp
namespace Example

type Variant =
    | Num of int
    | Str of string
  
module Variant =
    let print v =
        match v with
        | Num n -> printf "Num %d" n
        | Str s -> printf "Str %s" s

// Add a member to Variant as an extension
type Variant with
    member x.Print() = Variant.print x
```

<span data-ttu-id="d28fb-117">型拡張を使用すると、次の各項目を分離できます。</span><span class="sxs-lookup"><span data-stu-id="d28fb-117">Using a type extension allows you to separate each of the following:</span></span>

* <span data-ttu-id="d28fb-118">`Variant`型の宣言</span><span class="sxs-lookup"><span data-stu-id="d28fb-118">The declaration of a `Variant` type</span></span>
* <span data-ttu-id="d28fb-119">"Shape" に`Variant`応じてクラスを印刷する機能</span><span class="sxs-lookup"><span data-stu-id="d28fb-119">Functionality to print the `Variant` class depending on its "shape"</span></span>
* <span data-ttu-id="d28fb-120">印刷機能にオブジェクト形式`.`の表記でアクセスする方法</span><span class="sxs-lookup"><span data-stu-id="d28fb-120">A way to access the printing functionality with object-style `.`-notation</span></span>

<span data-ttu-id="d28fb-121">これは、すべてをの`Variant`メンバーとして定義する方法の1つです。</span><span class="sxs-lookup"><span data-stu-id="d28fb-121">This is an alternative to defining everything as a member on `Variant`.</span></span> <span data-ttu-id="d28fb-122">これは本質的には優れたアプローチではありませんが、状況によっては機能が明確に表示される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="d28fb-122">Although it is not an inherently better approach, it can be a cleaner representation of functionality in some situations.</span></span>

<span data-ttu-id="d28fb-123">組み込み型の拡張は、それが拡張する型のメンバーとしてコンパイルされ、リフレクションによって型が検証されるときに型に表示されます。</span><span class="sxs-lookup"><span data-stu-id="d28fb-123">Intrinsic type extensions are compiled as members of the type they augment, and appear on the type when the type is examined by reflection.</span></span>

## <a name="optional-type-extensions"></a><span data-ttu-id="d28fb-124">省略可能な型拡張</span><span class="sxs-lookup"><span data-stu-id="d28fb-124">Optional type extensions</span></span>

<span data-ttu-id="d28fb-125">省略可能な型拡張は、拡張される型の元のモジュール、名前空間、またはアセンブリの外側に表示される拡張機能です。</span><span class="sxs-lookup"><span data-stu-id="d28fb-125">An optional type extension is an extension that appears outside the original module, namespace, or assembly of the type being extended.</span></span>

<span data-ttu-id="d28fb-126">省略可能な型拡張は、自分で定義していない型を拡張する場合に便利です。</span><span class="sxs-lookup"><span data-stu-id="d28fb-126">Optional type extensions are useful for extending a type that you have not defined yourself.</span></span> <span data-ttu-id="d28fb-127">例:</span><span class="sxs-lookup"><span data-stu-id="d28fb-127">For example:</span></span>

```fsharp
module Extensions

open System.Collections.Generic

type IEnumerable<'T> with
    /// Repeat each element of the sequence n times
    member xs.RepeatElements(n: int) =
        seq {
            for x in xs do
                for i in 1 .. n do
                    yield x
        }
```

<span data-ttu-id="d28fb-128">これで、使用`RepeatElements`しているスコープで`Extensions`モジュールが<xref:System.Collections.Generic.IEnumerable%601>開かれている限り、にアクセスできるようになりました。</span><span class="sxs-lookup"><span data-stu-id="d28fb-128">You can now access `RepeatElements` as if it's a member of <xref:System.Collections.Generic.IEnumerable%601> as long as the `Extensions` module is opened in the scope that you are working in.</span></span>

<span data-ttu-id="d28fb-129">リフレクションによってチェックされる場合、拡張型にはオプションの拡張機能は表示されません。</span><span class="sxs-lookup"><span data-stu-id="d28fb-129">Optional extensions do not appear on the extended type when examined by reflection.</span></span> <span data-ttu-id="d28fb-130">オプションの拡張機能はモジュール内に存在する必要があり、拡張機能を含むモジュールが開いている場合、またはそれ以外の場合はスコープ内にある場合にのみスコープに含まれます。</span><span class="sxs-lookup"><span data-stu-id="d28fb-130">Optional extensions must be in modules, and they're only in scope when the module that contains the extension is open or is otherwise in scope.</span></span>

<span data-ttu-id="d28fb-131">任意拡張のメンバーはコンパイルされると、静的メンバーになります。このメンバーに対する最初のパラメーターとして、オブジェクト インスタンスが暗黙で渡されます。</span><span class="sxs-lookup"><span data-stu-id="d28fb-131">Optional extension members are compiled to static members for which the object instance is passed implicitly as the first parameter.</span></span> <span data-ttu-id="d28fb-132">ただし、これらは、それらが宣言されている方法に従って、インスタンスメンバーまたは静的メンバーであるかのように動作します。</span><span class="sxs-lookup"><span data-stu-id="d28fb-132">However, they act as if they're instance members or static members according to how they're declared.</span></span>

<span data-ttu-id="d28fb-133">オプションの拡張メンバーは、またはC# VB コンシューマーにも表示されません。</span><span class="sxs-lookup"><span data-stu-id="d28fb-133">Optional extension members are also not visible to C# or VB consumers.</span></span> <span data-ttu-id="d28fb-134">他のF#コードでのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="d28fb-134">They can only be consumed in other F# code.</span></span>

## <a name="generic-limitation-of-intrinsic-and-optional-type-extensions"></a><span data-ttu-id="d28fb-135">組み込みおよびオプションの型拡張の一般的な制限</span><span class="sxs-lookup"><span data-stu-id="d28fb-135">Generic limitation of intrinsic and optional type extensions</span></span>

<span data-ttu-id="d28fb-136">型変数が制限されているジェネリック型に対して型拡張を宣言できます。</span><span class="sxs-lookup"><span data-stu-id="d28fb-136">It's possible to declare a type extension on a generic type where the type variable is constrained.</span></span> <span data-ttu-id="d28fb-137">要件は、拡張宣言の制約が宣言された型の制約と一致することです。</span><span class="sxs-lookup"><span data-stu-id="d28fb-137">The requirement is that the constraint of the extension declaration matches the constraint of the declared type.</span></span>

<span data-ttu-id="d28fb-138">ただし、宣言された型と型拡張の間で制約が一致した場合でも、宣言された型よりも型パラメーターに対して異なる要件を課す拡張メンバーの本体によって制約が推論される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="d28fb-138">However, even when constraints are matched between a declared type and a type extension, it's possible for a constraint to be inferred by the body of an extended member that imposes a different requirement on the type parameter than the declared type.</span></span> <span data-ttu-id="d28fb-139">例:</span><span class="sxs-lookup"><span data-stu-id="d28fb-139">For example:</span></span>

```fsharp
open System.Collections.Generic

// NOT POSSIBLE AND FAILS TO COMPILE!
//
// The member 'Sum' has a different requirement on 'T than the type IEnumerable<'T>
type IEnumerable<'T> with
    member this.Sum() = Seq.sum this
```

<span data-ttu-id="d28fb-140">このコードを取得して、オプションの型拡張機能を使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="d28fb-140">There is no way to get this code to work with an optional type extension:</span></span>

* <span data-ttu-id="d28fb-141">そのように、 `Sum`メンバーは、型拡張機能`'T`で`static member get_Zero`定義`static member (+)`されているものとは異なる制約を (および) 持ちます。</span><span class="sxs-lookup"><span data-stu-id="d28fb-141">As is, the `Sum` member has a different constraint on `'T` (`static member get_Zero` and `static member (+)`) than what the type extension defines.</span></span>
* <span data-ttu-id="d28fb-142">と同じ制約を持つように型拡張を`Sum`変更すると、で`IEnumerable<'T>`定義されている制約とは一致しなくなります。</span><span class="sxs-lookup"><span data-stu-id="d28fb-142">Modifying the type extension to have the same constraint as `Sum` will no longer match the defined constraint on `IEnumerable<'T>`.</span></span>
* <span data-ttu-id="d28fb-143">を`member this.Sum` に`member inline this.Sum`変更すると、型制約が一致しないというエラーが表示されます。</span><span class="sxs-lookup"><span data-stu-id="d28fb-143">Changing `member this.Sum` to `member inline this.Sum` will give an error that type constraints are mismatched.</span></span>

<span data-ttu-id="d28fb-144">必要なのは、"スペースで浮動小数点" を使用する静的メソッドであり、型を拡張するかのように表示できます。</span><span class="sxs-lookup"><span data-stu-id="d28fb-144">What is desired are static methods that "float in space" and can be presented as if they're extending a type.</span></span> <span data-ttu-id="d28fb-145">ここで拡張メソッドが必要になります。</span><span class="sxs-lookup"><span data-stu-id="d28fb-145">This is where extension methods become necessary.</span></span>

## <a name="extension-methods"></a><span data-ttu-id="d28fb-146">拡張メソッド</span><span class="sxs-lookup"><span data-stu-id="d28fb-146">Extension methods</span></span>

<span data-ttu-id="d28fb-147">最後に、(「C# スタイル拡張メンバー」とも呼ばれます) の拡張メソッドは、クラスのプロセスのメンバーが静的メソッドとして F# で宣言できます。</span><span class="sxs-lookup"><span data-stu-id="d28fb-147">Finally, extension methods (sometimes called "C# style extension members") can be declared in F# as a static member method on a class.</span></span>

<span data-ttu-id="d28fb-148">拡張メソッドは、型変数を制約するジェネリック型の拡張機能を定義する場合に便利です。</span><span class="sxs-lookup"><span data-stu-id="d28fb-148">Extension methods are useful for when you wish to define extensions on a generic type that will constrain the type variable.</span></span> <span data-ttu-id="d28fb-149">例:</span><span class="sxs-lookup"><span data-stu-id="d28fb-149">For example:</span></span>

```fsharp
namespace Extensions

open System.Runtime.CompilerServices

[<Extension>]
type IEnumerableExtensions() =
    [<Extension>]
    static member inline Sum(xs: IEnumerable<'T>) = Seq.sum xs
```

<span data-ttu-id="d28fb-150">このコードを使用すると、が開かれて`Sum`いるかスコープ<xref:System.Collections.Generic.IEnumerable%601>内にある限り`Extensions` 、がに定義されているかのように表示されます。</span><span class="sxs-lookup"><span data-stu-id="d28fb-150">When used, this code will make it appear as if `Sum` is defined on <xref:System.Collections.Generic.IEnumerable%601>, so long as `Extensions` has been opened or is in scope.</span></span>

## <a name="other-remarks"></a><span data-ttu-id="d28fb-151">その他の解説</span><span class="sxs-lookup"><span data-stu-id="d28fb-151">Other remarks</span></span>

<span data-ttu-id="d28fb-152">型拡張には、次の属性もあります。</span><span class="sxs-lookup"><span data-stu-id="d28fb-152">Type extensions also have the following attributes:</span></span>

* <span data-ttu-id="d28fb-153">アクセス可能なすべての型を拡張できます。</span><span class="sxs-lookup"><span data-stu-id="d28fb-153">Any type that can be accessed can be extended.</span></span>
* <span data-ttu-id="d28fb-154">組み込みおよびオプションの型拡張では、メソッドだけでなく、_任意_のメンバー型を定義できます。</span><span class="sxs-lookup"><span data-stu-id="d28fb-154">Intrinsic and optional type extensions can define _any_ member type, not just methods.</span></span> <span data-ttu-id="d28fb-155">たとえば、拡張機能のプロパティも可能です。</span><span class="sxs-lookup"><span data-stu-id="d28fb-155">So extension properties are also possible, for example.</span></span>
* <span data-ttu-id="d28fb-156">[構文](type-extensions.md#syntax)の `self-identifier` トークンは 、通常のメンバーと同じように、呼び出される型のインスタンスを表します。</span><span class="sxs-lookup"><span data-stu-id="d28fb-156">The `self-identifier` token in the [syntax](type-extensions.md#syntax) represents the instance of the type being invoked, just like ordinary members.</span></span>
* <span data-ttu-id="d28fb-157">拡張メンバーは、静的メンバーまたはインスタンスメンバーにすることができます。</span><span class="sxs-lookup"><span data-stu-id="d28fb-157">Extended members can be static or instance members.</span></span>
* <span data-ttu-id="d28fb-158">型の拡張機能の型変数は、宣言された型の制約と一致する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d28fb-158">Type variables on a type extension must match the constraints of the declared type.</span></span>

<span data-ttu-id="d28fb-159">型拡張機能には、次の制限もあります。</span><span class="sxs-lookup"><span data-stu-id="d28fb-159">The following limitations also exist for type extensions:</span></span>

* <span data-ttu-id="d28fb-160">型拡張は、仮想メソッドまたは抽象メソッドをサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="d28fb-160">Type extensions do not support virtual or abstract methods.</span></span>
* <span data-ttu-id="d28fb-161">型拡張は、拡張としてのオーバーライドメソッドをサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="d28fb-161">Type extensions do not support override methods as augmentations.</span></span>
* <span data-ttu-id="d28fb-162">型拡張は、[静的に解決される型パラメーター](./generics/statically-resolved-type-parameters.md)をサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="d28fb-162">Type extensions do not support [Statically Resolved Type Parameters](./generics/statically-resolved-type-parameters.md).</span></span>
* <span data-ttu-id="d28fb-163">省略可能な型拡張は、拡張としてのコンストラクターをサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="d28fb-163">Optional Type extensions do not support constructors as augmentations.</span></span>
* <span data-ttu-id="d28fb-164">型の拡張子を型の[省略形](type-abbreviations.md)に対して定義することはできません。</span><span class="sxs-lookup"><span data-stu-id="d28fb-164">Type extensions cannot be defined on [type abbreviations](type-abbreviations.md).</span></span>
* <span data-ttu-id="d28fb-165">型拡張は、では`byref<'T>`有効ではありません (ただし、宣言することはできます)。</span><span class="sxs-lookup"><span data-stu-id="d28fb-165">Type extensions are not valid for `byref<'T>` (though they can be declared).</span></span>
* <span data-ttu-id="d28fb-166">型拡張は、属性に対しては有効ではありません (ただし、宣言することはできます)。</span><span class="sxs-lookup"><span data-stu-id="d28fb-166">Type extensions are not valid for attributes (though they can be declared).</span></span>
* <span data-ttu-id="d28fb-167">同じ名前の他のメソッドをオーバー ロードする拡張機能を定義することができますが、F# コンパイラでは、あいまいな呼び出しがある場合は非拡張メソッドを優先します。</span><span class="sxs-lookup"><span data-stu-id="d28fb-167">You can define extensions that overload other methods of the same name, but the F# compiler gives preference to non-extension methods if there is an ambiguous call.</span></span>

<span data-ttu-id="d28fb-168">最後に、1つの型に対して複数の組み込み型拡張が存在する場合は、すべてのメンバーが一意である必要があります。</span><span class="sxs-lookup"><span data-stu-id="d28fb-168">Finally, if multiple intrinsic type extensions exist for one type, all members must be unique.</span></span> <span data-ttu-id="d28fb-169">オプション型拡張の場合は、1 つの型に対する複数の型拡張が存在する場合でも、各メンバーに同じ名前を付けることができます。</span><span class="sxs-lookup"><span data-stu-id="d28fb-169">For optional type extensions, members in different type extensions to the same type can have the same names.</span></span> <span data-ttu-id="d28fb-170">クライアント コードで同じメンバー名が定義されている 2 つの異なるスコープを開いている場合にのみ、あいまいさに対するエラーが発生します。</span><span class="sxs-lookup"><span data-stu-id="d28fb-170">Ambiguity errors occur only if client code opens two different scopes that define the same member names.</span></span>

## <a name="see-also"></a><span data-ttu-id="d28fb-171">関連項目</span><span class="sxs-lookup"><span data-stu-id="d28fb-171">See also</span></span>

- [<span data-ttu-id="d28fb-172">F# 言語リファレンス</span><span class="sxs-lookup"><span data-stu-id="d28fb-172">F# Language Reference</span></span>](index.md)
- [<span data-ttu-id="d28fb-173">メンバー</span><span class="sxs-lookup"><span data-stu-id="d28fb-173">Members</span></span>](./members/index.md)
