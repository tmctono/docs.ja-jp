---
title: 比較演算子 - C# リファレンス
description: 数値の順序を確認するために使用できる C# 比較演算子について説明します。
ms.date: 05/11/2020
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
ms.openlocfilehash: eda039d950e4be13d9c041c8bb95b6ea773b83f6
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/12/2020
ms.locfileid: "83207226"
---
# <a name="comparison-operators-c-reference"></a><span data-ttu-id="d9446-103">比較演算子 (C# リファレンス)</span><span class="sxs-lookup"><span data-stu-id="d9446-103">Comparison operators (C# reference)</span></span>

<span data-ttu-id="d9446-104">[`<` (小なり)](#less-than-operator-)、[`>` (大なり)](#greater-than-operator-)、[`<=` (以下)](#less-than-or-equal-operator-)、および [`>=` (以上) ](#greater-than-or-equal-operator-) 比較演算子は、関係演算子とも呼ばれ、そのオペランドの比較に使用されます。</span><span class="sxs-lookup"><span data-stu-id="d9446-104">The [`<` (less than)](#less-than-operator-), [`>` (greater than)](#greater-than-operator-), [`<=` (less than or equal)](#less-than-or-equal-operator-), and [`>=` (greater than or equal)](#greater-than-or-equal-operator-) comparison, also known as relational, operators compare their operands.</span></span> <span data-ttu-id="d9446-105">これらの演算子は、[整数](../builtin-types/integral-numeric-types.md)と[浮動小数点](../builtin-types/floating-point-numeric-types.md)のすべての数値型によってサポートされています。</span><span class="sxs-lookup"><span data-stu-id="d9446-105">Those operators are supported by all [integral](../builtin-types/integral-numeric-types.md) and [floating-point](../builtin-types/floating-point-numeric-types.md) numeric types.</span></span>

> [!NOTE]
> <span data-ttu-id="d9446-106">`==`、`<`、`>`、`<=`、および `>=` 演算子の場合、いずれかのオペランドが数値 (<xref:System.Double.NaN?displayProperty=nameWithType> または <xref:System.Single.NaN?displayProperty=nameWithType>) でない場合、演算結果は `false` になります。</span><span class="sxs-lookup"><span data-stu-id="d9446-106">For the `==`, `<`, `>`, `<=`, and `>=` operators, if any of the operands is not a number (<xref:System.Double.NaN?displayProperty=nameWithType> or <xref:System.Single.NaN?displayProperty=nameWithType>), the result of operation is `false`.</span></span> <span data-ttu-id="d9446-107">つまり、`NaN` の値は、`NaN` を含む他のどの `double` (または `float`) の値を上回ることも、下回ることも、等しいこともありません。</span><span class="sxs-lookup"><span data-stu-id="d9446-107">That means that the `NaN` value is neither greater than, less than, nor equal to any other `double` (or `float`) value, including `NaN`.</span></span> <span data-ttu-id="d9446-108">詳細およびサンプルについては、<xref:System.Double.NaN?displayProperty=nameWithType> または <xref:System.Single.NaN?displayProperty=nameWithType> の参照記事をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="d9446-108">For more information and examples, see the <xref:System.Double.NaN?displayProperty=nameWithType> or <xref:System.Single.NaN?displayProperty=nameWithType> reference article.</span></span>

<span data-ttu-id="d9446-109">[char](../builtin-types/char.md) 型では、比較演算子もサポートされています。</span><span class="sxs-lookup"><span data-stu-id="d9446-109">The [char](../builtin-types/char.md) type also supports comparison operators.</span></span> <span data-ttu-id="d9446-110">オペランドが `char` 場合は、対応する文字コードが比較されます。</span><span class="sxs-lookup"><span data-stu-id="d9446-110">In the case of `char` operands, the corresponding character codes are compared.</span></span>

<span data-ttu-id="d9446-111">列挙型は比較演算子もサポートします。</span><span class="sxs-lookup"><span data-stu-id="d9446-111">Enumeration types also support comparison operators.</span></span> <span data-ttu-id="d9446-112">同じ[列挙](../builtin-types/enum.md)型のオペランドで、基になる整数型の対応する値が比較されます。</span><span class="sxs-lookup"><span data-stu-id="d9446-112">For operands of the same [enum](../builtin-types/enum.md) type, the corresponding values of the underlying integral type are compared.</span></span>

<span data-ttu-id="d9446-113">[`==` および `!=` 演算子](equality-operators.md) では、そのオペランドが等しいかどうかが確認されます。</span><span class="sxs-lookup"><span data-stu-id="d9446-113">The [`==` and `!=` operators](equality-operators.md) check if their operands are equal or not.</span></span>

## <a name="less-than-operator-"></a><span data-ttu-id="d9446-114">小なり演算子 \<</span><span class="sxs-lookup"><span data-stu-id="d9446-114">Less than operator \<</span></span>

<span data-ttu-id="d9446-115">左側のオペランドが右側のオペランドより小さい場合、`<` 演算子から `true` が返され、それ以外の場合は `false` が返されます。</span><span class="sxs-lookup"><span data-stu-id="d9446-115">The `<` operator returns `true` if its left-hand operand is less than its right-hand operand, `false` otherwise:</span></span>

[!code-csharp-interactive[less than example](snippets/ComparisonOperators.cs#Less)]

## <a name="greater-than-operator-"></a><span data-ttu-id="d9446-116">大なり演算子 ></span><span class="sxs-lookup"><span data-stu-id="d9446-116">Greater than operator ></span></span>

<span data-ttu-id="d9446-117">左側のオペランドが右側のオペランドより大きい場合、`>` 演算子から `true` が返され、それ以外の場合は `false` が返されます。</span><span class="sxs-lookup"><span data-stu-id="d9446-117">The `>` operator returns `true` if its left-hand operand is greater than its right-hand operand, `false` otherwise:</span></span>

[!code-csharp-interactive[greater than example](snippets/ComparisonOperators.cs#Greater)]

## <a name="less-than-or-equal-operator-"></a><span data-ttu-id="d9446-118">以下演算子 \<=</span><span class="sxs-lookup"><span data-stu-id="d9446-118">Less than or equal operator \<=</span></span>

<span data-ttu-id="d9446-119">左側のオペランドが右側のオペランド以下の場合、`<=` 演算子から `true` が返され、それ以外の場合は `false` が返されます。</span><span class="sxs-lookup"><span data-stu-id="d9446-119">The `<=` operator returns `true` if its left-hand operand is less than or equal to its right-hand operand, `false` otherwise:</span></span>

[!code-csharp-interactive[less than or equal example](snippets/ComparisonOperators.cs#LessOrEqual)]

## <a name="greater-than-or-equal-operator-"></a><span data-ttu-id="d9446-120">以上演算子 >=</span><span class="sxs-lookup"><span data-stu-id="d9446-120">Greater than or equal operator >=</span></span>

<span data-ttu-id="d9446-121">左側のオペランドが右側のオペランド以上の場合、`>=` 演算子から `true` が返され、それ以外の場合は `false` が返されます。</span><span class="sxs-lookup"><span data-stu-id="d9446-121">The `>=` operator returns `true` if its left-hand operand is greater than or equal to its right-hand operand, `false` otherwise:</span></span>

[!code-csharp-interactive[greater than or equal example](snippets/ComparisonOperators.cs#GreaterOrEqual)]

## <a name="operator-overloadability"></a><span data-ttu-id="d9446-122">演算子のオーバーロード可/不可</span><span class="sxs-lookup"><span data-stu-id="d9446-122">Operator overloadability</span></span>

<span data-ttu-id="d9446-123">ユーザー定義型は、`<`、`>`、`<=`、および `>=` 演算子を[オーバーロード](operator-overloading.md)できます。</span><span class="sxs-lookup"><span data-stu-id="d9446-123">A user-defined type can [overload](operator-overloading.md) the `<`, `>`, `<=`, and `>=` operators.</span></span>

<span data-ttu-id="d9446-124">ある型で `<` または `>` 演算子のいずれかをオーバーロードする場合は、`<` と `>` の両方をオーバーロードする必要があります。</span><span class="sxs-lookup"><span data-stu-id="d9446-124">If a type overloads one of the `<` or `>` operators, it must overload both `<` and `>`.</span></span> <span data-ttu-id="d9446-125">ある型で `<=` または `>=` 演算子のいずれかをオーバーロードする場合は、`<=` と `>=` の両方をオーバーロードする必要があります。</span><span class="sxs-lookup"><span data-stu-id="d9446-125">If a type overloads one of the `<=` or `>=` operators, it must overload both `<=` and `>=`.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="d9446-126">C# 言語仕様</span><span class="sxs-lookup"><span data-stu-id="d9446-126">C# language specification</span></span>

<span data-ttu-id="d9446-127">詳細については、[C# 言語仕様](~/_csharplang/spec/introduction.md)に関するページの「[関係演算子と型検査演算子](~/_csharplang/spec/expressions.md#relational-and-type-testing-operators)」のセクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="d9446-127">For more information, see the [Relational and type-testing operators](~/_csharplang/spec/expressions.md#relational-and-type-testing-operators) section of the [C# language specification](~/_csharplang/spec/introduction.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="d9446-128">関連項目</span><span class="sxs-lookup"><span data-stu-id="d9446-128">See also</span></span>

- [<span data-ttu-id="d9446-129">C# リファレンス</span><span class="sxs-lookup"><span data-stu-id="d9446-129">C# reference</span></span>](../index.md)
- [<span data-ttu-id="d9446-130">C# 演算子</span><span class="sxs-lookup"><span data-stu-id="d9446-130">C# operators</span></span>](index.md)
- <xref:System.IComparable%601?displayProperty=nameWithType>
- [<span data-ttu-id="d9446-131">等値演算子</span><span class="sxs-lookup"><span data-stu-id="d9446-131">Equality operators</span></span>](equality-operators.md)
