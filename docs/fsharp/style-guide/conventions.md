---
title: F# のコーディング規則
description: F# コードを記述する際の一般的なガイドラインとイディオムについて説明します。
ms.date: 01/15/2020
ms.openlocfilehash: 7266211e501bdb52564220781e2347d1aceaf296
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/14/2020
ms.locfileid: "79401149"
---
# <a name="f-coding-conventions"></a><span data-ttu-id="89862-103">F# のコーディング規則</span><span class="sxs-lookup"><span data-stu-id="89862-103">F# coding conventions</span></span>

<span data-ttu-id="89862-104">次の規則は、大きな F# コードベースでの作業経験から定式化されています。</span><span class="sxs-lookup"><span data-stu-id="89862-104">The following conventions are formulated from experience working with large F# codebases.</span></span> <span data-ttu-id="89862-105">[優れた F# コードの 5 つの原則](index.md#five-principles-of-good-f-code)は、各推奨事項の基礎です。</span><span class="sxs-lookup"><span data-stu-id="89862-105">The [Five principles of good F# code](index.md#five-principles-of-good-f-code) are the foundation of each recommendation.</span></span> <span data-ttu-id="89862-106">これらは[F# コンポーネントの設計ガイドライン](component-design-guidelines.md)に関連していますが、ライブラリなどのコンポーネントだけでなく、F# コードに適用できます。</span><span class="sxs-lookup"><span data-stu-id="89862-106">They are related to the [F# component design guidelines](component-design-guidelines.md), but are applicable for any F# code, not just components such as libraries.</span></span>

## <a name="organizing-code"></a><span data-ttu-id="89862-107">コードの整理</span><span class="sxs-lookup"><span data-stu-id="89862-107">Organizing code</span></span>

<span data-ttu-id="89862-108">F# では、コードを整理する主な方法として、モジュールと名前空間の 2 種類があります。</span><span class="sxs-lookup"><span data-stu-id="89862-108">F# features two primary ways to organize code: modules and namespaces.</span></span> <span data-ttu-id="89862-109">これらは似ていますが、次の違いがあります。</span><span class="sxs-lookup"><span data-stu-id="89862-109">These are similar, but do have the following differences:</span></span>

* <span data-ttu-id="89862-110">名前空間は .NET 名前空間としてコンパイルされます。</span><span class="sxs-lookup"><span data-stu-id="89862-110">Namespaces are compiled as .NET namespaces.</span></span> <span data-ttu-id="89862-111">モジュールは静的クラスとしてコンパイルされます。</span><span class="sxs-lookup"><span data-stu-id="89862-111">Modules are compiled as static classes.</span></span>
* <span data-ttu-id="89862-112">名前空間は常に最上位レベルです。</span><span class="sxs-lookup"><span data-stu-id="89862-112">Namespaces are always top level.</span></span> <span data-ttu-id="89862-113">モジュールは最上位レベルにすることができ、他のモジュール内でネストできます。</span><span class="sxs-lookup"><span data-stu-id="89862-113">Modules can be top-level and nested within other modules.</span></span>
* <span data-ttu-id="89862-114">名前空間は複数のファイルにまたがることができます。</span><span class="sxs-lookup"><span data-stu-id="89862-114">Namespaces can span multiple files.</span></span> <span data-ttu-id="89862-115">モジュールはできません。</span><span class="sxs-lookup"><span data-stu-id="89862-115">Modules cannot.</span></span>
* <span data-ttu-id="89862-116">モジュールはとで`[<RequireQualifiedAccess>]`飾ることができます. `[<AutoOpen>]`</span><span class="sxs-lookup"><span data-stu-id="89862-116">Modules can be decorated with `[<RequireQualifiedAccess>]` and `[<AutoOpen>]`.</span></span>

<span data-ttu-id="89862-117">次のガイドラインは、これらを使用してコードを整理するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="89862-117">The following guidelines will help you use these to organize your code.</span></span>

### <a name="prefer-namespaces-at-the-top-level"></a><span data-ttu-id="89862-118">最上位レベルで名前空間を優先する</span><span class="sxs-lookup"><span data-stu-id="89862-118">Prefer namespaces at the top level</span></span>

<span data-ttu-id="89862-119">パブリックに使用できるコードの場合、名前空間は最上位レベルのモジュールよりも優先されます。</span><span class="sxs-lookup"><span data-stu-id="89862-119">For any publicly consumable code, namespaces are preferential to modules at the top level.</span></span> <span data-ttu-id="89862-120">これらの名前空間は .NET 名前空間としてコンパイルされるため、C# からは問題なく使用できます。</span><span class="sxs-lookup"><span data-stu-id="89862-120">Because they are compiled as .NET namespaces, they are consumable from C# with no issue.</span></span>

```fsharp
// Good!
namespace MyCode

type MyClass() =
    ...
```

<span data-ttu-id="89862-121">トップレベルモジュールを使用すると、F# からのみ呼び出されたときには違いが見えないかもしれませんが、C# コンシューマーの場合、呼び出`MyClass`し元`MyCode`はモジュールで修飾する必要があると驚くかもしれません。</span><span class="sxs-lookup"><span data-stu-id="89862-121">Using a top-level module may not appear different when called only from F#, but for C# consumers, callers may be surprised by having to qualify `MyClass` with the `MyCode` module.</span></span>

```fsharp
// Bad!
module MyCode

type MyClass() =
    ...
```

### <a name="carefully-apply-autoopen"></a><span data-ttu-id="89862-122">慎重に適用`[<AutoOpen>]`</span><span class="sxs-lookup"><span data-stu-id="89862-122">Carefully apply `[<AutoOpen>]`</span></span>

<span data-ttu-id="89862-123">この`[<AutoOpen>]`構造は、発信者が利用できるものの範囲を汚染する可能性があり、何かがどこから来ているかの答えは「魔法」です。</span><span class="sxs-lookup"><span data-stu-id="89862-123">The `[<AutoOpen>]` construct can pollute the scope of what is available to callers, and the answer to where something comes from is "magic".</span></span> <span data-ttu-id="89862-124">これは良いことではありません。</span><span class="sxs-lookup"><span data-stu-id="89862-124">This is not a good thing.</span></span> <span data-ttu-id="89862-125">この規則の例外は、F# コア ライブラリ自体です (ただし、この事実も少し議論の余地があります)。</span><span class="sxs-lookup"><span data-stu-id="89862-125">An exception to this rule is the F# Core Library itself (though this fact is also a bit controversial).</span></span>

<span data-ttu-id="89862-126">ただし、パブリック API とは別に整理するパブリック API のヘルパー機能がある場合は便利です。</span><span class="sxs-lookup"><span data-stu-id="89862-126">However, it is a convenience if you have helper functionality for a public API that you wish to organize separately from that public API.</span></span>

```fsharp
module MyAPI =
    [<AutoOpen>]
    module private Helpers =
        let helper1 x y z =
            ...

    let myFunction1 x =
        let y = ...
        let z = ...

        helper1 x y z
```

<span data-ttu-id="89862-127">これにより、ヘルパーを呼び出すたびに完全に修飾しなくても、関数のパブリック API から実装の詳細を明確に分離できます。</span><span class="sxs-lookup"><span data-stu-id="89862-127">This lets you cleanly separate implementation details from the public API of a function without having to fully qualify a helper each time you call it.</span></span>

<span data-ttu-id="89862-128">さらに、名前空間レベルで拡張メソッドと式ビルダーを公開することは、 で`[<AutoOpen>]`きちんと表現できます。</span><span class="sxs-lookup"><span data-stu-id="89862-128">Additionally, exposing extension methods and expression builders at the namespace level can be neatly expressed with `[<AutoOpen>]`.</span></span>

### <a name="use-requirequalifiedaccess-whenever-names-could-conflict-or-you-feel-it-helps-with-readability"></a><span data-ttu-id="89862-129">名前`[<RequireQualifiedAccess>]`が競合する可能性がある場合や、読みやすさを感じた場合に使用する</span><span class="sxs-lookup"><span data-stu-id="89862-129">Use `[<RequireQualifiedAccess>]` whenever names could conflict or you feel it helps with readability</span></span>

<span data-ttu-id="89862-130">モジュールに`[<RequireQualifiedAccess>]`属性を追加すると、モジュールが開かれていないこと、およびモジュールの要素への参照が明示的に修飾されたアクセスを必要とすることを示します。</span><span class="sxs-lookup"><span data-stu-id="89862-130">Adding the `[<RequireQualifiedAccess>]` attribute to a module indicates that the module may not be opened and that references to the elements of the module require explicit qualified access.</span></span> <span data-ttu-id="89862-131">たとえば、モジュールには`Microsoft.FSharp.Collections.List`この属性があります。</span><span class="sxs-lookup"><span data-stu-id="89862-131">For example, the `Microsoft.FSharp.Collections.List` module has this attribute.</span></span>

<span data-ttu-id="89862-132">これは、モジュール内の関数と値の名前が、他のモジュールの名前と競合する可能性がある場合に便利です。</span><span class="sxs-lookup"><span data-stu-id="89862-132">This is useful when functions and values in the module have names that are likely to conflict with names in other modules.</span></span> <span data-ttu-id="89862-133">適格なアクセスを要求すると、ライブラリの長期的な保守性と進化性が大幅に向上します。</span><span class="sxs-lookup"><span data-stu-id="89862-133">Requiring qualified access can greatly increase the long-term maintainability and evolvability of a library.</span></span>

```fsharp
[<RequireQualifiedAccess>]
module StringTokenization =
    let parse s = ...

...

let s = getAString()
let parsed = StringTokenization.parse s // Must qualify to use 'parse'
```

### <a name="sort-open-statements-topologically"></a><span data-ttu-id="89862-134">トポロジ`open`的にステートメントを並べ替える</span><span class="sxs-lookup"><span data-stu-id="89862-134">Sort `open` statements topologically</span></span>

<span data-ttu-id="89862-135">F# では、宣言の順序は、ステートメントを`open`含めて重要です。</span><span class="sxs-lookup"><span data-stu-id="89862-135">In F#, the order of declarations matters, including with `open` statements.</span></span> <span data-ttu-id="89862-136">これは、ファイル内のステートメントの`using`順序に依存しない`using static`、およびの効果が関係ない C# とは異なる。</span><span class="sxs-lookup"><span data-stu-id="89862-136">This is unlike C#, where the effect of `using` and `using static` is independent of the ordering of those statements in a file.</span></span>

<span data-ttu-id="89862-137">F# では、スコープに開かれた要素は、既に存在する他の要素をシャドウできます。</span><span class="sxs-lookup"><span data-stu-id="89862-137">In F#, elements opened into a scope can shadow others already present.</span></span> <span data-ttu-id="89862-138">つまり、ステートメントの並`open`べ替えによってコードの意味が変わる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="89862-138">This means that reordering `open` statements could alter the meaning of code.</span></span> <span data-ttu-id="89862-139">その結果、すべての`open`ステートメントの任意の並べ替え (英数字など) は推奨されません。</span><span class="sxs-lookup"><span data-stu-id="89862-139">As a result, any arbitrary sorting of all `open` statements (for example, alphanumerically) is not recommended, lest you generate different behavior that you might expect.</span></span>

