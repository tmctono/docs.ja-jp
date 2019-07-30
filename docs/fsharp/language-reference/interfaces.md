---
title: インターフェイス
description: 他のF#クラスが実装する関連メンバーのセットをインターフェイスが指定する方法について説明します。
ms.date: 05/16/2016
ms.openlocfilehash: 8f054a668ad0fbc2453a45883e8052471280eca3
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/30/2019
ms.locfileid: "68627650"
---
# <a name="interfaces"></a><span data-ttu-id="55cd1-103">インターフェイス</span><span class="sxs-lookup"><span data-stu-id="55cd1-103">Interfaces</span></span>

<span data-ttu-id="55cd1-104">*インターフェイス*は、他のクラスが実装する関連メンバーのセットを指定します。</span><span class="sxs-lookup"><span data-stu-id="55cd1-104">*Interfaces* specify sets of related members that other classes implement.</span></span>

## <a name="syntax"></a><span data-ttu-id="55cd1-105">構文</span><span class="sxs-lookup"><span data-stu-id="55cd1-105">Syntax</span></span>

```fsharp
// Interface declaration:
[ attributes ]
type [accessibility-modifier] interface-name =
    [ interface ]     [ inherit base-interface-name ...]
    abstract member1 : [ argument-types1 -> ] return-type1
    abstract member2 : [ argument-types2 -> ] return-type2
    ...
[ end ]

// Implementing, inside a class type definition:
interface interface-name with
    member self-identifier.member1argument-list = method-body1
    member self-identifier.member2argument-list = method-body2

// Implementing, by using an object expression:
[ attributes ]
let class-name (argument-list) =
    { new interface-name with
        member self-identifier.member1argument-list = method-body1
        member self-identifier.member2argument-list = method-body2
        [ base-interface-definitions ]
    }
    member-list
```

## <a name="remarks"></a><span data-ttu-id="55cd1-106">Remarks</span><span class="sxs-lookup"><span data-stu-id="55cd1-106">Remarks</span></span>

<span data-ttu-id="55cd1-107">インターフェイス宣言は、メンバーが実装されていないことを除いて、クラス宣言に似ています。</span><span class="sxs-lookup"><span data-stu-id="55cd1-107">Interface declarations resemble class declarations except that no members are implemented.</span></span> <span data-ttu-id="55cd1-108">代わりに、キーワード`abstract`によって示されているように、すべてのメンバーが抽象型になります。</span><span class="sxs-lookup"><span data-stu-id="55cd1-108">Instead, all the members are abstract, as indicated by the keyword `abstract`.</span></span> <span data-ttu-id="55cd1-109">抽象メソッドにメソッド本体を指定することはできません。</span><span class="sxs-lookup"><span data-stu-id="55cd1-109">You do not provide a method body for abstract methods.</span></span> <span data-ttu-id="55cd1-110">ただし、 `default`キーワードと共にメンバーの別の定義をメソッドとして含めることで、既定の実装を提供することもできます。</span><span class="sxs-lookup"><span data-stu-id="55cd1-110">However, you can provide a default implementation by also including a separate definition of the member as a method together with the `default` keyword.</span></span> <span data-ttu-id="55cd1-111">これは、他の .NET 言語で基底クラスの仮想メソッドを作成することと同じです。</span><span class="sxs-lookup"><span data-stu-id="55cd1-111">Doing so is equivalent to creating a virtual method in a base class in other .NET languages.</span></span> <span data-ttu-id="55cd1-112">このような仮想メソッドは、インターフェイスを実装するクラスでオーバーライドできます。</span><span class="sxs-lookup"><span data-stu-id="55cd1-112">Such a virtual method can be overridden in classes that implement the interface.</span></span>

<span data-ttu-id="55cd1-113">インターフェイスの既定のアクセシビリティは`public`です。</span><span class="sxs-lookup"><span data-stu-id="55cd1-113">The default accessibility for interfaces is `public`.</span></span>

