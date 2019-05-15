---
title: 新機能F#
description: どのような F# プログラミング言語とはなどの F# プログラミングについて説明します。 豊富なデータ型、関数、およびそれらをまとめる方法について説明します。
ms.date: 08/03/2018
ms.openlocfilehash: 9d5b0de9828aa91857d3961bf7d40c02c344adaa
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/15/2019
ms.locfileid: "65641569"
---
# <a name="what-is-f"></a><span data-ttu-id="4f6ec-104">F とは\#</span><span class="sxs-lookup"><span data-stu-id="4f6ec-104">What is F\#</span></span>

<span data-ttu-id="4f6ec-105">F#関数型プログラミング言語を適切な保守しやすいコードを記述するが容易にするにです。</span><span class="sxs-lookup"><span data-stu-id="4f6ec-105">F# is a functional programming language that makes it easy to write correct and maintainable code.</span></span>

<span data-ttu-id="4f6ec-106">F#主にプログラミングするには、型と型推論され、自動的に汎用化されている関数を定義する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4f6ec-106">F# programming primarily involves defining types and functions that are type-inferred and generalized automatically.</span></span> <span data-ttu-id="4f6ec-107">これにより、問題のドメインとプログラミングの詳細ではなく、そのデータの操作上に残すに専念できます。</span><span class="sxs-lookup"><span data-stu-id="4f6ec-107">This allows your focus to remain on the problem domain and manipulating its data, rather than the details of programming.</span></span>

```fsharp
open System // Gets access to functionality in System namespace.

// Defines a function that takes a name and produces a greeting.
let getGreeting name =
    sprintf "Hello, %s! Isn't F# great?" name

[<EntryPoint>]
let main args =
    // Defines a list of names
    let names = [ "Don"; "Julia"; "Xi" ]

    // Prints a greeting for each name!
    names
    |> List.map getGreeting
    |> List.iter (fun greeting -> printfn "%s" greeting)

    0
```

<span data-ttu-id="4f6ec-108">F#など、多数の機能があります。</span><span class="sxs-lookup"><span data-stu-id="4f6ec-108">F# has numerous features, including:</span></span>

* <span data-ttu-id="4f6ec-109">軽量構文</span><span class="sxs-lookup"><span data-stu-id="4f6ec-109">Lightweight syntax</span></span>
* <span data-ttu-id="4f6ec-110">既定では変更できません。</span><span class="sxs-lookup"><span data-stu-id="4f6ec-110">Immutable by default</span></span>
* <span data-ttu-id="4f6ec-111">型の推論と自動ジェネリック化</span><span class="sxs-lookup"><span data-stu-id="4f6ec-111">Type inference and automatic generalization</span></span>
* <span data-ttu-id="4f6ec-112">ファーストクラス関数</span><span class="sxs-lookup"><span data-stu-id="4f6ec-112">First-class functions</span></span>
* <span data-ttu-id="4f6ec-113">強力なデータ型</span><span class="sxs-lookup"><span data-stu-id="4f6ec-113">Powerful data types</span></span>
* <span data-ttu-id="4f6ec-114">パターン マッチング</span><span class="sxs-lookup"><span data-stu-id="4f6ec-114">Pattern matching</span></span>
* <span data-ttu-id="4f6ec-115">非同期プログラミング</span><span class="sxs-lookup"><span data-stu-id="4f6ec-115">Async programming</span></span>