<span data-ttu-id="89862-140">代わりに、[トポロジ的](https://en.wikipedia.org/wiki/Topological_sorting)に並べ替えることをお勧めします。つまり、システムの`open`_層_が定義されている順序でステートメントを並べ替えます。</span><span class="sxs-lookup"><span data-stu-id="89862-140">Instead, we recommend that you sort them [topologically](https://en.wikipedia.org/wiki/Topological_sorting); that is, order your `open` statements in the order in which _layers_ of your system are defined.</span></span> <span data-ttu-id="89862-141">異なるトポロジー層内で英数字のソートを行うことも考慮されるかもしれません。</span><span class="sxs-lookup"><span data-stu-id="89862-141">Doing alphanumeric sorting within different topological layers may also be considered.</span></span>

<span data-ttu-id="89862-142">例として、F# コンパイラ サービスパブリック API ファイルのトポロジ並べ替えを次に示します。</span><span class="sxs-lookup"><span data-stu-id="89862-142">As an example, here is the topological sorting for the F# compiler service public API file:</span></span>

```fsharp
namespace Microsoft.FSharp.Compiler.SourceCodeServices

open System
open System.Collections.Generic
open System.Collections.Concurrent
open System.Diagnostics
open System.IO
open System.Reflection
open System.Text

open Microsoft.FSharp.Compiler
open Microsoft.FSharp.Compiler.AbstractIL
open Microsoft.FSharp.Compiler.AbstractIL.Diagnostics
open Microsoft.FSharp.Compiler.AbstractIL.IL
open Microsoft.FSharp.Compiler.AbstractIL.ILBinaryReader
open Microsoft.FSharp.Compiler.AbstractIL.Internal
open Microsoft.FSharp.Compiler.AbstractIL.Internal.Library

open Microsoft.FSharp.Compiler.AccessibilityLogic
open Microsoft.FSharp.Compiler.Ast
open Microsoft.FSharp.Compiler.CompileOps
open Microsoft.FSharp.Compiler.CompileOptions
open Microsoft.FSharp.Compiler.Driver
open Microsoft.FSharp.Compiler.ErrorLogger
open Microsoft.FSharp.Compiler.Infos
open Microsoft.FSharp.Compiler.InfoReader
open Microsoft.FSharp.Compiler.Lexhelp
open Microsoft.FSharp.Compiler.Layout
open Microsoft.FSharp.Compiler.Lib
open Microsoft.FSharp.Compiler.NameResolution
open Microsoft.FSharp.Compiler.PrettyNaming
open Microsoft.FSharp.Compiler.Parser
open Microsoft.FSharp.Compiler.Range
open Microsoft.FSharp.Compiler.Tast
open Microsoft.FSharp.Compiler.Tastops
open Microsoft.FSharp.Compiler.TcGlobals
open Microsoft.FSharp.Compiler.TypeChecker
open Microsoft.FSharp.Compiler.SourceCodeServices.SymbolHelpers

open Internal.Utilities
open Internal.Utilities.Collections
```

<span data-ttu-id="89862-143">改行はトポロジ レイヤーを分離し、各レイヤーは後で英数字でソートされることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="89862-143">Note that a line break separates topological layers, with each layer being sorted alphanumerically afterwards.</span></span> <span data-ttu-id="89862-144">これにより、誤ってシャドウする値を使用せずに、コードが整理されます。</span><span class="sxs-lookup"><span data-stu-id="89862-144">This cleanly organizes code without accidentally shadowing values.</span></span>

## <a name="use-classes-to-contain-values-that-have-side-effects"></a><span data-ttu-id="89862-145">副作用のある値をクラスに格納する</span><span class="sxs-lookup"><span data-stu-id="89862-145">Use classes to contain values that have side effects</span></span>

<span data-ttu-id="89862-146">データベースやその他のリモート リソースにコンテキストをインスタンス化するなど、値の初期化に副作用が発生する場合が多くあります。</span><span class="sxs-lookup"><span data-stu-id="89862-146">There are many times when initializing a value can have side effects, such as instantiating a context to a database or other remote resource.</span></span> <span data-ttu-id="89862-147">モジュール内でこのようなことを初期化し、後続の関数で使用するのは魅力的です。</span><span class="sxs-lookup"><span data-stu-id="89862-147">It is tempting to initialize such things in a module and use it in subsequent functions:</span></span>

```fsharp
// This is bad!
module MyApi =
    let dep1 = File.ReadAllText "/Users/{your name}/connectionstring.txt"
    let dep2 = Environment.GetEnvironmentVariable "DEP_2"

    let private r = Random()
    let dep3() = r.Next() // Problematic if multiple threads use this

    let function1 arg = doStuffWith dep1 dep2 dep3 arg
    let function2 arg = doSutffWith dep1 dep2 dep3 arg
```

<span data-ttu-id="89862-148">これは、いくつかの理由からしばしば悪い考えです:</span><span class="sxs-lookup"><span data-stu-id="89862-148">This is frequently a bad idea for a few reasons:</span></span>

<span data-ttu-id="89862-149">まず、 と を使用`dep1`して、アプリケーション構成が`dep2`コードベースにプッシュされます。</span><span class="sxs-lookup"><span data-stu-id="89862-149">First, application configuration is pushed into the codebase with `dep1` and `dep2`.</span></span> <span data-ttu-id="89862-150">これは、大規模なコードベースでの維持が困難です。</span><span class="sxs-lookup"><span data-stu-id="89862-150">This is difficult to maintain in larger codebases.</span></span>

<span data-ttu-id="89862-151">第 2 に、静的に初期化されたデータには、コンポーネント自体が複数のスレッドを使用する場合にスレッド セーフではない値を含めないようにします。</span><span class="sxs-lookup"><span data-stu-id="89862-151">Second, statically initialized data should not include values that are not thread safe if your component will itself use multiple threads.</span></span> <span data-ttu-id="89862-152">これは明らかに. `dep3`</span><span class="sxs-lookup"><span data-stu-id="89862-152">This is clearly violated by `dep3`.</span></span>

<span data-ttu-id="89862-153">最後に、モジュールの初期化は、コンパイル単位全体の静的コンストラクターにコンパイルされます。</span><span class="sxs-lookup"><span data-stu-id="89862-153">Finally, module initialization compiles into a static constructor for the entire compilation unit.</span></span> <span data-ttu-id="89862-154">そのモジュールの let バインド値の初期化でエラーが発生した場合は、アプリケーションの`TypeInitializationException`有効期間全体をキャッシュするとしてマニフェストされます。</span><span class="sxs-lookup"><span data-stu-id="89862-154">If any error occurs in let-bound value initialization in that module, it manifests as a `TypeInitializationException` that is then cached for the entire lifetime of the application.</span></span> <span data-ttu-id="89862-155">これは診断が難しい場合があります。</span><span class="sxs-lookup"><span data-stu-id="89862-155">This can be difficult to diagnose.</span></span> <span data-ttu-id="89862-156">通常、推論しようとする内部例外がありますが、存在しない場合は、根本的な原因が何であるかを知りません。</span><span class="sxs-lookup"><span data-stu-id="89862-156">There is usually an inner exception that you can attempt to reason about, but if there is not, then there is no telling what the root cause is.</span></span>

<span data-ttu-id="89862-157">代わりに、単純なクラスを使用して依存関係を保持するだけです。</span><span class="sxs-lookup"><span data-stu-id="89862-157">Instead, just use a simple class to hold dependencies:</span></span>

```fsharp
type MyParametricApi(dep1, dep2, dep3) =
    member _.Function1 arg1 = doStuffWith dep1 dep2 dep3 arg1
    member _.Function2 arg2 = doStuffWith dep1 dep2 dep3 arg2
```

<span data-ttu-id="89862-158">これにより、次のことが可能になります。</span><span class="sxs-lookup"><span data-stu-id="89862-158">This enables the following:</span></span>

1. <span data-ttu-id="89862-159">API 自体の外部に依存状態をプッシュします。</span><span class="sxs-lookup"><span data-stu-id="89862-159">Pushing any dependent state outside of the API itself.</span></span>
2. <span data-ttu-id="89862-160">構成は API の外部で行えるようになりました。</span><span class="sxs-lookup"><span data-stu-id="89862-160">Configuration can now be done outside of the API.</span></span>
3. <span data-ttu-id="89862-161">依存値の初期化のエラーは、 としては現れ`TypeInitializationException`ないでしょう。</span><span class="sxs-lookup"><span data-stu-id="89862-161">Errors in initialization for dependent values are not likely to manifest as a `TypeInitializationException`.</span></span>
4. <span data-ttu-id="89862-162">API のテストが簡単になりました。</span><span class="sxs-lookup"><span data-stu-id="89862-162">The API is now easier to test.</span></span>

## <a name="error-management"></a><span data-ttu-id="89862-163">エラー管理</span><span class="sxs-lookup"><span data-stu-id="89862-163">Error management</span></span>

<span data-ttu-id="89862-164">大規模なシステムでのエラー管理は複雑で微妙な努力であり、システムがフォールトトレラントでうまく動作することを保証する銀色の弾丸はありません。</span><span class="sxs-lookup"><span data-stu-id="89862-164">Error management in large systems is a complex and nuanced endeavor, and there are no silver bullets in ensuring your systems are fault-tolerant and behave well.</span></span> <span data-ttu-id="89862-165">次のガイドラインは、この困難な領域をナビゲートする際のガイダンスを提供する必要があります。</span><span class="sxs-lookup"><span data-stu-id="89862-165">The following guidelines should offer guidance in navigating this difficult space.</span></span>

### <a name="represent-error-cases-and-illegal-state-in-types-intrinsic-to-your-domain"></a><span data-ttu-id="89862-166">ドメイン固有の型でエラーケースと不正な状態を表す</span><span class="sxs-lookup"><span data-stu-id="89862-166">Represent error cases and illegal state in types intrinsic to your domain</span></span>

<span data-ttu-id="89862-167">[判別共用体](../language-reference/discriminated-unions.md)を使用すると、F# は、型システムでプログラムの状態に障害があることを表す機能を提供します。</span><span class="sxs-lookup"><span data-stu-id="89862-167">With [Discriminated Unions](../language-reference/discriminated-unions.md), F# gives you the ability to represent faulty program state in your type system.</span></span> <span data-ttu-id="89862-168">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="89862-168">For example:</span></span>

```fsharp
type MoneyWithdrawalResult =
    | Success of amount:decimal
    | InsufficientFunds of balance:decimal
    | CardExpired of DateTime
    | UndisclosedFailure
```

<span data-ttu-id="89862-169">この場合、銀行口座からのお金を引き出す方法が 3 つあると、失敗する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="89862-169">In this case, there are three known ways that withdrawing money from a bank account can fail.</span></span> <span data-ttu-id="89862-170">各エラーケースは型で表され、プログラム全体で安全に対処できます。</span><span class="sxs-lookup"><span data-stu-id="89862-170">Each error case is represented in the type, and can thus be dealt with safely throughout the program.</span></span>

```fsharp
let handleWithdrawal amount =
    let w = withdrawMoney amount
    match w with
    | Success am -> printfn "Successfully withdrew %f" am
    | InsufficientFunds balance -> printfn "Failed: balance is %f" balance
    | CardExpired expiredDate -> printfn "Failed: card expired on %O" expiredDate
    | UndisclosedFailure -> printfn "Failed: unknown"
```

<span data-ttu-id="89862-171">一般に、ドメイン内で何かが**失敗**する可能性のあるさまざまな方法をモデル化できる場合、エラー処理コードは通常のプログラムフローに加えて対処する必要があるものとして扱われなくなります。</span><span class="sxs-lookup"><span data-stu-id="89862-171">In general, if you can model the different ways that something can **fail** in your domain, then error handling code is no longer treated as something you must deal with in addition to regular program flow.</span></span> <span data-ttu-id="89862-172">これは単に通常のプログラムフローの一部であり、**例外的**とは考えられません。</span><span class="sxs-lookup"><span data-stu-id="89862-172">It is simply a part of normal program flow, and not considered **exceptional**.</span></span> <span data-ttu-id="89862-173">これには、主に 2 つの利点があります。</span><span class="sxs-lookup"><span data-stu-id="89862-173">There are two primary benefits to this:</span></span>

1. <span data-ttu-id="89862-174">ドメインが時間の経過とともに変化するため、保守が容易になります。</span><span class="sxs-lookup"><span data-stu-id="89862-174">It is easier to maintain as your domain changes over time.</span></span>
2. <span data-ttu-id="89862-175">エラーケースは単体テストが簡単です。</span><span class="sxs-lookup"><span data-stu-id="89862-175">Error cases are easier to unit test.</span></span>

### <a name="use-exceptions-when-errors-cannot-be-represented-with-types"></a><span data-ttu-id="89862-176">エラーを型で表すことができない場合は例外を使用する</span><span class="sxs-lookup"><span data-stu-id="89862-176">Use exceptions when errors cannot be represented with types</span></span>

<span data-ttu-id="89862-177">問題のあるドメインですべてのエラーを表すわけではありません。</span><span class="sxs-lookup"><span data-stu-id="89862-177">Not all errors can be represented in a problem domain.</span></span> <span data-ttu-id="89862-178">このようなエラーは*本質的に例外的*であるため、F# で例外を発生およびキャッチする機能があります。</span><span class="sxs-lookup"><span data-stu-id="89862-178">These kinds of faults are *exceptional* in nature, hence the ability to raise and catch exceptions in F#.</span></span>

<span data-ttu-id="89862-179">まず、「[例外設計ガイドライン](../../standard/design-guidelines/exceptions.md)」を読むことをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="89862-179">First, it is recommended that you read the [Exception Design Guidelines](../../standard/design-guidelines/exceptions.md).</span></span> <span data-ttu-id="89862-180">これらは F# にも適用できます。</span><span class="sxs-lookup"><span data-stu-id="89862-180">These are also applicable to F#.</span></span>

<span data-ttu-id="89862-181">例外を発生させる目的で F# で使用できる主な構成要素は、次の優先順位で考慮する必要があります。</span><span class="sxs-lookup"><span data-stu-id="89862-181">The main constructs available in F# for the purposes of raising exceptions should be considered in the following order of preference:</span></span>

| <span data-ttu-id="89862-182">Function</span><span class="sxs-lookup"><span data-stu-id="89862-182">Function</span></span> | <span data-ttu-id="89862-183">構文</span><span class="sxs-lookup"><span data-stu-id="89862-183">Syntax</span></span> | <span data-ttu-id="89862-184">目的</span><span class="sxs-lookup"><span data-stu-id="89862-184">Purpose</span></span> |
|----------|--------|---------|
| `nullArg` | `nullArg "argumentName"` | <span data-ttu-id="89862-185">指定した引数`System.ArgumentNullException`名を持つ a を発生させます。</span><span class="sxs-lookup"><span data-stu-id="89862-185">Raises a `System.ArgumentNullException` with the specified argument name.</span></span> |
| `invalidArg` | `invalidArg "argumentName" "message"` | <span data-ttu-id="89862-186">引数名と`System.ArgumentException`メッセージを指定して a を発生させます。</span><span class="sxs-lookup"><span data-stu-id="89862-186">Raises a `System.ArgumentException` with a specified argument name and message.</span></span> |
| `invalidOp` | `invalidOp "message"` | <span data-ttu-id="89862-187">指定したメッセージ`System.InvalidOperationException`を持つ a を発生させます。</span><span class="sxs-lookup"><span data-stu-id="89862-187">Raises a `System.InvalidOperationException` with the specified message.</span></span> |
|`raise`| `raise (ExceptionType("message"))` | <span data-ttu-id="89862-188">例外をスローするための汎用メカニズム。</span><span class="sxs-lookup"><span data-stu-id="89862-188">General-purpose mechanism for throwing exceptions.</span></span> |
| `failwith` | `failwith "message"` | <span data-ttu-id="89862-189">指定したメッセージ`System.Exception`を持つ a を発生させます。</span><span class="sxs-lookup"><span data-stu-id="89862-189">Raises a `System.Exception` with the specified message.</span></span> |
| `failwithf` | `failwithf "format string" argForFormatString` | <span data-ttu-id="89862-190">フォーマット文字列とその`System.Exception`入力によって決定されるメッセージを持つ を発生させます。</span><span class="sxs-lookup"><span data-stu-id="89862-190">Raises a `System.Exception` with a message determined by the format string and its inputs.</span></span> |

<span data-ttu-id="89862-191">を`nullArg``invalidArg`使用し`invalidOp`、スローするメカニズムとして`ArgumentNullException`、`ArgumentException`必要`InvalidOperationException`に応じてを使用します。</span><span class="sxs-lookup"><span data-stu-id="89862-191">Use `nullArg`, `invalidArg` and `invalidOp` as the mechanism to throw `ArgumentNullException`, `ArgumentException` and `InvalidOperationException` when appropriate.</span></span>

<span data-ttu-id="89862-192">と`failwith``failwithf`関数は、特定の例外ではなく基本`Exception`型を発生させるため、一般的には避けるべきです。</span><span class="sxs-lookup"><span data-stu-id="89862-192">The `failwith` and `failwithf` functions should generally be avoided because they raise the base `Exception` type, not a specific exception.</span></span> <span data-ttu-id="89862-193">[例外設計ガイドライン](../../standard/design-guidelines/exceptions.md)に従って、可能な場合は、より具体的な例外を発生させる必要があります。</span><span class="sxs-lookup"><span data-stu-id="89862-193">As per the [Exception Design Guidelines](../../standard/design-guidelines/exceptions.md), you want to raise more specific exceptions when you can.</span></span>

### <a name="using-exception-handling-syntax"></a><span data-ttu-id="89862-194">例外処理構文の使用</span><span class="sxs-lookup"><span data-stu-id="89862-194">Using exception-handling syntax</span></span>

<span data-ttu-id="89862-195">F# は、次の`try...with`構文を使用して例外パターンをサポートします。</span><span class="sxs-lookup"><span data-stu-id="89862-195">F# supports exception patterns via the `try...with` syntax:</span></span>

```fsharp
try
    tryGetFileContents()
with
| :? System.IO.FileNotFoundException as e -> // Do something with it here
| :? System.Security.SecurityException as e -> // Do something with it here
```

<span data-ttu-id="89862-196">コードをクリーンに保ちたいなら、パターンマッチングを使用して例外に直面して実行する機能を調整するのは少し難しいかもしれません。</span><span class="sxs-lookup"><span data-stu-id="89862-196">Reconciling functionality to perform in the face of an exception with pattern matching can be a bit tricky if you wish to keep the code clean.</span></span> <span data-ttu-id="89862-197">これを処理する方法の 1 つは、エラーケースを囲む機能を例外自体にグループ化する手段として[アクティブパターン](../language-reference/active-patterns.md)を使用することです。</span><span class="sxs-lookup"><span data-stu-id="89862-197">One such way to handle this is to use [active patterns](../language-reference/active-patterns.md) as a means to group functionality surrounding an error case with an exception itself.</span></span> <span data-ttu-id="89862-198">たとえば、例外をスローしたときに、例外メタデータに貴重な情報を含む API を使用している場合があります。</span><span class="sxs-lookup"><span data-stu-id="89862-198">For example, you may be consuming an API that, when it throws an exception, encloses valuable information in the exception metadata.</span></span> <span data-ttu-id="89862-199">アクティブ パターン内でキャプチャされた例外の本体で有用な値をラップ解除し、その値を返すと、状況によっては役立ちます。</span><span class="sxs-lookup"><span data-stu-id="89862-199">Unwrapping a useful value in the body of the captured exception inside the Active Pattern and returning that value can be helpful in some situations.</span></span>

### <a name="do-not-use-monadic-error-handling-to-replace-exceptions"></a><span data-ttu-id="89862-200">例外を置き換えるためにモナディックエラー処理を使用しない</span><span class="sxs-lookup"><span data-stu-id="89862-200">Do not use monadic error handling to replace exceptions</span></span>

<span data-ttu-id="89862-201">関数型プログラミングでは、例外はややタブーと見なされます。</span><span class="sxs-lookup"><span data-stu-id="89862-201">Exceptions are seen as somewhat taboo in functional programming.</span></span> <span data-ttu-id="89862-202">実際、例外は純度に違反するため、機能していないと考えても安全です。</span><span class="sxs-lookup"><span data-stu-id="89862-202">Indeed, exceptions violate purity, so it's safe to consider them not-quite functional.</span></span> <span data-ttu-id="89862-203">ただし、これはコードが実行される場所の現実を無視し、ランタイム エラーが発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="89862-203">However, this ignores the reality of where code must run, and that runtime errors can occur.</span></span> <span data-ttu-id="89862-204">一般に、ほとんどのものが純粋でもトータルでもないという前提でコードを書いて、不愉快な驚きを最小限に抑えます。</span><span class="sxs-lookup"><span data-stu-id="89862-204">In general, write code on the assumption that most things are neither pure nor total, to minimize unpleasant surprises.</span></span>

<span data-ttu-id="89862-205">.NET ランタイムおよび言語間のエコシステム全体における関連性と妥当性に関して、次の主な長所と側面を考慮することが重要です。</span><span class="sxs-lookup"><span data-stu-id="89862-205">It is important to consider the following core strengths/aspects of Exceptions with respect to their relevance and appropriateness in the .NET runtime and cross-language ecosystem as a whole:</span></span>

1. <span data-ttu-id="89862-206">問題をデバッグする際に非常に役立つ詳細な診断情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="89862-206">They contain detailed diagnostic information, which is very helpful when debugging an issue.</span></span>
2. <span data-ttu-id="89862-207">ランタイムや他の .NET 言語ではよく理解されています。</span><span class="sxs-lookup"><span data-stu-id="89862-207">They are well-understood by the runtime and other .NET languages.</span></span>
3. <span data-ttu-id="89862-208">例外を回避するために例外を*回避*するコードと比較すると、意味の一部をアドホックベースで実装することで、重要な定型文を削減できます。</span><span class="sxs-lookup"><span data-stu-id="89862-208">They can reduce significant boilerplate when compared with code that goes out of its way to *avoid* exceptions by implementing some subset of their semantics on an ad-hoc basis.</span></span>

<span data-ttu-id="89862-209">この3番目のポイントは非常に重要です。</span><span class="sxs-lookup"><span data-stu-id="89862-209">This third point is critical.</span></span> <span data-ttu-id="89862-210">複雑でない操作では、例外を使用しないと、次のような構造体が処理される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="89862-210">For nontrivial complex operations, failing to use exceptions can result in dealing with structures like this:</span></span>

```fsharp
Result<Result<MyType, string>, string list>
```

<span data-ttu-id="89862-211">これは簡単に「文字列型付き」エラーでパターンマッチングのような脆弱なコードにつながる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="89862-211">Which can easily lead to fragile code like pattern matching on "stringly-typed" errors:</span></span>

```fsharp
let result = doStuff()
match result with
| Ok r -> ...
| Error e ->
    if e.Contains "Error string 1" then ...
    elif e.Contains "Error string 2" then ...
    else ... // Who knows?
```

<span data-ttu-id="89862-212">さらに、"より素敵な" 型を返す "単純な" 関数の欲求の例外を飲み込むのは魅力的です。</span><span class="sxs-lookup"><span data-stu-id="89862-212">Additionally, it can be tempting to swallow any exception in the desire for a "simple" function that returns a "nicer" type:</span></span>

```fsharp
// This is bad!
let tryReadAllText (path : string) =
    try System.IO.File.ReadAllText path |> Some
    with _ -> None
```

<span data-ttu-id="89862-213">残念`tryReadAllText`ながら、ファイル システムで発生する可能性のある無数の処理に基づいて多数の例外をスローする可能性があり、このコードは、実際に環境で問題が発生している可能性のある情報を破棄します。</span><span class="sxs-lookup"><span data-stu-id="89862-213">Unfortunately, `tryReadAllText` can throw numerous exceptions based on the myriad of things that can happen on a file system, and this code discards away any information about what might actually be going wrong in your environment.</span></span> <span data-ttu-id="89862-214">このコードを結果の型に置き換える場合は、"文字列型" エラー メッセージの解析に戻ります。</span><span class="sxs-lookup"><span data-stu-id="89862-214">If you replace this code with a result type, then you're back to "stringly-typed" error message parsing:</span></span>

```fsharp
// This is bad!
let tryReadAllText (path : string) =
    try System.IO.File.ReadAllText path |> Ok
    with e -> Error e.Message

let r = tryReadAllText "path-to-file"
match r with
| Ok text -> ...
| Error e ->
    if e.Contains "uh oh, here we go again..." then ...
    else ...
```

<span data-ttu-id="89862-215">さらに、`Error`例外オブジェクト自体をコンストラクタに配置すると、関数ではなく呼び出しサイトで例外の種類を適切に処理する必要があります。</span><span class="sxs-lookup"><span data-stu-id="89862-215">And placing the exception object itself in the `Error` constructor just forces you to properly deal with the exception type at the call site rather than in the function.</span></span> <span data-ttu-id="89862-216">これを効果的に行うと、API の呼び出し元として扱うのも楽しくない、チェックされた例外が効果的に作成されます。</span><span class="sxs-lookup"><span data-stu-id="89862-216">Doing this effectively creates checked exceptions, which are notoriously unfun to deal with as a caller of an API.</span></span>

<span data-ttu-id="89862-217">上記の例の代わりに、*特定*の例外をキャッチし、その例外のコンテキストで意味のある値を返す方法があります。</span><span class="sxs-lookup"><span data-stu-id="89862-217">A good alternative to the above examples is to catch *specific* exceptions and return a meaningful value in the context of that exception.</span></span> <span data-ttu-id="89862-218">関数を`tryReadAllText`次のように変更すると、`None`より多くの意味があります。</span><span class="sxs-lookup"><span data-stu-id="89862-218">If you modify the `tryReadAllText` function as follows, `None` has more meaning:</span></span>

```fsharp
let tryReadAllTextIfPresent (path : string) =
    try System.IO.File.ReadAllText path |> Some
    with :? FileNotFoundException -> None
```

<span data-ttu-id="89862-219">catch-all として機能する代わりに、この関数はファイルが見つからなかった場合を適切に処理し、その意味を戻りに割り当てます。</span><span class="sxs-lookup"><span data-stu-id="89862-219">Instead of functioning as a catch-all, this function will now properly handle the case when a file was not found and assign that meaning to a return.</span></span> <span data-ttu-id="89862-220">この戻り値は、コンテキスト情報を破棄したり、コードのその時点で関係のないケースを呼び出し元に強制したりしながら、そのエラーケースにマップできます。</span><span class="sxs-lookup"><span data-stu-id="89862-220">This return value can map to that error case, while not discarding any contextual information or forcing callers to deal with a case that may not be relevant at that point in the code.</span></span>

<span data-ttu-id="89862-221">たとえば`Result<'Success, 'Error>`、入れ子になっていない基本的な操作に適した型や、F# のオプション型は、*何かが何かを*返す可能性がある場合と*何も返さない*場合に表現するのに最適です。</span><span class="sxs-lookup"><span data-stu-id="89862-221">Types such as `Result<'Success, 'Error>` are appropriate for basic operations where they aren't nested, and F# optional types are perfect for representing when something could either return *something* or *nothing*.</span></span> <span data-ttu-id="89862-222">ただし、例外の代わりとなるものではありません。</span><span class="sxs-lookup"><span data-stu-id="89862-222">They are not a replacement for exceptions, though, and should not be used in an attempt to replace exceptions.</span></span> <span data-ttu-id="89862-223">むしろ、例外およびエラー管理ポリシーの特定の側面に対して、対象を絞った方法で対応するために、慎重に適用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="89862-223">Rather, they should be applied judiciously to address specific aspects of exception and error management policy in targeted ways.</span></span>

## <a name="partial-application-and-point-free-programming"></a><span data-ttu-id="89862-224">部分的なアプリケーションとポイントフリープログラミング</span><span class="sxs-lookup"><span data-stu-id="89862-224">Partial application and point-free programming</span></span>

<span data-ttu-id="89862-225">F# は部分的なアプリケーションをサポートしているため、ポイントフリー のスタイルでプログラミングするさまざまな方法がサポートされます。</span><span class="sxs-lookup"><span data-stu-id="89862-225">F# supports partial application, and thus, various ways to program in a point-free style.</span></span> <span data-ttu-id="89862-226">これは、モジュール内でコードを再利用したり、何かの実装を行う場合に役立ちますが、公開するものではありません。</span><span class="sxs-lookup"><span data-stu-id="89862-226">This can be beneficial for code reuse within a module or the implementation of something, but it is not something to expose publicly.</span></span> <span data-ttu-id="89862-227">一般に、ポイントフリープログラミングはそれ自体の美徳ではなく、スタイルに没頭していない人々にとって重要な認知障壁を追加することができます。</span><span class="sxs-lookup"><span data-stu-id="89862-227">In general, point-free programming is not a virtue in and of itself, and can add a significant cognitive barrier for people who are not immersed in the style.</span></span>

### <a name="do-not-use-partial-application-and-currying-in-public-apis"></a><span data-ttu-id="89862-228">パブリック API で部分的なアプリケーションとカリー化を使用しない</span><span class="sxs-lookup"><span data-stu-id="89862-228">Do not use partial application and currying in public APIs</span></span>

<span data-ttu-id="89862-229">例外を除いて、パブリック API で部分的なアプリケーションを使用すると、コンシューマーにとって混乱を招く可能性があります。</span><span class="sxs-lookup"><span data-stu-id="89862-229">With little exception, the use of partial application in public APIs can be confusing for consumers.</span></span> <span data-ttu-id="89862-230">通常、F#`let`コードの -バインド値は**値**であり、**関数値**ではありません。</span><span class="sxs-lookup"><span data-stu-id="89862-230">Usually, `let`-bound values in F# code are **values**, not **function values**.</span></span> <span data-ttu-id="89862-231">値と関数値を混在させると、特に関数を構成するなどの演算子と組み合わせる場合、認知オーバーヘッドのかなりの部分と引き換えに、少数`>>`のコード行を節約できます。</span><span class="sxs-lookup"><span data-stu-id="89862-231">Mixing together values and function values can result in saving a small number of lines of code in exchange for quite a bit of cognitive overhead, especially if combined with operators such as `>>` to compose functions.</span></span>

### <a name="consider-the-tooling-implications-for-point-free-programming"></a><span data-ttu-id="89862-232">ポイントフリープログラミングに対するツールの影響を考慮する</span><span class="sxs-lookup"><span data-stu-id="89862-232">Consider the tooling implications for point-free programming</span></span>

<span data-ttu-id="89862-233">カリー化関数は、引数にラベルを付けないでください。</span><span class="sxs-lookup"><span data-stu-id="89862-233">Curried functions do not label their arguments.</span></span> <span data-ttu-id="89862-234">これは、ツールに影響を与えます。</span><span class="sxs-lookup"><span data-stu-id="89862-234">This has tooling implications.</span></span> <span data-ttu-id="89862-235">次の 2 つの関数を検討してください。</span><span class="sxs-lookup"><span data-stu-id="89862-235">Consider the following two functions:</span></span>

```fsharp
let func name age =
    printfn "My name is %s and I am %d years old!" name age

let funcWithApplication =
    printfn "My name is %s and I am %d years old!"
```

<span data-ttu-id="89862-236">どちらも有効な関数ですが`funcWithApplication`、カリー化された関数です。</span><span class="sxs-lookup"><span data-stu-id="89862-236">Both are valid functions, but `funcWithApplication` is a curried function.</span></span> <span data-ttu-id="89862-237">エディタでタイプにカーソルを合わせると、次のことがわかります。</span><span class="sxs-lookup"><span data-stu-id="89862-237">When you hover over their types in an editor, you see this:</span></span>

```fsharp
val func : name:string -> age:int -> unit

val funcWithApplication : (string -> int -> unit)
```

<span data-ttu-id="89862-238">呼び出しサイトでは、Visual Studio などのツールのツールヒントは、入力型と`string``int`入力型が実際に何を表すのか、意味のある情報を提供しません。</span><span class="sxs-lookup"><span data-stu-id="89862-238">At the call site, tooltips in tooling such as Visual Studio will not give you meaningful information as to what the `string` and `int` input types actually represent.</span></span>

<span data-ttu-id="89862-239">そのような`funcWithApplication`ポイントフリーコードが一般に消耗品である場合は、ツールが引数の意味のある名前を拾うことができるように、完全なη拡張を行うことをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="89862-239">If you encounter point-free code like `funcWithApplication` that is publicly consumable, it is recommended to do a full η-expansion so that tooling can pick up on meaningful names for arguments.</span></span>

<span data-ttu-id="89862-240">さらに、ポイントフリーコードのデバッグは、不可能ではないにしても困難な場合があります。</span><span class="sxs-lookup"><span data-stu-id="89862-240">Furthermore, debugging point-free code can be challenging, if not impossible.</span></span> <span data-ttu-id="89862-241">デバッグ ツールは、名前にバインドされた値 (`let`たとえば、バインディング) に依存するため、中間値を実行の途中で検査できます。</span><span class="sxs-lookup"><span data-stu-id="89862-241">Debugging tools rely on values bound to names (for example, `let` bindings) so that you can inspect intermediate values midway through execution.</span></span> <span data-ttu-id="89862-242">コードに検査する値がない場合、デバッグする必要はありません。</span><span class="sxs-lookup"><span data-stu-id="89862-242">When your code has no values to inspect, there is nothing to debug.</span></span> <span data-ttu-id="89862-243">将来、デバッグ ツールは、以前に実行されたパスに基づいてこれらの値を合成するように進化する可能性がありますが、*潜在的な*デバッグ機能に対する賭けをヘッジすることはお勧めします。</span><span class="sxs-lookup"><span data-stu-id="89862-243">In the future, debugging tools may evolve to synthesize these values based on previously executed paths, but it's not a good idea to hedge your bets on *potential* debugging functionality.</span></span>

### <a name="consider-partial-application-as-a-technique-to-reduce-internal-boilerplate"></a><span data-ttu-id="89862-244">内部定型法を削減する手法として部分的なアプリケーションを検討する</span><span class="sxs-lookup"><span data-stu-id="89862-244">Consider partial application as a technique to reduce internal boilerplate</span></span>

<span data-ttu-id="89862-245">前の点とは対照的に、部分アプリケーションはアプリケーション内部または API のより深い内部の定型を減らすための素晴らしいツールです。</span><span class="sxs-lookup"><span data-stu-id="89862-245">In contrast to the previous point, partial application is a wonderful tool for reducing boilerplate inside of an application or the deeper internals of an API.</span></span> <span data-ttu-id="89862-246">これは、多くの場合、定型文が対処する苦痛である、より複雑なAPIの実装を単体テストするのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="89862-246">It can be helpful for unit testing the implementation of more complicated APIs, where boilerplate is often a pain to deal with.</span></span> <span data-ttu-id="89862-247">たとえば、次のコードは、このようなフレームワークに外部依存関係を持たずに、関連する別注 API を学習することなく、ほとんどのモック フレームワークが提供する内容を実現する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="89862-247">For example, the following code shows how you can accomplish what most mocking frameworks give you without taking an external dependency on such a framework and having to learn a related bespoke API.</span></span>

<span data-ttu-id="89862-248">たとえば、次のソリューションの地形を考えてみましょう。</span><span class="sxs-lookup"><span data-stu-id="89862-248">For example, consider the following solution topography:</span></span>

```
MySolution.sln
|_/ImplementationLogic.fsproj
|_/ImplementationLogic.Tests.fsproj
|_/API.fsproj
```

<span data-ttu-id="89862-249">`ImplementationLogic.fsproj`次のようなコードを公開する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="89862-249">`ImplementationLogic.fsproj` might expose code such as:</span></span>

```fsharp
module Transactions =
    let doTransaction txnContext txnType balance =
        ...

type Transactor(ctx, currentBalance) =
    member _.ExecuteTransaction(txnType) =
        Transactions.doTransaction ctx txtType currentBalance
        ...
```

<span data-ttu-id="89862-250">での`Transactions.doTransaction``ImplementationLogic.Tests.fsproj`単体テストは簡単です:</span><span class="sxs-lookup"><span data-stu-id="89862-250">Unit testing `Transactions.doTransaction` in `ImplementationLogic.Tests.fsproj` is easy:</span></span>

```fsharp
namespace TransactionsTestingUtil

open Transactions

module TransactionsTestable =
    let getTestableTransactionRoutine mockContext = Transactions.doTransaction mockContext
```

<span data-ttu-id="89862-251">モック コンテキスト`doTransaction`オブジェクトを使用して部分的に適用すると、モック コンテキストを毎回構築する必要なく、すべての単体テストで関数を呼び出すことができます。</span><span class="sxs-lookup"><span data-stu-id="89862-251">Partially applying `doTransaction` with a mocking context object lets you call the function in all of your unit tests without needing to construct a mocked context each time:</span></span>

```fsharp
namespace TransactionTests

open Xunit
open TransactionTypes
open TransactionsTestingUtil
open TransactionsTestingUtil.TransactionsTestable

let testableContext =
    { new ITransactionContext with
        member _.TheFirstMember() = ...
        member _.TheSecondMember() = ... }

let transactionRoutine = getTestableTransactionRoutine testableContext

[<Fact>]
let ``Test withdrawal transaction with 0.0 for balance``() =
    let expected = ...
    let actual = transactionRoutine TransactionType.Withdraw 0.0
    Assert.Equal(expected, actual)
```

<span data-ttu-id="89862-252">この手法は、コードベース全体に対して汎用的に適用されるべきではありませんが、複雑な内部とそれらの内部を単体テストする際の定型化を減らすには良い方法です。</span><span class="sxs-lookup"><span data-stu-id="89862-252">This technique should not be universally applied to your entire codebase, but it is a good way to reduce boilerplate for complicated internals and unit testing those internals.</span></span>

## <a name="access-control"></a><span data-ttu-id="89862-253">アクセス制御</span><span class="sxs-lookup"><span data-stu-id="89862-253">Access control</span></span>

<span data-ttu-id="89862-254">F# には、.NET ランタイムで使用できるオプションから継承された[アクセス制御](../language-reference/access-control.md)の複数のオプションがあります。</span><span class="sxs-lookup"><span data-stu-id="89862-254">F# has multiple options for [Access control](../language-reference/access-control.md), inherited from what is available in the .NET runtime.</span></span> <span data-ttu-id="89862-255">これらは型に対して使用できるだけでなく、関数にも使用できます。</span><span class="sxs-lookup"><span data-stu-id="89862-255">These are not just usable for types - you can use them for functions, too.</span></span>

* <span data-ttu-id="89862-256">非型と`public`メンバーをパブリックに消耗品にする必要があるまで、非型とメンバーを優先します。</span><span class="sxs-lookup"><span data-stu-id="89862-256">Prefer non-`public` types and members until you need them to be publicly consumable.</span></span> <span data-ttu-id="89862-257">これにより、消費者のカップルが何を組み合わせるかを最小限に抑えることができます。</span><span class="sxs-lookup"><span data-stu-id="89862-257">This also minimizes what consumers couple to.</span></span>
* <span data-ttu-id="89862-258">すべてのヘルパー機能`private`を維持するよう努める 。</span><span class="sxs-lookup"><span data-stu-id="89862-258">Strive to keep all helper functionality `private`.</span></span>
* <span data-ttu-id="89862-259">ヘルパー関数が多数`[<AutoOpen>]`になる場合は、プライベートモジュールでの使用を検討してください。</span><span class="sxs-lookup"><span data-stu-id="89862-259">Consider the use of `[<AutoOpen>]` on a private module of helper functions if they become numerous.</span></span>

## <a name="type-inference-and-generics"></a><span data-ttu-id="89862-260">型の推論とジェネリック</span><span class="sxs-lookup"><span data-stu-id="89862-260">Type inference and generics</span></span>

<span data-ttu-id="89862-261">型の推論により、多くの定型文を入力する手間を省くことができます。</span><span class="sxs-lookup"><span data-stu-id="89862-261">Type inference can save you from typing a lot of boilerplate.</span></span> <span data-ttu-id="89862-262">また、F# コンパイラの自動汎化は、追加の作業をほとんど行わなく、より汎用的なコードを記述するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="89862-262">And automatic generalization in the F# compiler can help you write more generic code with almost no extra effort on your part.</span></span> <span data-ttu-id="89862-263">しかし、これらの機能は普遍的に良いものではありません。</span><span class="sxs-lookup"><span data-stu-id="89862-263">However, these features are not universally good.</span></span>

* <span data-ttu-id="89862-264">パブリック API では明示的な型を持つ引数名にラベルを付け、この型の推論に依存しないようにします。</span><span class="sxs-lookup"><span data-stu-id="89862-264">Consider labeling argument names with explicit types in public APIs and do not rely on type inference for this.</span></span>

    <span data-ttu-id="89862-265">この理由**は、コンパイラ**ではなく、API の形状を制御する必要があるためです。</span><span class="sxs-lookup"><span data-stu-id="89862-265">The reason for this is that **you** should be in control of the shape of your API, not the compiler.</span></span> <span data-ttu-id="89862-266">コンパイラは、型を推論する際に細かい処理を行うことができますが、依存している内部が型を変更した場合、API の形状を変更することができます。</span><span class="sxs-lookup"><span data-stu-id="89862-266">Although the compiler can do a fine job at inferring types for you, it is possible to have the shape of your API change if the internals it relies on have changed types.</span></span> <span data-ttu-id="89862-267">これはあなたが望むものかもしれませんが、下流の消費者が対処しなければならない画期的なAPI変更をもたらす可能性はほぼ間違いいます。</span><span class="sxs-lookup"><span data-stu-id="89862-267">This may be what you want, but it will almost certainly result in a breaking API change that downstream consumers will then have to deal with.</span></span> <span data-ttu-id="89862-268">代わりに、パブリック API の形状を明示的に制御する場合は、これらの変更を制御できます。</span><span class="sxs-lookup"><span data-stu-id="89862-268">Instead, if you explicitly control the shape of your public API, then you can control these breaking changes.</span></span> <span data-ttu-id="89862-269">DDD の用語では、これは腐敗防止レイヤーと考えることができます。</span><span class="sxs-lookup"><span data-stu-id="89862-269">In DDD terms, this can be thought of as an Anti-corruption layer.</span></span>

* <span data-ttu-id="89862-270">汎用引数に意味のある名前を付けることを検討してください。</span><span class="sxs-lookup"><span data-stu-id="89862-270">Consider giving a meaningful name to your generic arguments.</span></span>

    <span data-ttu-id="89862-271">特定のドメインに固有ではない本当に汎用的なコードを記述していない限り、意味のある名前を付けて、他のプログラマが自分が作業しているドメインを理解するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="89862-271">Unless you are writing truly generic code that is not specific to a particular domain, a meaningful name can help other programmers understanding the domain they're working in.</span></span> <span data-ttu-id="89862-272">たとえば、ドキュメント データベースとの`'Document`対話のコンテキストで名前が付けられた型パラメーターは、汎用ドキュメント型が、使用している関数またはメンバーによって受け入れられることを明確にします。</span><span class="sxs-lookup"><span data-stu-id="89862-272">For example, a type parameter named `'Document` in the context of interacting with a document database makes it clearer that generic document types can be accepted by the function or member you are working with.</span></span>

* <span data-ttu-id="89862-273">PascalCase を使用してジェネリック型パラメーターの名前を付けることを検討してください。</span><span class="sxs-lookup"><span data-stu-id="89862-273">Consider naming generic type parameters with PascalCase.</span></span>

    <span data-ttu-id="89862-274">これは .NET で行う一般的な方法なので、snake_caseやキャメルケースではなく、PascalCase を使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="89862-274">This is the general way to do things in .NET, so it's recommended that you use PascalCase rather than snake_case or camelCase.</span></span>

<span data-ttu-id="89862-275">最後に、自動汎化は、F# や大規模なコードベースを使い始めた人にとっては、必ずしも恩恵であるとは限りません。</span><span class="sxs-lookup"><span data-stu-id="89862-275">Finally, automatic generalization is not always a boon for people who are new to F# or a large codebase.</span></span> <span data-ttu-id="89862-276">汎用的なコンポーネントを使用する場合には、認知的オーバーヘッドがあります。</span><span class="sxs-lookup"><span data-stu-id="89862-276">There is cognitive overhead in using components that are generic.</span></span> <span data-ttu-id="89862-277">さらに、自動汎用化関数が異なる入力タイプで使用されない場合(もちろん、それらがそのように使用される予定であれば)、その時点でジェネリックであることには本当の利点はありません。</span><span class="sxs-lookup"><span data-stu-id="89862-277">Furthermore, if automatically generalized functions are not used with different input types (let alone if they are intended to be used as such), then there is no real benefit to them being generic at that point in time.</span></span> <span data-ttu-id="89862-278">作成するコードが実際にジェネリックであることからメリットがあるかどうかを常に考慮してください。</span><span class="sxs-lookup"><span data-stu-id="89862-278">Always consider if the code you are writing will actually benefit from being generic.</span></span>

## <a name="performance"></a><span data-ttu-id="89862-279">パフォーマンス</span><span class="sxs-lookup"><span data-stu-id="89862-279">Performance</span></span>

### <a name="prefer-structs-for-small-data-types"></a><span data-ttu-id="89862-280">小さなデータ型の構造体を優先する</span><span class="sxs-lookup"><span data-stu-id="89862-280">Prefer structs for small data types</span></span>

<span data-ttu-id="89862-281">構造体 (Value Types とも呼ばれる) を使用すると、通常はオブジェクトの割り当てを回避するため、一部のコードのパフォーマンスが向上する場合があります。</span><span class="sxs-lookup"><span data-stu-id="89862-281">Using structs (also called Value Types) can often result in higher performance for some code because it typically avoids allocating objects.</span></span> <span data-ttu-id="89862-282">ただし、構造体は常に "高速" ボタンとは限りません: 構造体内のデータのサイズが 16 バイトを超える場合、データをコピーすると、参照型を使用するよりも多くの CPU 時間が消費される場合があります。</span><span class="sxs-lookup"><span data-stu-id="89862-282">However, structs are not always a "go faster" button: if the size of the data in a struct exceeds 16 bytes, copying the data can often result in more CPU time spend than using a reference type.</span></span>

<span data-ttu-id="89862-283">構造体を使用する必要があるかどうかを判断するには、次の条件を考慮してください。</span><span class="sxs-lookup"><span data-stu-id="89862-283">To determine if you should use a struct, consider the following conditions:</span></span>

- <span data-ttu-id="89862-284">データのサイズが 16 バイト以下の場合。</span><span class="sxs-lookup"><span data-stu-id="89862-284">If the size of your data is 16 bytes or smaller.</span></span>
- <span data-ttu-id="89862-285">これらのデータ型の多くが実行中のプログラムのメモリに常駐している可能性がある場合。</span><span class="sxs-lookup"><span data-stu-id="89862-285">If you're likely to have many of these data types resident in memory in a running program.</span></span>

<span data-ttu-id="89862-286">最初の条件が当てはまる場合は、通常は構造体を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="89862-286">If the first condition applies, you should generally use a struct.</span></span> <span data-ttu-id="89862-287">両方を適用する場合は、ほとんどの場合、構造体を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="89862-287">If both apply, you should almost always use a struct.</span></span> <span data-ttu-id="89862-288">前の条件が当てはまる場合もありますが、構造体の使用は参照型を使用するよりも良くも悪くもありませんが、まれに発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="89862-288">There may be some cases where the previous conditions apply, but using a struct is no better or worse than using a reference type, but they are likely to be rare.</span></span> <span data-ttu-id="89862-289">しかし、このような変更を行うときは常に測定し、仮定や直感に基づいて動作しないことが重要です。</span><span class="sxs-lookup"><span data-stu-id="89862-289">It's important to always measure when making changes like this, though, and not operate on assumption or intuition.</span></span>

#### <a name="prefer-struct-tuples-when-grouping-small-value-types"></a><span data-ttu-id="89862-290">小さな値型をグループ化する場合は構造体の組を優先する</span><span class="sxs-lookup"><span data-stu-id="89862-290">Prefer struct tuples when grouping small value types</span></span>

<span data-ttu-id="89862-291">次の 2 つの関数を検討してください。</span><span class="sxs-lookup"><span data-stu-id="89862-291">Consider the following two functions:</span></span>

```fsharp
let rec runWithTuple t offset times =
    let offsetValues x y z offset =
        (x + offset, y + offset, z + offset)

    if times <= 0 then
        t
    else
        let (x, y, z) = t
        let r = offsetValues x y z offset
        runWithTuple r offset (times - 1)

let rec runWithStructTuple t offset times =
    let offsetValues x y z offset =
        struct(x + offset, y + offset, z + offset)

    if times <= 0 then
        t
    else
        let struct(x, y, z) = t
        let r = offsetValues x y z offset
        runWithStructTuple r offset (times - 1)
```

<span data-ttu-id="89862-292">[BenchmarkDotNet](https://benchmarkdotnet.org/)のような統計的ベンチマークツールを使用してこれらの関数をベンチマークすると、構造体の組を使用`runWithStructTuple`する関数は 40% 高速でメモリを割り当てません。</span><span class="sxs-lookup"><span data-stu-id="89862-292">When you benchmark these functions with a statistical benchmarking tool like [BenchmarkDotNet](https://benchmarkdotnet.org/), you'll find that the `runWithStructTuple` function that uses struct tuples runs 40% faster and allocates no memory.</span></span>

<span data-ttu-id="89862-293">ただし、これらの結果は、必ずしも独自のコードに当てはまるとは限りません。</span><span class="sxs-lookup"><span data-stu-id="89862-293">However, these results won't always be the case in your own code.</span></span> <span data-ttu-id="89862-294">関数を`inline`としてマークすると、参照タプルを使用するコードに追加の最適化が行われるか、割り当てるコードを簡単に最適化できます。</span><span class="sxs-lookup"><span data-stu-id="89862-294">If you mark a function as `inline`, code that uses reference tuples may get some additional optimizations, or code that would allocate could simply be optimized away.</span></span> <span data-ttu-id="89862-295">パフォーマンスが懸念される場合は常に結果を測定し、仮定や直感に基づいて決して動作しないでください。</span><span class="sxs-lookup"><span data-stu-id="89862-295">You should always measure results whenever performance is concerned, and never operate based on assumption or intuition.</span></span>

#### <a name="prefer-struct-records-when-the-data-type-is-small"></a><span data-ttu-id="89862-296">データ型が小さい場合は構造体レコードを優先する</span><span class="sxs-lookup"><span data-stu-id="89862-296">Prefer struct records when the data type is small</span></span>

<span data-ttu-id="89862-297">前述の経験則は、 [F# レコードの種類](../language-reference/records.md)にも当てはまる。</span><span class="sxs-lookup"><span data-stu-id="89862-297">The rule of thumb described earlier also holds for [F# record types](../language-reference/records.md).</span></span> <span data-ttu-id="89862-298">それらを処理する次のデータ型と関数を検討してください。</span><span class="sxs-lookup"><span data-stu-id="89862-298">Consider the following data types and functions that process them:</span></span>

```fsharp
type Point = { X: float; Y: float; Z: float }

[<Struct>]
type SPoint = { X: float; Y: float; Z: float }

let rec processPoint (p: Point) offset times =
    let inline offsetValues (p: Point) offset =
        { p with X = p.X + offset; Y = p.Y + offset; Z = p.Z + offset }

    if times <= 0 then
        p
    else
        let r = offsetValues p offset
        processPoint r offset (times - 1)

let rec processStructPoint (p: SPoint) offset times =
    let inline offsetValues (p: SPoint) offset =
        { p with X = p.X + offset; Y = p.Y + offset; Z = p.Z + offset }

    if times <= 0 then
        p
    else
        let r = offsetValues p offset
        processStructPoint r offset (times - 1)
```

<span data-ttu-id="89862-299">これは前のタプルコードと似ていますが、今回の例ではレコードとインライン内部関数を使用しています。</span><span class="sxs-lookup"><span data-stu-id="89862-299">This is similar to the previous tuple code, but this time the example uses records and an inlined inner function.</span></span>

<span data-ttu-id="89862-300">[BenchmarkDotNet](https://benchmarkdotnet.org/)のような統計的ベンチマークツールを使用してこれらの関数をベンチマークすると、60%`processStructPoint`近く高速に実行され、マネージ ヒープに何も割り当てられていないことがわかります。</span><span class="sxs-lookup"><span data-stu-id="89862-300">When you benchmark these functions with a statistical benchmarking tool like [BenchmarkDotNet](https://benchmarkdotnet.org/), you'll find that `processStructPoint` runs nearly 60% faster and allocates nothing on the managed heap.</span></span>

#### <a name="prefer-struct-discriminated-unions-when-the-data-type-is-small"></a><span data-ttu-id="89862-301">データ型が小さい場合は、構造体の判別共用体を優先する</span><span class="sxs-lookup"><span data-stu-id="89862-301">Prefer struct discriminated unions when the data type is small</span></span>

<span data-ttu-id="89862-302">構造体の組とレコードを使用したパフォーマンスに関する以前の観測は[、F# 判別共用体にも当てはめます](../language-reference/discriminated-unions.md)。</span><span class="sxs-lookup"><span data-stu-id="89862-302">The previous observations about performance with struct tuples and records also holds for [F# Discriminated Unions](../language-reference/discriminated-unions.md).</span></span> <span data-ttu-id="89862-303">次のコードについて考えてみましょう。</span><span class="sxs-lookup"><span data-stu-id="89862-303">Consider the following code:</span></span>

```fsharp
    type Name = Name of string

    [<Struct>]
    type SName = SName of string

    let reverseName (Name s) =
        s.ToCharArray()
        |> Array.rev
        |> string
        |> Name

    let structReverseName (SName s) =
        s.ToCharArray()
        |> Array.rev
        |> string
        |> SName
```

<span data-ttu-id="89862-304">ドメイン モデリングでは、単一ケースの判別共用体を次のように定義するのが一般的です。</span><span class="sxs-lookup"><span data-stu-id="89862-304">It's common to define single-case Discriminated Unions like this for domain modeling.</span></span> <span data-ttu-id="89862-305">[BenchmarkDotNet](https://benchmarkdotnet.org/)のような統計的ベンチマークツールを使用してこれらの関数をベンチマークすると、小さな文字列よりも`structReverseName``reverseName`約 25% 高速に実行されることがわかります。</span><span class="sxs-lookup"><span data-stu-id="89862-305">When you benchmark these functions with a statistical benchmarking tool like [BenchmarkDotNet](https://benchmarkdotnet.org/), you'll find that `structReverseName` runs about 25% faster than `reverseName` for small strings.</span></span> <span data-ttu-id="89862-306">大きな文字列の場合、どちらも同じ動作をします。</span><span class="sxs-lookup"><span data-stu-id="89862-306">For large strings, both perform about the same.</span></span> <span data-ttu-id="89862-307">したがって、この場合は、構造体を使用することが常に望ましいです。</span><span class="sxs-lookup"><span data-stu-id="89862-307">So, in this case, it's always preferable to use a struct.</span></span> <span data-ttu-id="89862-308">前述したように、常に測定し、仮定や直感に基づいて動作しません。</span><span class="sxs-lookup"><span data-stu-id="89862-308">As previously mentioned, always measure and do not operate on assumptions or intuition.</span></span>

<span data-ttu-id="89862-309">前の例では、構造体の判別共用体の方がパフォーマンスが向上することが示されましたが、ドメインをモデル化する際に、より大きな判別共用体を持つことは一般的です。</span><span class="sxs-lookup"><span data-stu-id="89862-309">Although the previous example showed that a struct Discriminated Union yielded better performance, it is common to have larger Discriminated Unions when modeling a domain.</span></span> <span data-ttu-id="89862-310">そのような大きなデータ型は、より多くのコピーが必要になる可能性があるため、構造体の場合は、その操作によってはうまく機能しない場合があります。</span><span class="sxs-lookup"><span data-stu-id="89862-310">Larger data types like that may not perform as well if they are structs depending on the operations on them, since more copying could be involved.</span></span>

### <a name="functional-programming-and-mutation"></a><span data-ttu-id="89862-311">関数型プログラミングと変異</span><span class="sxs-lookup"><span data-stu-id="89862-311">Functional programming and mutation</span></span>

<span data-ttu-id="89862-312">F# 値は既定で変更不可であり、特定のクラスのバグ (特に同時実行と並列処理を伴うバグ) を回避できます。</span><span class="sxs-lookup"><span data-stu-id="89862-312">F# values are immutable by default, which allows you to avoid certain classes of bugs (especially those involving concurrency and parallelism).</span></span> <span data-ttu-id="89862-313">しかし、特定の場合において、実行時間またはメモリ割り当ての最適な(あるいは合理的な)効率を達成するために、作業のスパンは、インプレース状態の突然変異を使用して最適に実装することができる。</span><span class="sxs-lookup"><span data-stu-id="89862-313">However, in certain cases, in order to achieve optimal (or even reasonable) efficiency of execution time or memory allocations, a span of work may best be implemented by using in-place mutation of state.</span></span> <span data-ttu-id="89862-314">これは、キーワードを使用して F# を使用したオ`mutable`プトインベースで可能です。</span><span class="sxs-lookup"><span data-stu-id="89862-314">This is possible in an opt-in basis with F# with the `mutable` keyword.</span></span>

<span data-ttu-id="89862-315">F#`mutable`での使用は、機能的な純度と対立する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="89862-315">Use of `mutable` in F# may feel at odds with functional purity.</span></span> <span data-ttu-id="89862-316">これは理解できますが、機能純度はどこでもパフォーマンス目標と対立する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="89862-316">This is understandable, but functional purity everywhere can be at odds with performance goals.</span></span> <span data-ttu-id="89862-317">妥協点は、呼び出し元が関数を呼び出したときに何が起こるかを気にする必要がないように、変異をカプセル化することです。</span><span class="sxs-lookup"><span data-stu-id="89862-317">A compromise is to encapsulate mutation such that callers need not care about what happens when they call a function.</span></span> <span data-ttu-id="89862-318">これにより、パフォーマンスに重要なコードの変異ベースの実装を介して機能インターフェイスを記述できます。</span><span class="sxs-lookup"><span data-stu-id="89862-318">This allows you to write a functional interface over a mutation-based implementation for performance-critical code.</span></span>

#### <a name="wrap-mutable-code-in-immutable-interfaces"></a><span data-ttu-id="89862-319">変更できないインターフェイスでの変更可能なコードのラップ</span><span class="sxs-lookup"><span data-stu-id="89862-319">Wrap mutable code in immutable interfaces</span></span>

<span data-ttu-id="89862-320">参照の透明性を目標として使用する場合、パフォーマンスに重要な関数の変更可能な下腹を公開しないコードを記述することが重要です。</span><span class="sxs-lookup"><span data-stu-id="89862-320">With referential transparency as a goal, it is critical to write code that does not expose the mutable underbelly of performance-critical functions.</span></span> <span data-ttu-id="89862-321">たとえば、次のコードは、F#`Array.contains`コア ライブラリに関数を実装します。</span><span class="sxs-lookup"><span data-stu-id="89862-321">For example, the following code implements the `Array.contains` function in the F# core library:</span></span>

```fsharp
[<CompiledName("Contains")>]
let inline contains value (array:'T[]) =
    checkNonNull "array" array
    let mutable state = false
    let mutable i = 0
    while not state && i < array.Length do
        state <- value = array.[i]
        i <- i + 1
    state
```

<span data-ttu-id="89862-322">この関数を複数回呼び出しても、基になる配列は変更されず、また、それを使用する際に変更可能な状態を維持する必要もありません。</span><span class="sxs-lookup"><span data-stu-id="89862-322">Calling this function multiple times does not change the underlying array, nor does it require you to maintain any mutable state in consuming it.</span></span> <span data-ttu-id="89862-323">これは、その中のほとんどすべてのコード行がミューテーションを使用しているにもかかわらず、参照的に透過的です。</span><span class="sxs-lookup"><span data-stu-id="89862-323">It is referentially transparent, even though almost every line of code within it uses mutation.</span></span>

#### <a name="consider-encapsulating-mutable-data-in-classes"></a><span data-ttu-id="89862-324">クラスに変更可能なデータをカプセル化することを検討してください</span><span class="sxs-lookup"><span data-stu-id="89862-324">Consider encapsulating mutable data in classes</span></span>

<span data-ttu-id="89862-325">前の例では、1 つの関数を使用して、変更可能なデータを使用して操作をカプセル化しました。</span><span class="sxs-lookup"><span data-stu-id="89862-325">The previous example used a single function to encapsulate operations using mutable data.</span></span> <span data-ttu-id="89862-326">複雑なデータセットでは、この方法で十分ではありません。</span><span class="sxs-lookup"><span data-stu-id="89862-326">This is not always sufficient for more complex sets of data.</span></span> <span data-ttu-id="89862-327">次の関数のセットを検討してください。</span><span class="sxs-lookup"><span data-stu-id="89862-327">Consider the following sets of functions:</span></span>

```fsharp
open System.Collections.Generic

let addToClosureTable (key, value) (t: Dictionary<_,_>) =
    if not (t.ContainsKey(key)) then
        t.Add(key, value)
    else
        t.[key] <- value

let closureTableCount (t: Dictionary<_,_>) = t.Count

let closureTableContains (key, value) (t: Dictionary<_, HashSet<_>>) =
    match t.TryGetValue(key) with
    | (true, v) -> v.Equals(value)
    | (false, _) -> false
```

<span data-ttu-id="89862-328">このコードはパフォーマンスが高いが、呼び出し元が管理する必要がある、変更に基づくデータ構造を公開します。</span><span class="sxs-lookup"><span data-stu-id="89862-328">This code is performant, but it exposes the mutation-based data structure that callers are responsible for maintaining.</span></span> <span data-ttu-id="89862-329">これは、変更できる基になるメンバーがないクラスの内部でラップできます。</span><span class="sxs-lookup"><span data-stu-id="89862-329">This can be wrapped inside of a class with no underlying members that can change:</span></span>

```fsharp
open System.Collections.Generic

/// The results of computing the LALR(1) closure of an LR(0) kernel
type Closure1Table() =
    let t = Dictionary<Item0, HashSet<TerminalIndex>>()

    member _.Add(key, value) =
        if not (t.ContainsKey(key)) then
            t.Add(key, value)
        else
            t.[key] <- value

    member _.Count = t.Count

    member _.Contains(key, value) =
        match t.TryGetValue(key) with
        | (true, v) -> v.Equals(value)
        | (false, _) -> false
```

<span data-ttu-id="89862-330">`Closure1Table`は、基になる変異ベースのデータ構造をカプセル化するため、呼び出し元が基になるデータ構造を維持することを強制しません。</span><span class="sxs-lookup"><span data-stu-id="89862-330">`Closure1Table` encapsulates the underlying mutation-based data structure, thereby not forcing callers to maintain the underlying data structure.</span></span> <span data-ttu-id="89862-331">クラスは、呼び出し元に詳細を公開せずに、変更に基づくデータとルーチンをカプセル化する強力な方法です。</span><span class="sxs-lookup"><span data-stu-id="89862-331">Classes are a powerful way to encapsulate data and routines that are mutation-based without exposing the details to callers.</span></span>

#### <a name="prefer-let-mutable-to-reference-cells"></a><span data-ttu-id="89862-332">参照`let mutable`セルを優先する</span><span class="sxs-lookup"><span data-stu-id="89862-332">Prefer `let mutable` to reference cells</span></span>

<span data-ttu-id="89862-333">参照セルは、値自体ではなく、値への参照を表す方法です。</span><span class="sxs-lookup"><span data-stu-id="89862-333">Reference cells are a way to represent the reference to a value rather than the value itself.</span></span> <span data-ttu-id="89862-334">パフォーマンスに重要なコードに使用できますが、推奨されません。</span><span class="sxs-lookup"><span data-stu-id="89862-334">Although they can be used for performance-critical code, they are not recommended.</span></span> <span data-ttu-id="89862-335">次の例を確認してください。</span><span class="sxs-lookup"><span data-stu-id="89862-335">Consider the following example:</span></span>

```fsharp
let kernels =
    let acc = ref Set.empty

    processWorkList startKernels (fun kernel ->
        if not ((!acc).Contains(kernel)) then
            acc := (!acc).Add(kernel)
        ...)

    !acc |> Seq.toList
```

<span data-ttu-id="89862-336">参照セルの使用は、基礎となるデータを逆参照して再参照する必要がある、後続のすべてのコードを「汚染」するようになりました。</span><span class="sxs-lookup"><span data-stu-id="89862-336">The use of a reference cell now "pollutes" all subsequent code with having to dereference and re-reference the underlying data.</span></span> <span data-ttu-id="89862-337">代わりに、`let mutable`次の点を考慮してください。</span><span class="sxs-lookup"><span data-stu-id="89862-337">Instead, consider `let mutable`:</span></span>

```fsharp
let kernels =
    let mutable acc = Set.empty

    processWorkList startKernels (fun kernel ->
        if not (acc.Contains(kernel)) then
            acc <- acc.Add(kernel)
        ...)

    acc |> Seq.toList
```

<span data-ttu-id="89862-338">ラムダ式の途中での単一の変異点を除いて、タッチ`acc`する他のすべてのコードは、通常`let`バインドされた不変値の使用法と変わらない方法で行うことができます。</span><span class="sxs-lookup"><span data-stu-id="89862-338">Aside from the single point of mutation in the middle of the lambda expression, all other code that touches `acc` can do so in a manner that is no different to the usage of a normal `let`-bound immutable value.</span></span> <span data-ttu-id="89862-339">これにより、時間の経過と同時に変更が容易になります。</span><span class="sxs-lookup"><span data-stu-id="89862-339">This will make it easier to change over time.</span></span>

## <a name="object-programming"></a><span data-ttu-id="89862-340">オブジェクトプログラミング</span><span class="sxs-lookup"><span data-stu-id="89862-340">Object programming</span></span>

<span data-ttu-id="89862-341">F# は、オブジェクトとオブジェクト指向 (OO) の概念を完全にサポートしています。</span><span class="sxs-lookup"><span data-stu-id="89862-341">F# has full support for objects and object-oriented (OO) concepts.</span></span> <span data-ttu-id="89862-342">多くの OO 概念は強力で便利ですが、すべての概念が使用に適しているわけではありません。</span><span class="sxs-lookup"><span data-stu-id="89862-342">Although many OO concepts are powerful and useful, not all of them are ideal to use.</span></span> <span data-ttu-id="89862-343">以下のリストは、OO 機能のカテゴリに関する概要を示しています。</span><span class="sxs-lookup"><span data-stu-id="89862-343">The following lists offer guidance on categories of OO features at a high level.</span></span>

<span data-ttu-id="89862-344">**これらの機能は、多くの状況で使用することを検討してください。**</span><span class="sxs-lookup"><span data-stu-id="89862-344">**Consider using these features in many situations:**</span></span>

* <span data-ttu-id="89862-345">ドット表記 (`x.Length`)</span><span class="sxs-lookup"><span data-stu-id="89862-345">Dot notation (`x.Length`)</span></span>
* <span data-ttu-id="89862-346">インスタンス メンバー</span><span class="sxs-lookup"><span data-stu-id="89862-346">Instance members</span></span>
* <span data-ttu-id="89862-347">暗黙的コンストラクター</span><span class="sxs-lookup"><span data-stu-id="89862-347">Implicit constructors</span></span>
* <span data-ttu-id="89862-348">静的メンバー</span><span class="sxs-lookup"><span data-stu-id="89862-348">Static members</span></span>
* <span data-ttu-id="89862-349">インデクサー表記`arr.[x]`( )</span><span class="sxs-lookup"><span data-stu-id="89862-349">Indexer notation (`arr.[x]`)</span></span>
* <span data-ttu-id="89862-350">名前付き引数とオプション引数</span><span class="sxs-lookup"><span data-stu-id="89862-350">Named and Optional arguments</span></span>
* <span data-ttu-id="89862-351">インターフェイスとインターフェイスの実装</span><span class="sxs-lookup"><span data-stu-id="89862-351">Interfaces and interface implementations</span></span>

<span data-ttu-id="89862-352">**最初にこれらの機能に手を伸ばさないでくださいが、問題を解決するのに便利なときに慎重に適用してください。**</span><span class="sxs-lookup"><span data-stu-id="89862-352">**Don't reach for these features first, but do judiciously apply them when they are convenient to solve a problem:**</span></span>

* <span data-ttu-id="89862-353">メソッドのオーバーロード</span><span class="sxs-lookup"><span data-stu-id="89862-353">Method overloading</span></span>
* <span data-ttu-id="89862-354">カプセル化された変更可能データ</span><span class="sxs-lookup"><span data-stu-id="89862-354">Encapsulated mutable data</span></span>
* <span data-ttu-id="89862-355">型の演算子</span><span class="sxs-lookup"><span data-stu-id="89862-355">Operators on types</span></span>
* <span data-ttu-id="89862-356">自動プロパティ</span><span class="sxs-lookup"><span data-stu-id="89862-356">Auto properties</span></span>
* <span data-ttu-id="89862-357">実装`IDisposable`と`IEnumerable`</span><span class="sxs-lookup"><span data-stu-id="89862-357">Implementing `IDisposable` and `IEnumerable`</span></span>
* <span data-ttu-id="89862-358">型の拡張機能</span><span class="sxs-lookup"><span data-stu-id="89862-358">Type extensions</span></span>
* <span data-ttu-id="89862-359">events</span><span class="sxs-lookup"><span data-stu-id="89862-359">Events</span></span>
* <span data-ttu-id="89862-360">構造体</span><span class="sxs-lookup"><span data-stu-id="89862-360">Structs</span></span>
* <span data-ttu-id="89862-361">デリゲート</span><span class="sxs-lookup"><span data-stu-id="89862-361">Delegates</span></span>
* <span data-ttu-id="89862-362">列挙型</span><span class="sxs-lookup"><span data-stu-id="89862-362">Enums</span></span>

<span data-ttu-id="89862-363">**通常、これらの機能は、次の機能を使用する必要がない限り、使用しないでください。**</span><span class="sxs-lookup"><span data-stu-id="89862-363">**Generally avoid these features unless you must use them:**</span></span>

* <span data-ttu-id="89862-364">継承ベースの型階層と実装の継承</span><span class="sxs-lookup"><span data-stu-id="89862-364">Inheritance-based type hierarchies and implementation inheritance</span></span>
* <span data-ttu-id="89862-365">ヌルと`Unchecked.defaultof<_>`</span><span class="sxs-lookup"><span data-stu-id="89862-365">Nulls and `Unchecked.defaultof<_>`</span></span>

### <a name="prefer-composition-over-inheritance"></a><span data-ttu-id="89862-366">継承よりもコンポジションを優先する</span><span class="sxs-lookup"><span data-stu-id="89862-366">Prefer composition over inheritance</span></span>

<span data-ttu-id="89862-367">[継承に対する合成](https://en.wikipedia.org/wiki/Composition_over_inheritance)は、優れた F# コードが従うことができる長年の慣用句です。</span><span class="sxs-lookup"><span data-stu-id="89862-367">[Composition over inheritance](https://en.wikipedia.org/wiki/Composition_over_inheritance) is a long-standing idiom that good F# code can adhere to.</span></span> <span data-ttu-id="89862-368">基本原則は、基本クラスを公開せず、機能を取得するために呼び出し元にその基本クラスから継承させる必要があります。</span><span class="sxs-lookup"><span data-stu-id="89862-368">The fundamental principle is that you should not expose a base class and force callers to inherit from that base class to get functionality.</span></span>

### <a name="use-object-expressions-to-implement-interfaces-if-you-dont-need-a-class"></a><span data-ttu-id="89862-369">クラスが必要ない場合は、オブジェクト式を使用してインターフェイスを実装する</span><span class="sxs-lookup"><span data-stu-id="89862-369">Use object expressions to implement interfaces if you don't need a class</span></span>

<span data-ttu-id="89862-370">[オブジェクト式](../language-reference/object-expressions.md)を使用すると、インターフェイスを実行時に実装し、実装されたインターフェイスをクラス内で行う必要なく値にバインドできます。</span><span class="sxs-lookup"><span data-stu-id="89862-370">[Object Expressions](../language-reference/object-expressions.md) allow you to implement interfaces on the fly, binding the implemented interface to a value without needing to do so inside of a class.</span></span> <span data-ttu-id="89862-371">これは、特にインターフェイスを実装する必要_があり_、フル クラスを必要としない場合に便利です。</span><span class="sxs-lookup"><span data-stu-id="89862-371">This is convenient, especially if you _only_ need to implement the interface and have no need for a full class.</span></span>

<span data-ttu-id="89862-372">たとえば、次のコードは、`open`ステートメントがないシンボルを追加した場合にコード修正アクションを提供するために[Ionide](http://ionide.io/)で実行されます。</span><span class="sxs-lookup"><span data-stu-id="89862-372">For example, here is the code that is run in [Ionide](http://ionide.io/) to provide a code fix action if you've added a symbol that you don't have an `open` statement for:</span></span>

```fsharp
    let private createProvider () =
        { new CodeActionProvider with
            member this.provideCodeActions(doc, range, context, ct) =
                let diagnostics = context.diagnostics
                let diagnostic = diagnostics |> Seq.tryFind (fun d -> d.message.Contains "Unused open statement")
                let res =
                    match diagnostic with
                    | None -> [||]
                    | Some d ->
                        let line = doc.lineAt d.range.start.line
                        let cmd = createEmpty<Command>
                        cmd.title <- "Remove unused open"
                        cmd.command <- "fsharp.unusedOpenFix"
                        cmd.arguments <- Some ([| doc |> unbox; line.range |> unbox; |] |> ResizeArray)
                        [|cmd |]
                res
                |> ResizeArray
                |> U2.Case1
        }
```

<span data-ttu-id="89862-373">Visual Studio コード API を操作する際にクラスを使用する必要がないため、オブジェクト式はこれに最適なツールです。</span><span class="sxs-lookup"><span data-stu-id="89862-373">Because there is no need for a class when interacting with the Visual Studio Code API, Object Expressions are an ideal tool for this.</span></span> <span data-ttu-id="89862-374">また、テスト ルーチンを使用するインターフェイスをアドホックにスタブアウトする場合は、単体テストにも役立ちます。</span><span class="sxs-lookup"><span data-stu-id="89862-374">They are also valuable for unit testing, when you want to stub out an interface with test routines in an ad hoc manner.</span></span>

## <a name="consider-type-abbreviations-to-shorten-signatures"></a><span data-ttu-id="89862-375">署名を短くする型の省略形を考慮する</span><span class="sxs-lookup"><span data-stu-id="89862-375">Consider Type Abbreviations to shorten signatures</span></span>

<span data-ttu-id="89862-376">[型省略形](../language-reference/type-abbreviations.md)は、関数シグネチャや複雑な型など、別の型にラベルを割り当てるのに便利な方法です。</span><span class="sxs-lookup"><span data-stu-id="89862-376">[Type Abbreviations](../language-reference/type-abbreviations.md) are a convenient way to assign a label to another type, such as a function signature or a more complex type.</span></span> <span data-ttu-id="89862-377">たとえば、次のエイリアスは、ディープ ラーニング ライブラリである[CNTK](https://docs.microsoft.com/cognitive-toolkit/)で計算を定義するために必要な情報にラベルを割り当てます。</span><span class="sxs-lookup"><span data-stu-id="89862-377">For example, the following alias assigns a label to what's needed to define a computation with [CNTK](https://docs.microsoft.com/cognitive-toolkit/), a deep learning library:</span></span>

```fsharp
open CNTK

// DeviceDescriptor, Variable, and Function all come from CNTK
type Computation = DeviceDescriptor -> Variable -> Function
```

<span data-ttu-id="89862-378">この`Computation`名前は、エイリアス化しているシグネチャに一致する関数を表す便利な方法です。</span><span class="sxs-lookup"><span data-stu-id="89862-378">The `Computation` name is a convenient way to denote any function that matches the signature it is aliasing.</span></span> <span data-ttu-id="89862-379">このような型の略語を使用すると便利で、より簡潔なコードが可能になります。</span><span class="sxs-lookup"><span data-stu-id="89862-379">Using Type Abbreviations like this is convenient and allows for more succinct code.</span></span>

### <a name="avoid-using-type-abbreviations-to-represent-your-domain"></a><span data-ttu-id="89862-380">ドメインを表す型の省略形を使用しないようにする</span><span class="sxs-lookup"><span data-stu-id="89862-380">Avoid using Type Abbreviations to represent your domain</span></span>

<span data-ttu-id="89862-381">型の省略形は関数シグネチャに名前を付ける場合に便利ですが、他の型を省略すると混乱する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="89862-381">Although Type Abbreviations are convenient for giving a name to function signatures, they can be confusing when abbreviating other types.</span></span> <span data-ttu-id="89862-382">次の省略形を考えてみましょう。</span><span class="sxs-lookup"><span data-stu-id="89862-382">Consider this abbreviation:</span></span>

```fsharp
// Does not actually abstract integers.
type BufferSize = int
```

<span data-ttu-id="89862-383">これは、複数の方法で混乱を招く可能性があります。</span><span class="sxs-lookup"><span data-stu-id="89862-383">This can be confusing in multiple ways:</span></span>

* <span data-ttu-id="89862-384">`BufferSize`は抽象化ではありません。これは整数の別の名前にすぎません。</span><span class="sxs-lookup"><span data-stu-id="89862-384">`BufferSize` is not an abstraction; it is just another name for an integer.</span></span>
* <span data-ttu-id="89862-385">パブリック`BufferSize`API で公開されている場合、単なる`int`意味以上の意味を持つ可能性が簡単に誤って解釈される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="89862-385">If `BufferSize` is exposed in a public API, it can easily be misinterpreted to mean more than just `int`.</span></span> <span data-ttu-id="89862-386">一般に、ドメイン型には複数の属性があり、 のような`int`プリミティブ型ではありません。</span><span class="sxs-lookup"><span data-stu-id="89862-386">Generally, domain types have multiple attributes to them and are not primitive types like `int`.</span></span> <span data-ttu-id="89862-387">この省略形は、その仮定に違反します。</span><span class="sxs-lookup"><span data-stu-id="89862-387">This abbreviation violates that assumption.</span></span>
* <span data-ttu-id="89862-388">(PascalCase) の`BufferSize`大文字と小文字は、この型がより多くのデータを保持することを意味します。</span><span class="sxs-lookup"><span data-stu-id="89862-388">The casing of `BufferSize` (PascalCase) implies that this type holds more data.</span></span>
* <span data-ttu-id="89862-389">このエイリアスは、関数に名前付き引数を指定する場合と比較して、明確性を高めるものではありません。</span><span class="sxs-lookup"><span data-stu-id="89862-389">This alias does not offer increased clarity compared with providing a named argument to a function.</span></span>
* <span data-ttu-id="89862-390">省略形はコンパイルされた IL では現われません。これは単なる整数であり、このエイリアスはコンパイル時の構成要素です。</span><span class="sxs-lookup"><span data-stu-id="89862-390">The abbreviation will not manifest in compiled IL; it is just an integer and this alias is a compile-time construct.</span></span>

```fsharp
module Networking =
    ...
    let send data (bufferSize: int) = ...
```

<span data-ttu-id="89862-391">要約すると、型の省略形の落とし穴は、それらが省略型の型に対する抽象化**ではない**ということです。</span><span class="sxs-lookup"><span data-stu-id="89862-391">In summary, the pitfall with Type Abbreviations is that they are **not** abstractions over the types they are abbreviating.</span></span> <span data-ttu-id="89862-392">前の例では、`BufferSize`追加のデータ`int`がなく、すでに持っているもの`int`以外にも型システムからの利点を持たない、ただのカバーの下にあります。</span><span class="sxs-lookup"><span data-stu-id="89862-392">In the previous example, `BufferSize` is just an `int` under the covers, with no additional data, nor any benefits from the type system besides what `int` already has.</span></span>

<span data-ttu-id="89862-393">型の省略形を使用してドメインを表す方法として、単一ケースの判別共用体を使用する方法があります。</span><span class="sxs-lookup"><span data-stu-id="89862-393">An alternative approach to using type abbreviations to represent a domain is to use single-case discriminated unions.</span></span> <span data-ttu-id="89862-394">前のサンプルは次のようにモデリングできます。</span><span class="sxs-lookup"><span data-stu-id="89862-394">The previous sample can be modeled as follows:</span></span>

```fsharp
type BufferSize = BufferSize of int
```

<span data-ttu-id="89862-395">の値と基になる値の観点から`BufferSize`動作するコードを記述する場合は、任意の整数を渡すのではなく、1 つを構築する必要があります。</span><span class="sxs-lookup"><span data-stu-id="89862-395">If you write code that operates in terms of `BufferSize` and its underlying value, you need to construct one rather than pass in any arbitrary integer:</span></span>

```fsharp
module Networking =
    ...
    let send data (BufferSize size) =
    ...
```

<span data-ttu-id="89862-396">これにより、呼び出し元が関数を呼び出`send`す前に値をラップする型`BufferSize`を構築する必要があるため、関数に誤って任意の整数を渡す可能性が低くなります。</span><span class="sxs-lookup"><span data-stu-id="89862-396">This reduces the likelihood of mistakenly passing an arbitrary integer into the `send` function, because the caller must construct a `BufferSize` type to wrap a value before calling the function.</span></span>
