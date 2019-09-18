---
title: フレキシブル型
description: 柔軟な型のF#注釈を使用する方法について説明します。これは、パラメーター、変数、または値に、指定した型と互換性のある型があることを示します。
ms.date: 05/16/2016
ms.openlocfilehash: bf05f78f163d1f9c73c667df60925b66a5315627
ms.sourcegitcommit: a2d0e1f66367367065bc8dc0dde488ab536da73f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2019
ms.locfileid: "71083064"
---
# <a name="flexible-types"></a><span data-ttu-id="bf853-103">フレキシブル型</span><span class="sxs-lookup"><span data-stu-id="bf853-103">Flexible Types</span></span>

<span data-ttu-id="bf853-104">*柔軟な型の注釈*は、パラメーター、変数、または値に、指定された型と互換性のある型があることを示します。互換性は、クラスまたはインターフェイスのオブジェクト指向階層内の位置によって決まります。</span><span class="sxs-lookup"><span data-stu-id="bf853-104">A *flexible type annotation* indicates that a parameter, variable, or value has a type that is compatible with a specified type, where compatibility is determined by position in an object-oriented hierarchy of classes or interfaces.</span></span> <span data-ttu-id="bf853-105">柔軟な型は、型階層の上位にある型への自動変換が行われず、階層内の任意の型、またはインターフェイスを実装する任意の型で機能できるようにする場合に特に便利です。</span><span class="sxs-lookup"><span data-stu-id="bf853-105">Flexible types are useful specifically when the automatic conversion to types higher in the type hierarchy does not occur but you still want to enable your functionality to work with any type in the hierarchy or any type that implements an interface.</span></span>

## <a name="syntax"></a><span data-ttu-id="bf853-106">構文</span><span class="sxs-lookup"><span data-stu-id="bf853-106">Syntax</span></span>

```fsharp
#type
```

## <a name="remarks"></a><span data-ttu-id="bf853-107">Remarks</span><span class="sxs-lookup"><span data-stu-id="bf853-107">Remarks</span></span>

<span data-ttu-id="bf853-108">前の構文では、*型*は基本型またはインターフェイスを表します。</span><span class="sxs-lookup"><span data-stu-id="bf853-108">In the previous syntax, *type* represents a base type or an interface.</span></span>

<span data-ttu-id="bf853-109">柔軟な型は、基本型またはインターフェイス型と互換性のある型に対して許可される型を制限する制約を持つジェネリック型に相当します。</span><span class="sxs-lookup"><span data-stu-id="bf853-109">A flexible type is equivalent to a generic type that has a constraint that limits the allowed types to types that are compatible with the base or interface type.</span></span> <span data-ttu-id="bf853-110">つまり、次の2行のコードは同等です。</span><span class="sxs-lookup"><span data-stu-id="bf853-110">That is, the following two lines of code are equivalent.</span></span>

```fsharp
#SomeType

'T when 'T :> SomeType
```

<span data-ttu-id="bf853-111">柔軟性のある型は、さまざまな状況で役立ちます。</span><span class="sxs-lookup"><span data-stu-id="bf853-111">Flexible types are useful in several types of situations.</span></span> <span data-ttu-id="bf853-112">たとえば、高階関数 (関数を引数として受け取る関数) がある場合、多くの場合、関数が柔軟な型を返すようにすると便利です。</span><span class="sxs-lookup"><span data-stu-id="bf853-112">For example, when you have a higher order function (a function that takes a function as an argument), it is often useful to have the function return a flexible type.</span></span> <span data-ttu-id="bf853-113">次の例では、で`iterate2`シーケンス引数を持つ柔軟な型を使用することにより、高階関数を使用して、シーケンス、配列、リスト、およびその他の列挙可能な型を生成する関数を操作できます。</span><span class="sxs-lookup"><span data-stu-id="bf853-113">In the following example, the use of a flexible type with a sequence argument in `iterate2` enables the higher order function to work with functions that generate sequences, arrays, lists, and any other enumerable type.</span></span>

<span data-ttu-id="bf853-114">次の2つの関数について考えてみます。1つはシーケンスを返し、もう一方は柔軟な型を返します。</span><span class="sxs-lookup"><span data-stu-id="bf853-114">Consider the following two functions, one of which returns a sequence, the other of which returns a flexible type.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet4101.fs)]

