---
title: 結果
description: 使用する方法について説明します、 F# 'Result' の入力エラー トレラントなコードを作成できるようにします。
ms.date: 04/24/2017
ms.openlocfilehash: 8b419412b406018a21f2c23103c8193fec8766f2
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61770514"
---
# <a name="results"></a><span data-ttu-id="7a7a4-103">結果</span><span class="sxs-lookup"><span data-stu-id="7a7a4-103">Results</span></span>

<span data-ttu-id="7a7a4-104">以降でF#4.1 は、`Result<'T,'TFailure>`できるエラー トレラントのコードを書くために使用できる型。</span><span class="sxs-lookup"><span data-stu-id="7a7a4-104">Starting with F# 4.1, there is a `Result<'T,'TFailure>` type which you can use for writing error-tolerant code which can be composed.</span></span>

## <a name="syntax"></a><span data-ttu-id="7a7a4-105">構文</span><span class="sxs-lookup"><span data-stu-id="7a7a4-105">Syntax</span></span>

```fsharp
// The definition of Result in FSharp.Core
[<StructuralEquality; StructuralComparison>]
[<CompiledName("FSharpResult`2")>]
[<Struct>]
type Result<'T,'TError> = 
    | Ok of ResultValue:'T 
    | Error of ErrorValue:'TError
```

## <a name="remarks"></a><span data-ttu-id="7a7a4-106">Remarks</span><span class="sxs-lookup"><span data-stu-id="7a7a4-106">Remarks</span></span>

<span data-ttu-id="7a7a4-107">結果型は、[構造体の判別共用体](discriminated-unions.md#struct-discriminated-unions)、F# 4.1 で導入されたもう 1 つの機能であります。</span><span class="sxs-lookup"><span data-stu-id="7a7a4-107">Note that the result type is a [struct discriminated union](discriminated-unions.md#struct-discriminated-unions), which is another feature introduced in F# 4.1.</span></span>  <span data-ttu-id="7a7a4-108">構造の等値セマンティクスがここに適用されます。</span><span class="sxs-lookup"><span data-stu-id="7a7a4-108">Structural equality semantics apply here.</span></span>

<span data-ttu-id="7a7a4-109">`Result`モナディック エラー処理と呼ばれるに多くの場合で、型が通常使用される[鉄道指向プログラミング](https://swlaschin.gitbooks.io/fsharpforfunandprofit/content/posts/recipe-part2.html)F# コミュニティ内で。</span><span class="sxs-lookup"><span data-stu-id="7a7a4-109">The `Result` type is typically used in monadic error-handling, which is often referred to as [Railway-oriented Programming](https://swlaschin.gitbooks.io/fsharpforfunandprofit/content/posts/recipe-part2.html) within the F# community.</span></span>  <span data-ttu-id="7a7a4-110">次の単純な例では、この方法を示します。</span><span class="sxs-lookup"><span data-stu-id="7a7a4-110">The following trivial example demonstrates this approach.</span></span>

```fsharp
// Define a simple type which has fields that can be validated
type Request = 
    { Name: string
      Email: string }

// Define some logic for what defines a valid name.
//
// Generates a Result which is an Ok if the name validates;
// otherwise, it generates a Result which is an Error.
let validateName req =
    match req.Name with
    | null -> Error "No name found."
    | "" -> Error "Name is empty."
    | "bananas" -> Error "Bananas is not a name."
    | _ -> Ok req

// Similarly, define some email validation logic.
let validateEmail req =
    match req.Email with
    | null -> Error "No email found."
    | "" -> Error "Email is empty."
    | s when s.EndsWith("bananas.com") -> Error "No email from bananas.com is allowed."
    | _ -> Ok req

let validateRequest reqResult =
    reqResult 
    |> Result.bind validateName
    |> Result.bind validateEmail

let test() = 
    // Now, create a Request and pattern match on the result.
    let req1 = { Name = "Phillip"; Email = "phillip@contoso.biz" }
    let res1 = validateRequest (Ok req1)
    match res1 with
    | Ok req -> printfn "My request was valid! Name: %s Email %s" req.Name req.Email
    | Error e -> printfn "Error: %s" e
    // Prints: "My request was valid!  Name: Phillip Email: phillip@consoto.biz"

    let req2 = { Name = "Phillip"; Email = "phillip@bananas.com" }
    let res2 = validateRequest (Ok req2)
    match res2 with
    | Ok req -> printfn "My request was valid! Name: %s Email %s" req.Name req.Email
    | Error e -> printfn "Error: %s" e
    // Prints: "Error: No email from bananas.com is allowed."

test()
```

<span data-ttu-id="7a7a4-111">非常に簡単に返すためにすべてを強制する場合は、さまざまな検証機能を連結、ご覧のとおり、`Result`します。</span><span class="sxs-lookup"><span data-stu-id="7a7a4-111">As you can see, it's quite easy to chain together various validation functions if you force them all to return a `Result`.</span></span>  <span data-ttu-id="7a7a4-112">このような機能を必要に応じて、コンポーザブルである小規模なを分割するこのことができます。</span><span class="sxs-lookup"><span data-stu-id="7a7a4-112">This lets you break up functionality like this into small pieces which are as composable as you need them to be.</span></span>  <span data-ttu-id="7a7a4-113">これも、追加の値を持つ*を適用する*の使用[パターンに一致する](pattern-matching.md)検証のラウンドの末尾には、プログラムの正確性の高いを適用すると、それに続いて。</span><span class="sxs-lookup"><span data-stu-id="7a7a4-113">This also has the added value of *enforcing* the use of [pattern matching](pattern-matching.md) at the end of a round of validation, which in turns enforces a higher degree of program correctness.</span></span>

## <a name="see-also"></a><span data-ttu-id="7a7a4-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="7a7a4-114">See also</span></span>

- [<span data-ttu-id="7a7a4-115">判別共用体</span><span class="sxs-lookup"><span data-stu-id="7a7a4-115">Discriminated Unions</span></span>](discriminated-unions.md)
- [<span data-ttu-id="7a7a4-116">パターン一致</span><span class="sxs-lookup"><span data-stu-id="7a7a4-116">Pattern Matching</span></span>](pattern-matching.md)