<span data-ttu-id="55cd1-114">各メソッドのパラメーターに通常の F# 構文を使用して名前を付けることができます必要に応じて。</span><span class="sxs-lookup"><span data-stu-id="55cd1-114">You can optionally give each method parameter a name using normal F# syntax:</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet24032.fs)]

<span data-ttu-id="55cd1-115">上`ISprintable`の例`Print`では、メソッドには、という名前`format`の`string`型の1つのパラメーターがあります。</span><span class="sxs-lookup"><span data-stu-id="55cd1-115">In the above `ISprintable` example, the `Print` method has a single parameter of the type `string` with the name `format`.</span></span>

<span data-ttu-id="55cd1-116">インターフェイスを実装するには、オブジェクト式を使用する方法とクラス型を使用する方法の2つの方法があります。</span><span class="sxs-lookup"><span data-stu-id="55cd1-116">There are two ways to implement interfaces: by using object expressions, and by using class types.</span></span> <span data-ttu-id="55cd1-117">どちらの場合も、クラス型またはオブジェクト式は、インターフェイスの抽象メソッドにメソッド本体を提供します。</span><span class="sxs-lookup"><span data-stu-id="55cd1-117">In either case, the class type or object expression provides method bodies for abstract methods of the interface.</span></span> <span data-ttu-id="55cd1-118">実装は、インターフェイスを実装する各型に固有です。</span><span class="sxs-lookup"><span data-stu-id="55cd1-118">Implementations are specific to each type that implements the interface.</span></span> <span data-ttu-id="55cd1-119">したがって、異なる型のインターフェイスメソッドは相互に異なる場合があります。</span><span class="sxs-lookup"><span data-stu-id="55cd1-119">Therefore, interface methods on different types might be different from each other.</span></span>

<span data-ttu-id="55cd1-120">簡易構文`interface`を`end`使用する場合、定義の開始と終了をマークするキーワードとは省略可能です。</span><span class="sxs-lookup"><span data-stu-id="55cd1-120">The keywords `interface` and `end`, which mark the start and end of the definition, are optional when you use lightweight syntax.</span></span> <span data-ttu-id="55cd1-121">これらのキーワードを使用しない場合、コンパイラは、使用するコンストラクトを分析することで、型がクラスであるかインターフェイスであるかを推論しようとします。</span><span class="sxs-lookup"><span data-stu-id="55cd1-121">If you do not use these keywords, the compiler attempts to infer whether the type is a class or an interface by analyzing the constructs that you use.</span></span> <span data-ttu-id="55cd1-122">メンバーを定義する場合、または他のクラス構文を使用する場合、型はクラスとして解釈されます。</span><span class="sxs-lookup"><span data-stu-id="55cd1-122">If you define a member or use other class syntax, the type is interpreted as a class.</span></span>

<span data-ttu-id="55cd1-123">.NET のコーディングスタイルでは、すべてのインターフェイスを大文字`I`で開始します。</span><span class="sxs-lookup"><span data-stu-id="55cd1-123">The .NET coding style is to begin all interfaces with a capital `I`.</span></span>

## <a name="implementing-interfaces-by-using-class-types"></a><span data-ttu-id="55cd1-124">クラス型を使用したインターフェイスの実装</span><span class="sxs-lookup"><span data-stu-id="55cd1-124">Implementing Interfaces by Using Class Types</span></span>

<span data-ttu-id="55cd1-125">次のコードに示すように、 `interface`キーワード、インターフェイスの名前、 `with`およびキーワードを使用して、クラス型に1つ以上のインターフェイスを実装することができます。</span><span class="sxs-lookup"><span data-stu-id="55cd1-125">You can implement one or more interfaces in a class type by using the `interface` keyword, the name of the interface, and the `with` keyword, followed by the interface member definitions, as shown in the following code.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet2801.fs)]

<span data-ttu-id="55cd1-126">インターフェイスの実装は継承されるため、派生クラスはそれらを再実装する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="55cd1-126">Interface implementations are inherited, so any derived classes do not need to reimplement them.</span></span>

