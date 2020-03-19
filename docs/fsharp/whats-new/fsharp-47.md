---
title: F# 4.7 の新機能 - F# ガイド
description: F# 4.7 で利用可能な新機能の概要を取得します。
ms.date: 11/27/2019
ms.openlocfilehash: 7a6e744a398719bcb55d168dd700459e0b122dd6
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2020
ms.locfileid: "79185869"
---
# <a name="whats-new-in-f-47"></a><span data-ttu-id="ec42e-103">F# 4.7 の新機能</span><span class="sxs-lookup"><span data-stu-id="ec42e-103">What's new in F# 4.7</span></span>

<span data-ttu-id="ec42e-104">F# 4.7 では、F# 言語に複数の改良が加えました。</span><span class="sxs-lookup"><span data-stu-id="ec42e-104">F# 4.7 adds multiple improvements to the F# language.</span></span>

## <a name="get-started"></a><span data-ttu-id="ec42e-105">はじめに</span><span class="sxs-lookup"><span data-stu-id="ec42e-105">Get started</span></span>

<span data-ttu-id="ec42e-106">F# 4.7 は、すべての .NET コアディストリビューションと Visual Studio ツールで使用できます。</span><span class="sxs-lookup"><span data-stu-id="ec42e-106">F# 4.7 is available in all .NET Core distributions and Visual Studio tooling.</span></span> <span data-ttu-id="ec42e-107">[F# の使用を開始](../get-started/index.md)して、詳細を確認してください。</span><span class="sxs-lookup"><span data-stu-id="ec42e-107">[Get started with F#](../get-started/index.md) to learn more.</span></span>

## <a name="language-version"></a><span data-ttu-id="ec42e-108">言語バージョン</span><span class="sxs-lookup"><span data-stu-id="ec42e-108">Language version</span></span>

<span data-ttu-id="ec42e-109">F# 4.7 コンパイラでは、プロジェクト ファイルのプロパティを使用して、有効な言語バージョンを設定する機能が導入されています。</span><span class="sxs-lookup"><span data-stu-id="ec42e-109">The F# 4.7 compiler introduces the ability to set your effective language version via a property in your project file:</span></span>

```xml
<PropertyGroup>
    <LangVersion>preview</LangVersion>
</PropertyGroup>
```

<span data-ttu-id="ec42e-110">値`4.6`、 、 、`4.7``latest`および`preview`に設定できます。</span><span class="sxs-lookup"><span data-stu-id="ec42e-110">You can set it to the values `4.6`, `4.7`, `latest`, and `preview`.</span></span> <span data-ttu-id="ec42e-111">既定では、 `latest`です。</span><span class="sxs-lookup"><span data-stu-id="ec42e-111">The default is `latest`.</span></span>

<span data-ttu-id="ec42e-112">に`preview`設定すると、コンパイラは、コンパイラに実装されているすべての F# プレビュー機能をアクティブ化します。</span><span class="sxs-lookup"><span data-stu-id="ec42e-112">If you set it to `preview`, your compiler will activate all F# preview features that are implemented in your compiler.</span></span>

## <a name="implicit-yields"></a><span data-ttu-id="ec42e-113">暗黙的な利回り</span><span class="sxs-lookup"><span data-stu-id="ec42e-113">Implicit yields</span></span>

<span data-ttu-id="ec42e-114">配列、リスト、シーケンス、または`yield`計算式で、型を推論できる場合にキーワードを適用する必要がなくなりました。</span><span class="sxs-lookup"><span data-stu-id="ec42e-114">You no longer need to apply the `yield` keyword in arrays, lists, sequences, or computation expressions where the type can be inferred.</span></span> <span data-ttu-id="ec42e-115">次の例では、F# 4.7 より前の`yield`各エントリに対して、両方の式にステートメントが必要でした。</span><span class="sxs-lookup"><span data-stu-id="ec42e-115">In the following example, both expressions required the `yield` statement for each entry prior to F# 4.7:</span></span>

```fsharp
let s = seq { 1; 2; 3; 4; 5 }

let daysOfWeek includeWeekend =
    [
        "Monday"
        "Tuesday"
        "Wednesday"
        "Thursday"
        "Friday"
        if includeWeekend then
            "Saturday"
            "Sunday"
    ]
```

<span data-ttu-id="ec42e-116">単一`yield`のキーワードを導入する場合は、他のすべての項目`yield`もそのキーワードに適用されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="ec42e-116">If you introduce a single `yield` keyword, every other item must also have `yield` applied to it.</span></span>

<span data-ttu-id="ec42e-117">暗黙的な利回りは、シーケンスの平坦化などの処理`yield!`にも使用される式で使用される場合はアクティブ化されません。</span><span class="sxs-lookup"><span data-stu-id="ec42e-117">Implicit yields are not activated when used in an expression that also uses `yield!` to do something like flatten a sequence.</span></span> <span data-ttu-id="ec42e-118">このような場合は、今日`yield`も使用し続ける必要があります。</span><span class="sxs-lookup"><span data-stu-id="ec42e-118">You must continue to use `yield` today in these cases.</span></span>

## <a name="wildcard-identifiers"></a><span data-ttu-id="ec42e-119">ワイルドカード識別子</span><span class="sxs-lookup"><span data-stu-id="ec42e-119">Wildcard identifiers</span></span>

<span data-ttu-id="ec42e-120">クラスを含む F# コードでは、メンバー宣言では自己識別子を常に明示的に指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ec42e-120">In F# code involving classes, the self-identifier needs to always be explicit in member declarations.</span></span> <span data-ttu-id="ec42e-121">しかし、自己識別子が使用されていない場合、伝統的に、名前のない自己識別子を示すためにダブルアンダースコアを使用することが慣例でした。</span><span class="sxs-lookup"><span data-stu-id="ec42e-121">But in cases where the self-identifier is never used, it has traditionally been convention to use a double-underscore to indicate a nameless self-identifiers.</span></span> <span data-ttu-id="ec42e-122">下線を 1 つ使用できるようになりました。</span><span class="sxs-lookup"><span data-stu-id="ec42e-122">You can now use a single underscore:</span></span>

```fsharp
type C() =
    member _.M() = ()
```

<span data-ttu-id="ec42e-123">これは`for`ループにも当てはまります。</span><span class="sxs-lookup"><span data-stu-id="ec42e-123">This also applies for `for` loops:</span></span>

```fsharp
for _ in 1..10 do printfn "Hello!"
```

## <a name="indentation-relaxations"></a><span data-ttu-id="ec42e-124">インデントの緩和</span><span class="sxs-lookup"><span data-stu-id="ec42e-124">Indentation relaxations</span></span>

<span data-ttu-id="ec42e-125">F# 4.7 より前のバージョンでは、プライマリ コンストラクターと静的メンバー引数のインデント要件に過剰なインデントが必要でした。</span><span class="sxs-lookup"><span data-stu-id="ec42e-125">Prior to F# 4.7, the indentation requirements for primary constructor and static member arguments required excessive indentation.</span></span> <span data-ttu-id="ec42e-126">これで、1 つのインデント スコープのみが必要になります。</span><span class="sxs-lookup"><span data-stu-id="ec42e-126">They now only require a single indentation scope:</span></span>

```fsharp
type OffsideCheck(a:int,
    b:int, c:int,
    d:int) = class end

type C() =
    static member M(a:int,
        b:int, c:int,
        d:int) = 1
```
