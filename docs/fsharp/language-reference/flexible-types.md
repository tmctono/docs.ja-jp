---
title: フレキシブル型
description: 使用する方法について説明しますF#柔軟な型の注釈は、パラメーター、変数、または値に指定した型と互換性がある型があることを示します。
ms.date: 05/16/2016
ms.openlocfilehash: 32857cc317bc6b4b7baf53b623b551e8e0733e41
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61981384"
---
# <a name="flexible-types"></a><span data-ttu-id="2713d-103">フレキシブル型</span><span class="sxs-lookup"><span data-stu-id="2713d-103">Flexible Types</span></span>

<span data-ttu-id="2713d-104">A*柔軟な型の注釈*パラメーター、変数、または値に互換性がクラスまたはインターフェイスのオブジェクト指向の階層内の位置によって決まりますが、種類を指定して互換性のある型があることを示します。</span><span class="sxs-lookup"><span data-stu-id="2713d-104">A *flexible type annotation* indicates that a parameter, variable, or value has a type that is compatible with a specified type, where compatibility is determined by position in an object-oriented hierarchy of classes or interfaces.</span></span> <span data-ttu-id="2713d-105">フレキシブル型は、型の階層で上位の型への自動変換は発生しませんが、階層内の任意の型またはインターフェイスを実装する任意の型を使用する、機能を有効にするときに特に便利です。</span><span class="sxs-lookup"><span data-stu-id="2713d-105">Flexible types are useful specifically when the automatic conversion to types higher in the type hierarchy does not occur but you still want to enable your functionality to work with any type in the hierarchy or any type that implements an interface.</span></span>

## <a name="syntax"></a><span data-ttu-id="2713d-106">構文</span><span class="sxs-lookup"><span data-stu-id="2713d-106">Syntax</span></span>

```fsharp
#type
```

## <a name="remarks"></a><span data-ttu-id="2713d-107">Remarks</span><span class="sxs-lookup"><span data-stu-id="2713d-107">Remarks</span></span>

<span data-ttu-id="2713d-108">前の構文で*型*基本データ型またはインターフェイスを表します。</span><span class="sxs-lookup"><span data-stu-id="2713d-108">In the previous syntax, *type* represents a base type or an interface.</span></span>

<span data-ttu-id="2713d-109">柔軟な型では、基本またはインターフェイス型と互換性がある型に使用できる型を制限する制約を持つジェネリック型に相当します。</span><span class="sxs-lookup"><span data-stu-id="2713d-109">A flexible type is equivalent to a generic type that has a constraint that limits the allowed types to types that are compatible with the base or interface type.</span></span> <span data-ttu-id="2713d-110">つまり、次の 2 行のコードは同等です。</span><span class="sxs-lookup"><span data-stu-id="2713d-110">That is, the following two lines of code are equivalent.</span></span>

```fsharp
#SomeType

'T when 'T :> SomeType
```

<span data-ttu-id="2713d-111">フレキシブル型は、いくつかの種類の状況で便利です。</span><span class="sxs-lookup"><span data-stu-id="2713d-111">Flexible types are useful in several types of situations.</span></span> <span data-ttu-id="2713d-112">たとえば、高階関数 (引数として関数を受け取る関数) を使用するは、柔軟な型を返す関数を用意すると便利は多くの場合。</span><span class="sxs-lookup"><span data-stu-id="2713d-112">For example, when you have a higher order function (a function that takes a function as an argument), it is often useful to have the function return a flexible type.</span></span> <span data-ttu-id="2713d-113">次の例では、シーケンスに引数を持つ柔軟な型を使用して`iterate2`シーケンス、配列、リスト、およびその他の列挙可能な型を生成する関数を使用する、高階関数を使用します。</span><span class="sxs-lookup"><span data-stu-id="2713d-113">In the following example, the use of a flexible type with a sequence argument in `iterate2` enables the higher order function to work with functions that generate sequences, arrays, lists, and any other enumerable type.</span></span>

<span data-ttu-id="2713d-114">次の 2 つ関数のシーケンスを返しますが、柔軟な型を返しますが、その他のいずれかを検討してください。</span><span class="sxs-lookup"><span data-stu-id="2713d-114">Consider the following two functions, one of which returns a sequence, the other of which returns a flexible type.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4101.fs)]

