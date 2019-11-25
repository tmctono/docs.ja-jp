---
title: new 演算子 - C# リファレンス
ms.custom: seodec18
ms.date: 06/25/2019
helpviewer_keywords:
- new operator keyword [C#]
ms.assetid: a212b697-a79b-4105-9923-1f7b108036e8
ms.openlocfilehash: c21132a6622ce697fe3c52a461a33f548e0c8f31
ms.sourcegitcommit: ad800f019ac976cb669e635fb0ea49db740e6890
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/29/2019
ms.locfileid: "73036385"
---
# <a name="new-operator-c-reference"></a><span data-ttu-id="d40e9-102">new 演算子 (C# リファレンス)</span><span class="sxs-lookup"><span data-stu-id="d40e9-102">new operator (C# reference)</span></span>

<span data-ttu-id="d40e9-103">`new` 演算子は型の新しいインスタンスを作成します。</span><span class="sxs-lookup"><span data-stu-id="d40e9-103">The `new` operator creates a new instance of a type.</span></span>

<span data-ttu-id="d40e9-104">`new` キーワードは、[メンバーの宣言修飾子](../keywords/new-modifier.md)または[ジェネリック型制約](../keywords/new-constraint.md)として使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="d40e9-104">You can also use the `new` keyword as a [member declaration modifier](../keywords/new-modifier.md) or a [generic type constraint](../keywords/new-constraint.md).</span></span>

## <a name="constructor-invocation"></a><span data-ttu-id="d40e9-105">コンストラクターの呼び出し</span><span class="sxs-lookup"><span data-stu-id="d40e9-105">Constructor invocation</span></span>

<span data-ttu-id="d40e9-106">型の新しいインスタンスを作成するには、通常は `new` 演算子を使用して、その型の[コンストラクター](../../programming-guide/classes-and-structs/constructors.md)の 1 つを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="d40e9-106">To create a new instance of a type, you typically invoke one of the [constructors](../../programming-guide/classes-and-structs/constructors.md) of that type using the `new` operator:</span></span>

[!code-csharp-interactive[invoke constructor](~/samples/csharp/language-reference/operators/NewOperator.cs#Constructor)]

<span data-ttu-id="d40e9-107">[オブジェクトまたはコレクション初期化子](../../programming-guide/classes-and-structs/object-and-collection-initializers.md)を `new` 演算子と共に使用して、1 つのステートメント内でオブジェクトのインスタンス化と初期化を行うことができます。次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="d40e9-107">You can use an [object or collection initializer](../../programming-guide/classes-and-structs/object-and-collection-initializers.md) with the `new` operator to instantiate and initialize an object in one statement, as the following example shows:</span></span>

[!code-csharp-interactive[constructor with initializer](~/samples/csharp/language-reference/operators/NewOperator.cs#ConstructorWithInitializer)]

## <a name="array-creation"></a><span data-ttu-id="d40e9-108">配列の作成</span><span class="sxs-lookup"><span data-stu-id="d40e9-108">Array creation</span></span>

<span data-ttu-id="d40e9-109">`new` 演算子を使用して配列インスタンスを作成することもできます。次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="d40e9-109">You also use the `new` operator to create an array instance, as the following example shows:</span></span>

[!code-csharp-interactive[create array](~/samples/csharp/language-reference/operators/NewOperator.cs#Array)]

<span data-ttu-id="d40e9-110">1 つのステートメント内で配列の初期化構文を使用して配列インスタンスを作成し、そこに要素を設定します。</span><span class="sxs-lookup"><span data-stu-id="d40e9-110">Use array initialization syntax to create an array instance and populate it with elements in one statement.</span></span> <span data-ttu-id="d40e9-111">次の例に、これを行うためのさまざまな方法を示します。</span><span class="sxs-lookup"><span data-stu-id="d40e9-111">The following example shows various ways how you can do that:</span></span>

[!code-csharp-interactive[initialize array](~/samples/csharp/language-reference/operators/NewOperator.cs#ArrayInitialization)]

<span data-ttu-id="d40e9-112">配列の詳細については、「[配列](../../programming-guide/arrays/index.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d40e9-112">For more information about arrays, see [Arrays](../../programming-guide/arrays/index.md).</span></span>

## <a name="instantiation-of-anonymous-types"></a><span data-ttu-id="d40e9-113">匿名型のインスタンス化</span><span class="sxs-lookup"><span data-stu-id="d40e9-113">Instantiation of anonymous types</span></span>

<span data-ttu-id="d40e9-114">[匿名型](../../programming-guide/classes-and-structs/anonymous-types.md)のインスタンスを作成するには、`new` 演算子とオブジェクト初期化子構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="d40e9-114">To create an instance of an [anonymous type](../../programming-guide/classes-and-structs/anonymous-types.md), use the `new` operator and object initializer syntax:</span></span>

[!code-csharp-interactive[anonymous type](~/samples/csharp/language-reference/operators/NewOperator.cs#AnonymousType)]

## <a name="destruction-of-type-instances"></a><span data-ttu-id="d40e9-115">型インスタンストの破棄</span><span class="sxs-lookup"><span data-stu-id="d40e9-115">Destruction of type instances</span></span>

<span data-ttu-id="d40e9-116">以前作成した型のインスタンスを破棄する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="d40e9-116">You don't have to destroy earlier created type instances.</span></span> <span data-ttu-id="d40e9-117">参照型と値型のインスタンスは両方とも自動的に破棄されます。</span><span class="sxs-lookup"><span data-stu-id="d40e9-117">Instances of both reference and value types are destroyed automatically.</span></span> <span data-ttu-id="d40e9-118">値型のインスタンスは、それらを格納しているコンテキストが破棄されるとすぐに破棄されます。</span><span class="sxs-lookup"><span data-stu-id="d40e9-118">Instances of value types are destroyed as soon as the context that contains them is destroyed.</span></span> <span data-ttu-id="d40e9-119">参照型のインスタンスは[ガベージ コレクター](../../../standard/garbage-collection/index.md)によって、そのインスタンスへの最後の参照が削除された後、不特定のタイミングで破棄されます。</span><span class="sxs-lookup"><span data-stu-id="d40e9-119">Instances of reference types are destroyed by the [garbage collector](../../../standard/garbage-collection/index.md) at unspecified time after the last reference to them is removed.</span></span>

<span data-ttu-id="d40e9-120">ファイル ハンドルなどのアンマネージド リソースを含む型インスタンスの場合、格納されているリソースができるだけ早く確実に解放されるように、決定的なクリーンアップを使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="d40e9-120">For type instances that contain unmanaged resources, for example, a file handle, it's recommended to employ deterministic clean-up to ensure that the resources they contain are released as soon as possible.</span></span> <span data-ttu-id="d40e9-121">詳細については、<xref:System.IDisposable?displayProperty=nameWithType> API リファレンスと [using ステートメント](../keywords/using-statement.md)に関する記事を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d40e9-121">For more information, see the <xref:System.IDisposable?displayProperty=nameWithType> API reference and the [using statement](../keywords/using-statement.md) article.</span></span>

## <a name="operator-overloadability"></a><span data-ttu-id="d40e9-122">演算子のオーバーロード可/不可</span><span class="sxs-lookup"><span data-stu-id="d40e9-122">Operator overloadability</span></span>

<span data-ttu-id="d40e9-123">ユーザー定義型は `new` 演算子をオーバーロードできません。</span><span class="sxs-lookup"><span data-stu-id="d40e9-123">A user-defined type cannot overload the `new` operator.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="d40e9-124">C# 言語仕様</span><span class="sxs-lookup"><span data-stu-id="d40e9-124">C# language specification</span></span>

<span data-ttu-id="d40e9-125">詳細については、[C# 言語仕様](~/_csharplang/spec/introduction.md)の [new 演算子](~/_csharplang/spec/expressions.md#the-new-operator)に関するセクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="d40e9-125">For more information, see [The new operator](~/_csharplang/spec/expressions.md#the-new-operator) section of the [C# language specification](~/_csharplang/spec/introduction.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="d40e9-126">関連項目</span><span class="sxs-lookup"><span data-stu-id="d40e9-126">See also</span></span>

- [<span data-ttu-id="d40e9-127">C# リファレンス</span><span class="sxs-lookup"><span data-stu-id="d40e9-127">C# reference</span></span>](../index.md)
- [<span data-ttu-id="d40e9-128">C# 演算子</span><span class="sxs-lookup"><span data-stu-id="d40e9-128">C# operators</span></span>](index.md)
- [<span data-ttu-id="d40e9-129">オブジェクト初期化子とコレクション初期化子</span><span class="sxs-lookup"><span data-stu-id="d40e9-129">Object and collection initializers</span></span>](../../programming-guide/classes-and-structs/object-and-collection-initializers.md)
