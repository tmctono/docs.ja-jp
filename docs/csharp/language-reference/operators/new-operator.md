---
description: new 演算子 - C# リファレンス
title: new 演算子 - C# リファレンス
ms.date: 10/02/2020
f1_keywords:
- new_CSharpKeyword
helpviewer_keywords:
- new operator keyword [C#]
ms.assetid: a212b697-a79b-4105-9923-1f7b108036e8
ms.openlocfilehash: 3125f3d2c694dcfc5682ee482f3f76072ac3726d
ms.sourcegitcommit: 97405ed212f69b0a32faa66a5d5fae7e76628b68
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/01/2020
ms.locfileid: "91609383"
---
# <a name="new-operator-c-reference"></a><span data-ttu-id="773be-103">new 演算子 (C# リファレンス)</span><span class="sxs-lookup"><span data-stu-id="773be-103">new operator (C# reference)</span></span>

<span data-ttu-id="773be-104">`new` 演算子は型の新しいインスタンスを作成します。</span><span class="sxs-lookup"><span data-stu-id="773be-104">The `new` operator creates a new instance of a type.</span></span>

<span data-ttu-id="773be-105">`new` キーワードは、[メンバーの宣言修飾子](../keywords/new-modifier.md)または[ジェネリック型制約](../keywords/new-constraint.md)として使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="773be-105">You can also use the `new` keyword as a [member declaration modifier](../keywords/new-modifier.md) or a [generic type constraint](../keywords/new-constraint.md).</span></span>

## <a name="constructor-invocation"></a><span data-ttu-id="773be-106">コンストラクターの呼び出し</span><span class="sxs-lookup"><span data-stu-id="773be-106">Constructor invocation</span></span>

<span data-ttu-id="773be-107">型の新しいインスタンスを作成するには、通常は `new` 演算子を使用して、その型の[コンストラクター](../../programming-guide/classes-and-structs/constructors.md)の 1 つを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="773be-107">To create a new instance of a type, you typically invoke one of the [constructors](../../programming-guide/classes-and-structs/constructors.md) of that type using the `new` operator:</span></span>

[!code-csharp-interactive[invoke constructor](snippets/shared/NewOperator.cs#Constructor)]

<span data-ttu-id="773be-108">[オブジェクトまたはコレクション初期化子](../../programming-guide/classes-and-structs/object-and-collection-initializers.md)を `new` 演算子と共に使用して、1 つのステートメント内でオブジェクトのインスタンス化と初期化を行うことができます。次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="773be-108">You can use an [object or collection initializer](../../programming-guide/classes-and-structs/object-and-collection-initializers.md) with the `new` operator to instantiate and initialize an object in one statement, as the following example shows:</span></span>

[!code-csharp-interactive[constructor with initializer](snippets/shared/NewOperator.cs#ConstructorWithInitializer)]

<span data-ttu-id="773be-109">C# 9.0 以降、コンストラクターの呼び出し式はターゲット型になっています。</span><span class="sxs-lookup"><span data-stu-id="773be-109">Beginning with C# 9.0, constructor invocation expressions are target-typed.</span></span> <span data-ttu-id="773be-110">つまり、式のターゲット型がわかっている場合は、次の例に示すように、型名を省略できます。</span><span class="sxs-lookup"><span data-stu-id="773be-110">That is, if a target type of an expression is known, you can omit a type name, as the following example shows:</span></span>

:::code language="csharp" source="snippets/shared/NewOperator.cs" id="SnippetTargetTyped":::

<span data-ttu-id="773be-111">前の例に示されているように、ターゲット型の `new` 式では常にかっこを使用します。</span><span class="sxs-lookup"><span data-stu-id="773be-111">As the preceding example shows, you always use parentheses in a target-typed `new` expression.</span></span>

<span data-ttu-id="773be-112">`new` 式のターゲット型が不明な場合 (たとえば [`var`](../keywords/var.md) キーワードを使用する場合) は、型名を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="773be-112">If a target type of a `new` expression is unknown (for example, when you use the [`var`](../keywords/var.md) keyword), you must specify a type name.</span></span>

## <a name="array-creation"></a><span data-ttu-id="773be-113">配列の作成</span><span class="sxs-lookup"><span data-stu-id="773be-113">Array creation</span></span>

<span data-ttu-id="773be-114">`new` 演算子を使用して配列インスタンスを作成することもできます。次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="773be-114">You also use the `new` operator to create an array instance, as the following example shows:</span></span>

[!code-csharp-interactive[create array](snippets/shared/NewOperator.cs#Array)]

<span data-ttu-id="773be-115">1 つのステートメント内で配列の初期化構文を使用して配列インスタンスを作成し、そこに要素を設定します。</span><span class="sxs-lookup"><span data-stu-id="773be-115">Use array initialization syntax to create an array instance and populate it with elements in one statement.</span></span> <span data-ttu-id="773be-116">次の例に、これを行うためのさまざまな方法を示します。</span><span class="sxs-lookup"><span data-stu-id="773be-116">The following example shows various ways how you can do that:</span></span>

[!code-csharp-interactive[initialize array](snippets/shared/NewOperator.cs#ArrayInitialization)]

<span data-ttu-id="773be-117">配列の詳細については、「[配列](../../programming-guide/arrays/index.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="773be-117">For more information about arrays, see [Arrays](../../programming-guide/arrays/index.md).</span></span>

## <a name="instantiation-of-anonymous-types"></a><span data-ttu-id="773be-118">匿名型のインスタンス化</span><span class="sxs-lookup"><span data-stu-id="773be-118">Instantiation of anonymous types</span></span>

<span data-ttu-id="773be-119">[匿名型](../../programming-guide/classes-and-structs/anonymous-types.md)のインスタンスを作成するには、`new` 演算子とオブジェクト初期化子構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="773be-119">To create an instance of an [anonymous type](../../programming-guide/classes-and-structs/anonymous-types.md), use the `new` operator and object initializer syntax:</span></span>

[!code-csharp-interactive[anonymous type](snippets/shared/NewOperator.cs#AnonymousType)]

## <a name="destruction-of-type-instances"></a><span data-ttu-id="773be-120">型インスタンストの破棄</span><span class="sxs-lookup"><span data-stu-id="773be-120">Destruction of type instances</span></span>

<span data-ttu-id="773be-121">以前作成した型のインスタンスを破棄する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="773be-121">You don't have to destroy earlier created type instances.</span></span> <span data-ttu-id="773be-122">参照型と値型のインスタンスは両方とも自動的に破棄されます。</span><span class="sxs-lookup"><span data-stu-id="773be-122">Instances of both reference and value types are destroyed automatically.</span></span> <span data-ttu-id="773be-123">値型のインスタンスは、それらを格納しているコンテキストが破棄されるとすぐに破棄されます。</span><span class="sxs-lookup"><span data-stu-id="773be-123">Instances of value types are destroyed as soon as the context that contains them is destroyed.</span></span> <span data-ttu-id="773be-124">参照型のインスタンスは[ガベージ コレクター](../../../standard/garbage-collection/index.md)によって、そのインスタンスへの最後の参照が削除された後、不特定のタイミングで破棄されます。</span><span class="sxs-lookup"><span data-stu-id="773be-124">Instances of reference types are destroyed by the [garbage collector](../../../standard/garbage-collection/index.md) at some unspecified time after the last reference to them is removed.</span></span>

<span data-ttu-id="773be-125">ファイル ハンドルなどのアンマネージド リソースを含む型インスタンスの場合、格納されているリソースができるだけ早く確実に解放されるように、決定的なクリーンアップを使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="773be-125">For type instances that contain unmanaged resources, for example, a file handle, it's recommended to employ deterministic clean-up to ensure that the resources they contain are released as soon as possible.</span></span> <span data-ttu-id="773be-126">詳細については、<xref:System.IDisposable?displayProperty=nameWithType> API リファレンスと [using ステートメント](../keywords/using-statement.md)に関する記事を参照してください。</span><span class="sxs-lookup"><span data-stu-id="773be-126">For more information, see the <xref:System.IDisposable?displayProperty=nameWithType> API reference and the [using statement](../keywords/using-statement.md) article.</span></span>

## <a name="operator-overloadability"></a><span data-ttu-id="773be-127">演算子のオーバーロード可/不可</span><span class="sxs-lookup"><span data-stu-id="773be-127">Operator overloadability</span></span>

<span data-ttu-id="773be-128">ユーザー定義型は `new` 演算子をオーバーロードできません。</span><span class="sxs-lookup"><span data-stu-id="773be-128">A user-defined type cannot overload the `new` operator.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="773be-129">C# 言語仕様</span><span class="sxs-lookup"><span data-stu-id="773be-129">C# language specification</span></span>

<span data-ttu-id="773be-130">詳細については、[C# 言語仕様](~/_csharplang/spec/introduction.md)の [new 演算子](~/_csharplang/spec/expressions.md#the-new-operator)に関するセクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="773be-130">For more information, see [The new operator](~/_csharplang/spec/expressions.md#the-new-operator) section of the [C# language specification](~/_csharplang/spec/introduction.md).</span></span>

<span data-ttu-id="773be-131">ターゲット型の `new` 式について詳しくは、[機能提案メモ](~/_csharplang/proposals/csharp-9.0/target-typed-new.md)をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="773be-131">For more information about a target-typed `new` expression, see the [feature proposal note](~/_csharplang/proposals/csharp-9.0/target-typed-new.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="773be-132">参照</span><span class="sxs-lookup"><span data-stu-id="773be-132">See also</span></span>

- [<span data-ttu-id="773be-133">C# リファレンス</span><span class="sxs-lookup"><span data-stu-id="773be-133">C# reference</span></span>](../index.md)
- [<span data-ttu-id="773be-134">C# の演算子と式</span><span class="sxs-lookup"><span data-stu-id="773be-134">C# operators and expressions</span></span>](index.md)
- [<span data-ttu-id="773be-135">オブジェクト初期化子とコレクション初期化子</span><span class="sxs-lookup"><span data-stu-id="773be-135">Object and collection initializers</span></span>](../../programming-guide/classes-and-structs/object-and-collection-initializers.md)
