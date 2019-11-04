---
title: 値のオプション
description: F# Value オプションの型について説明します。これは、オプションの型の構造体のバージョンです。
ms.date: 02/06/2019
ms.openlocfilehash: 4dc3f7217943345b7aaf1165fd648ab2e01bd727
ms.sourcegitcommit: 14ad34f7c4564ee0f009acb8bfc0ea7af3bc9541
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/01/2019
ms.locfileid: "73424013"
---
# <a name="value-options"></a><span data-ttu-id="f06c4-103">値のオプション</span><span class="sxs-lookup"><span data-stu-id="f06c4-103">Value Options</span></span>

<span data-ttu-id="f06c4-104">次の2つのF#状況では、の値オプションの種類が使用されます。</span><span class="sxs-lookup"><span data-stu-id="f06c4-104">The Value Option type in F# is used when the following two circumstances hold:</span></span>

1. <span data-ttu-id="f06c4-105">シナリオは、 [ F#オプション](options.md)に適しています。</span><span class="sxs-lookup"><span data-stu-id="f06c4-105">A scenario is appropriate for an [F# Option](options.md).</span></span>
2. <span data-ttu-id="f06c4-106">構造体を使用すると、シナリオにおけるパフォーマンス上の利点が得られます。</span><span class="sxs-lookup"><span data-stu-id="f06c4-106">Using a struct provides a performance benefit in your scenario.</span></span>

<span data-ttu-id="f06c4-107">すべてのパフォーマンスを重視するシナリオは、構造体を使用して "解決" されるわけではありません。</span><span class="sxs-lookup"><span data-stu-id="f06c4-107">Not all performance-sensitive scenarios are "solved" by using structs.</span></span> <span data-ttu-id="f06c4-108">参照型の代わりに使用する場合は、コピーにかかる追加コストを考慮する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f06c4-108">You must consider the additional cost of copying when using them instead of reference types.</span></span> <span data-ttu-id="f06c4-109">ただし、大F#規模なプログラムでは、多くの場合、ホットパスを通過する多くの省略可能な型がインスタンス化されるため、多くの場合、構造体はプログラムの有効期間全体のパフォーマンスを向上させることができます。</span><span class="sxs-lookup"><span data-stu-id="f06c4-109">However, large F# programs commonly instantiate many optional types that flow through hot paths, and in such cases, structs can often yield better overall performance over the lifetime of a program.</span></span>

## <a name="definition"></a><span data-ttu-id="f06c4-110">定義</span><span class="sxs-lookup"><span data-stu-id="f06c4-110">Definition</span></span>

<span data-ttu-id="f06c4-111">Value オプションは、参照オプションの型に似た[構造体の判別共用体](discriminated-unions.md#struct-discriminated-unions)として定義されます。</span><span class="sxs-lookup"><span data-stu-id="f06c4-111">Value Option is defined as a [struct discriminated union](discriminated-unions.md#struct-discriminated-unions) that is similar to the reference option type.</span></span> <span data-ttu-id="f06c4-112">その定義は、次のように考えることができます。</span><span class="sxs-lookup"><span data-stu-id="f06c4-112">Its definition can be thought of this way:</span></span>

```fsharp
[<StructuralEquality; StructuralComparison>]
[<Struct>]
type ValueOption<'T> =
    | ValueNone
    | ValueSome of 'T
```

<span data-ttu-id="f06c4-113">値オプションは構造的等価性と比較に準拠しています。</span><span class="sxs-lookup"><span data-stu-id="f06c4-113">Value Option conforms to structural equality and comparison.</span></span> <span data-ttu-id="f06c4-114">主な違いは、コンパイルされた名前、型名、およびケース名はすべて、値型であることを示しています。</span><span class="sxs-lookup"><span data-stu-id="f06c4-114">The main difference is that the compiled name, type name, and case names all indicate that it is a value type.</span></span>

## <a name="using-value-options"></a><span data-ttu-id="f06c4-115">Value オプションの使用</span><span class="sxs-lookup"><span data-stu-id="f06c4-115">Using Value Options</span></span>

<span data-ttu-id="f06c4-116">値のオプションは、[オプション](options.md)と同じように使用されます。</span><span class="sxs-lookup"><span data-stu-id="f06c4-116">Value Options are used just like [Options](options.md).</span></span> <span data-ttu-id="f06c4-117">値が存在することを示すために `ValueSome` を使用し、値が存在しない場合は `ValueNone` を使用します。</span><span class="sxs-lookup"><span data-stu-id="f06c4-117">`ValueSome` is used to indicate that a value is present, and `ValueNone` is used when a value is not present:</span></span>

```fsharp
let tryParseDateTime (s: string) =
    match System.DateTime.TryParse(s) with
    | (true, dt) -> ValueSome dt
    | (false, _) -> ValueNone

let possibleDateString1 = "1990-12-25"
let possibleDateString2 = "This is not a date"

let result1 = tryParseDateTime possibleDateString1
let result2 = tryParseDateTime possibleDateString2

match (result1, result2) with
| ValueSome d1, ValueSome d2 -> printfn "Both are dates!"
| ValueSome d1, ValueNone -> printfn "Only the first is a date!"
| ValueNone, ValueSome d2 -> printfn "Only the second is a date!"
| ValueNone, ValueNone -> printfn "None of them are dates!"
```

<span data-ttu-id="f06c4-118">[オプション](options.md)と同様に、`ValueOption` を返す関数の名前付け規則は、`try`にプレフィックスを付けることです。</span><span class="sxs-lookup"><span data-stu-id="f06c4-118">As with [Options](options.md), the naming convention for a function that returns `ValueOption` is to prefix it with `try`.</span></span>

## <a name="value-option-properties-and-methods"></a><span data-ttu-id="f06c4-119">Value オプションのプロパティとメソッド</span><span class="sxs-lookup"><span data-stu-id="f06c4-119">Value Option properties and methods</span></span>

<span data-ttu-id="f06c4-120">現時点では、Value オプションには、`Value`の1つのプロパティがあります。</span><span class="sxs-lookup"><span data-stu-id="f06c4-120">There is one property for Value Options at this time: `Value`.</span></span> <span data-ttu-id="f06c4-121">このプロパティが呼び出されたときに値が存在しない場合は、<xref:System.InvalidOperationException> が発生します。</span><span class="sxs-lookup"><span data-stu-id="f06c4-121">An <xref:System.InvalidOperationException> is raised if no value is present when this property is invoked.</span></span>

## <a name="value-option-functions"></a><span data-ttu-id="f06c4-122">Value オプションの関数</span><span class="sxs-lookup"><span data-stu-id="f06c4-122">Value Option functions</span></span>

<span data-ttu-id="f06c4-123">現時点では、値のオプションにはモジュールバインド関数が1つ `defaultValueArg`。</span><span class="sxs-lookup"><span data-stu-id="f06c4-123">There is currently one module-bound function for Value Options, `defaultValueArg`:</span></span>

```fsharp
val defaultValueArg : arg:'T voption -> defaultValue:'T -> 'T
```

<span data-ttu-id="f06c4-124">`defaultArg` 関数と同様に、`defaultValueArg` は、指定された Value オプションが存在する場合は、基になる値を返します。それ以外の場合は、指定された既定値を返します。</span><span class="sxs-lookup"><span data-stu-id="f06c4-124">As with the `defaultArg` function, `defaultValueArg` returns the underlying value of the given Value Option if it exists; otherwise, it returns the specified default value.</span></span>

<span data-ttu-id="f06c4-125">現時点では、値オプション用のモジュールバインド関数は他にありません。</span><span class="sxs-lookup"><span data-stu-id="f06c4-125">At this time, there are no other module-bound functions for Value Options.</span></span>

## <a name="see-also"></a><span data-ttu-id="f06c4-126">関連項目</span><span class="sxs-lookup"><span data-stu-id="f06c4-126">See also</span></span>

- [<span data-ttu-id="f06c4-127">Options</span><span class="sxs-lookup"><span data-stu-id="f06c4-127">Options</span></span>](options.md)
