---
title: デリゲート
description: 内のデリゲートを使用する方法について説明しますF#します。
ms.date: 05/16/2016
ms.openlocfilehash: 772685488b7caef92123979d817929c631248afb
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61766078"
---
# <a name="delegates"></a><span data-ttu-id="b6d11-103">デリゲート</span><span class="sxs-lookup"><span data-stu-id="b6d11-103">Delegates</span></span>

<span data-ttu-id="b6d11-104">デリゲートは、オブジェクトとして関数呼び出しを表します。</span><span class="sxs-lookup"><span data-stu-id="b6d11-104">A delegate represents a function call as an object.</span></span> <span data-ttu-id="b6d11-105">F#、通常は値を使用する関数を表すファーストクラスの値として関数ただし、デリゲートは、.NET Framework で使用され、それらを期待する Api と相互運用するときに、必要なため。</span><span class="sxs-lookup"><span data-stu-id="b6d11-105">In F#, you ordinarily should use function values to represent functions as first-class values; however, delegates are used in the .NET Framework and so are needed when you interoperate with APIs that expect them.</span></span> <span data-ttu-id="b6d11-106">他の .NET Framework 言語用に設計されたオーサリング ライブラリを使用して、ときも使用できます。</span><span class="sxs-lookup"><span data-stu-id="b6d11-106">They may also be used when authoring libraries designed for use from other .NET Framework languages.</span></span>

## <a name="syntax"></a><span data-ttu-id="b6d11-107">構文</span><span class="sxs-lookup"><span data-stu-id="b6d11-107">Syntax</span></span>

```fsharp
type delegate-typename = delegate of type1 -> type2
```

## <a name="remarks"></a><span data-ttu-id="b6d11-108">Remarks</span><span class="sxs-lookup"><span data-stu-id="b6d11-108">Remarks</span></span>

<span data-ttu-id="b6d11-109">前の構文で`type1`引数の型または型を表すと`type2`戻り値の型を表します。</span><span class="sxs-lookup"><span data-stu-id="b6d11-109">In the previous syntax, `type1` represents the argument type or types and `type2` represents the return type.</span></span> <span data-ttu-id="b6d11-110">引数の型によって表される`type1`は自動的にカリー化します。</span><span class="sxs-lookup"><span data-stu-id="b6d11-110">The argument types that are represented by `type1` are automatically curried.</span></span> <span data-ttu-id="b6d11-111">これはタプル形式を使用する場合は、対象の関数の引数がカリー化、この型を引数には、既にタプル形式のかっこで囲まれたタプルのことを示します。</span><span class="sxs-lookup"><span data-stu-id="b6d11-111">This suggests that for this type you use a tuple form if the arguments of the target function are curried, and a parenthesized tuple for arguments that are already in the tuple form.</span></span> <span data-ttu-id="b6d11-112">自動のカリー化対象のメソッドに一致する組の引数を残して、かっこのセットを削除します。</span><span class="sxs-lookup"><span data-stu-id="b6d11-112">The automatic currying removes a set of parentheses, leaving a tuple argument that matches the target method.</span></span> <span data-ttu-id="b6d11-113">各ケースで使用する構文のコード例を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b6d11-113">Refer to the code example for the syntax you should use in each case.</span></span>

<span data-ttu-id="b6d11-114">デリゲートは、F# 関数値、および静的に接続できるまたはインスタンス メソッド。</span><span class="sxs-lookup"><span data-stu-id="b6d11-114">Delegates can be attached to F# function values, and static or instance methods.</span></span> <span data-ttu-id="b6d11-115">デリゲート コンス トラクターに引数として直接 F# 関数値を渡すことができます。</span><span class="sxs-lookup"><span data-stu-id="b6d11-115">F# function values can be passed directly as arguments to delegate constructors.</span></span> <span data-ttu-id="b6d11-116">静的メソッドでは、クラスとメソッドの名前を使用してデリゲートを構築します。</span><span class="sxs-lookup"><span data-stu-id="b6d11-116">For a static method, you construct the delegate by using the name of the class and the method.</span></span> <span data-ttu-id="b6d11-117">インスタンス メソッドの場合は、オブジェクトのインスタンスと 1 つの引数でメソッドを指定します。</span><span class="sxs-lookup"><span data-stu-id="b6d11-117">For an instance method, you provide the object instance and method in one argument.</span></span> <span data-ttu-id="b6d11-118">どちらの場合で、メンバー アクセス演算子 (`.`) が使用されます。</span><span class="sxs-lookup"><span data-stu-id="b6d11-118">In both cases, the member access operator (`.`) is used.</span></span>

<span data-ttu-id="b6d11-119">`Invoke`デリゲート型のメソッドでは、カプセル化された関数を呼び出します。</span><span class="sxs-lookup"><span data-stu-id="b6d11-119">The `Invoke` method on the delegate type calls the encapsulated function.</span></span> <span data-ttu-id="b6d11-120">また、デリゲートは、かっこがない場合、Invoke メソッドの名前を参照して関数の値として渡すことができます。</span><span class="sxs-lookup"><span data-stu-id="b6d11-120">Also, delegates can be passed as function values by referencing the Invoke method name without the parentheses.</span></span>

<span data-ttu-id="b6d11-121">次のコードでは、クラスでさまざまなメソッドを表すデリゲートを作成するための構文を示します。</span><span class="sxs-lookup"><span data-stu-id="b6d11-121">The following code shows the syntax for creating delegates that represent various methods in a class.</span></span> <span data-ttu-id="b6d11-122">メソッドは、静的メソッドまたはインスタンス メソッドかどうかと、タプル形式またはカリー化されたフォームでの引数があるかどうか、によっては、宣言してデリゲートを割り当てるのための構文が少し異なります。</span><span class="sxs-lookup"><span data-stu-id="b6d11-122">Depending on whether the method is a static method or an instance method, and whether it has arguments in the tuple form or the curried form, the syntax for declaring and assigning the delegate is a little different.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4201.fs)]

<span data-ttu-id="b6d11-123">次のコードでは、デリゲートを扱うさまざまな方法の一部を示します。</span><span class="sxs-lookup"><span data-stu-id="b6d11-123">The following code shows some of the different ways you can work with delegates.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4202.fs)]

<span data-ttu-id="b6d11-124">上記のコード例の出力は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="b6d11-124">The output of the previous code example is as follows.</span></span>

```console
aaaaa
bbbbb
ccccc
[|"aaa"; "bbb"|]
```

## <a name="see-also"></a><span data-ttu-id="b6d11-125">関連項目</span><span class="sxs-lookup"><span data-stu-id="b6d11-125">See also</span></span>

- [<span data-ttu-id="b6d11-126">F# 言語リファレンス</span><span class="sxs-lookup"><span data-stu-id="b6d11-126">F# Language Reference</span></span>](index.md)
- [<span data-ttu-id="b6d11-127">パラメーターと引数</span><span class="sxs-lookup"><span data-stu-id="b6d11-127">Parameters and Arguments</span></span>](parameters-and-arguments.md)
- [<span data-ttu-id="b6d11-128">イベント</span><span class="sxs-lookup"><span data-stu-id="b6d11-128">Events</span></span>](members/events.md)