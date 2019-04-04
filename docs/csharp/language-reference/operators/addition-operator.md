---
title: + 演算子 - C# リファレンス
ms.custom: seodec18
ms.date: 10/22/2018
f1_keywords:
- +_CSharpKeyword
helpviewer_keywords:
- + operator [C#]
- concatenation operator [C#]
- addition operator [C#]
ms.assetid: 93e56486-bb42-43c1-bd43-60af11e64e67
ms.openlocfilehash: 0f04ba837f9c03107acd0b2174cbd07c14a8c213
ms.sourcegitcommit: 8258515adc6c37ab6278e5a3d102d593246f8672
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/27/2019
ms.locfileid: "58504471"
---
# <a name="-operator-c-reference"></a><span data-ttu-id="12ddf-102">+ 演算子 (C# リファレンス)</span><span class="sxs-lookup"><span data-stu-id="12ddf-102">+ Operator (C# Reference)</span></span>

<span data-ttu-id="12ddf-103">`+` 演算子は 2 つの形式でサポートされます。単項プラス演算子と二項加算演算子です。</span><span class="sxs-lookup"><span data-stu-id="12ddf-103">The `+` operator is supported in two forms: a unary plus operator or a binary addition operator.</span></span>

## <a name="unary-plus-operator"></a><span data-ttu-id="12ddf-104">単項プラス演算子</span><span class="sxs-lookup"><span data-stu-id="12ddf-104">Unary plus operator</span></span>

<span data-ttu-id="12ddf-105">単項 `+` 演算子によって、そのオペランドの値が返されます。</span><span class="sxs-lookup"><span data-stu-id="12ddf-105">The unary `+` operator returns the value of its operand.</span></span> <span data-ttu-id="12ddf-106">すべての数値型でサポートされます。</span><span class="sxs-lookup"><span data-stu-id="12ddf-106">It's supported by all numeric types.</span></span>

## <a name="numeric-addition"></a><span data-ttu-id="12ddf-107">数値加算</span><span class="sxs-lookup"><span data-stu-id="12ddf-107">Numeric addition</span></span>

<span data-ttu-id="12ddf-108">数値型の場合、`+` 演算子によってそのオペランドの合計が計算されます。</span><span class="sxs-lookup"><span data-stu-id="12ddf-108">For numeric types, the `+` operator computes the sum of its operands:</span></span>

[!code-csharp-interactive[numeric addition](~/samples/snippets/csharp/language-reference/operators/AdditionExamples.cs#AddNumerics)]

<span data-ttu-id="12ddf-109">算術演算子の詳細については、「[Arithmetic operators](arithmetic-operators.md)」 (算術演算子) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="12ddf-109">For more information about arithmetic operators, see [Arithmetic operators](arithmetic-operators.md).</span></span>

## <a name="string-concatenation"></a><span data-ttu-id="12ddf-110">文字列連結</span><span class="sxs-lookup"><span data-stu-id="12ddf-110">String concatenation</span></span>

<span data-ttu-id="12ddf-111">一方または両方のオペランドが[文字列](../keywords/string.md)型の場合、`+` 演算子によってそのオペランドの文字列表現が連結されます。</span><span class="sxs-lookup"><span data-stu-id="12ddf-111">When one or both operands are of type [string](../keywords/string.md), the `+` operator concatenates the string representations of its operands:</span></span>

[!code-csharp-interactive[string concatenation](~/samples/snippets/csharp/language-reference/operators/AdditionExamples.cs#AddStrings)]

<span data-ttu-id="12ddf-112">C# 6 以降、[文字列補間](../tokens/interpolated.md)という文字列を書式設定するより便利な方法が提供されます。</span><span class="sxs-lookup"><span data-stu-id="12ddf-112">Starting with C# 6, [string interpolation](../tokens/interpolated.md) provides a more convenient way to format strings:</span></span>

[!code-csharp-interactive[string interpolation](~/samples/snippets/csharp/language-reference/operators/AdditionExamples.cs#UseStringInterpolation)]

## <a name="delegate-combination"></a><span data-ttu-id="12ddf-113">デリゲートの組み合わせ</span><span class="sxs-lookup"><span data-stu-id="12ddf-113">Delegate combination</span></span>

<span data-ttu-id="12ddf-114">[デリゲート](../keywords/delegate.md)型の場合、`+` 演算子によって、呼び出されたとき、最初のオペランドを呼び出し、次に 2 番目のオペランドを呼び出す新しいデリゲート インスタンスが返されます。</span><span class="sxs-lookup"><span data-stu-id="12ddf-114">For [delegate](../keywords/delegate.md) types, the `+` operator returns a new delegate instance that, when invoked, invokes the first operand and then invokes the second operand.</span></span> <span data-ttu-id="12ddf-115">いずれかのオペランドが `null` の場合、`+` 演算子によって別のオペランドの値が返されます (`null` でもある場合があります)。</span><span class="sxs-lookup"><span data-stu-id="12ddf-115">If any of the operands is `null`, the `+` operator returns the value of another operand (which also might be `null`).</span></span> <span data-ttu-id="12ddf-116">次の例では、デリゲートが `+` 演算子と組み合わされるしくみを説明しています。</span><span class="sxs-lookup"><span data-stu-id="12ddf-116">The following example shows how delegates can be combined with the `+` operator:</span></span>

[!code-csharp-interactive[delegate combination](~/samples/snippets/csharp/language-reference/operators/AdditionExamples.cs#AddDelegates)]

<span data-ttu-id="12ddf-117">デリゲート型の詳細については、[デリゲート](../../programming-guide/delegates/index.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="12ddf-117">For more information about delegate types, see [Delegates](../../programming-guide/delegates/index.md).</span></span>

## <a name="operator-overloadability"></a><span data-ttu-id="12ddf-118">演算子のオーバーロード可/不可</span><span class="sxs-lookup"><span data-stu-id="12ddf-118">Operator overloadability</span></span>

<span data-ttu-id="12ddf-119">単項演算子と二項 `+` 演算子は、ユーザー定義型で[オーバーロード](../keywords/operator.md)できます。</span><span class="sxs-lookup"><span data-stu-id="12ddf-119">User-defined types can [overload](../keywords/operator.md) the unary and binary `+` operators.</span></span> <span data-ttu-id="12ddf-120">二項 `+` 演算子をオーバーロードすると、[加算代入演算子](addition-assignment-operator.md) `+=` も暗黙的にオーバーロードされます。</span><span class="sxs-lookup"><span data-stu-id="12ddf-120">When a binary `+` operator is overloaded, the [addition assignment operator](addition-assignment-operator.md) `+=` is also implicitly overloaded.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="12ddf-121">C# 言語仕様</span><span class="sxs-lookup"><span data-stu-id="12ddf-121">C# language specification</span></span>

<span data-ttu-id="12ddf-122">詳細については、[C# 言語仕様](../language-specification/index.md)の[単項プラス演算子](~/_csharplang/spec/expressions.md#unary-plus-operator)と[加算演算子](~/_csharplang/spec/expressions.md#addition-operator)に関するセクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="12ddf-122">For more information, see the [Unary plus operator](~/_csharplang/spec/expressions.md#unary-plus-operator) and [Addition operator](~/_csharplang/spec/expressions.md#addition-operator) sections of the [C# language specification](../language-specification/index.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="12ddf-123">関連項目</span><span class="sxs-lookup"><span data-stu-id="12ddf-123">See also</span></span>

- [<span data-ttu-id="12ddf-124">C# リファレンス</span><span class="sxs-lookup"><span data-stu-id="12ddf-124">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="12ddf-125">C# プログラミングガイド</span><span class="sxs-lookup"><span data-stu-id="12ddf-125">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="12ddf-126">C# 演算子</span><span class="sxs-lookup"><span data-stu-id="12ddf-126">C# Operators</span></span>](index.md)
- [<span data-ttu-id="12ddf-127">文字列補間</span><span class="sxs-lookup"><span data-stu-id="12ddf-127">String interpolation</span></span>](../tokens/interpolated.md)
- [<span data-ttu-id="12ddf-128">方法: 複数の文字列を連結する</span><span class="sxs-lookup"><span data-stu-id="12ddf-128">How to: Concatenate Multiple Strings</span></span>](../../how-to/concatenate-multiple-strings.md)
- [<span data-ttu-id="12ddf-129">デリゲート</span><span class="sxs-lookup"><span data-stu-id="12ddf-129">Delegates</span></span>](../../programming-guide/delegates/index.md)
- [<span data-ttu-id="12ddf-130">checked と unchecked</span><span class="sxs-lookup"><span data-stu-id="12ddf-130">Checked and unchecked</span></span>](../keywords/checked-and-unchecked.md)
