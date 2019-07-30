---
title: デリゲート
description: でF#デリゲートを使用する方法について説明します。
ms.date: 05/16/2016
ms.openlocfilehash: 65875897d5fc4b2ac66f1dfbe913f29fb74137cd
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/30/2019
ms.locfileid: "68630372"
---
# <a name="delegates"></a><span data-ttu-id="77f9f-103">デリゲート</span><span class="sxs-lookup"><span data-stu-id="77f9f-103">Delegates</span></span>

<span data-ttu-id="77f9f-104">デリゲートは、関数呼び出しをオブジェクトとして表します。</span><span class="sxs-lookup"><span data-stu-id="77f9f-104">A delegate represents a function call as an object.</span></span> <span data-ttu-id="77f9f-105">でF#は、関数を最初のクラスの値として表すために、通常は関数の値を使用する必要があります。ただし、デリゲートは .NET Framework で使用されるため、想定される Api と相互運用するときに必要になります。</span><span class="sxs-lookup"><span data-stu-id="77f9f-105">In F#, you ordinarily should use function values to represent functions as first-class values; however, delegates are used in the .NET Framework and so are needed when you interoperate with APIs that expect them.</span></span> <span data-ttu-id="77f9f-106">また、他の .NET Framework 言語から使用できるように設計されたライブラリを作成するときにも使用できます。</span><span class="sxs-lookup"><span data-stu-id="77f9f-106">They may also be used when authoring libraries designed for use from other .NET Framework languages.</span></span>

## <a name="syntax"></a><span data-ttu-id="77f9f-107">構文</span><span class="sxs-lookup"><span data-stu-id="77f9f-107">Syntax</span></span>

```fsharp
type delegate-typename = delegate of type1 -> type2
```

## <a name="remarks"></a><span data-ttu-id="77f9f-108">Remarks</span><span class="sxs-lookup"><span data-stu-id="77f9f-108">Remarks</span></span>

<span data-ttu-id="77f9f-109">前の構文では`type1` 、は引数の型または`type2`型を表し、戻り値の型を表します。</span><span class="sxs-lookup"><span data-stu-id="77f9f-109">In the previous syntax, `type1` represents the argument type or types and `type2` represents the return type.</span></span> <span data-ttu-id="77f9f-110">によって`type1`表される引数の型は、自動的にカリー化されます。</span><span class="sxs-lookup"><span data-stu-id="77f9f-110">The argument types that are represented by `type1` are automatically curried.</span></span> <span data-ttu-id="77f9f-111">これにより、この型では、対象の関数の引数がカリー化されている場合は組形式を使用し、既にタプル形式の引数にはかっこで囲まれたタプルを使用することが推奨されます。</span><span class="sxs-lookup"><span data-stu-id="77f9f-111">This suggests that for this type you use a tuple form if the arguments of the target function are curried, and a parenthesized tuple for arguments that are already in the tuple form.</span></span> <span data-ttu-id="77f9f-112">自動カリー化は、対象のメソッドに一致するタプル引数を残して、一連のかっこを削除します。</span><span class="sxs-lookup"><span data-stu-id="77f9f-112">The automatic currying removes a set of parentheses, leaving a tuple argument that matches the target method.</span></span> <span data-ttu-id="77f9f-113">各ケースで使用する構文については、コード例を参照してください。</span><span class="sxs-lookup"><span data-stu-id="77f9f-113">Refer to the code example for the syntax you should use in each case.</span></span>

<span data-ttu-id="77f9f-114">デリゲートは、F# 関数値、および静的に接続できるまたはインスタンス メソッド。</span><span class="sxs-lookup"><span data-stu-id="77f9f-114">Delegates can be attached to F# function values, and static or instance methods.</span></span> <span data-ttu-id="77f9f-115">デリゲート コンストラクターに引数として直接 F# 関数値を渡すことができます。</span><span class="sxs-lookup"><span data-stu-id="77f9f-115">F# function values can be passed directly as arguments to delegate constructors.</span></span> <span data-ttu-id="77f9f-116">静的メソッドの場合は、クラスの名前とメソッドを使用してデリゲートを構築します。</span><span class="sxs-lookup"><span data-stu-id="77f9f-116">For a static method, you construct the delegate by using the name of the class and the method.</span></span> <span data-ttu-id="77f9f-117">インスタンスメソッドの場合は、1つの引数にオブジェクトのインスタンスとメソッドを指定します。</span><span class="sxs-lookup"><span data-stu-id="77f9f-117">For an instance method, you provide the object instance and method in one argument.</span></span> <span data-ttu-id="77f9f-118">どちらの場合も、メンバーアクセス演算子 (`.`) が使用されます。</span><span class="sxs-lookup"><span data-stu-id="77f9f-118">In both cases, the member access operator (`.`) is used.</span></span>

<span data-ttu-id="77f9f-119">デリゲート`Invoke`型のメソッドは、カプセル化された関数を呼び出します。</span><span class="sxs-lookup"><span data-stu-id="77f9f-119">The `Invoke` method on the delegate type calls the encapsulated function.</span></span> <span data-ttu-id="77f9f-120">また、デリゲートを関数値として渡すには、呼び出しメソッド名をかっこで囲んで参照します。</span><span class="sxs-lookup"><span data-stu-id="77f9f-120">Also, delegates can be passed as function values by referencing the Invoke method name without the parentheses.</span></span>

<span data-ttu-id="77f9f-121">次のコードは、クラス内のさまざまなメソッドを表すデリゲートを作成するための構文を示しています。</span><span class="sxs-lookup"><span data-stu-id="77f9f-121">The following code shows the syntax for creating delegates that represent various methods in a class.</span></span> <span data-ttu-id="77f9f-122">メソッドが静的メソッドとインスタンスメソッドのどちらであるか、また、タプル形式またはカリー化形式の引数があるかどうかによって、デリゲートの宣言と割り当ての構文は少し異なります。</span><span class="sxs-lookup"><span data-stu-id="77f9f-122">Depending on whether the method is a static method or an instance method, and whether it has arguments in the tuple form or the curried form, the syntax for declaring and assigning the delegate is a little different.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet4201.fs)]

<span data-ttu-id="77f9f-123">次のコードは、デリゲートを操作するためのさまざまな方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="77f9f-123">The following code shows some of the different ways you can work with delegates.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet4202.fs)]

<span data-ttu-id="77f9f-124">前のコード例の出力は次のようになります。</span><span class="sxs-lookup"><span data-stu-id="77f9f-124">The output of the previous code example is as follows.</span></span>

```console
aaaaa
bbbbb
ccccc
[|"aaa"; "bbb"|]
```

## <a name="see-also"></a><span data-ttu-id="77f9f-125">関連項目</span><span class="sxs-lookup"><span data-stu-id="77f9f-125">See also</span></span>

- [<span data-ttu-id="77f9f-126">F# 言語リファレンス</span><span class="sxs-lookup"><span data-stu-id="77f9f-126">F# Language Reference</span></span>](index.md)
- [<span data-ttu-id="77f9f-127">パラメーターと引数</span><span class="sxs-lookup"><span data-stu-id="77f9f-127">Parameters and Arguments</span></span>](parameters-and-arguments.md)
- [<span data-ttu-id="77f9f-128">イベント</span><span class="sxs-lookup"><span data-stu-id="77f9f-128">Events</span></span>](./members/events.md)