<span data-ttu-id="bf853-115">もう1つの例として、 [Seq. concat](https://msdn.microsoft.com/library/2eeb69a9-fc2f-4b7d-8dee-101fa2b00712)ライブラリ関数を考えてみます。</span><span class="sxs-lookup"><span data-stu-id="bf853-115">As another example, consider the [Seq.concat](https://msdn.microsoft.com/library/2eeb69a9-fc2f-4b7d-8dee-101fa2b00712) library function:</span></span>

```fsharp
val concat: sequences:seq<#seq<'T>> -> seq<'T>
```

<span data-ttu-id="bf853-116">この関数には、次のいずれかの列挙可能なシーケンスを渡すことができます。</span><span class="sxs-lookup"><span data-stu-id="bf853-116">You can pass any of the following enumerable sequences to this function:</span></span>

- <span data-ttu-id="bf853-117">リストの一覧</span><span class="sxs-lookup"><span data-stu-id="bf853-117">A list of lists</span></span>
- <span data-ttu-id="bf853-118">配列の一覧</span><span class="sxs-lookup"><span data-stu-id="bf853-118">A list of arrays</span></span>
- <span data-ttu-id="bf853-119">リストの配列</span><span class="sxs-lookup"><span data-stu-id="bf853-119">An array of lists</span></span>
- <span data-ttu-id="bf853-120">シーケンスの配列</span><span class="sxs-lookup"><span data-stu-id="bf853-120">An array of sequences</span></span>
- <span data-ttu-id="bf853-121">列挙可能なシーケンスのその他の組み合わせ</span><span class="sxs-lookup"><span data-stu-id="bf853-121">Any other combination of enumerable sequences</span></span>

<span data-ttu-id="bf853-122">次のコードで`Seq.concat`は、を使用して、柔軟な型を使用してサポートできるシナリオを示します。</span><span class="sxs-lookup"><span data-stu-id="bf853-122">The following code uses `Seq.concat` to demonstrate the scenarios that you can support by using flexible types.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet4102.fs)]

<span data-ttu-id="bf853-123">出力は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="bf853-123">The output is as follows.</span></span>

```console
seq [1; 2; 3; 4; ...]
seq [1; 2; 3; 4; ...]
seq [1; 2; 3; 4; ...]
seq [1; 2; 3; 4; ...]
seq [1; 2; 3; 4; ...]
```

<span data-ttu-id="bf853-124">でF#は、他のオブジェクト指向言語と同様に、インターフェイスを実装する派生型または型が基本型またはインターフェイス型に自動的に変換されるコンテキストがあります。</span><span class="sxs-lookup"><span data-stu-id="bf853-124">In F#, as in other object-oriented languages, there are contexts in which derived types or types that implement interfaces are automatically converted to a base type or interface type.</span></span> <span data-ttu-id="bf853-125">これらの自動変換は直接引数で行われますが、型が下位の位置にある場合や、型が関数型の戻り値の型などのより複雑な型の一部として、または型引数として存在する場合には発生しません。</span><span class="sxs-lookup"><span data-stu-id="bf853-125">These automatic conversions occur in direct arguments, but not when the type is in a subordinate position, as part of a more complex type such as a return type of a function type, or as a type argument.</span></span> <span data-ttu-id="bf853-126">したがって、柔軟な型表記は、それを適用している型がより複雑な型の一部である場合に、主に役立ちます。</span><span class="sxs-lookup"><span data-stu-id="bf853-126">Thus, the flexible type notation is primarily useful when the type you are applying it to is part of a more complex type.</span></span>

## <a name="see-also"></a><span data-ttu-id="bf853-127">関連項目</span><span class="sxs-lookup"><span data-stu-id="bf853-127">See also</span></span>

- [<span data-ttu-id="bf853-128">F# 言語リファレンス</span><span class="sxs-lookup"><span data-stu-id="bf853-128">F# Language Reference</span></span>](index.md)
- [<span data-ttu-id="bf853-129">ジェネリック</span><span class="sxs-lookup"><span data-stu-id="bf853-129">Generics</span></span>](./generics/index.md)
