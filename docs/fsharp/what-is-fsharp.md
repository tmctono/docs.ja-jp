---
title: F# とは
description: どのような F# プログラミング言語とはなどの F# プログラミングについて説明します。 豊富なデータ型、関数、およびそれらがどのように組み合わされているかについて説明します。
ms.date: 08/03/2018
ms.openlocfilehash: 0c576fe49fadebd68e4fc9d2b20ea8f0cb991af5
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/30/2019
ms.locfileid: "68630463"
---
# <a name="what-is-f"></a><span data-ttu-id="bf603-104">F とは\#</span><span class="sxs-lookup"><span data-stu-id="bf603-104">What is F\#</span></span>

<span data-ttu-id="bf603-105">F#は、適切で保守が容易なコードを簡単に記述できるようにする関数型プログラミング言語です。</span><span class="sxs-lookup"><span data-stu-id="bf603-105">F# is a functional programming language that makes it easy to write correct and maintainable code.</span></span>

<span data-ttu-id="bf603-106">F#プログラミングでは、主に、型が推論され、自動的に一般化される型と関数を定義する必要があります。</span><span class="sxs-lookup"><span data-stu-id="bf603-106">F# programming primarily involves defining types and functions that are type-inferred and generalized automatically.</span></span> <span data-ttu-id="bf603-107">これにより、プログラミングの詳細ではなく、問題のドメインにとどまり、そのデータを操作することができます。</span><span class="sxs-lookup"><span data-stu-id="bf603-107">This allows your focus to remain on the problem domain and manipulating its data, rather than the details of programming.</span></span>

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

<span data-ttu-id="bf603-108">F#には、次のようなさまざまな機能があります。</span><span class="sxs-lookup"><span data-stu-id="bf603-108">F# has numerous features, including:</span></span>

* <span data-ttu-id="bf603-109">簡易構文</span><span class="sxs-lookup"><span data-stu-id="bf603-109">Lightweight syntax</span></span>
* <span data-ttu-id="bf603-110">既定で変更不可</span><span class="sxs-lookup"><span data-stu-id="bf603-110">Immutable by default</span></span>
* <span data-ttu-id="bf603-111">型の推論と自動汎化</span><span class="sxs-lookup"><span data-stu-id="bf603-111">Type inference and automatic generalization</span></span>
* <span data-ttu-id="bf603-112">ファーストクラス関数</span><span class="sxs-lookup"><span data-stu-id="bf603-112">First-class functions</span></span>
* <span data-ttu-id="bf603-113">強力なデータ型</span><span class="sxs-lookup"><span data-stu-id="bf603-113">Powerful data types</span></span>
* <span data-ttu-id="bf603-114">パターン マッチング</span><span class="sxs-lookup"><span data-stu-id="bf603-114">Pattern matching</span></span>
* <span data-ttu-id="bf603-115">非同期プログラミング</span><span class="sxs-lookup"><span data-stu-id="bf603-115">Async programming</span></span>

