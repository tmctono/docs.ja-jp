---
title: F# 4.6 の新機能- F#ガイド
description: 4\.6 でF#利用可能な新機能の概要を説明します。
ms.date: 11/27/2019
ms.openlocfilehash: 620c1edd8ea212fee306a02d5844b6b322808251
ms.sourcegitcommit: 19014f9c081ca2ff19652ca12503828db8239d48
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "76980393"
---
# <a name="whats-new-in-f-46"></a><span data-ttu-id="77477-103">4\.6 のF#新機能</span><span class="sxs-lookup"><span data-stu-id="77477-103">What's new in F# 4.6</span></span>

<span data-ttu-id="77477-104">F#4.6 では、言語にF#複数の機能強化が追加されています。</span><span class="sxs-lookup"><span data-stu-id="77477-104">F# 4.6 adds multiple improvements to the F# language.</span></span>

## <a name="get-started"></a><span data-ttu-id="77477-105">作業開始</span><span class="sxs-lookup"><span data-stu-id="77477-105">Get started</span></span>

<span data-ttu-id="77477-106">F#4.6 は、すべての .NET Core ディストリビューションと Visual Studio ツールで使用できます。</span><span class="sxs-lookup"><span data-stu-id="77477-106">F# 4.6 is available in all .NET Core distributions and Visual Studio tooling.</span></span> <span data-ttu-id="77477-107">詳細につい[ては、 F# ](../get-started/index.md) 「」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="77477-107">[Get started with F#](../get-started/index.md) to learn more.</span></span>

## <a name="anonymous-records"></a><span data-ttu-id="77477-108">匿名レコード</span><span class="sxs-lookup"><span data-stu-id="77477-108">Anonymous records</span></span>

<span data-ttu-id="77477-109">[匿名レコード](../language-reference/anonymous-records.md)は、4.6 でF# F#導入された新しい種類の種類です。</span><span class="sxs-lookup"><span data-stu-id="77477-109">[Anonymous records](../language-reference/anonymous-records.md) are a new kind of F# type introduced in F# 4.6.</span></span> <span data-ttu-id="77477-110">これらは、使用前に宣言する必要のない名前付きの値の単純な集計です。</span><span class="sxs-lookup"><span data-stu-id="77477-110">They are simple aggregates of named values that don't need to be declared before use.</span></span> <span data-ttu-id="77477-111">これらは、構造体または参照型として宣言できます。</span><span class="sxs-lookup"><span data-stu-id="77477-111">You can declare them as either structs or reference types.</span></span> <span data-ttu-id="77477-112">既定では、これらは参照型です。</span><span class="sxs-lookup"><span data-stu-id="77477-112">They're reference types by default.</span></span>

```fsharp
open System

let getCircleStats radius =
    let d = radius * 2.0
    let a = Math.PI * (radius ** 2.0)
    let c = 2.0 * Math.PI * radius

    {| Diameter = d; Area = a; Circumference = c |}

let r = 2.0
let stats = getCircleStats r
printfn "Circle with radius: %f has diameter %f, area %f, and circumference %f"
    r stats.Diameter stats.Area stats.Circumference
```

<span data-ttu-id="77477-113">また、値型をグループ化し、パフォーマンスを重視するシナリオで動作する場合に、の構造体として宣言することもできます。</span><span class="sxs-lookup"><span data-stu-id="77477-113">They can also be declared as structs for when you want to group value types and are operating in performance-sensitive scenarios:</span></span>

```fsharp
open System

let getCircleStats radius =
    let d = radius * 2.0
    let a = Math.PI * (radius ** 2.0)
    let c = 2.0 * Math.PI * radius

    struct {| Diameter = d; Area = a; Circumference = c |}

let r = 2.0
let stats = getCircleStats r
printfn "Circle with radius: %f has diameter %f, area %f, and circumference %f"
    r stats.Diameter stats.Area stats.Circumference
```

<span data-ttu-id="77477-114">非常に強力であり、さまざまなシナリオで使用できます。</span><span class="sxs-lookup"><span data-stu-id="77477-114">They're quite powerful and can be used in numerous scenarios.</span></span> <span data-ttu-id="77477-115">詳細については、「[匿名レコード](../language-reference/anonymous-records.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="77477-115">Learn more at [Anonymous records](../language-reference/anonymous-records.md).</span></span>

## <a name="valueoption-functions"></a><span data-ttu-id="77477-116">ValueOption 関数</span><span class="sxs-lookup"><span data-stu-id="77477-116">ValueOption functions</span></span>

<span data-ttu-id="77477-117">4\.5 でF#追加された valueoption 型には、"モジュールバインド関数のパリティ" がオプションの種類として含まれるようになりました。</span><span class="sxs-lookup"><span data-stu-id="77477-117">The ValueOption type added in F# 4.5 now has "module-bound function parity" with the Option type.</span></span> <span data-ttu-id="77477-118">一般的に使用される例には、次のようなものがあります。</span><span class="sxs-lookup"><span data-stu-id="77477-118">Some of the more commonly-used examples are as follows:</span></span>

```fsharp
// Multiply a value option by 2 if it has  value
let xOpt = ValueSome 99
let result = xOpt |> ValueOption.map (fun v -> v * 2)

// Reverse a string if it exists
let strOpt = ValueSome "Mirror image"
let reverse (str: string) =
    match str with
    | null
    | "" -> ValueNone
    | s ->
        str.ToCharArray()
        |> Array.rev
        |> string
        |> ValueSome

let reversedString = strOpt |> ValueOption.bind reverse
```

<span data-ttu-id="77477-119">これにより、値型を持つシナリオでは、ValueOption をオプションと同じように使用して、パフォーマンスを向上させることができます。</span><span class="sxs-lookup"><span data-stu-id="77477-119">This allows for ValueOption to be used just like Option in scenarios where having a value type improves performance.</span></span>