<span data-ttu-id="2713d-115">別の例として、 [Seq.concat](https://msdn.microsoft.com/library/2eeb69a9-fc2f-4b7d-8dee-101fa2b00712)ライブラリ関数。</span><span class="sxs-lookup"><span data-stu-id="2713d-115">As another example, consider the [Seq.concat](https://msdn.microsoft.com/library/2eeb69a9-fc2f-4b7d-8dee-101fa2b00712) library function:</span></span>

```fsharp
val concat: sequences:seq<#seq<'T>> -> seq<'T>
```

<span data-ttu-id="2713d-116">次の列挙可能なシーケンスのいずれかは、この関数に渡すことができます。</span><span class="sxs-lookup"><span data-stu-id="2713d-116">You can pass any of the following enumerable sequences to this function:</span></span>

- <span data-ttu-id="2713d-117">リストの一覧</span><span class="sxs-lookup"><span data-stu-id="2713d-117">A list of lists</span></span>
- <span data-ttu-id="2713d-118">配列の一覧</span><span class="sxs-lookup"><span data-stu-id="2713d-118">A list of arrays</span></span>
- <span data-ttu-id="2713d-119">リストの配列</span><span class="sxs-lookup"><span data-stu-id="2713d-119">An array of lists</span></span>
- <span data-ttu-id="2713d-120">シーケンスの配列</span><span class="sxs-lookup"><span data-stu-id="2713d-120">An array of sequences</span></span>
- <span data-ttu-id="2713d-121">列挙可能なシーケンスの他の任意の組み合わせ</span><span class="sxs-lookup"><span data-stu-id="2713d-121">Any other combination of enumerable sequences</span></span>

<span data-ttu-id="2713d-122">次のコードでは`Seq.concat`に柔軟な型を使用してサポートできるシナリオについて説明します。</span><span class="sxs-lookup"><span data-stu-id="2713d-122">The following code uses `Seq.concat` to demonstrate the scenarios that you can support by using flexible types.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4102.fs)]

<span data-ttu-id="2713d-123">出力は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="2713d-123">The output is as follows.</span></span>

```
seq [1; 2; 3; 4; ...]
seq [1; 2; 3; 4; ...]
seq [1; 2; 3; 4; ...]
seq [1; 2; 3; 4; ...]
seq [1; 2; 3; 4; ...]
```

<span data-ttu-id="2713d-124">F#、その他のオブジェクト指向の言語があるコンテキストを派生型またはインターフェイスを実装する型が基本型またはインターフェイス型に自動的に変換します。</span><span class="sxs-lookup"><span data-stu-id="2713d-124">In F#, as in other object-oriented languages, there are contexts in which derived types or types that implement interfaces are automatically converted to a base type or interface type.</span></span> <span data-ttu-id="2713d-125">直接の引数が関数の型の戻り値の型などのより複雑な型の一部として、または型引数として、下位の位置での型がの場合は、これらの自動変換が発生します。</span><span class="sxs-lookup"><span data-stu-id="2713d-125">These automatic conversions occur in direct arguments, but not when the type is in a subordinate position, as part of a more complex type such as a return type of a function type, or as a type argument.</span></span> <span data-ttu-id="2713d-126">したがってに適用する型がより複雑な型の一部である場合は、柔軟な表記は主に役立ちます。</span><span class="sxs-lookup"><span data-stu-id="2713d-126">Thus, the flexible type notation is primarily useful when the type you are applying it to is part of a more complex type.</span></span>

## <a name="see-also"></a><span data-ttu-id="2713d-127">関連項目</span><span class="sxs-lookup"><span data-stu-id="2713d-127">See also</span></span>

- [<span data-ttu-id="2713d-128">F# 言語リファレンス</span><span class="sxs-lookup"><span data-stu-id="2713d-128">F# Language Reference</span></span>](index.md)
- [<span data-ttu-id="2713d-129">ジェネリック</span><span class="sxs-lookup"><span data-stu-id="2713d-129">Generics</span></span>](generics/index.md)