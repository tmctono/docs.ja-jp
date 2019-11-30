---
title: F# 4.7 の新機能- F#ガイド
description: 4\.7 でF#利用可能な新機能の概要を説明します。
ms.date: 11/27/2019
ms.openlocfilehash: 203b258466cb9f1f50215ecf8884e92e7e86416b
ms.sourcegitcommit: 79a2d6a07ba4ed08979819666a0ee6927bbf1b01
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2019
ms.locfileid: "74644122"
---
# <a name="whats-new-in-f-47"></a><span data-ttu-id="e37d4-103">4\.7 のF#新機能</span><span class="sxs-lookup"><span data-stu-id="e37d4-103">What's new in F# 4.7</span></span>

<span data-ttu-id="e37d4-104">F#4.7 では、言語にF#複数の機能強化が追加されています。</span><span class="sxs-lookup"><span data-stu-id="e37d4-104">F# 4.7 adds multiple improvements to the F# language.</span></span>

## <a name="get-started"></a><span data-ttu-id="e37d4-105">作業開始</span><span class="sxs-lookup"><span data-stu-id="e37d4-105">Get started</span></span>

<span data-ttu-id="e37d4-106">F#4.7 は、すべての .NET Core ディストリビューションと Visual Studio ツールで使用できます。</span><span class="sxs-lookup"><span data-stu-id="e37d4-106">F# 4.7 is available in all .NET Core distributions and Visual Studio tooling.</span></span> <span data-ttu-id="e37d4-107">詳細につい[ては、 F# ](../get-started/index.md) 「」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e37d4-107">[Get started with F#](../get-started/index.md) to learn more.</span></span>

## <a name="language-version"></a><span data-ttu-id="e37d4-108">言語バージョン</span><span class="sxs-lookup"><span data-stu-id="e37d4-108">Language version</span></span>

<span data-ttu-id="e37d4-109">4\.7 F#コンパイラでは、プロジェクトファイルのプロパティを使用して有効な言語バージョンを設定する機能が導入されています。</span><span class="sxs-lookup"><span data-stu-id="e37d4-109">The F# 4.7 compiler introduces the ability to set your effective language version via a property in your project file:</span></span>

```xml
<PropertyGroup>
    <LangVersion>preview</LangVersion>
</PropertyGroup>
```

<span data-ttu-id="e37d4-110">`4.6`、`4.7`、`latest`、および `preview`の値に設定できます。</span><span class="sxs-lookup"><span data-stu-id="e37d4-110">You can set it to the values `4.6`, `4.7`, `latest`, and `preview`.</span></span> <span data-ttu-id="e37d4-111">既定値は、 `latest`です。</span><span class="sxs-lookup"><span data-stu-id="e37d4-111">The default is `latest`.</span></span>

<span data-ttu-id="e37d4-112">`preview`に設定した場合は、コンパイラによってF#実装されているすべてのプレビュー機能がアクティブ化されます。</span><span class="sxs-lookup"><span data-stu-id="e37d4-112">If you set it to `preview`, your compiler will activate all F# preview features that are implemented in your compiler.</span></span>

## <a name="implicit-yields"></a><span data-ttu-id="e37d4-113">暗黙的な生成</span><span class="sxs-lookup"><span data-stu-id="e37d4-113">Implicit yields</span></span>

<span data-ttu-id="e37d4-114">型を推論できる配列、リスト、シーケンス、または計算式に `yield` キーワードを適用する必要がなくなりました。</span><span class="sxs-lookup"><span data-stu-id="e37d4-114">You no longer need to apply the `yield` keyword in arrays, lists, sequences, or computation expressions where the type can be inferred.</span></span> <span data-ttu-id="e37d4-115">次の例では、両方の式でF# 4.7 より前の各エントリに対して `yield` ステートメントが必要でした。</span><span class="sxs-lookup"><span data-stu-id="e37d4-115">In the following example, both expressions required the `yield` statement for each entry prior to F# 4.7:</span></span>

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

<span data-ttu-id="e37d4-116">1つの `yield` キーワードを導入する場合は、他のすべての項目にも `yield` 適用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e37d4-116">If you introduce a single `yield` keyword, every other item must also have `yield` applied to it.</span></span>

<span data-ttu-id="e37d4-117">暗黙的な生成は、シーケンスを平坦化するように `yield!` を使用する式で使用されている場合はアクティブ化されません。</span><span class="sxs-lookup"><span data-stu-id="e37d4-117">Implicit yields are not activated when used in an expression that also uses `yield!` to do something like flatten a sequence.</span></span> <span data-ttu-id="e37d4-118">このような場合は、今日の `yield` を引き続き使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e37d4-118">You must continue to use `yield` today in these cases.</span></span>

## <a name="wildcard-identifiers"></a><span data-ttu-id="e37d4-119">ワイルドカード識別子</span><span class="sxs-lookup"><span data-stu-id="e37d4-119">Wildcard identifiers</span></span>

<span data-ttu-id="e37d4-120">クラスF#を使用するコードでは、自己識別子は常にメンバー宣言で明示的である必要があります。</span><span class="sxs-lookup"><span data-stu-id="e37d4-120">In F# code involving classes, the self-identifier needs to always be explicit in member declarations.</span></span> <span data-ttu-id="e37d4-121">しかし、自己識別子が使用されていない場合は、無名の自己識別子を示すために、2つのアンダースコアを使用することが従来の慣例でした。</span><span class="sxs-lookup"><span data-stu-id="e37d4-121">But in cases where the self-identifier is never used, it has traditionally been convention to use a double-underscore to indicate a nameless self-identifiers.</span></span> <span data-ttu-id="e37d4-122">1つのアンダースコアを使用できるようになりました。</span><span class="sxs-lookup"><span data-stu-id="e37d4-122">You can now use a single underscore:</span></span>

```fsharp
type C() =
    member _.M() = ()
```

<span data-ttu-id="e37d4-123">これは、`for` ループにも適用されます。</span><span class="sxs-lookup"><span data-stu-id="e37d4-123">This also applies for `for` loops:</span></span>

```fsharp
for _ in 1..10 do printfn "Hello!"
```

## <a name="indentation-relaxations"></a><span data-ttu-id="e37d4-124">インデントリラクゼーション</span><span class="sxs-lookup"><span data-stu-id="e37d4-124">Indentation relaxations</span></span>

<span data-ttu-id="e37d4-125">F# 4.7 より前の場合、プライマリコンストラクターと静的メンバー引数のインデント要件には過剰なインデントが必要でした。</span><span class="sxs-lookup"><span data-stu-id="e37d4-125">Prior to F# 4.7, the indentation requirements for primary constructor and static member arguments required excessive indentation.</span></span> <span data-ttu-id="e37d4-126">ここでは、インデントスコープを1つだけ必要とします。</span><span class="sxs-lookup"><span data-stu-id="e37d4-126">They now only require a single indentation scope:</span></span>

```fsharp
type OffsideCheck(a:int,
    b:int, c:int,
    d:int) = class end

type C() =
    static member M(a:int,
        b:int, c:int,
        d:int) = 1
```
