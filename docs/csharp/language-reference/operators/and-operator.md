---
title: '&amp; 演算子 - C# リファレンス'
ms.custom: seodec18
ms.date: 10/29/2018
f1_keywords:
- '&_CSharpKeyword'
helpviewer_keywords:
- bitwise AND operator [C#]
- ampersand operator (&) [C#]
- '& operator [C#]'
- AND operator (&) [C#]
ms.assetid: afa346d5-90ec-4b1f-a2c8-3881f018741d
ms.openlocfilehash: 67d60709e1c6c76071ecfb7aac74c83dec6f372a
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59310045"
---
# <a name="amp-operator-c-reference"></a><span data-ttu-id="66f15-102">&amp; 演算子 (C# リファレンス)</span><span class="sxs-lookup"><span data-stu-id="66f15-102">&amp; Operator (C# Reference)</span></span>

<span data-ttu-id="66f15-103">`&` 演算子は 2 つの形式でサポートされます。単項 address-of 演算子と二項論理演算子です。</span><span class="sxs-lookup"><span data-stu-id="66f15-103">The `&` operator is supported in two forms: a unary address-of operator or a binary logical operator.</span></span>

## <a name="unary-address-of-operator"></a><span data-ttu-id="66f15-104">単項 address-of 演算子</span><span class="sxs-lookup"><span data-stu-id="66f15-104">Unary address-of operator</span></span>

<span data-ttu-id="66f15-105">単項 `&` 演算子によって、そのオペランドのアドレスが返されます。</span><span class="sxs-lookup"><span data-stu-id="66f15-105">The unary `&` operator returns the address of its operand.</span></span> <span data-ttu-id="66f15-106">詳細については、「[方法: 変数のアドレスを取得する](../../programming-guide/unsafe-code-pointers/how-to-obtain-the-address-of-a-variable.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="66f15-106">For more information, see [How to: obtain the address of a variable](../../programming-guide/unsafe-code-pointers/how-to-obtain-the-address-of-a-variable.md).</span></span>

<span data-ttu-id="66f15-107">address-of 演算子 `&` には [unsafe](../keywords/unsafe.md) コンテキストが必要です。</span><span class="sxs-lookup"><span data-stu-id="66f15-107">The address-of operator `&` requires [unsafe](../keywords/unsafe.md) context.</span></span>

## <a name="integer-logical-bitwise-and-operator"></a><span data-ttu-id="66f15-108">整数論理ビット演算 AND 演算子</span><span class="sxs-lookup"><span data-stu-id="66f15-108">Integer logical bitwise AND operator</span></span>

<span data-ttu-id="66f15-109">整数型の場合、`&` 演算子がそのオペランドの論理ビット演算 AND を計算します。</span><span class="sxs-lookup"><span data-stu-id="66f15-109">For integer types, the `&` operator computes the logical bitwise AND of its operands:</span></span>

[!code-csharp-interactive[integer logical bitwise AND](~/samples/snippets/csharp/language-reference/operators/AndOperatorExamples.cs#IntegerOperands)]

> [!NOTE]
> <span data-ttu-id="66f15-110">上記の例では、[C# 7.0 で導入され](../../whats-new/csharp-7.md#numeric-literal-syntax-improvements)、[C# 7.2 で強化された](../../whats-new/csharp-7-2.md#leading-underscores-in-numeric-literals)バイナリ リテラルを使用しています。</span><span class="sxs-lookup"><span data-stu-id="66f15-110">The preceding example uses the binary literals [introduced in C# 7.0](../../whats-new/csharp-7.md#numeric-literal-syntax-improvements) and [enhanced in C# 7.2](../../whats-new/csharp-7-2.md#leading-underscores-in-numeric-literals).</span></span>

<span data-ttu-id="66f15-111">整数型に対する演算は一般的に列挙型でも許可されているため、`&` 演算子は [enum](../keywords/enum.md) オペランドもサポートします。</span><span class="sxs-lookup"><span data-stu-id="66f15-111">Because operations on integer types are generally allowed on enumeration types, the `&` operator also supports [enum](../keywords/enum.md) operands.</span></span>

## <a name="boolean-logical-and-operator"></a><span data-ttu-id="66f15-112">ブール論理 AND 演算子</span><span class="sxs-lookup"><span data-stu-id="66f15-112">Boolean logical AND operator</span></span>

<span data-ttu-id="66f15-113">[bool](../keywords/bool.md) オペランドの場合、`&` 演算子がそのオペランドの論理 AND を計算します。</span><span class="sxs-lookup"><span data-stu-id="66f15-113">For [bool](../keywords/bool.md) operands, the `&` operator computes the logical AND of its operands.</span></span> <span data-ttu-id="66f15-114">`x` と `y` の両方が `true` であれば、`x & y` の結果は `true` です。</span><span class="sxs-lookup"><span data-stu-id="66f15-114">The result of `x & y` is `true` if both `x` and `y` are `true`.</span></span> <span data-ttu-id="66f15-115">それ以外の場合、結果は `false` です。</span><span class="sxs-lookup"><span data-stu-id="66f15-115">Otherwise, the result is `false`.</span></span>

<span data-ttu-id="66f15-116">`&` 演算子は最初のオペランドが `false` と評価されても両方のオペランドを評価するため、結果は 2 番目のオペランドの値に関係なく、必ず `false` になります。</span><span class="sxs-lookup"><span data-stu-id="66f15-116">The `&` operator evaluates both operands even if the first operand evaluates to `false`, so that the result must be `false` regardless of the value of the second operand.</span></span> <span data-ttu-id="66f15-117">次の例は、その動作を示します。</span><span class="sxs-lookup"><span data-stu-id="66f15-117">The following example demonstrates that behavior:</span></span>

[!code-csharp-interactive[bool logical AND](~/samples/snippets/csharp/language-reference/operators/AndOperatorExamples.cs#BooleanOperands)]

<span data-ttu-id="66f15-118">[条件付き AND 演算子](boolean-logical-operators.md#conditional-logical-and-operator-) `&&` もそのオペランドの論理 AND を計算しますが、最初のオペランドが `false` と評価された場合、2 番目のオペランドは評価されません。</span><span class="sxs-lookup"><span data-stu-id="66f15-118">The [conditional AND operator](boolean-logical-operators.md#conditional-logical-and-operator-) `&&` also computes the logical AND of its operands, but doesn't evaluate the second operand if the first operand evaluates to `false`.</span></span>

<span data-ttu-id="66f15-119">Null 許容型ブールのオペランドの場合、`&` 演算子の動作は、SQL の 3 値論理と一致します。</span><span class="sxs-lookup"><span data-stu-id="66f15-119">For nullable bool operands, the behavior of the `&` operator is consistent with SQL's three-valued logic.</span></span> <span data-ttu-id="66f15-120">詳細については、「[Boolean logical operators (ブール論理演算子)](boolean-logical-operators.md)」記事の「[Nullable Boolean logical operators (null 許容論理演算子)](boolean-logical-operators.md#nullable-boolean-logical-operators)」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="66f15-120">For more information, see the [Nullable Boolean logical operators](boolean-logical-operators.md#nullable-boolean-logical-operators) section of the [Boolean logical operators](boolean-logical-operators.md) article.</span></span>

## <a name="operator-overloadability"></a><span data-ttu-id="66f15-121">演算子のオーバーロード可/不可</span><span class="sxs-lookup"><span data-stu-id="66f15-121">Operator overloadability</span></span>

<span data-ttu-id="66f15-122">ユーザー定義型は二項 `&` 演算子を[オーバーロード](../keywords/operator.md)できます。</span><span class="sxs-lookup"><span data-stu-id="66f15-122">User-defined types can [overload](../keywords/operator.md) the binary `&` operator.</span></span> <span data-ttu-id="66f15-123">二項 `&` 演算子をオーバーロードすると、[AND 代入演算子](and-assignment-operator.md) `&=` も暗黙的にオーバーロードされます。</span><span class="sxs-lookup"><span data-stu-id="66f15-123">When a binary `&` operator is overloaded, the [AND assignment operator](and-assignment-operator.md) `&=` is also implicitly overloaded.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="66f15-124">C# 言語仕様</span><span class="sxs-lookup"><span data-stu-id="66f15-124">C# language specification</span></span>

<span data-ttu-id="66f15-125">詳細については、「[C# 言語仕様](../language-specification/index.md)」の [address-of 演算子](~/_csharplang/spec/unsafe-code.md#the-address-of-operator)と[論理演算子](~/_csharplang/spec/expressions.md#logical-operators)に関するセクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="66f15-125">For more information, see [The address-of operator](~/_csharplang/spec/unsafe-code.md#the-address-of-operator) and [Logical operators](~/_csharplang/spec/expressions.md#logical-operators) sections of the [C# language specification](../language-specification/index.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="66f15-126">関連項目</span><span class="sxs-lookup"><span data-stu-id="66f15-126">See also</span></span>

- [<span data-ttu-id="66f15-127">C# リファレンス</span><span class="sxs-lookup"><span data-stu-id="66f15-127">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="66f15-128">C# プログラミングガイド</span><span class="sxs-lookup"><span data-stu-id="66f15-128">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="66f15-129">C# 演算子</span><span class="sxs-lookup"><span data-stu-id="66f15-129">C# Operators</span></span>](index.md)
- [<span data-ttu-id="66f15-130">ブール論理演算子</span><span class="sxs-lookup"><span data-stu-id="66f15-130">Boolean logical operators</span></span>](boolean-logical-operators.md)
- [<span data-ttu-id="66f15-131">ポインター型</span><span class="sxs-lookup"><span data-stu-id="66f15-131">Pointer types</span></span>](../../programming-guide/unsafe-code-pointers/pointer-types.md)
- [<span data-ttu-id="66f15-132">| 演算子</span><span class="sxs-lookup"><span data-stu-id="66f15-132">| operator</span></span>](or-operator.md)
- [<span data-ttu-id="66f15-133">^ 演算子</span><span class="sxs-lookup"><span data-stu-id="66f15-133">^ operator</span></span>](xor-operator.md)
- [<span data-ttu-id="66f15-134">~ 演算子</span><span class="sxs-lookup"><span data-stu-id="66f15-134">~ operator</span></span>](bitwise-complement-operator.md)
