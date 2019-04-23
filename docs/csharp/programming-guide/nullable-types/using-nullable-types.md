---
title: Null 許容型の使用 - C# プログラミング ガイド
ms.custom: seodec18
description: Learn how to work with C# nullable types (C# Null 許容型の操作方法について)
ms.date: 08/02/2018
helpviewer_keywords:
- nullable types [C#], about nullable types
ms.assetid: 0bacbe72-ce15-4b14-83e1-9c14e6380c28
ms.openlocfilehash: ef7c9c18d303131b5a1c0156be820e1d475e7ec1
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59306652"
---
# <a name="using-nullable-types-c-programming-guide"></a><span data-ttu-id="08796-103">Null 許容型の使用 (C# プログラミング ガイド)</span><span class="sxs-lookup"><span data-stu-id="08796-103">Using nullable types (C# Programming Guide)</span></span>

<span data-ttu-id="08796-104">Null 許容型は、基になる値型 `T` のすべての値と、追加の [null](../../language-reference/keywords/null.md) 値を表す型です。</span><span class="sxs-lookup"><span data-stu-id="08796-104">Nullable types are types that represent all the values of an underlying value type `T`, and an additional [null](../../language-reference/keywords/null.md) value.</span></span> <span data-ttu-id="08796-105">詳細については、「[Null 許容型](index.md)」のトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="08796-105">For more information, see the [Nullable types](index.md) topic.</span></span>

<span data-ttu-id="08796-106">Null 許容型は、`Nullable<T>` または `T?` のいずれかの形式で参照できます。</span><span class="sxs-lookup"><span data-stu-id="08796-106">You can refer to a nullable type in any of the following forms: `Nullable<T>` or `T?`.</span></span> <span data-ttu-id="08796-107">この 2 つの形式は同義であり、どちらでも使用できます。</span><span class="sxs-lookup"><span data-stu-id="08796-107">These two forms are interchangeable.</span></span>  
  
## <a name="declaration-and-assignment"></a><span data-ttu-id="08796-108">宣言と代入</span><span class="sxs-lookup"><span data-stu-id="08796-108">Declaration and assignment</span></span>

<span data-ttu-id="08796-109">値型は、対応する Null 許容型に暗黙的に変換できるので、基になる値型の場合と同様に Null 許容型に値を代入します。</span><span class="sxs-lookup"><span data-stu-id="08796-109">As a value type can be implicitly converted to the corresponding nullable type, you assign a value to a nullable type as you would for its underlying value type.</span></span> <span data-ttu-id="08796-110">`null` 値を代入することもできます。</span><span class="sxs-lookup"><span data-stu-id="08796-110">You also can assign the `null` value.</span></span>  <span data-ttu-id="08796-111">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="08796-111">For example:</span></span>
  
[!code-csharp[declare and assign](../../../../samples/snippets/csharp/programming-guide/nullable-types/NullableTypesUsage.cs#1)]

## <a name="examination-of-a-nullable-type-value"></a><span data-ttu-id="08796-112">Null 許容型の値の検査</span><span class="sxs-lookup"><span data-stu-id="08796-112">Examination of a nullable type value</span></span>

<span data-ttu-id="08796-113">Null 許容型のインスタンスが null かどうかを調べて、基になる型の値を取得するには、次の読み取り専用プロパティを使用します。</span><span class="sxs-lookup"><span data-stu-id="08796-113">Use the following readonly properties to examine an instance of a nullable type for null and retrieve a value of an underlying type:</span></span>  
  
- <span data-ttu-id="08796-114"><xref:System.Nullable%601.HasValue%2A?displayProperty=nameWithType> は、Null 許容型のインスタンスに、基になる型の値が含まれるかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="08796-114"><xref:System.Nullable%601.HasValue%2A?displayProperty=nameWithType> indicates whether an instance of a nullable type has a value of its underlying type.</span></span>
  
- <span data-ttu-id="08796-115"><xref:System.Nullable%601.HasValue%2A> が `true` の場合、<xref:System.Nullable%601.Value%2A?displayProperty=nameWithType> は基になる型の値を取得します。</span><span class="sxs-lookup"><span data-stu-id="08796-115"><xref:System.Nullable%601.Value%2A?displayProperty=nameWithType> gets the value of an underlying type if <xref:System.Nullable%601.HasValue%2A> is `true`.</span></span> <span data-ttu-id="08796-116"><xref:System.Nullable%601.HasValue%2A> が `false` の場合、<xref:System.Nullable%601.Value%2A> プロパティは <xref:System.InvalidOperationException> をスローします。</span><span class="sxs-lookup"><span data-stu-id="08796-116">If <xref:System.Nullable%601.HasValue%2A> is `false`, the <xref:System.Nullable%601.Value%2A> property throws an <xref:System.InvalidOperationException>.</span></span>
  
<span data-ttu-id="08796-117">次の例のコードでは、`HasValue` プロパティを使用して、値を表示する前に変数に値が格納されているかどうかをテストします。</span><span class="sxs-lookup"><span data-stu-id="08796-117">The code in the following example uses the `HasValue` property to test whether the variable contains a value before displaying it:</span></span>
  
[!code-csharp-interactive[use HasValue](../../../../samples/snippets/csharp/programming-guide/nullable-types/NullableTypesUsage.cs#2)]
  
<span data-ttu-id="08796-118">次の例に示すように、`HasValue` プロパティを使用する代わりに、Null 許容型の変数を `null` と比較することもできます。</span><span class="sxs-lookup"><span data-stu-id="08796-118">You also can compare a nullable type variable with `null` instead of using the `HasValue` property, as the following example shows:</span></span>  
  
[!code-csharp-interactive[use comparison with null](../../../../samples/snippets/csharp/programming-guide/nullable-types/NullableTypesUsage.cs#3)]

<span data-ttu-id="08796-119">C# 7.0 以降では、[パターン マッチング](../../pattern-matching.md)を使用して Null 許容型の値を調べて取得することができます。</span><span class="sxs-lookup"><span data-stu-id="08796-119">Beginning with C# 7.0, you can use [pattern matching](../../pattern-matching.md) to both examine and get a value of a nullable type:</span></span>

[!code-csharp-interactive[use pattern matching](../../../../samples/snippets/csharp/programming-guide/nullable-types/NullableTypesUsage.cs#4)]

## <a name="conversion-from-a-nullable-type-to-an-underlying-type"></a><span data-ttu-id="08796-120">Null 許容型から基になる型への変換</span><span class="sxs-lookup"><span data-stu-id="08796-120">Conversion from a nullable type to an underlying type</span></span>

<span data-ttu-id="08796-121">Null 許容型の値を Null 非許容型に代入する必要がある場合は、[Null 合体演算子 `??`](../../language-reference/operators/null-coalescing-operator.md) を使用して、Null 許容型の値が null の場合に代入される値を指定します (<xref:System.Nullable%601.GetValueOrDefault(%600)?displayProperty=nameWithType> メソッドを使用してこの操作を行うこともできます)。</span><span class="sxs-lookup"><span data-stu-id="08796-121">If you need to assign a nullable type value to a non-nullable type, use the [null-coalescing operator `??`](../../language-reference/operators/null-coalescing-operator.md) to specify the value to be assigned if a nullable type value is null (you also can use the <xref:System.Nullable%601.GetValueOrDefault(%600)?displayProperty=nameWithType> method to do that):</span></span>
  
[!code-csharp-interactive[?? operator](../../../../samples/snippets/csharp/programming-guide/nullable-types/NullableTypesUsage.cs#5)]

<span data-ttu-id="08796-122">Null 許容型の値が null の場合に使用される値を、基になる値型の既定値にする場合は、<xref:System.Nullable%601.GetValueOrDefault?displayProperty=nameWithType> メソッドを使用します。</span><span class="sxs-lookup"><span data-stu-id="08796-122">Use the <xref:System.Nullable%601.GetValueOrDefault?displayProperty=nameWithType> method if the value to be used when a nullable type value is null should be the default value of the underlying value type.</span></span>
  
<span data-ttu-id="08796-123">Null 許容型を Null 非許容型に明示的にキャストすることができます。</span><span class="sxs-lookup"><span data-stu-id="08796-123">You can explicitly cast a nullable type to a non-nullable type.</span></span> <span data-ttu-id="08796-124">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="08796-124">For example:</span></span>  
  
[!code-csharp[explicit cast](../../../../samples/snippets/csharp/programming-guide/nullable-types/NullableTypesUsage.cs#6)]

<span data-ttu-id="08796-125">実行時に Null 許容型の値が null の場合は、明示的なキャストによって <xref:System.InvalidOperationException> がスローされます。</span><span class="sxs-lookup"><span data-stu-id="08796-125">At run time, if the value of a nullable type is null, the explicit cast throws an <xref:System.InvalidOperationException>.</span></span>

<span data-ttu-id="08796-126">Null 非許容値型は、対応する Null 許容型に暗黙的に変換されます。</span><span class="sxs-lookup"><span data-stu-id="08796-126">A non-nullable value type is implicitly converted to the corresponding nullable type.</span></span>
  
## <a name="operators"></a><span data-ttu-id="08796-127">演算子</span><span class="sxs-lookup"><span data-stu-id="08796-127">Operators</span></span>

<span data-ttu-id="08796-128">値型向けに存在している定義済みの単項演算子、2 項演算子およびすべてのユーザー定義演算子は、Null 許容型でも使用できます。</span><span class="sxs-lookup"><span data-stu-id="08796-128">The predefined unary and binary operators and any user-defined operators that exist for value types may also be used by nullable types.</span></span> <span data-ttu-id="08796-129">これらの演算子では、1 つまたは両方のオペランドが null の場合は null 値が生成され、null 以外の場合は、含まれている値に基づいて結果が算出されます。</span><span class="sxs-lookup"><span data-stu-id="08796-129">These operators produce a null value if one or both operands are null; otherwise, the operator uses the contained values to calculate the result.</span></span> <span data-ttu-id="08796-130">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="08796-130">For example:</span></span>  
  
[!code-csharp[operators](../../../../samples/snippets/csharp/programming-guide/nullable-types/NullableTypesUsage.cs#7)]

> [!NOTE]
> <span data-ttu-id="08796-131">`bool?` 型の場合、定義済みの `&` および `|` 演算子は、このセクションで説明されている規則に従わないことに注意してください。オペランドの 1 つが null の場合も、演算子の評価の結果は null 以外である可能性があります。</span><span class="sxs-lookup"><span data-stu-id="08796-131">For the `bool?` type, the predefined `&` and `|` operators don't follow the rules described in this section: the result of an operator evaluation can be non-null even if one of the operands is null.</span></span> <span data-ttu-id="08796-132">詳細については、「[Boolean logical operators (ブール論理演算子)](../../language-reference/operators/boolean-logical-operators.md)」記事の「[Nullable Boolean logical operators (null 許容論理演算子)](../../language-reference/operators/boolean-logical-operators.md#nullable-boolean-logical-operators)」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="08796-132">For more information, see the [Nullable Boolean logical operators](../../language-reference/operators/boolean-logical-operators.md#nullable-boolean-logical-operators) section of the [Boolean logical operators](../../language-reference/operators/boolean-logical-operators.md) article.</span></span>
  
<span data-ttu-id="08796-133">関係演算子 (`<`、`>`、`<=`、`>=`) では、1 つまたは両方のオペランドが null の場合、結果は `false` になります。</span><span class="sxs-lookup"><span data-stu-id="08796-133">For the relational operators (`<`, `>`, `<=`, `>=`), if one or both operands are null, the result is `false`.</span></span> <span data-ttu-id="08796-134">ある比較 (たとえば、`<=`) から返される結果が `false` であっても、逆の比較 (`>`) から返される結果が `true` であるとは限りません。</span><span class="sxs-lookup"><span data-stu-id="08796-134">Do not assume that because a particular comparison (for example, `<=`) returns `false`, the opposite comparison (`>`) returns `true`.</span></span> <span data-ttu-id="08796-135">次の例は、10 が</span><span class="sxs-lookup"><span data-stu-id="08796-135">The following example shows that 10 is</span></span>

- <span data-ttu-id="08796-136">null より大きくも等しくもなく、</span><span class="sxs-lookup"><span data-stu-id="08796-136">neither greater than or equal to null,</span></span>
- <span data-ttu-id="08796-137">null 未満でもないことを示しています。</span><span class="sxs-lookup"><span data-stu-id="08796-137">nor less than null.</span></span>
  
[!code-csharp-interactive[relational and equality operators](../../../../samples/snippets/csharp/programming-guide/nullable-types/NullableTypesUsage.cs#8)]
  
<span data-ttu-id="08796-138">上記の例は、どちらも null である 2 つの null 許容型を等価比較すると、結果が `true` と評価されることを示しています。</span><span class="sxs-lookup"><span data-stu-id="08796-138">The above example also shows that an equality comparison of two nullable types that are both null evaluates to `true`.</span></span>

<span data-ttu-id="08796-139">詳細については、[C# 言語仕様](~/_csharplang/spec/introduction.md)に関するページの「[リフトされた演算子](~/_csharplang/spec/expressions.md#lifted-operators)」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="08796-139">For more information, see the [Lifted operators](~/_csharplang/spec/expressions.md#lifted-operators) section of the [C# language specification](~/_csharplang/spec/introduction.md).</span></span>

## <a name="boxing-and-unboxing"></a><span data-ttu-id="08796-140">ボックス化とボックス化解除</span><span class="sxs-lookup"><span data-stu-id="08796-140">Boxing and unboxing</span></span>

<span data-ttu-id="08796-141">Null 許容値型は、次の規則に従って[ボックス化](../types/boxing-and-unboxing.md)されます。</span><span class="sxs-lookup"><span data-stu-id="08796-141">A nullable value type is [boxed](../types/boxing-and-unboxing.md) by the following rules:</span></span>

- <span data-ttu-id="08796-142"><xref:System.Nullable%601.HasValue%2A> が `false` を返した場合は、null 参照が生成されます。</span><span class="sxs-lookup"><span data-stu-id="08796-142">If <xref:System.Nullable%601.HasValue%2A> returns `false`, the null reference is produced.</span></span>  
- <span data-ttu-id="08796-143"><xref:System.Nullable%601.HasValue%2A> が `true` を返した場合は、<xref:System.Nullable%601> のインスタンスではなく、基になる値型 `T` の値がボックス化されます。</span><span class="sxs-lookup"><span data-stu-id="08796-143">If <xref:System.Nullable%601.HasValue%2A> returns `true`, a value of the underlying value type `T` is boxed, not the instance of <xref:System.Nullable%601>.</span></span>

<span data-ttu-id="08796-144">次の例に示すように、ボックス化された値型を、対応する Null 許容型にボックス化解除できます。</span><span class="sxs-lookup"><span data-stu-id="08796-144">You can unbox the boxed value type to the corresponding nullable type, as the following example shows:</span></span>

[!code-csharp-interactive[boxing and unboxing](../../../../samples/snippets/csharp/programming-guide/nullable-types/NullableTypesUsage.cs#9)]

## <a name="see-also"></a><span data-ttu-id="08796-145">関連項目</span><span class="sxs-lookup"><span data-stu-id="08796-145">See also</span></span>

- [<span data-ttu-id="08796-146">Null 許容型</span><span class="sxs-lookup"><span data-stu-id="08796-146">Nullable types</span></span>](index.md)
- [<span data-ttu-id="08796-147">C# プログラミング ガイド</span><span class="sxs-lookup"><span data-stu-id="08796-147">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="08796-148">What Exactly Does 'Lifted' mean? ('Lifted' の正確な意味)</span><span class="sxs-lookup"><span data-stu-id="08796-148">What exactly does 'lifted' mean?</span></span>](https://blogs.msdn.microsoft.com/ericlippert/2007/06/27/what-exactly-does-lifted-mean/)