## <a name="calling-interface-methods"></a><span data-ttu-id="55cd1-127">インターフェイスメソッドの呼び出し</span><span class="sxs-lookup"><span data-stu-id="55cd1-127">Calling Interface Methods</span></span>

<span data-ttu-id="55cd1-128">インターフェイスメソッドを呼び出すことができるのは、インターフェイスを実装する型のオブジェクトではなく、インターフェイスのみです。</span><span class="sxs-lookup"><span data-stu-id="55cd1-128">Interface methods can be called only through the interface, not through any object of the type that implements the interface.</span></span> <span data-ttu-id="55cd1-129">そのため、これらのメソッドを呼び出すに`:>` `upcast`は、演算子または演算子を使用して、インターフェイス型にアップキャストすることが必要になる場合があります。</span><span class="sxs-lookup"><span data-stu-id="55cd1-129">Thus, you might have to upcast to the interface type by using the `:>` operator or the `upcast` operator in order to call these methods.</span></span>

<span data-ttu-id="55cd1-130">型`SomeClass`のオブジェクトがある場合にインターフェイスメソッドを呼び出すには、次のコードに示すように、オブジェクトをインターフェイス型にアップキャストする必要があります。</span><span class="sxs-lookup"><span data-stu-id="55cd1-130">To call the interface method when you have an object of type `SomeClass`, you must upcast the object to the interface type, as shown in the following code.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet2802.fs)]

<span data-ttu-id="55cd1-131">別の方法として、次の例のように、キャストしてインターフェイスメソッドを呼び出すオブジェクトに対してメソッドを宣言する方法があります。</span><span class="sxs-lookup"><span data-stu-id="55cd1-131">An alternative is to declare a method on the object that upcasts and calls the interface method, as in the following example.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet2803.fs)]

## <a name="implementing-interfaces-by-using-object-expressions"></a><span data-ttu-id="55cd1-132">オブジェクト式を使用したインターフェイスの実装</span><span class="sxs-lookup"><span data-stu-id="55cd1-132">Implementing Interfaces by Using Object Expressions</span></span>

<span data-ttu-id="55cd1-133">オブジェクト式は、インターフェイスを実装するための簡単な方法を提供します。</span><span class="sxs-lookup"><span data-stu-id="55cd1-133">Object expressions provide a short way to implement an interface.</span></span> <span data-ttu-id="55cd1-134">これらは、名前付きの型を作成する必要がなく、インターフェイスメソッドをサポートするオブジェクトを必要とする場合に、追加のメソッドを使用しない場合に便利です。</span><span class="sxs-lookup"><span data-stu-id="55cd1-134">They are useful when you do not have to create a named type, and you just want an object that supports the interface methods, without any additional methods.</span></span> <span data-ttu-id="55cd1-135">オブジェクト式を次のコードに示します。</span><span class="sxs-lookup"><span data-stu-id="55cd1-135">An object expression is illustrated in the following code.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet2804.fs)]

## <a name="interface-inheritance"></a><span data-ttu-id="55cd1-136">インターフェイスの継承</span><span class="sxs-lookup"><span data-stu-id="55cd1-136">Interface Inheritance</span></span>

<span data-ttu-id="55cd1-137">インターフェイスは、1つまたは複数の基本インターフェイスから継承できます。</span><span class="sxs-lookup"><span data-stu-id="55cd1-137">Interfaces can inherit from one or more base interfaces.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet2805.fs)]

## <a name="see-also"></a><span data-ttu-id="55cd1-138">関連項目</span><span class="sxs-lookup"><span data-stu-id="55cd1-138">See also</span></span>

- [<span data-ttu-id="55cd1-139">F# 言語リファレンス</span><span class="sxs-lookup"><span data-stu-id="55cd1-139">F# Language Reference</span></span>](index.md)
- [<span data-ttu-id="55cd1-140">オブジェクト式</span><span class="sxs-lookup"><span data-stu-id="55cd1-140">Object Expressions</span></span>](object-expressions.md)
- [<span data-ttu-id="55cd1-141">クラス</span><span class="sxs-lookup"><span data-stu-id="55cd1-141">Classes</span></span>](classes.md)