<span data-ttu-id="4f6ec-116">機能の完全なセットが記載されて、 [F# 言語リファレンス](language-reference/index.md)します。</span><span class="sxs-lookup"><span data-stu-id="4f6ec-116">A full set of features are documented in the [F# language reference](language-reference/index.md).</span></span>

## <a name="rich-data-types"></a><span data-ttu-id="4f6ec-117">豊富なデータ型</span><span class="sxs-lookup"><span data-stu-id="4f6ec-117">Rich data types</span></span>

<span data-ttu-id="4f6ec-118">などのデータ型[レコード](language-reference/records.md)と[判別共用体](language-reference/discriminated-unions.md)複雑なデータとドメインを表現することができます。</span><span class="sxs-lookup"><span data-stu-id="4f6ec-118">Data types such as [Records](language-reference/records.md) and [Discriminated Unions](language-reference/discriminated-unions.md) let you represent complex data and domains.</span></span>

```fsharp
// Group data with Records
type SuccessfulWithdrawal = {
    Amount: decimal
    Balance: decimal
}

type FailedWithdrawal = {
    Amount: decimal
    Balance: decimal
    IsOverdraft: bool
}

// Use discriminated unions to represent data of 1 or more forms
type WithdrawalResult =
    | Success of SuccessfulWithdrawal
    | InsufficientFunds of FailedWithdrawal
    | CardExpired of System.DateTime
    | UndisclosedFailure
```

<span data-ttu-id="4f6ec-119">F#レコード、判別共用体は、null 以外、変更できない、および簡単に使用できるように、既定では同等です。</span><span class="sxs-lookup"><span data-stu-id="4f6ec-119">F# records and discriminated unions are non-null, immutable, and comparable by default, making them very easy to use.</span></span>

## <a name="enforced-correctness-with-functions-and-pattern-matching"></a><span data-ttu-id="4f6ec-120">関数およびパターン マッチングで正確性を強制</span><span class="sxs-lookup"><span data-stu-id="4f6ec-120">Enforced correctness with functions and pattern matching</span></span>

<span data-ttu-id="4f6ec-121">F#関数は、宣言する簡単で実際には強力です。</span><span class="sxs-lookup"><span data-stu-id="4f6ec-121">F# functions are easy to declare and powerful in practice.</span></span> <span data-ttu-id="4f6ec-122">組み合わせると[パターン マッチング](language-reference/pattern-matching.md)コンパイラが正確性が適用される動作を定義することができます。</span><span class="sxs-lookup"><span data-stu-id="4f6ec-122">When combined with [pattern matching](language-reference/pattern-matching.md), they allow you to define behavior whose correctness is enforced by the compiler.</span></span>

```fsharp
// Returns a WithdrawalResult
let withdrawMoney amount = // Implementation elided

let handleWithdrawal amount =
    let w = withdrawMoney amount

    // The F# compiler enforces accounting for each case!
    match w with
    | Success s -> printfn "Successfully withdrew %f" s.Amount
    | InsufficientFunds f -> printfn "Failed: balance is %f" f.Balance
    | CardExpired d -> printfn "Failed: card expired on %O" d
    | UndisclosedFailure -> printfn "Failed: unknown :("
```

<span data-ttu-id="4f6ec-123">F#関数は、ファースト クラス、つまりパラメーターとして渡され、その他の関数から返されることができますも。</span><span class="sxs-lookup"><span data-stu-id="4f6ec-123">F# functions are also first-class, meaning they can be passed as parameters and returned from other functions.</span></span>

## <a name="functions-to-define-operations-on-objects"></a><span data-ttu-id="4f6ec-124">オブジェクトに対する操作を定義する関数</span><span class="sxs-lookup"><span data-stu-id="4f6ec-124">Functions to define operations on objects</span></span>

<span data-ttu-id="4f6ec-125">F#有用なデータ型は、blend のデータと機能する必要がある場合、オブジェクトの完全サポートしています。</span><span class="sxs-lookup"><span data-stu-id="4f6ec-125">F# has full support for objects, which are useful data types when you need to blend data and functionality.</span></span> <span data-ttu-id="4f6ec-126">F#オブジェクトを操作する関数が使用されます。</span><span class="sxs-lookup"><span data-stu-id="4f6ec-126">F# functions are used to manipulate objects.</span></span>

```fsharp
type Set<[<EqualityConditionOn>] ‘T when ‘T: comparison>(elements: seq<'T>) =
    member s.IsEmpty = // Implementation elided
    member s.Contains (value) =// Implementation elided
    member s.Add (value) = // Implementation elided
    // ...
    // Further Implementation elided
    // ...
    interface IEnumerable<‘T>
    interface IReadOnlyCollection<‘T>

[<RequireQualifiedAccess>]
module Set =
    let isEmpty (set: Set<'T>) = set.IsEmpty

    let contains element (set: Set<'T>) = set.Contains(element)

    let add value (set: Set<'T>) = set.Add(value)
```

<span data-ttu-id="4f6ec-127">内のオブジェクト指向コードを記述するのではなくF#、オブジェクトを操作する関数として別のデータ型を処理するコードを記述する多くの場合。</span><span class="sxs-lookup"><span data-stu-id="4f6ec-127">Rather than writing code that is object-oriented, in F#, you will often write code that treats objects as another data type for functions to manipulate.</span></span> <span data-ttu-id="4f6ec-128">などの機能[ジェネリック インターフェイス](language-reference/interfaces.md)、[オブジェクト式](language-reference/object-expressions.md)とを賢く利用[メンバー](language-reference/members/index.md)は大規模な F# プログラムでは一般的です。</span><span class="sxs-lookup"><span data-stu-id="4f6ec-128">Features such as [generic interfaces](language-reference/interfaces.md), [object expressions](language-reference/object-expressions.md), and judicious use of [members](language-reference/members/index.md) are common in larger F# programs.</span></span>

## <a name="next-steps"></a><span data-ttu-id="4f6ec-129">次の手順</span><span class="sxs-lookup"><span data-stu-id="4f6ec-129">Next steps</span></span>

<span data-ttu-id="4f6ec-130">多数の F# の機能の詳細については、チェック アウト、 [F# のツアー](tour.md)します。</span><span class="sxs-lookup"><span data-stu-id="4f6ec-130">To learn more about a larger set of F# features, check out the [F# Tour](tour.md).</span></span>
