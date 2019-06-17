---
title: '- および -= 演算子 - C# リファレンス'
ms.custom: seodec18
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
ms.openlocfilehash: aae10f8b03a16e55f0b26981f17585c8790e00c1
ms.sourcegitcommit: 5ae6affa0b171be3bb5f4729fb68ea4fe799f959
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/10/2019
ms.locfileid: "66816070"
---
# <a name="--and---operators-c-reference"></a><span data-ttu-id="a81e6-102">- および -= 演算子 (C# リファレンス)</span><span class="sxs-lookup"><span data-stu-id="a81e6-102">- and -= operators (C# Reference)</span></span>

<span data-ttu-id="a81e6-103">`-` 演算子は、組み込み数値型と[デリゲート](../keywords/delegate.md)型でサポートされています。</span><span class="sxs-lookup"><span data-stu-id="a81e6-103">The `-` operator is supported by the built-in numeric types and [delegate](../keywords/delegate.md) types.</span></span>

<span data-ttu-id="a81e6-104">算術演算子 `-` については、「[算術演算子 (C# リファレンス)](arithmetic-operators.md)」の記事の「[単項プラス演算子と単項マイナス演算子](arithmetic-operators.md#unary-plus-and-minus-operators)」セクションと「[減算演算子 -](arithmetic-operators.md#subtraction-operator--)」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="a81e6-104">For information about the arithmetic `-` operator, see the [Unary plus and minus operators](arithmetic-operators.md#unary-plus-and-minus-operators) and [Subtraction operator -](arithmetic-operators.md#subtraction-operator--) sections of the [Arithmetic operators](arithmetic-operators.md) article.</span></span>

## <a name="delegate-removal"></a><span data-ttu-id="a81e6-105">デリゲートの削除</span><span class="sxs-lookup"><span data-stu-id="a81e6-105">Delegate removal</span></span>

<span data-ttu-id="a81e6-106">同じ[デリゲート](../keywords/delegate.md)型のオペランドに対しては、`-` 演算子は、次のように計算されるデリゲート インスタンスを返します。</span><span class="sxs-lookup"><span data-stu-id="a81e6-106">For operands of the same [delegate](../keywords/delegate.md) type, the `-` operator returns a delegate instance that is calculated as follows:</span></span>

- <span data-ttu-id="a81e6-107">両方のオペランドが null ではなく、2 番目のオペランドの呼び出しリストが最初のオペランドの呼び出しリストの適切な連続するサブリストの場合は、演算の結果は 2 番目のオペランドのエントリを最初のオペランドの呼び出しリストから削除することによって取得される新しい呼び出しリストとなります。</span><span class="sxs-lookup"><span data-stu-id="a81e6-107">If both operands are non-null and the invocation list of the second operand is a proper contiguous sublist of the invocation list of the first operand, the result of the operation is a new invocation list that is obtained by removing the second operand's entries from the invocation list of the first operand.</span></span> <span data-ttu-id="a81e6-108">2 番目のオペランドのリストが、最初のオペランドのリストで複数の連続するサブリストと一致する場合、右端の一致するサブリストのみが削除されます。</span><span class="sxs-lookup"><span data-stu-id="a81e6-108">If the second operand's list matches multiple contiguous sublists in the first operand's list, only the right-most matching sublist is removed.</span></span> <span data-ttu-id="a81e6-109">削除によりリストが空になる場合、結果は `null` になります。</span><span class="sxs-lookup"><span data-stu-id="a81e6-109">If removal results in an empty list, the result is `null`.</span></span>

  [!code-csharp-interactive[delegate removal](~/samples/csharp/language-reference/operators/SubtractionOperator.cs#DelegateRemoval)]

- <span data-ttu-id="a81e6-110">2 番目のオペランドの呼び出しリストが最初のオペランドの呼び出しリストの適切な連続するサブリストでない場合は、演算結果は最初のオペランドになります。</span><span class="sxs-lookup"><span data-stu-id="a81e6-110">If the invocation list of the second operand is not a proper contiguous sublist of the invocation list of the first operand, the result of the operation is the first operand.</span></span> <span data-ttu-id="a81e6-111">たとえば、マルチキャストのデリゲートの一部ではないデリゲートを削除しても何も行われず、マルチキャストのデリゲートは変更されません。</span><span class="sxs-lookup"><span data-stu-id="a81e6-111">For example, removing a delegate that is not part of the multicast delegate does nothing and results in the unchanged multicast delegate.</span></span>

  [!code-csharp-interactive[delegate removal with no effect](~/samples/csharp/language-reference/operators/SubtractionOperator.cs#DelegateRemovalNoChange)]

  <span data-ttu-id="a81e6-112">前の例では、デリゲート中に削除デリゲートのインスタンスが比較されることも示しています。</span><span class="sxs-lookup"><span data-stu-id="a81e6-112">The preceding example also demonstrates that during delegate removal delegate instances are compared.</span></span> <span data-ttu-id="a81e6-113">たとえば、同一の[ラムダ式](../../programming-guide/statements-expressions-operators/lambda-expressions.md)の評価から生成されるデリゲートが等しくない、などです。</span><span class="sxs-lookup"><span data-stu-id="a81e6-113">For example, delegates that are produced from evaluation of identical [lambda expressions](../../programming-guide/statements-expressions-operators/lambda-expressions.md) are not equal.</span></span> <span data-ttu-id="a81e6-114">デリゲートの等値の詳細については、[C# 言語仕様](../language-specification/index.md)の[デリゲートの等値演算子](~/_csharplang/spec/expressions.md#delegate-equality-operators)に関するセクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="a81e6-114">For more information about delegate equality, see the [Delegate equality operators](~/_csharplang/spec/expressions.md#delegate-equality-operators) section of the [C# language specification](../language-specification/index.md).</span></span>

- <span data-ttu-id="a81e6-115">最初のオペランドが `null` の場合は、演算結果は `null` になります。</span><span class="sxs-lookup"><span data-stu-id="a81e6-115">If the first operand is `null`, the result of the operation is `null`.</span></span> <span data-ttu-id="a81e6-116">2 番目のオペランドが `null` の場合は、演算結果は最初のオペランドになります。</span><span class="sxs-lookup"><span data-stu-id="a81e6-116">If the second operand is `null`, the result of the operation is the first operand.</span></span>

  [!code-csharp-interactive[delegate removal and null](~/samples/csharp/language-reference/operators/SubtractionOperator.cs#DelegateRemovalAndNull)]

<span data-ttu-id="a81e6-117">デリゲートを組み合わせるには、[`+` 演算子](addition-operator.md#delegate-combination)を使用します。</span><span class="sxs-lookup"><span data-stu-id="a81e6-117">To combine delegates, use the [`+` operator](addition-operator.md#delegate-combination).</span></span>

<span data-ttu-id="a81e6-118">デリゲート型の詳細については、[デリゲート](../../programming-guide/delegates/index.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="a81e6-118">For more information about delegate types, see [Delegates](../../programming-guide/delegates/index.md).</span></span>

## <a name="subtraction-assignment-operator--"></a><span data-ttu-id="a81e6-119">減算代入演算子 -=</span><span class="sxs-lookup"><span data-stu-id="a81e6-119">Subtraction assignment operator -=</span></span>

<span data-ttu-id="a81e6-120">次のような `-=` 演算子を使用する式があるとします</span><span class="sxs-lookup"><span data-stu-id="a81e6-120">An expression using the `-=` operator, such as</span></span>

```csharp
x -= y
```

<span data-ttu-id="a81e6-121">上記の式は、次の式と同じです。</span><span class="sxs-lookup"><span data-stu-id="a81e6-121">is equivalent to</span></span>

```csharp
x = x - y
```

<span data-ttu-id="a81e6-122">ただし、`x` が評価されるのは 1 回だけです。</span><span class="sxs-lookup"><span data-stu-id="a81e6-122">except that `x` is only evaluated once.</span></span>
  
<span data-ttu-id="a81e6-123">`-=` 演算子の使用例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="a81e6-123">The following example demonstrates the usage of the `-=` operator:</span></span>

[!code-csharp-interactive[-= examples](~/samples/csharp/language-reference/operators/SubtractionOperator.cs#SubtractAndAssign)]

<span data-ttu-id="a81e6-124">[イベント](../keywords/event.md)から登録を解除するときに、`-=` 演算子を使用して削除するイベント ハンドラー メソッドを指定することもできます。</span><span class="sxs-lookup"><span data-stu-id="a81e6-124">You also use the `-=` operator to specify an event handler method to remove when you unsubscribe from an [event](../keywords/event.md).</span></span> <span data-ttu-id="a81e6-125">詳細については、「[方法: イベント サブスクリプションとサブスクリプションの解除](../../programming-guide/events/how-to-subscribe-to-and-unsubscribe-from-events.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a81e6-125">For more information, see [How to: subscribe to and unsubscribe from events](../../programming-guide/events/how-to-subscribe-to-and-unsubscribe-from-events.md).</span></span>

## <a name="operator-overloadability"></a><span data-ttu-id="a81e6-126">演算子のオーバーロード可/不可</span><span class="sxs-lookup"><span data-stu-id="a81e6-126">Operator overloadability</span></span>

<span data-ttu-id="a81e6-127">ユーザー定義型は `-` 演算子を[オーバーロード](../keywords/operator.md)できます。</span><span class="sxs-lookup"><span data-stu-id="a81e6-127">A user-defined type can [overload](../keywords/operator.md) the `-` operator.</span></span> <span data-ttu-id="a81e6-128">2 項 `-` 演算子をオーバーロードすると、`-=` 演算子も暗黙的にオーバーロードされます。</span><span class="sxs-lookup"><span data-stu-id="a81e6-128">When a binary `-` operator is overloaded, the `-=` operator is also implicitly overloaded.</span></span> <span data-ttu-id="a81e6-129">ユーザー定義型では、`-=` 演算子を明示的にオーバーロードできません。</span><span class="sxs-lookup"><span data-stu-id="a81e6-129">A user-defined type cannot explicitly overload the `-=` operator.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="a81e6-130">C# 言語仕様</span><span class="sxs-lookup"><span data-stu-id="a81e6-130">C# language specification</span></span>

<span data-ttu-id="a81e6-131">詳細については、[C# 言語仕様](~/_csharplang/spec/introduction.md)の[単項マイナス演算子](~/_csharplang/spec/expressions.md#unary-minus-operator)と[減算演算子](~/_csharplang/spec/expressions.md#subtraction-operator)に関するセクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="a81e6-131">For more information, see the [Unary minus operator](~/_csharplang/spec/expressions.md#unary-minus-operator) and [Subtraction operator](~/_csharplang/spec/expressions.md#subtraction-operator) sections of the [C# language specification](~/_csharplang/spec/introduction.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="a81e6-132">関連項目</span><span class="sxs-lookup"><span data-stu-id="a81e6-132">See also</span></span>

- [<span data-ttu-id="a81e6-133">C# リファレンス</span><span class="sxs-lookup"><span data-stu-id="a81e6-133">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="a81e6-134">C# プログラミングガイド</span><span class="sxs-lookup"><span data-stu-id="a81e6-134">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="a81e6-135">C# 演算子</span><span class="sxs-lookup"><span data-stu-id="a81e6-135">C# Operators</span></span>](index.md)
- [<span data-ttu-id="a81e6-136">デリゲート</span><span class="sxs-lookup"><span data-stu-id="a81e6-136">Delegates</span></span>](../../programming-guide/delegates/index.md)
- [<span data-ttu-id="a81e6-137">イベント</span><span class="sxs-lookup"><span data-stu-id="a81e6-137">Events</span></span>](../../programming-guide/events/index.md)
- [<span data-ttu-id="a81e6-138">checked と unchecked</span><span class="sxs-lookup"><span data-stu-id="a81e6-138">Checked and unchecked</span></span>](../keywords/checked-and-unchecked.md)
- [<span data-ttu-id="a81e6-139">算術演算子</span><span class="sxs-lookup"><span data-stu-id="a81e6-139">Arithmetic operators</span></span>](arithmetic-operators.md)
- [<span data-ttu-id="a81e6-140">+ および += 演算子</span><span class="sxs-lookup"><span data-stu-id="a81e6-140">+ and += operators</span></span>](addition-operator.md)
