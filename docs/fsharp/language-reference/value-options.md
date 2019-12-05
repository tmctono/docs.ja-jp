---
title: 値のオプション
description: F# Value オプションの型について説明します。これは、オプションの型の構造体のバージョンです。
ms.date: 12/04/2019
ms.openlocfilehash: 0e9882ab4acdf2757705ef6022516d3572d87ef2
ms.sourcegitcommit: a4f9b754059f0210e29ae0578363a27b9ba84b64
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/05/2019
ms.locfileid: "74837117"
---
# <a name="value-options"></a><span data-ttu-id="829ce-103">値のオプション</span><span class="sxs-lookup"><span data-stu-id="829ce-103">Value Options</span></span>

<span data-ttu-id="829ce-104">次の2つのF#状況では、の値オプションの種類が使用されます。</span><span class="sxs-lookup"><span data-stu-id="829ce-104">The Value Option type in F# is used when the following two circumstances hold:</span></span>

1. <span data-ttu-id="829ce-105">シナリオは、 [ F#オプション](options.md)に適しています。</span><span class="sxs-lookup"><span data-stu-id="829ce-105">A scenario is appropriate for an [F# Option](options.md).</span></span>
2. <span data-ttu-id="829ce-106">構造体を使用すると、シナリオにおけるパフォーマンス上の利点が得られます。</span><span class="sxs-lookup"><span data-stu-id="829ce-106">Using a struct provides a performance benefit in your scenario.</span></span>

<span data-ttu-id="829ce-107">すべてのパフォーマンスを重視するシナリオは、構造体を使用して "解決" されるわけではありません。</span><span class="sxs-lookup"><span data-stu-id="829ce-107">Not all performance-sensitive scenarios are "solved" by using structs.</span></span> <span data-ttu-id="829ce-108">参照型の代わりに使用する場合は、コピーにかかる追加コストを考慮する必要があります。</span><span class="sxs-lookup"><span data-stu-id="829ce-108">You must consider the additional cost of copying when using them instead of reference types.</span></span> <span data-ttu-id="829ce-109">ただし、大F#規模なプログラムでは、多くの場合、ホットパスを通過する多くの省略可能な型がインスタンス化されるため、多くの場合、構造体はプログラムの有効期間全体のパフォーマンスを向上させることができます。</span><span class="sxs-lookup"><span data-stu-id="829ce-109">However, large F# programs commonly instantiate many optional types that flow through hot paths, and in such cases, structs can often yield better overall performance over the lifetime of a program.</span></span>

## <a name="definition"></a><span data-ttu-id="829ce-110">Definition</span><span class="sxs-lookup"><span data-stu-id="829ce-110">Definition</span></span>

<span data-ttu-id="829ce-111">Value オプションは、参照オプションの型に似た[構造体の判別共用体](discriminated-unions.md#struct-discriminated-unions)として定義されます。</span><span class="sxs-lookup"><span data-stu-id="829ce-111">Value Option is defined as a [struct discriminated union](discriminated-unions.md#struct-discriminated-unions) that is similar to the reference option type.</span></span> <span data-ttu-id="829ce-112">その定義は、次のように考えることができます。</span><span class="sxs-lookup"><span data-stu-id="829ce-112">Its definition can be thought of this way:</span></span>

```fsharp
[<StructuralEquality; StructuralComparison>]
[<Struct>]
type ValueOption<'T> =
    | ValueNone
    | ValueSome of 'T
```

<span data-ttu-id="829ce-113">値オプションは構造的等価性と比較に準拠しています。</span><span class="sxs-lookup"><span data-stu-id="829ce-113">Value Option conforms to structural equality and comparison.</span></span> <span data-ttu-id="829ce-114">主な違いは、コンパイルされた名前、型名、およびケース名はすべて、値型であることを示しています。</span><span class="sxs-lookup"><span data-stu-id="829ce-114">The main difference is that the compiled name, type name, and case names all indicate that it is a value type.</span></span>

## <a name="using-value-options"></a><span data-ttu-id="829ce-115">Value オプションの使用</span><span class="sxs-lookup"><span data-stu-id="829ce-115">Using Value Options</span></span>

<span data-ttu-id="829ce-116">値のオプションは、[オプション](options.md)と同じように使用されます。</span><span class="sxs-lookup"><span data-stu-id="829ce-116">Value Options are used just like [Options](options.md).</span></span> <span data-ttu-id="829ce-117">値が存在することを示すために `ValueSome` を使用し、値が存在しない場合は `ValueNone` を使用します。</span><span class="sxs-lookup"><span data-stu-id="829ce-117">`ValueSome` is used to indicate that a value is present, and `ValueNone` is used when a value is not present:</span></span>

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

<span data-ttu-id="829ce-118">[オプション](options.md)と同様に、`ValueOption` を返す関数の名前付け規則は、`try`にプレフィックスを付けることです。</span><span class="sxs-lookup"><span data-stu-id="829ce-118">As with [Options](options.md), the naming convention for a function that returns `ValueOption` is to prefix it with `try`.</span></span>

## <a name="value-option-properties-and-methods"></a><span data-ttu-id="829ce-119">Value オプションのプロパティとメソッド</span><span class="sxs-lookup"><span data-stu-id="829ce-119">Value Option properties and methods</span></span>

<span data-ttu-id="829ce-120">現時点では、Value オプションには、`Value`の1つのプロパティがあります。</span><span class="sxs-lookup"><span data-stu-id="829ce-120">There is one property for Value Options at this time: `Value`.</span></span> <span data-ttu-id="829ce-121">このプロパティが呼び出されたときに値が存在しない場合は、<xref:System.InvalidOperationException> が発生します。</span><span class="sxs-lookup"><span data-stu-id="829ce-121">An <xref:System.InvalidOperationException> is raised if no value is present when this property is invoked.</span></span>

## <a name="value-option-functions"></a><span data-ttu-id="829ce-122">Value オプションの関数</span><span class="sxs-lookup"><span data-stu-id="829ce-122">Value Option functions</span></span>

<span data-ttu-id="829ce-123">Fsharp.core の `ValueOption` モジュールには、`Option` モジュールと同等の機能が含まれています。</span><span class="sxs-lookup"><span data-stu-id="829ce-123">The `ValueOption` module in FSharp.Core contains equivalent functionality to the `Option` module.</span></span> <span data-ttu-id="829ce-124">`defaultValueArg`のように、名前にはいくつかの違いがあります。</span><span class="sxs-lookup"><span data-stu-id="829ce-124">There are a few differences in name, such as `defaultValueArg`:</span></span>

```fsharp
val defaultValueArg : arg:'T voption -> defaultValue:'T -> 'T
```

<span data-ttu-id="829ce-125">これは、`Option` モジュールの `defaultArg` と同じように動作しますが、代わりに値オプションを操作します。</span><span class="sxs-lookup"><span data-stu-id="829ce-125">This acts just like `defaultArg` in the `Option` module, but operates on a Value Option instead.</span></span>

## <a name="see-also"></a><span data-ttu-id="829ce-126">参照</span><span class="sxs-lookup"><span data-stu-id="829ce-126">See also</span></span>

- [<span data-ttu-id="829ce-127">Options</span><span class="sxs-lookup"><span data-stu-id="829ce-127">Options</span></span>](options.md)
