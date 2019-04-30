---
title: 型拡張
description: 学習方法F#型の拡張機能により、定義済みのオブジェクト型に新しいメンバーを追加します。
ms.date: 02/08/2019
ms.openlocfilehash: 69fb3b771b5334c5771f2ac75341b38c1dad5b90
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61982606"
---
# <a name="type-extensions"></a><span data-ttu-id="96823-103">型の拡張機能</span><span class="sxs-lookup"><span data-stu-id="96823-103">Type extensions</span></span>

<span data-ttu-id="96823-104">拡張機能を入力 (とも呼ばれる_拡張_) は、以前に定義されたオブジェクト型に新しいメンバーを追加する機能のファミリです。</span><span class="sxs-lookup"><span data-stu-id="96823-104">Type extensions (also called _augmentations_) are a family of features that let you add new members to a previously defined object type.</span></span> <span data-ttu-id="96823-105">3 つの機能は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="96823-105">The three features are:</span></span>

* <span data-ttu-id="96823-106">組み込み型拡張</span><span class="sxs-lookup"><span data-stu-id="96823-106">Intrinsic type extensions</span></span>
* <span data-ttu-id="96823-107">省略可能な型の拡張機能</span><span class="sxs-lookup"><span data-stu-id="96823-107">Optional type extensions</span></span>
* <span data-ttu-id="96823-108">拡張メソッド</span><span class="sxs-lookup"><span data-stu-id="96823-108">Extension methods</span></span>

<span data-ttu-id="96823-109">それぞれ異なるシナリオで使用できるあり、さまざまなトレードオフです。</span><span class="sxs-lookup"><span data-stu-id="96823-109">Each can be used in different scenarios and has different tradeoffs.</span></span>

## <a name="syntax"></a><span data-ttu-id="96823-110">構文</span><span class="sxs-lookup"><span data-stu-id="96823-110">Syntax</span></span>

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

## <a name="intrinsic-type-extensions"></a><span data-ttu-id="96823-111">組み込み型拡張</span><span class="sxs-lookup"><span data-stu-id="96823-111">Intrinsic type extensions</span></span>

<span data-ttu-id="96823-112">組み込み型拡張機能とは、ユーザー定義型を拡張する型の拡張機能です。</span><span class="sxs-lookup"><span data-stu-id="96823-112">An intrinsic type extension is a type extension that extends a user-defined type.</span></span>

<span data-ttu-id="96823-113">組み込み型拡張を同じファイルで定義する必要があります**と**で同じ名前空間またはモジュールを展開している、型として。</span><span class="sxs-lookup"><span data-stu-id="96823-113">Intrinsic type extensions must be defined in the same file **and** in the same namespace or module as the type they're extending.</span></span> <span data-ttu-id="96823-114">その他の任意の定義が発生している[オプション型拡張](type-extensions.md#optional-type-extensions)。</span><span class="sxs-lookup"><span data-stu-id="96823-114">Any other definition will result in them being [optional type extensions](type-extensions.md#optional-type-extensions).</span></span>

<span data-ttu-id="96823-115">組み込み型拡張機能は、機能型の宣言から分離する使うがよい場合があります。</span><span class="sxs-lookup"><span data-stu-id="96823-115">Intrinsic type extensions are sometimes a cleaner way to separate functionality from the type declaration.</span></span> <span data-ttu-id="96823-116">次の例では、組み込み型拡張機能を定義する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="96823-116">The following example shows how to define an intrinsic type extension:</span></span>

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

<span data-ttu-id="96823-117">型拡張機能を使用すると、それぞれを次のことができます。</span><span class="sxs-lookup"><span data-stu-id="96823-117">Using a type extension allows you to separate each of the following:</span></span>

