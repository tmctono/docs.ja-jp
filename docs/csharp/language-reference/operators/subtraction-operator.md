---
title: '- および -= 演算子 - C# リファレンス'
ms.date: 05/27/2019
f1_keywords:
- -_CSharpKeyword
- -=_CSharpKeyword
helpviewer_keywords:
- subtraction operator [C#]
- delegate removal [C#]
- '- operator [C#]'
- subtraction assignment operator [C#]
- event unsubscription [C#]
- -= operator [C#]
ms.assetid: 4de7a4fa-c69d-48e6-aff1-3130af970b2d
ms.openlocfilehash: 2017aade92e8d7ad2af7101a107122fa8d7b9e27
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/14/2020
ms.locfileid: "78847652"
---
# <a name="--and---operators-c-reference"></a><span data-ttu-id="a2b15-102">- および -= 演算子 (C# リファレンス)</span><span class="sxs-lookup"><span data-stu-id="a2b15-102">- and -= operators (C# reference)</span></span>

<span data-ttu-id="a2b15-103">`-` 演算子と `-=` 演算子は、組み込みの[整数](../builtin-types/integral-numeric-types.md)および[浮動小数点型](../builtin-types/floating-point-numeric-types.md)の数値型と、[デリゲート](../builtin-types/reference-types.md#the-delegate-type)型によってサポートされています。</span><span class="sxs-lookup"><span data-stu-id="a2b15-103">The `-` and `-=` operators are supported by the built-in [integral](../builtin-types/integral-numeric-types.md) and [floating-point](../builtin-types/floating-point-numeric-types.md) numeric types and [delegate](../builtin-types/reference-types.md#the-delegate-type) types.</span></span>

<span data-ttu-id="a2b15-104">算術演算子 `-` については、「[算術演算子 (C# リファレンス)](arithmetic-operators.md#unary-plus-and-minus-operators)」の記事の「[単項プラス演算子と単項マイナス演算子](arithmetic-operators.md#subtraction-operator--)」セクションと「[減算演算子 -](arithmetic-operators.md)」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="a2b15-104">For information about the arithmetic `-` operator, see the [Unary plus and minus operators](arithmetic-operators.md#unary-plus-and-minus-operators) and [Subtraction operator -](arithmetic-operators.md#subtraction-operator--) sections of the [Arithmetic operators](arithmetic-operators.md) article.</span></span>

## <a name="delegate-removal"></a><span data-ttu-id="a2b15-105">デリゲートの削除</span><span class="sxs-lookup"><span data-stu-id="a2b15-105">Delegate removal</span></span>

<span data-ttu-id="a2b15-106">同じ[デリゲート](../builtin-types/reference-types.md#the-delegate-type)型のオペランドに対しては、`-` 演算子は、次のように計算されるデリゲート インスタンスを返します。</span><span class="sxs-lookup"><span data-stu-id="a2b15-106">For operands of the same [delegate](../builtin-types/reference-types.md#the-delegate-type) type, the `-` operator returns a delegate instance that is calculated as follows:</span></span>

- <span data-ttu-id="a2b15-107">両方のオペランドが null 値ではなく、右側のオペランドの呼び出しリストが左側のオペランドの呼び出しリストの適切な連続するサブリストの場合は、演算の結果は右側のオペランドのエントリを左側のオペランドの呼び出しリストから削除することによって取得される新しい呼び出しリストとなります。</span><span class="sxs-lookup"><span data-stu-id="a2b15-107">If both operands are non-null and the invocation list of the right-hand operand is a proper contiguous sublist of the invocation list of the left-hand operand, the result of the operation is a new invocation list that is obtained by removing the right-hand operand's entries from the invocation list of the left-hand operand.</span></span> <span data-ttu-id="a2b15-108">右側のオペランドのリストが、左側のオペランドのリストで複数の連続するサブリストと一致する場合、右端の一致するサブリストのみが削除されます。</span><span class="sxs-lookup"><span data-stu-id="a2b15-108">If the right-hand operand's list matches multiple contiguous sublists in the left-hand operand's list, only the right-most matching sublist is removed.</span></span> <span data-ttu-id="a2b15-109">削除によりリストが空になる場合、結果は `null` になります。</span><span class="sxs-lookup"><span data-stu-id="a2b15-109">If removal results in an empty list, the result is `null`.</span></span>

  [!code-csharp-interactive[delegate removal](snippets/SubtractionOperator.cs#DelegateRemoval)]

- <span data-ttu-id="a2b15-110">右側のオペランドの呼び出しリストが左側のオペランドの呼び出しリストの適切な連続するサブリストでない場合は、演算結果は左側のオペランドになります。</span><span class="sxs-lookup"><span data-stu-id="a2b15-110">If the invocation list of the right-hand operand is not a proper contiguous sublist of the invocation list of the left-hand operand, the result of the operation is the left-hand operand.</span></span> <span data-ttu-id="a2b15-111">たとえば、マルチキャストのデリゲートの一部ではないデリゲートを削除しても何も行われず、マルチキャストのデリゲートは変更されません。</span><span class="sxs-lookup"><span data-stu-id="a2b15-111">For example, removing a delegate that is not part of the multicast delegate does nothing and results in the unchanged multicast delegate.</span></span>

  [!code-csharp-interactive[delegate removal with no effect](snippets/SubtractionOperator.cs#DelegateRemovalNoChange)]

  <span data-ttu-id="a2b15-112">前の例では、デリゲート中に削除デリゲートのインスタンスが比較されることも示しています。</span><span class="sxs-lookup"><span data-stu-id="a2b15-112">The preceding example also demonstrates that during delegate removal delegate instances are compared.</span></span> <span data-ttu-id="a2b15-113">たとえば、同一の[ラムダ式](../../programming-guide/statements-expressions-operators/lambda-expressions.md)の評価から生成されるデリゲートが等しくない、などです。</span><span class="sxs-lookup"><span data-stu-id="a2b15-113">For example, delegates that are produced from evaluation of identical [lambda expressions](../../programming-guide/statements-expressions-operators/lambda-expressions.md) are not equal.</span></span> <span data-ttu-id="a2b15-114">デリゲートの等値の詳細については、[C# 言語仕様](~/_csharplang/spec/expressions.md#delegate-equality-operators)の[デリゲートの等値演算子](~/_csharplang/spec/introduction.md)に関するセクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="a2b15-114">For more information about delegate equality, see the [Delegate equality operators](~/_csharplang/spec/expressions.md#delegate-equality-operators) section of the [C# language specification](~/_csharplang/spec/introduction.md).</span></span>

- <span data-ttu-id="a2b15-115">左側のオペランドが `null` の場合は、演算結果は `null` になります。</span><span class="sxs-lookup"><span data-stu-id="a2b15-115">If the left-hand operand is `null`, the result of the operation is `null`.</span></span> <span data-ttu-id="a2b15-116">右側のオペランドが `null` の場合は、演算結果は左側のオペランドになります。</span><span class="sxs-lookup"><span data-stu-id="a2b15-116">If the right-hand operand is `null`, the result of the operation is the left-hand operand.</span></span>

  [!code-csharp-interactive[delegate removal and null](snippets/SubtractionOperator.cs#DelegateRemovalAndNull)]

<span data-ttu-id="a2b15-117">デリゲートを組み合わせるには、[`+` 演算子](addition-operator.md#delegate-combination)を使用します。</span><span class="sxs-lookup"><span data-stu-id="a2b15-117">To combine delegates, use the [`+` operator](addition-operator.md#delegate-combination).</span></span>

<span data-ttu-id="a2b15-118">デリゲート型の詳細については、[デリゲート](../../programming-guide/delegates/index.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="a2b15-118">For more information about delegate types, see [Delegates](../../programming-guide/delegates/index.md).</span></span>

## <a name="subtraction-assignment-operator--"></a><span data-ttu-id="a2b15-119">減算代入演算子 -=</span><span class="sxs-lookup"><span data-stu-id="a2b15-119">Subtraction assignment operator -=</span></span>

<span data-ttu-id="a2b15-120">次のような `-=` 演算子を使用する式があるとします</span><span class="sxs-lookup"><span data-stu-id="a2b15-120">An expression using the `-=` operator, such as</span></span>

```csharp
x -= y
```

<span data-ttu-id="a2b15-121">上記の式は、次の式と同じです。</span><span class="sxs-lookup"><span data-stu-id="a2b15-121">is equivalent to</span></span>

```csharp
x = x - y
```

<span data-ttu-id="a2b15-122">ただし、`x` が評価されるのは 1 回だけです。</span><span class="sxs-lookup"><span data-stu-id="a2b15-122">except that `x` is only evaluated once.</span></span>

<span data-ttu-id="a2b15-123">`-=` 演算子の使用例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="a2b15-123">The following example demonstrates the usage of the `-=` operator:</span></span>

[!code-csharp-interactive[-= examples](snippets/SubtractionOperator.cs#SubtractAndAssign)]

<span data-ttu-id="a2b15-124">`-=`イベント[から登録を解除するときに、](../keywords/event.md) 演算子を使用して削除するイベント ハンドラー メソッドを指定することもできます。</span><span class="sxs-lookup"><span data-stu-id="a2b15-124">You also use the `-=` operator to specify an event handler method to remove when you unsubscribe from an [event](../keywords/event.md).</span></span> <span data-ttu-id="a2b15-125">詳細については、「[イベントのサブスクリプションとサブスクリプション解除を行う方法](../../programming-guide/events/how-to-subscribe-to-and-unsubscribe-from-events.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a2b15-125">For more information, see [How to subscribe to and unsubscribe from events](../../programming-guide/events/how-to-subscribe-to-and-unsubscribe-from-events.md).</span></span>

## <a name="operator-overloadability"></a><span data-ttu-id="a2b15-126">演算子のオーバーロード可/不可</span><span class="sxs-lookup"><span data-stu-id="a2b15-126">Operator overloadability</span></span>

<span data-ttu-id="a2b15-127">ユーザー定義型は [ 演算子を](operator-overloading.md)オーバーロード`-`できます。</span><span class="sxs-lookup"><span data-stu-id="a2b15-127">A user-defined type can [overload](operator-overloading.md) the `-` operator.</span></span> <span data-ttu-id="a2b15-128">2 項 `-` 演算子をオーバーロードすると、`-=` 演算子も暗黙的にオーバーロードされます。</span><span class="sxs-lookup"><span data-stu-id="a2b15-128">When a binary `-` operator is overloaded, the `-=` operator is also implicitly overloaded.</span></span> <span data-ttu-id="a2b15-129">ユーザー定義型では、`-=` 演算子を明示的にオーバーロードできません。</span><span class="sxs-lookup"><span data-stu-id="a2b15-129">A user-defined type cannot explicitly overload the `-=` operator.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="a2b15-130">C# 言語仕様</span><span class="sxs-lookup"><span data-stu-id="a2b15-130">C# language specification</span></span>

<span data-ttu-id="a2b15-131">詳細については、[C# 言語仕様](~/_csharplang/spec/expressions.md#unary-minus-operator)の[単項マイナス演算子](~/_csharplang/spec/expressions.md#subtraction-operator)と[減算演算子](~/_csharplang/spec/introduction.md)に関するセクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="a2b15-131">For more information, see the [Unary minus operator](~/_csharplang/spec/expressions.md#unary-minus-operator) and [Subtraction operator](~/_csharplang/spec/expressions.md#subtraction-operator) sections of the [C# language specification](~/_csharplang/spec/introduction.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="a2b15-132">参照</span><span class="sxs-lookup"><span data-stu-id="a2b15-132">See also</span></span>

- [<span data-ttu-id="a2b15-133">C# リファレンス</span><span class="sxs-lookup"><span data-stu-id="a2b15-133">C# reference</span></span>](../index.md)
- [<span data-ttu-id="a2b15-134">C# 演算子</span><span class="sxs-lookup"><span data-stu-id="a2b15-134">C# operators</span></span>](index.md)
- [<span data-ttu-id="a2b15-135">イベント</span><span class="sxs-lookup"><span data-stu-id="a2b15-135">Events</span></span>](../../programming-guide/events/index.md)
- [<span data-ttu-id="a2b15-136">算術演算子</span><span class="sxs-lookup"><span data-stu-id="a2b15-136">Arithmetic operators</span></span>](arithmetic-operators.md)
- [<span data-ttu-id="a2b15-137">+ および += 演算子</span><span class="sxs-lookup"><span data-stu-id="a2b15-137">+ and += operators</span></span>](addition-operator.md)
