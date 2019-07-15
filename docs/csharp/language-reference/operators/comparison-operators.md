---
title: 比較演算子 - C# リファレンス
description: 数値の順序を確認するために使用できる C# 比較演算子について説明します。
ms.date: 04/25/2019
author: pkulikov
f1_keywords:
- <_CSharpKeyword
- '>_CSharpKeyword'
- <=_CSharpKeyword
- '>=_CSharpKeyword'
helpviewer_keywords:
- comparison operators [C#]
- relational operators [C#]
- less than operator [C#]
- < operator [C#]
- greater than operator [C#]
- '> operator [C#]'
- less than or equal to operator [C#]
- <= operator [C#]
- greater than or equal to operator [C#]
- '>= operator [C#]'
ms.openlocfilehash: d3e9bf1356218f223f959b423dfc048972b075d3
ms.sourcegitcommit: d6e27023aeaffc4b5a3cb4b88685018d6284ada4
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/09/2019
ms.locfileid: "67661519"
---
# <a name="comparison-operators-c-reference"></a><span data-ttu-id="286bb-103">比較演算子 (C# リファレンス)</span><span class="sxs-lookup"><span data-stu-id="286bb-103">Comparison operators (C# reference)</span></span>

<span data-ttu-id="286bb-104">[`<` (小なり)](#less-than-operator-)、[`>` (大なり)](#greater-than-operator-)、[`<=` (以下)](#less-than-or-equal-operator-)、および [`>=` (以上) ](#greater-than-or-equal-operator-) 比較演算子は、関係演算子とも呼ばれ、そのオペランドの比較に使用されます。</span><span class="sxs-lookup"><span data-stu-id="286bb-104">The [`<` (less than)](#less-than-operator-), [`>` (greater than)](#greater-than-operator-), [`<=` (less than or equal)](#less-than-or-equal-operator-), and [`>=` (greater than or equal)](#greater-than-or-equal-operator-) comparison, also known as relational, operators compare their operands.</span></span> <span data-ttu-id="286bb-105">これらの演算子は、[整数](../builtin-types/integral-numeric-types.md)と[浮動小数点](../builtin-types/floating-point-numeric-types.md)のすべての数値型をサポートしています。</span><span class="sxs-lookup"><span data-stu-id="286bb-105">Those operators support all [integral](../builtin-types/integral-numeric-types.md) and [floating-point](../builtin-types/floating-point-numeric-types.md) numeric types.</span></span>

> [!NOTE]
> <span data-ttu-id="286bb-106">`==`、`<`、`>`、`<=`、および `>=` 演算子の場合、いずれかのオペランドが数値 (<xref:System.Double.NaN?displayProperty=nameWithType> または <xref:System.Single.NaN?displayProperty=nameWithType>) でない場合、演算結果は `false` になります。</span><span class="sxs-lookup"><span data-stu-id="286bb-106">For the `==`, `<`, `>`, `<=`, and `>=` operators, if any of the operands is not a number (<xref:System.Double.NaN?displayProperty=nameWithType> or <xref:System.Single.NaN?displayProperty=nameWithType>), the result of operation is `false`.</span></span> <span data-ttu-id="286bb-107">つまり、`NaN` の値は、`NaN` を含む他のどの `double` (または `float`) の値を上回ることも、下回ることも、等しいこともありません。</span><span class="sxs-lookup"><span data-stu-id="286bb-107">That means that the `NaN` value is neither greater than, less than, nor equal to any other `double` (or `float`) value, including `NaN`.</span></span> <span data-ttu-id="286bb-108">詳細およびサンプルについては、<xref:System.Double.NaN?displayProperty=nameWithType> または <xref:System.Single.NaN?displayProperty=nameWithType> の参照記事をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="286bb-108">For more information and examples, see the <xref:System.Double.NaN?displayProperty=nameWithType> or <xref:System.Single.NaN?displayProperty=nameWithType> reference article.</span></span>

<span data-ttu-id="286bb-109">列挙型は比較演算子もサポートします。</span><span class="sxs-lookup"><span data-stu-id="286bb-109">Enumeration types also support comparison operators.</span></span> <span data-ttu-id="286bb-110">同じ[列挙](../keywords/enum.md)型のオペランドで、基になる整数型の対応する値が比較されます。</span><span class="sxs-lookup"><span data-stu-id="286bb-110">For operands of the same [enum](../keywords/enum.md) type, the corresponding values of the underlying integral type are compared.</span></span>

<span data-ttu-id="286bb-111">[`==` および `!=` 演算子](equality-operators.md) では、そのオペランドが等しいかどうかが確認されます。</span><span class="sxs-lookup"><span data-stu-id="286bb-111">The [`==` and `!=` operators](equality-operators.md) check if their operands are equal or not.</span></span>

## <a name="less-than-operator-"></a><span data-ttu-id="286bb-112">小なり演算子 \<</span><span class="sxs-lookup"><span data-stu-id="286bb-112">Less than operator \<</span></span>

<span data-ttu-id="286bb-113">左側のオペランドが右側のオペランドより小さい場合、`<` 演算子から `true` が返され、それ以外の場合は `false` が返されます。</span><span class="sxs-lookup"><span data-stu-id="286bb-113">The `<` operator returns `true` if its left-hand operand is less than its right-hand operand, `false` otherwise:</span></span>

[!code-csharp-interactive[less than example](~/samples/csharp/language-reference/operators/ComparisonOperators.cs#Less)]

## <a name="greater-than-operator-"></a><span data-ttu-id="286bb-114">大なり演算子 ></span><span class="sxs-lookup"><span data-stu-id="286bb-114">Greater than operator ></span></span>

<span data-ttu-id="286bb-115">左側のオペランドが右側のオペランドより大きい場合、`>` 演算子から `true` が返され、それ以外の場合は `false` が返されます。</span><span class="sxs-lookup"><span data-stu-id="286bb-115">The `>` operator returns `true` if its left-hand operand is greater than its right-hand operand, `false` otherwise:</span></span>

[!code-csharp-interactive[greater than example](~/samples/csharp/language-reference/operators/ComparisonOperators.cs#Greater)]

## <a name="less-than-or-equal-operator-"></a><span data-ttu-id="286bb-116">以下演算子 \<=</span><span class="sxs-lookup"><span data-stu-id="286bb-116">Less than or equal operator \<=</span></span>

<span data-ttu-id="286bb-117">左側のオペランドが右側のオペランド以下の場合、`<=` 演算子から `true` が返され、それ以外の場合は `false` が返されます。</span><span class="sxs-lookup"><span data-stu-id="286bb-117">The `<=` operator returns `true` if its left-hand operand is less than or equal to its right-hand operand, `false` otherwise:</span></span>

[!code-csharp-interactive[less than or equal example](~/samples/csharp/language-reference/operators/ComparisonOperators.cs#LessOrEqual)]

## <a name="greater-than-or-equal-operator-"></a><span data-ttu-id="286bb-118">以上演算子 >=</span><span class="sxs-lookup"><span data-stu-id="286bb-118">Greater than or equal operator >=</span></span>

<span data-ttu-id="286bb-119">左側のオペランドが右側のオペランド以上の場合、`>=` 演算子から `true` が返され、それ以外の場合は `false` が返されます。</span><span class="sxs-lookup"><span data-stu-id="286bb-119">The `>=` operator returns `true` if its left-hand operand is greater than or equal to its right-hand operand, `false` otherwise:</span></span>

[!code-csharp-interactive[greater than or equal example](~/samples/csharp/language-reference/operators/ComparisonOperators.cs#GreaterOrEqual)]

## <a name="operator-overloadability"></a><span data-ttu-id="286bb-120">演算子のオーバーロード可/不可</span><span class="sxs-lookup"><span data-stu-id="286bb-120">Operator overloadability</span></span>

<span data-ttu-id="286bb-121">ユーザー定義型は、`<`、`>`、`<=`、および `>=` 演算子を[オーバーロード](operator-overloading.md)できます。</span><span class="sxs-lookup"><span data-stu-id="286bb-121">A user-defined type can [overload](operator-overloading.md) the `<`, `>`, `<=`, and `>=` operators.</span></span>

<span data-ttu-id="286bb-122">ある型で `<` または `>` 演算子のいずれかをオーバーロードする場合は、`<` と `>` の両方をオーバーロードする必要があります。</span><span class="sxs-lookup"><span data-stu-id="286bb-122">If a type overloads one of the `<` or `>` operators, it must overload both `<` and `>`.</span></span> <span data-ttu-id="286bb-123">ある型で `<=` または `>=` 演算子のいずれかをオーバーロードする場合は、`<=` と `>=` の両方をオーバーロードする必要があります。</span><span class="sxs-lookup"><span data-stu-id="286bb-123">If a type overloads one of the `<=` or `>=` operators, it must overload both `<=` and `>=`.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="286bb-124">C# 言語仕様</span><span class="sxs-lookup"><span data-stu-id="286bb-124">C# language specification</span></span>

<span data-ttu-id="286bb-125">詳細については、[C# 言語仕様](~/_csharplang/spec/introduction.md)に関するページの「[関係演算子と型検査演算子](~/_csharplang/spec/expressions.md#relational-and-type-testing-operators)」のセクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="286bb-125">For more information, see the [Relational and type-testing operators](~/_csharplang/spec/expressions.md#relational-and-type-testing-operators) section of the [C# language specification](~/_csharplang/spec/introduction.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="286bb-126">関連項目</span><span class="sxs-lookup"><span data-stu-id="286bb-126">See also</span></span>

- [<span data-ttu-id="286bb-127">C# リファレンス</span><span class="sxs-lookup"><span data-stu-id="286bb-127">C# reference</span></span>](../index.md)
- [<span data-ttu-id="286bb-128">C# 演算子</span><span class="sxs-lookup"><span data-stu-id="286bb-128">C# operators</span></span>](index.md)
- <xref:System.IComparable%601?displayProperty=nameWithType>
- [<span data-ttu-id="286bb-129">等値演算子</span><span class="sxs-lookup"><span data-stu-id="286bb-129">Equality operators</span></span>](equality-operators.md)