* <span data-ttu-id="96823-118">宣言を`Variant`型</span><span class="sxs-lookup"><span data-stu-id="96823-118">The declaration of a `Variant` type</span></span>
* <span data-ttu-id="96823-119">印刷する機能、`Variant`の「形状」によってクラス</span><span class="sxs-lookup"><span data-stu-id="96823-119">Functionality to print the `Variant` class depending on its "shape"</span></span>
* <span data-ttu-id="96823-120">オブジェクト スタイルの印刷機能にアクセスする手段`.`の表記</span><span class="sxs-lookup"><span data-stu-id="96823-120">A way to access the printing functionality with object-style `.`-notation</span></span>

<span data-ttu-id="96823-121">これの代わりにすべてのメンバーとして定義するのには、`Variant`します。</span><span class="sxs-lookup"><span data-stu-id="96823-121">This is an alternative to defining everything as a member on `Variant`.</span></span> <span data-ttu-id="96823-122">本質的に優れたアプローチではありませんが、一部の状況で機能のより明確な表現になります。</span><span class="sxs-lookup"><span data-stu-id="96823-122">Although it is not an inherently better approach, it can be a cleaner representation of functionality in some situations.</span></span>

<span data-ttu-id="96823-123">組み込み型拡張機能が強化され、型がリフレクションによって調べられると、型に表示されますが、型のメンバーとしてコンパイルされます。</span><span class="sxs-lookup"><span data-stu-id="96823-123">Intrinsic type extensions are compiled as members of the type they augment, and appear on the type when the type is examined by reflection.</span></span>

## <a name="optional-type-extensions"></a><span data-ttu-id="96823-124">省略可能な型の拡張機能</span><span class="sxs-lookup"><span data-stu-id="96823-124">Optional type extensions</span></span>

<span data-ttu-id="96823-125">省略可能な型の拡張機能は、元のモジュール、名前空間、または拡張する型のアセンブリの外側に表示される拡張機能です。</span><span class="sxs-lookup"><span data-stu-id="96823-125">An optional type extension is an extension that appears outside the original module, namespace, or assembly of the type being extended.</span></span>

<span data-ttu-id="96823-126">省略可能な型の拡張機能は、自分で定義していない種類の拡張に役立ちます。</span><span class="sxs-lookup"><span data-stu-id="96823-126">Optional type extensions are useful for extending a type that you have not defined yourself.</span></span> <span data-ttu-id="96823-127">例:</span><span class="sxs-lookup"><span data-stu-id="96823-127">For example:</span></span>

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

<span data-ttu-id="96823-128">今すぐアクセスすることができます`RepeatElements`のメンバーである場合、<xref:System.Collections.Generic.IEnumerable%601>限り、`Extensions`モジュールはで作業しているスコープで開かれます。</span><span class="sxs-lookup"><span data-stu-id="96823-128">You can now access `RepeatElements` as if it's a member of <xref:System.Collections.Generic.IEnumerable%601> as long as the `Extensions` module is opened in the scope that you are working in.</span></span>

<span data-ttu-id="96823-129">省略可能な拡張機能は、リフレクションして調べる場合は、拡張型には表示されません。</span><span class="sxs-lookup"><span data-stu-id="96823-129">Optional extensions do not appear on the extended type when examined by reflection.</span></span> <span data-ttu-id="96823-130">省略可能な拡張機能は、モジュールである必要がありますあり、スコープ内でのみ、拡張機能を含むモジュールが開いているか、それ以外の場合は、スコープ内で場合です。</span><span class="sxs-lookup"><span data-stu-id="96823-130">Optional extensions must be in modules, and they're only in scope when the module that contains the extension is open or is otherwise in scope.</span></span>

<span data-ttu-id="96823-131">任意拡張のメンバーはコンパイルされると、静的メンバーになります。このメンバーに対する最初のパラメーターとして、オブジェクト インスタンスが暗黙で渡されます。</span><span class="sxs-lookup"><span data-stu-id="96823-131">Optional extension members are compiled to static members for which the object instance is passed implicitly as the first parameter.</span></span> <span data-ttu-id="96823-132">ただし、インスタンス メンバーまたはそれらの宣言方法に従って、静的メンバーである場合に機能します。</span><span class="sxs-lookup"><span data-stu-id="96823-132">However, they act as if they're instance members or static members according to how they're declared.</span></span>