<span data-ttu-id="bf603-116">機能の完全なセットが記載されて、 [F# 言語リファレンス](./language-reference/index.md)します。</span><span class="sxs-lookup"><span data-stu-id="bf603-116">A full set of features are documented in the [F# language reference](./language-reference/index.md).</span></span>

## <a name="rich-data-types"></a><span data-ttu-id="bf603-117">豊富なデータ型</span><span class="sxs-lookup"><span data-stu-id="bf603-117">Rich data types</span></span>

<span data-ttu-id="bf603-118">[レコード](./language-reference/records.md)や[判別共用体](./language-reference/discriminated-unions.md)などのデータ型を使用すると、複雑なデータとドメインを表すことができます。</span><span class="sxs-lookup"><span data-stu-id="bf603-118">Data types such as [Records](./language-reference/records.md) and [Discriminated Unions](./language-reference/discriminated-unions.md) let you represent complex data and domains.</span></span>

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

<span data-ttu-id="bf603-119">F#レコードと判別共用体は、null ではなく、変更できず、既定では比較可能であるため、非常に使いやすくなっています。</span><span class="sxs-lookup"><span data-stu-id="bf603-119">F# records and discriminated unions are non-null, immutable, and comparable by default, making them very easy to use.</span></span>

## <a name="enforced-correctness-with-functions-and-pattern-matching"></a><span data-ttu-id="bf603-120">関数とパターンマッチングでの強制的な正確性</span><span class="sxs-lookup"><span data-stu-id="bf603-120">Enforced correctness with functions and pattern matching</span></span>

<span data-ttu-id="bf603-121">F#関数は、実際には簡単に宣言でき、非常に強力です。</span><span class="sxs-lookup"><span data-stu-id="bf603-121">F# functions are easy to declare and powerful in practice.</span></span> <span data-ttu-id="bf603-122">[パターンマッチング](./language-reference/pattern-matching.md)と組み合わせると、コンパイラによって正確性が強制される動作を定義できます。</span><span class="sxs-lookup"><span data-stu-id="bf603-122">When combined with [pattern matching](./language-reference/pattern-matching.md), they allow you to define behavior whose correctness is enforced by the compiler.</span></span>

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

<span data-ttu-id="bf603-123">F#関数もファーストクラスであり、パラメーターとして渡し、他の関数から返すことができます。</span><span class="sxs-lookup"><span data-stu-id="bf603-123">F# functions are also first-class, meaning they can be passed as parameters and returned from other functions.</span></span>

## <a name="functions-to-define-operations-on-objects"></a><span data-ttu-id="bf603-124">オブジェクトに対する操作を定義する関数</span><span class="sxs-lookup"><span data-stu-id="bf603-124">Functions to define operations on objects</span></span>

<span data-ttu-id="bf603-125">F#では、オブジェクトが完全にサポートされています。これは、データと機能をブレンドする必要がある場合に便利なデータ型です。</span><span class="sxs-lookup"><span data-stu-id="bf603-125">F# has full support for objects, which are useful data types when you need to blend data and functionality.</span></span> <span data-ttu-id="bf603-126">F#関数は、オブジェクトの操作に使用されます。</span><span class="sxs-lookup"><span data-stu-id="bf603-126">F# functions are used to manipulate objects.</span></span>

```fsharp
type Set<[<EqualityConditionOn>] 'T when 'T: comparison>(elements: seq<'T>) =
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

<span data-ttu-id="bf603-127">でF#は、オブジェクト指向のコードを記述するのではなく、多くの場合、オブジェクトを操作する関数の別のデータ型として扱うコードを記述します。</span><span class="sxs-lookup"><span data-stu-id="bf603-127">Rather than writing code that is object-oriented, in F#, you will often write code that treats objects as another data type for functions to manipulate.</span></span> <span data-ttu-id="bf603-128">などの機能[ジェネリック インターフェイス](./language-reference/interfaces.md)、[オブジェクト式](./language-reference/object-expressions.md)とを賢く利用[メンバー](./language-reference/members/index.md)は大規模な F# プログラムでは一般的です。</span><span class="sxs-lookup"><span data-stu-id="bf603-128">Features such as [generic interfaces](./language-reference/interfaces.md), [object expressions](./language-reference/object-expressions.md), and judicious use of [members](./language-reference/members/index.md) are common in larger F# programs.</span></span>

## <a name="next-steps"></a><span data-ttu-id="bf603-129">次の手順</span><span class="sxs-lookup"><span data-stu-id="bf603-129">Next steps</span></span>

<span data-ttu-id="bf603-130">多数の F# の機能の詳細については、チェック アウト、 [F# のツアー](tour.md)します。</span><span class="sxs-lookup"><span data-stu-id="bf603-130">To learn more about a larger set of F# features, check out the [F# Tour](tour.md).</span></span>
