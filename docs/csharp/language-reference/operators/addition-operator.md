---
title: + および += 演算子 - C# リファレンス
ms.custom: seodec18
ms.date: 05/24/2019
f1_keywords:
- +_CSharpKeyword
- +=_CSharpKeyword
helpviewer_keywords:
- addition operator [C#]
- concatenation operator [C#]
- delegate combination [C#]
- + operator [C#]
- addition assignment operator [C#]
- event subscription [C#]
- += operator [C#]
ms.assetid: 93e56486-bb42-43c1-bd43-60af11e64e67
ms.openlocfilehash: d03743bad47c60925462d027d18445047ebc0fc9
ms.sourcegitcommit: 621a5f6df00152006160987395b93b5b55f7ffcd
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/29/2019
ms.locfileid: "66300112"
---
# <a name="-and--operators-c-reference"></a><span data-ttu-id="2b0ba-102">+ および += 演算子 (C# リファレンス)</span><span class="sxs-lookup"><span data-stu-id="2b0ba-102">+ and += operators (C# Reference)</span></span>

<span data-ttu-id="2b0ba-103">`+` 演算子は、組み込み数値型、[文字列](../keywords/delegate.md)型、および[デリゲート](../keywords/string.md)型でサポートされています。</span><span class="sxs-lookup"><span data-stu-id="2b0ba-103">The `+` operator is supported by the built-in numeric types, [string](../keywords/string.md) type, and [delegate](../keywords/delegate.md) types.</span></span>

<span data-ttu-id="2b0ba-104">算術演算子 `+` については、「[算術演算子 (C# リファレンス)](arithmetic-operators.md)」の記事の「[単項プラス演算子と単項マイナス演算子](arithmetic-operators.md#unary-plus-and-minus-operators)」セクションと「[加算演算子 +](arithmetic-operators.md#addition-operator-)」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="2b0ba-104">For information about the arithmetic `+` operator, see the [Unary plus and minus operators](arithmetic-operators.md#unary-plus-and-minus-operators) and [Addition operator +](arithmetic-operators.md#addition-operator-) sections of the [Arithmetic operators](arithmetic-operators.md) article.</span></span>

## <a name="string-concatenation"></a><span data-ttu-id="2b0ba-105">文字列連結</span><span class="sxs-lookup"><span data-stu-id="2b0ba-105">String concatenation</span></span>

<span data-ttu-id="2b0ba-106">一方または両方のオペランドが[文字列](../keywords/string.md)型の場合、`+` 演算子によってそのオペランドの文字列表現が連結されます。</span><span class="sxs-lookup"><span data-stu-id="2b0ba-106">When one or both operands are of type [string](../keywords/string.md), the `+` operator concatenates the string representations of its operands:</span></span>

[!code-csharp-interactive[string concatenation](~/samples/snippets/csharp/language-reference/operators/AdditionExamples.cs#AddStrings)]

<span data-ttu-id="2b0ba-107">C# 6 以降、[文字列補間](../tokens/interpolated.md)という文字列を書式設定するより便利な方法が提供されます。</span><span class="sxs-lookup"><span data-stu-id="2b0ba-107">Starting with C# 6, [string interpolation](../tokens/interpolated.md) provides a more convenient way to format strings:</span></span>

[!code-csharp-interactive[string interpolation](~/samples/snippets/csharp/language-reference/operators/AdditionExamples.cs#UseStringInterpolation)]

## <a name="delegate-combination"></a><span data-ttu-id="2b0ba-108">デリゲートの組み合わせ</span><span class="sxs-lookup"><span data-stu-id="2b0ba-108">Delegate combination</span></span>

<span data-ttu-id="2b0ba-109">同じ[デリゲート](../keywords/delegate.md)型のオペランドの場合、`+` 呼び出されると最初のオペランドを呼び出してから 2 番目のオペランドを呼び出す新しいデリゲート インスタンスが演算子によって返されます。</span><span class="sxs-lookup"><span data-stu-id="2b0ba-109">For operands of the same [delegate](../keywords/delegate.md) type, the `+` operator returns a new delegate instance that, when invoked, invokes the first operand and then invokes the second operand.</span></span> <span data-ttu-id="2b0ba-110">いずれかのオペランドが `null` の場合、`+` 演算子によって別のオペランドの値が返されます (`null` でもある場合があります)。</span><span class="sxs-lookup"><span data-stu-id="2b0ba-110">If any of the operands is `null`, the `+` operator returns the value of another operand (which also might be `null`).</span></span> <span data-ttu-id="2b0ba-111">次の例では、デリゲートが `+` 演算子と組み合わされるしくみを説明しています。</span><span class="sxs-lookup"><span data-stu-id="2b0ba-111">The following example shows how delegates can be combined with the `+` operator:</span></span>

[!code-csharp-interactive[delegate combination](~/samples/snippets/csharp/language-reference/operators/AdditionExamples.cs#AddDelegates)]

<span data-ttu-id="2b0ba-112">デリゲート型の詳細については、[デリゲート](../../programming-guide/delegates/index.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="2b0ba-112">For more information about delegate types, see [Delegates](../../programming-guide/delegates/index.md).</span></span>

## <a name="addition-assignment-operator-"></a><span data-ttu-id="2b0ba-113">加算代入演算子 +=</span><span class="sxs-lookup"><span data-stu-id="2b0ba-113">Addition assignment operator +=</span></span>

<span data-ttu-id="2b0ba-114">次のような `+=` 演算子を使用する式があるとします</span><span class="sxs-lookup"><span data-stu-id="2b0ba-114">An expression using the `+=` operator, such as</span></span>

```csharp
x += y
```

<span data-ttu-id="2b0ba-115">上記の式は、次の式と同じです。</span><span class="sxs-lookup"><span data-stu-id="2b0ba-115">is equivalent to</span></span>

```csharp
x = x + y
```

<span data-ttu-id="2b0ba-116">ただし、`x` が評価されるのは 1 回だけです。</span><span class="sxs-lookup"><span data-stu-id="2b0ba-116">except that `x` is only evaluated once.</span></span>
  
<span data-ttu-id="2b0ba-117">`+=` 演算子の使用例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="2b0ba-117">The following example demonstrates the usage of the `+=` operator:</span></span>

[!code-csharp-interactive[+= examples](~/samples/snippets/csharp/language-reference/operators/AdditionExamples.cs#AddAndAssign)]

<span data-ttu-id="2b0ba-118">[イベント](../keywords/event.md)をサブスクライブするとき、`+=` 演算子を使用してイベント ハンドラー メソッドを指定することもできます。</span><span class="sxs-lookup"><span data-stu-id="2b0ba-118">You also use the `+=` operator to specify an event handler method when you subscribe to an [event](../keywords/event.md).</span></span> <span data-ttu-id="2b0ba-119">詳細については、「[方法: イベント サブスクリプションとサブスクリプションの解除](../../programming-guide/events/how-to-subscribe-to-and-unsubscribe-from-events.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2b0ba-119">For more information, see [How to: subscribe to and unsubscribe from events](../../programming-guide/events/how-to-subscribe-to-and-unsubscribe-from-events.md).</span></span>

## <a name="operator-overloadability"></a><span data-ttu-id="2b0ba-120">演算子のオーバーロード可/不可</span><span class="sxs-lookup"><span data-stu-id="2b0ba-120">Operator overloadability</span></span>

<span data-ttu-id="2b0ba-121">ユーザー定義型は `+` 演算子を[オーバーロード](../keywords/operator.md)できます。</span><span class="sxs-lookup"><span data-stu-id="2b0ba-121">A user-defined type can [overload](../keywords/operator.md) the `+` operator.</span></span> <span data-ttu-id="2b0ba-122">2 項 `+` 演算子をオーバーロードすると、`+=` 演算子も暗黙的にオーバーロードされます。</span><span class="sxs-lookup"><span data-stu-id="2b0ba-122">When a binary `+` operator is overloaded, the `+=` operator is also implicitly overloaded.</span></span> <span data-ttu-id="2b0ba-123">ユーザー定義型では、`+=` 演算子を明示的にオーバーロードできません。</span><span class="sxs-lookup"><span data-stu-id="2b0ba-123">A user-defined type cannot explicitly overload the `+=` operator.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="2b0ba-124">C# 言語仕様</span><span class="sxs-lookup"><span data-stu-id="2b0ba-124">C# language specification</span></span>

<span data-ttu-id="2b0ba-125">詳細については、[C# 言語仕様](../language-specification/index.md)の[単項プラス演算子](~/_csharplang/spec/expressions.md#unary-plus-operator)と[加算演算子](~/_csharplang/spec/expressions.md#addition-operator)に関するセクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="2b0ba-125">For more information, see the [Unary plus operator](~/_csharplang/spec/expressions.md#unary-plus-operator) and [Addition operator](~/_csharplang/spec/expressions.md#addition-operator) sections of the [C# language specification](../language-specification/index.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="2b0ba-126">関連項目</span><span class="sxs-lookup"><span data-stu-id="2b0ba-126">See also</span></span>

- [<span data-ttu-id="2b0ba-127">C# リファレンス</span><span class="sxs-lookup"><span data-stu-id="2b0ba-127">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="2b0ba-128">C# プログラミングガイド</span><span class="sxs-lookup"><span data-stu-id="2b0ba-128">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="2b0ba-129">C# 演算子</span><span class="sxs-lookup"><span data-stu-id="2b0ba-129">C# Operators</span></span>](index.md)
- [<span data-ttu-id="2b0ba-130">文字列補間</span><span class="sxs-lookup"><span data-stu-id="2b0ba-130">String interpolation</span></span>](../tokens/interpolated.md)
- [<span data-ttu-id="2b0ba-131">方法: 複数の文字列を連結する</span><span class="sxs-lookup"><span data-stu-id="2b0ba-131">How to: concatenate multiple strings</span></span>](../../how-to/concatenate-multiple-strings.md)
- [<span data-ttu-id="2b0ba-132">デリゲート</span><span class="sxs-lookup"><span data-stu-id="2b0ba-132">Delegates</span></span>](../../programming-guide/delegates/index.md)
- [<span data-ttu-id="2b0ba-133">イベント</span><span class="sxs-lookup"><span data-stu-id="2b0ba-133">Events</span></span>](../../programming-guide/events/index.md)
- [<span data-ttu-id="2b0ba-134">checked と unchecked</span><span class="sxs-lookup"><span data-stu-id="2b0ba-134">Checked and unchecked</span></span>](../keywords/checked-and-unchecked.md)
- [<span data-ttu-id="2b0ba-135">算術演算子</span><span class="sxs-lookup"><span data-stu-id="2b0ba-135">Arithmetic operators</span></span>](arithmetic-operators.md)
- [<span data-ttu-id="2b0ba-136">- および -= 演算子</span><span class="sxs-lookup"><span data-stu-id="2b0ba-136">- and -= operators</span></span>](subtraction-operator.md)