<span data-ttu-id="96823-133">省略可能な拡張メンバーもに表示されないC#または VB のコンシューマーです。</span><span class="sxs-lookup"><span data-stu-id="96823-133">Optional extension members are also not visible to C# or VB consumers.</span></span> <span data-ttu-id="96823-134">他でのみ利用F#コード。</span><span class="sxs-lookup"><span data-stu-id="96823-134">They can only be consumed in other F# code.</span></span>

## <a name="generic-limitation-of-intrinsic-and-optional-type-extensions"></a><span data-ttu-id="96823-135">組み込みと省略可能な型の拡張機能の一般的な制限</span><span class="sxs-lookup"><span data-stu-id="96823-135">Generic limitation of intrinsic and optional type extensions</span></span>

<span data-ttu-id="96823-136">型の変数が制限されるジェネリック型の型の拡張機能を宣言することになります。</span><span class="sxs-lookup"><span data-stu-id="96823-136">It's possible to declare a type extension on a generic type where the type variable is constrained.</span></span> <span data-ttu-id="96823-137">要件は、拡張機能の宣言の制約が宣言された型の制約と一致することです。</span><span class="sxs-lookup"><span data-stu-id="96823-137">The requirement is that the constraint of the extension declaration matches the constraint of the declared type.</span></span>

<span data-ttu-id="96823-138">ただし、宣言された型と型の拡張機能の間の制約に一致した場合でも、宣言された型よりも、型パラメーターに異なる要件を適用する拡張メンバーの本文で推測に、制約の可能なは。</span><span class="sxs-lookup"><span data-stu-id="96823-138">However, even when constraints are matched between a declared type and a type extension, it's possible for a constraint to be inferred by the body of an extended member that imposes a different requirement on the type parameter than the declared type.</span></span> <span data-ttu-id="96823-139">例:</span><span class="sxs-lookup"><span data-stu-id="96823-139">For example:</span></span>

```fsharp
open System.Collections.Generic

// NOT POSSIBLE AND FAILS TO COMPILE!
//
// The member 'Sum' has a different requirement on 'T than the type IEnumerable<'T>
type IEnumerable<'T> with
    member this.Sum() = Seq.sum this
```

<span data-ttu-id="96823-140">省略可能な型の拡張機能を使用するには、このコードを取得する方法はありません。</span><span class="sxs-lookup"><span data-stu-id="96823-140">There is no way to get this code to work with an optional type extension:</span></span>

* <span data-ttu-id="96823-141">`Sum`メンバーは、さまざまな制約に`'T`(`static member get_Zero`と`static member (+)`) よりの種類の拡張子で定義されています。</span><span class="sxs-lookup"><span data-stu-id="96823-141">As is, the `Sum` member has a different constraint on `'T` (`static member get_Zero` and `static member (+)`) than what the type extension defines.</span></span>
* <span data-ttu-id="96823-142">変更の種類の拡張子として同じ制約が`Sum`で定義された制約に一致が不要になった`IEnumerable<'T>`します。</span><span class="sxs-lookup"><span data-stu-id="96823-142">Modifying the type extension to have the same constraint as `Sum` will no longer match the defined constraint on `IEnumerable<'T>`.</span></span>
* <span data-ttu-id="96823-143">変更する`member this.Sum`に`member inline this.Sum`はエラーの種類の制約が一致しないことになります。</span><span class="sxs-lookup"><span data-stu-id="96823-143">Changing `member this.Sum` to `member inline this.Sum` will give an error that type constraints are mismatched.</span></span>

