---
title: + および += 演算子 - C# リファレンス
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
ms.openlocfilehash: 0c468f0fe56c68a16de660dbb3bd6356b4b6a00f
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/07/2020
ms.locfileid: "75712768"
---
# <a name="-and--operators-c-reference"></a><span data-ttu-id="d4797-102">+ および += 演算子 (C# リファレンス)</span><span class="sxs-lookup"><span data-stu-id="d4797-102">+ and += operators (C# reference)</span></span>

<span data-ttu-id="d4797-103">`+` 演算子と `+=` 演算子は、組み込みの[整数](../builtin-types/integral-numeric-types.md)および[浮動小数点型](../builtin-types/floating-point-numeric-types.md)の数値型、[文字列](../builtin-types/reference-types.md#the-string-type)型、[デリゲート](../builtin-types/reference-types.md#the-delegate-type)型によってサポートされています。</span><span class="sxs-lookup"><span data-stu-id="d4797-103">The `+` and `+=` operators are supported by the built-in [integral](../builtin-types/integral-numeric-types.md) and [floating-point](../builtin-types/floating-point-numeric-types.md) numeric types, the [string](../builtin-types/reference-types.md#the-string-type) type, and [delegate](../builtin-types/reference-types.md#the-delegate-type) types.</span></span>

<span data-ttu-id="d4797-104">算術演算子 `+` については、「[算術演算子 (C# リファレンス)](arithmetic-operators.md)」の記事の「[単項プラス演算子と単項マイナス演算子](arithmetic-operators.md#unary-plus-and-minus-operators)」セクションと「[加算演算子 +](arithmetic-operators.md#addition-operator-)」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="d4797-104">For information about the arithmetic `+` operator, see the [Unary plus and minus operators](arithmetic-operators.md#unary-plus-and-minus-operators) and [Addition operator +](arithmetic-operators.md#addition-operator-) sections of the [Arithmetic operators](arithmetic-operators.md) article.</span></span>

## <a name="string-concatenation"></a><span data-ttu-id="d4797-105">文字列連結</span><span class="sxs-lookup"><span data-stu-id="d4797-105">String concatenation</span></span>

<span data-ttu-id="d4797-106">一方または両方のオペランドが[文字列](../builtin-types/reference-types.md#the-string-type)型の場合、`+` 演算子によってそのオペランドの文字列表現が連結されます。</span><span class="sxs-lookup"><span data-stu-id="d4797-106">When one or both operands are of type [string](../builtin-types/reference-types.md#the-string-type), the `+` operator concatenates the string representations of its operands:</span></span>

[!code-csharp-interactive[string concatenation](~/samples/csharp/language-reference/operators/AdditionOperator.cs#AddStrings)]

<span data-ttu-id="d4797-107">C# 6 以降、[文字列補間](../tokens/interpolated.md)という文字列を書式設定するより便利な方法が提供されています。</span><span class="sxs-lookup"><span data-stu-id="d4797-107">Beginning with C# 6, [string interpolation](../tokens/interpolated.md) provides a more convenient way to format strings:</span></span>

[!code-csharp-interactive[string interpolation](~/samples/csharp/language-reference/operators/AdditionOperator.cs#UseStringInterpolation)]

## <a name="delegate-combination"></a><span data-ttu-id="d4797-108">デリゲートの組み合わせ</span><span class="sxs-lookup"><span data-stu-id="d4797-108">Delegate combination</span></span>

<span data-ttu-id="d4797-109">同じ[デリゲート](../builtin-types/reference-types.md#the-delegate-type)型のオペランドの場合、呼び出されると左側のオペランドを呼び出してから右側のオペランドを呼び出す新しいデリゲート インスタンスが `+` 演算子によって返されます。</span><span class="sxs-lookup"><span data-stu-id="d4797-109">For operands of the same [delegate](../builtin-types/reference-types.md#the-delegate-type) type, the `+` operator returns a new delegate instance that, when invoked, invokes the left-hand operand and then invokes the right-hand operand.</span></span> <span data-ttu-id="d4797-110">いずれかのオペランドが `null` の場合、`+` 演算子によって別のオペランドの値が返されます (`null` でもある場合があります)。</span><span class="sxs-lookup"><span data-stu-id="d4797-110">If any of the operands is `null`, the `+` operator returns the value of another operand (which also might be `null`).</span></span> <span data-ttu-id="d4797-111">次の例では、デリゲートが `+` 演算子と組み合わされるしくみを説明しています。</span><span class="sxs-lookup"><span data-stu-id="d4797-111">The following example shows how delegates can be combined with the `+` operator:</span></span>

[!code-csharp-interactive[delegate combination](~/samples/csharp/language-reference/operators/AdditionOperator.cs#AddDelegates)]

<span data-ttu-id="d4797-112">デリゲートの削除を実行するには、[`-` 演算子](subtraction-operator.md#delegate-removal)を使用します。</span><span class="sxs-lookup"><span data-stu-id="d4797-112">To perform delegate removal, use the [`-` operator](subtraction-operator.md#delegate-removal).</span></span>

<span data-ttu-id="d4797-113">デリゲート型の詳細については、[デリゲート](../../programming-guide/delegates/index.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="d4797-113">For more information about delegate types, see [Delegates](../../programming-guide/delegates/index.md).</span></span>

## <a name="addition-assignment-operator-"></a><span data-ttu-id="d4797-114">加算代入演算子 +=</span><span class="sxs-lookup"><span data-stu-id="d4797-114">Addition assignment operator +=</span></span>

<span data-ttu-id="d4797-115">次のような `+=` 演算子を使用する式があるとします</span><span class="sxs-lookup"><span data-stu-id="d4797-115">An expression using the `+=` operator, such as</span></span>

```csharp
x += y
```

<span data-ttu-id="d4797-116">上記の式は、次の式と同じです。</span><span class="sxs-lookup"><span data-stu-id="d4797-116">is equivalent to</span></span>

```csharp
x = x + y
```

<span data-ttu-id="d4797-117">ただし、`x` が評価されるのは 1 回だけです。</span><span class="sxs-lookup"><span data-stu-id="d4797-117">except that `x` is only evaluated once.</span></span>

<span data-ttu-id="d4797-118">`+=` 演算子の使用例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="d4797-118">The following example demonstrates the usage of the `+=` operator:</span></span>

[!code-csharp-interactive[+= examples](~/samples/csharp/language-reference/operators/AdditionOperator.cs#AddAndAssign)]

<span data-ttu-id="d4797-119">[イベント](../keywords/event.md)をサブスクライブするとき、`+=` 演算子を使用してイベント ハンドラー メソッドを指定することもできます。</span><span class="sxs-lookup"><span data-stu-id="d4797-119">You also use the `+=` operator to specify an event handler method when you subscribe to an [event](../keywords/event.md).</span></span> <span data-ttu-id="d4797-120">詳細については、「[方法: イベント サブスクリプションとサブスクリプションの解除](../../programming-guide/events/how-to-subscribe-to-and-unsubscribe-from-events.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d4797-120">For more information, see [How to: subscribe to and unsubscribe from events](../../programming-guide/events/how-to-subscribe-to-and-unsubscribe-from-events.md).</span></span>

## <a name="operator-overloadability"></a><span data-ttu-id="d4797-121">演算子のオーバーロード可/不可</span><span class="sxs-lookup"><span data-stu-id="d4797-121">Operator overloadability</span></span>

<span data-ttu-id="d4797-122">ユーザー定義型は `+` 演算子を[オーバーロード](operator-overloading.md)できます。</span><span class="sxs-lookup"><span data-stu-id="d4797-122">A user-defined type can [overload](operator-overloading.md) the `+` operator.</span></span> <span data-ttu-id="d4797-123">2 項 `+` 演算子をオーバーロードすると、`+=` 演算子も暗黙的にオーバーロードされます。</span><span class="sxs-lookup"><span data-stu-id="d4797-123">When a binary `+` operator is overloaded, the `+=` operator is also implicitly overloaded.</span></span> <span data-ttu-id="d4797-124">ユーザー定義型では、`+=` 演算子を明示的にオーバーロードできません。</span><span class="sxs-lookup"><span data-stu-id="d4797-124">A user-defined type cannot explicitly overload the `+=` operator.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="d4797-125">C# 言語仕様</span><span class="sxs-lookup"><span data-stu-id="d4797-125">C# language specification</span></span>

<span data-ttu-id="d4797-126">詳細については、[C# 言語仕様](~/_csharplang/spec/introduction.md)の[単項プラス演算子](~/_csharplang/spec/expressions.md#unary-plus-operator)と[加算演算子](~/_csharplang/spec/expressions.md#addition-operator)に関するセクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="d4797-126">For more information, see the [Unary plus operator](~/_csharplang/spec/expressions.md#unary-plus-operator) and [Addition operator](~/_csharplang/spec/expressions.md#addition-operator) sections of the [C# language specification](~/_csharplang/spec/introduction.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="d4797-127">関連項目</span><span class="sxs-lookup"><span data-stu-id="d4797-127">See also</span></span>

- [<span data-ttu-id="d4797-128">C# リファレンス</span><span class="sxs-lookup"><span data-stu-id="d4797-128">C# reference</span></span>](../index.md)
- [<span data-ttu-id="d4797-129">C# 演算子</span><span class="sxs-lookup"><span data-stu-id="d4797-129">C# operators</span></span>](index.md)
- [<span data-ttu-id="d4797-130">複数の文字列を連結する方法</span><span class="sxs-lookup"><span data-stu-id="d4797-130">How to concatenate multiple strings</span></span>](../../how-to/concatenate-multiple-strings.md)
- [<span data-ttu-id="d4797-131">イベント</span><span class="sxs-lookup"><span data-stu-id="d4797-131">Events</span></span>](../../programming-guide/events/index.md)
- [<span data-ttu-id="d4797-132">算術演算子</span><span class="sxs-lookup"><span data-stu-id="d4797-132">Arithmetic operators</span></span>](arithmetic-operators.md)
- [<span data-ttu-id="d4797-133">- および -= 演算子</span><span class="sxs-lookup"><span data-stu-id="d4797-133">- and -= operators</span></span>](subtraction-operator.md)