<span data-ttu-id="96823-144">何が必要なは、"領域で float"と、これらの種類の拡張しているかのように表示されることができますを静的メソッドです。</span><span class="sxs-lookup"><span data-stu-id="96823-144">What is desired are static methods that "float in space" and can be presented as if they're extending a type.</span></span> <span data-ttu-id="96823-145">これは、拡張メソッドが必要になります。</span><span class="sxs-lookup"><span data-stu-id="96823-145">This is where extension methods become necessary.</span></span>

## <a name="extension-methods"></a><span data-ttu-id="96823-146">拡張メソッド</span><span class="sxs-lookup"><span data-stu-id="96823-146">Extension methods</span></span>

<span data-ttu-id="96823-147">最後に、(「C# スタイル拡張メンバー」とも呼ばれます) の拡張メソッドは、クラスのプロセスのメンバーが静的メソッドとして F# で宣言できます。</span><span class="sxs-lookup"><span data-stu-id="96823-147">Finally, extension methods (sometimes called "C# style extension members") can be declared in F# as a static member method on a class.</span></span>

<span data-ttu-id="96823-148">拡張メソッドは、型の変数を制約するジェネリック型で拡張を定義するときに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="96823-148">Extension methods are useful for when you wish to define extensions on a generic type that will constrain the type variable.</span></span> <span data-ttu-id="96823-149">例:</span><span class="sxs-lookup"><span data-stu-id="96823-149">For example:</span></span>

```fsharp
namespace Extensions

open System.Runtime.CompilerServices

[<Extension>]
type IEnumerableExtensions() =
    [<Extension>]
    static member inline Sum(xs: IEnumerable<'T>) = Seq.sum xs
```

<span data-ttu-id="96823-150">使用すると、このコードが表示されるようにまるで`Sum`で定義された<xref:System.Collections.Generic.IEnumerable%601>限り、`Extensions`が開かれているかがスコープ内にします。</span><span class="sxs-lookup"><span data-stu-id="96823-150">When used, this code will make it appear as if `Sum` is defined on <xref:System.Collections.Generic.IEnumerable%601>, so long as `Extensions` has been opened or is in scope.</span></span>

## <a name="other-remarks"></a><span data-ttu-id="96823-151">その他のコメント</span><span class="sxs-lookup"><span data-stu-id="96823-151">Other remarks</span></span>

<span data-ttu-id="96823-152">型の拡張機能では、次の属性もあります。</span><span class="sxs-lookup"><span data-stu-id="96823-152">Type extensions also have the following attributes:</span></span>

* <span data-ttu-id="96823-153">アクセスできる任意の型を拡張できます。</span><span class="sxs-lookup"><span data-stu-id="96823-153">Any type that can be accessed can be extended.</span></span>
* <span data-ttu-id="96823-154">組み込みと省略可能な型の拡張機能を定義できます_任意_メンバーの種類、だけでなくメソッド。</span><span class="sxs-lookup"><span data-stu-id="96823-154">Intrinsic and optional type extensions can define _any_ member type, not just methods.</span></span> <span data-ttu-id="96823-155">拡張機能プロパティは、例では可能であればもします。</span><span class="sxs-lookup"><span data-stu-id="96823-155">So extension properties are also possible, for example.</span></span>
* <span data-ttu-id="96823-156">`self-identifier`トークンで、[構文](type-extensions.md#syntax)通常のメンバーと同じように、呼び出される型のインスタンスを表します。</span><span class="sxs-lookup"><span data-stu-id="96823-156">The `self-identifier` token in the [syntax](type-extensions.md#syntax) represents the instance of the type being invoked, just like ordinary members.</span></span>
* <span data-ttu-id="96823-157">拡張メンバーは、静的またはインスタンス メンバーです。</span><span class="sxs-lookup"><span data-stu-id="96823-157">Extended members can be static or instance members.</span></span>
* <span data-ttu-id="96823-158">型の変数型の拡張機能には、宣言型の制約に一致する必要があります。</span><span class="sxs-lookup"><span data-stu-id="96823-158">Type variables on a type extension must match the constraints of the declared type.</span></span>

<span data-ttu-id="96823-159">型の拡張機能も、次の制限があります。</span><span class="sxs-lookup"><span data-stu-id="96823-159">The following limitations also exist for type extensions:</span></span>

* <span data-ttu-id="96823-160">型の拡張機能は、仮想または抽象メソッドをサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="96823-160">Type extensions do not support virtual or abstract methods.</span></span>
* <span data-ttu-id="96823-161">型の拡張機能では、拡張としてオーバーライド メソッドをサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="96823-161">Type extensions do not support override methods as augmentations.</span></span>
* <span data-ttu-id="96823-162">型の拡張機能をサポートしていない[Statically Resolved Type Parameters](generics/statically-resolved-type-parameters.md)します。</span><span class="sxs-lookup"><span data-stu-id="96823-162">Type extensions do not support [Statically Resolved Type Parameters](generics/statically-resolved-type-parameters.md).</span></span>
* <span data-ttu-id="96823-163">省略可能な型の拡張機能では、拡張としてのコンス トラクターはサポートされません。</span><span class="sxs-lookup"><span data-stu-id="96823-163">Optional Type extensions do not support constructors as augmentations.</span></span>
* <span data-ttu-id="96823-164">型の拡張機能では定義できません[省略名を入力](type-abbreviations.md)します。</span><span class="sxs-lookup"><span data-stu-id="96823-164">Type extensions cannot be defined on [type abbreviations](type-abbreviations.md).</span></span>
* <span data-ttu-id="96823-165">型の拡張機能は無効な`byref<'T>`(ただし、これらを宣言することができます)。</span><span class="sxs-lookup"><span data-stu-id="96823-165">Type extensions are not valid for `byref<'T>` (though they can be declared).</span></span>
* <span data-ttu-id="96823-166">型の拡張機能は、(ただし、これらを宣言することができます)、属性は無効です。</span><span class="sxs-lookup"><span data-stu-id="96823-166">Type extensions are not valid for attributes (though they can be declared).</span></span>
* <span data-ttu-id="96823-167">同じ名前の他のメソッドをオーバー ロードする拡張機能を定義することができますが、F# コンパイラでは、あいまいな呼び出しがある場合は非拡張メソッドを優先します。</span><span class="sxs-lookup"><span data-stu-id="96823-167">You can define extensions that overload other methods of the same name, but the F# compiler gives preference to non-extension methods if there is an ambiguous call.</span></span>

<span data-ttu-id="96823-168">最後に、1 つの型に対して複数の組み込み型拡張が存在する場合は、すべてのメンバーが一意である必要があります。</span><span class="sxs-lookup"><span data-stu-id="96823-168">Finally, if multiple intrinsic type extensions exist for one type, all members must be unique.</span></span> <span data-ttu-id="96823-169">オプション型拡張の場合は、1 つの型に対する複数の型拡張が存在する場合でも、各メンバーに同じ名前を付けることができます。</span><span class="sxs-lookup"><span data-stu-id="96823-169">For optional type extensions, members in different type extensions to the same type can have the same names.</span></span> <span data-ttu-id="96823-170">クライアント コードで同じメンバー名が定義されている 2 つの異なるスコープを開いている場合にのみ、あいまいさに対するエラーが発生します。</span><span class="sxs-lookup"><span data-stu-id="96823-170">Ambiguity errors occur only if client code opens two different scopes that define the same member names.</span></span>

## <a name="see-also"></a><span data-ttu-id="96823-171">関連項目</span><span class="sxs-lookup"><span data-stu-id="96823-171">See also</span></span>

- [<span data-ttu-id="96823-172">F# 言語リファレンス</span><span class="sxs-lookup"><span data-stu-id="96823-172">F# Language Reference</span></span>](index.md)
- [<span data-ttu-id="96823-173">メンバー</span><span class="sxs-lookup"><span data-stu-id="96823-173">Members</span></span>](members/index.md)
