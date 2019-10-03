---
title: null 許容値型の使用 - C# プログラミング ガイド
ms.custom: seodec18
description: C# の null 許容値型を使用する方法について説明します。
ms.date: 09/26/2019
helpviewer_keywords:
- nullable types [C#], about nullable types
ms.assetid: 0bacbe72-ce15-4b14-83e1-9c14e6380c28
ms.openlocfilehash: 65fc3b0ca94f9a41c9375e96000449b52cb7db26
ms.sourcegitcommit: da2dd2772fcf32b44eb18b1cbe8affd17b1753c9
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/27/2019
ms.locfileid: "71396161"
---
# <a name="using-nullable-value-types-c-programming-guide"></a><span data-ttu-id="e9599-103">null 許容値型の使用 (C# プログラミング ガイド)</span><span class="sxs-lookup"><span data-stu-id="e9599-103">Using nullable value types (C# Programming Guide)</span></span>

<span data-ttu-id="e9599-104">null 許容値型は、基になる値型 `T` のすべての値と、追加の [null](../../language-reference/keywords/null.md) 値を表す型です。</span><span class="sxs-lookup"><span data-stu-id="e9599-104">Nullable value types are types that represent all the values of an underlying value type `T`, and an additional [null](../../language-reference/keywords/null.md) value.</span></span> <span data-ttu-id="e9599-105">詳細については、「[null 許容値型](index.md)」のトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="e9599-105">For more information, see the [Nullable value types](index.md) topic.</span></span>

> [!NOTE]
> <span data-ttu-id="e9599-106">C# 8.0 で、Null 許容参照型機能が導入されました。</span><span class="sxs-lookup"><span data-stu-id="e9599-106">C# 8.0 introduces the nullable reference types feature.</span></span> <span data-ttu-id="e9599-107">詳細については、「[null 許容参照型](../../nullable-references.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e9599-107">For more information, see [Nullable reference types](../../nullable-references.md).</span></span> <span data-ttu-id="e9599-108">null 許容値型は、C# 2 から使用できます。</span><span class="sxs-lookup"><span data-stu-id="e9599-108">The nullable value types are available starting with C# 2.</span></span>

<span data-ttu-id="e9599-109">`Nullable<T>` または `T?` の代替可能な形式のいずれかで null 許容値型を参照できます。</span><span class="sxs-lookup"><span data-stu-id="e9599-109">You can refer to a nullable value type in any of the following interchangeable forms: `Nullable<T>` or `T?`.</span></span> <span data-ttu-id="e9599-110">`T` は値の型である必要があります。</span><span class="sxs-lookup"><span data-stu-id="e9599-110">`T` must be a value type.</span></span>

## <a name="declaration-and-assignment"></a><span data-ttu-id="e9599-111">宣言と代入</span><span class="sxs-lookup"><span data-stu-id="e9599-111">Declaration and assignment</span></span>

<span data-ttu-id="e9599-112">値の型は、対応する null 許容値型に暗黙的に変換できるので、基になる値型の場合と同様に null 許容型に値を代入します。</span><span class="sxs-lookup"><span data-stu-id="e9599-112">As a value type can be implicitly converted to the corresponding nullable value type, you assign a value to a nullable type as you would for its underlying value type.</span></span> <span data-ttu-id="e9599-113">`null` 値を代入することもできます。</span><span class="sxs-lookup"><span data-stu-id="e9599-113">You also can assign the `null` value.</span></span> <span data-ttu-id="e9599-114">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="e9599-114">For example:</span></span>

[!code-csharp[declare and assign](../../../../samples/snippets/csharp/programming-guide/nullable-types/NullableTypesUsage.cs#1)]

## <a name="examination-of-a-nullable-type-value"></a><span data-ttu-id="e9599-115">Null 許容型の値の検査</span><span class="sxs-lookup"><span data-stu-id="e9599-115">Examination of a nullable type value</span></span>

<span data-ttu-id="e9599-116">null 許容値型のインスタンスが null かどうかを調べて、基になる型の値を取得するには、次の読み取り専用プロパティを使用します。</span><span class="sxs-lookup"><span data-stu-id="e9599-116">Use the following readonly properties to examine an instance of a nullable value type for null and retrieve a value of an underlying type:</span></span>

- <span data-ttu-id="e9599-117"><xref:System.Nullable%601.HasValue%2A?displayProperty=nameWithType> は、Null 許容型のインスタンスに、基になる型の値が含まれるかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="e9599-117"><xref:System.Nullable%601.HasValue%2A?displayProperty=nameWithType> indicates whether an instance of a nullable type has a value of its underlying type.</span></span>

- <span data-ttu-id="e9599-118"><xref:System.Nullable%601.HasValue%2A> が `true` の場合、<xref:System.Nullable%601.Value%2A?displayProperty=nameWithType> は基になる型の値を取得します。</span><span class="sxs-lookup"><span data-stu-id="e9599-118"><xref:System.Nullable%601.Value%2A?displayProperty=nameWithType> gets the value of an underlying type if <xref:System.Nullable%601.HasValue%2A> is `true`.</span></span> <span data-ttu-id="e9599-119"><xref:System.Nullable%601.HasValue%2A> が `false` の場合、<xref:System.Nullable%601.Value%2A> プロパティは <xref:System.InvalidOperationException> をスローします。</span><span class="sxs-lookup"><span data-stu-id="e9599-119">If <xref:System.Nullable%601.HasValue%2A> is `false`, the <xref:System.Nullable%601.Value%2A> property throws an <xref:System.InvalidOperationException>.</span></span>

<span data-ttu-id="e9599-120">次の例のコードでは、`HasValue` プロパティを使用して、値を表示する前に変数に値が格納されているかどうかをテストします。</span><span class="sxs-lookup"><span data-stu-id="e9599-120">The code in the following example uses the `HasValue` property to test whether the variable contains a value before displaying it:</span></span>

[!code-csharp-interactive[use HasValue](../../../../samples/snippets/csharp/programming-guide/nullable-types/NullableTypesUsage.cs#2)]

<span data-ttu-id="e9599-121">次の例に示すように、`HasValue` プロパティを使用する代わりに、null 許容値型の変数を `null` と比較することもできます。</span><span class="sxs-lookup"><span data-stu-id="e9599-121">You also can compare a variable of a nullable value type with `null` instead of using the `HasValue` property, as the following example shows:</span></span>

[!code-csharp-interactive[use comparison with null](../../../../samples/snippets/csharp/programming-guide/nullable-types/NullableTypesUsage.cs#3)]

<span data-ttu-id="e9599-122">C# 7.0 以降では、[パターン マッチング](../../pattern-matching.md)を使用して null 許容値型の値を調べて取得することができます。</span><span class="sxs-lookup"><span data-stu-id="e9599-122">Beginning with C# 7.0, you can use [pattern matching](../../pattern-matching.md) to both examine and get a value of a nullable value type:</span></span>

[!code-csharp-interactive[use pattern matching](../../../../samples/snippets/csharp/programming-guide/nullable-types/NullableTypesUsage.cs#4)]

## <a name="conversion-from-a-nullable-value-type-to-an-underlying-type"></a><span data-ttu-id="e9599-123">null 許容値型から基になる型への変換</span><span class="sxs-lookup"><span data-stu-id="e9599-123">Conversion from a nullable value type to an underlying type</span></span>

<span data-ttu-id="e9599-124">null 許容値型の値を非 null 許容型に代入する必要がある場合は、[null 合体演算子 `??`](../../language-reference/operators/null-coalescing-operator.md) を使用して、null 許容値型の値が null の場合に代入される値を指定します (<xref:System.Nullable%601.GetValueOrDefault(%600)?displayProperty=nameWithType> メソッドを使用してこの操作を行うこともできます)。</span><span class="sxs-lookup"><span data-stu-id="e9599-124">If you need to assign a value of a nullable value type to a non-nullable type, use the [null-coalescing operator `??`](../../language-reference/operators/null-coalescing-operator.md) to specify the value to be assigned if a value of a nullable value type is null (you also can use the <xref:System.Nullable%601.GetValueOrDefault(%600)?displayProperty=nameWithType> method to do that):</span></span>

[!code-csharp-interactive[?? operator](../../../../samples/snippets/csharp/programming-guide/nullable-types/NullableTypesUsage.cs#5)]

<span data-ttu-id="e9599-125">null 許容値型の値が `null` の場合に使用される値を、基になる値型の既定値にする場合は、<xref:System.Nullable%601.GetValueOrDefault?displayProperty=nameWithType> メソッドを使用します。</span><span class="sxs-lookup"><span data-stu-id="e9599-125">Use the <xref:System.Nullable%601.GetValueOrDefault?displayProperty=nameWithType> method if the value to be used when a value of a nullable value type is `null` should be the default value of the underlying value type.</span></span>

<span data-ttu-id="e9599-126">null 許容値型を非 null 許容型に明示的にキャストすることができます。</span><span class="sxs-lookup"><span data-stu-id="e9599-126">You can explicitly cast a nullable value type to a non-nullable type.</span></span> <span data-ttu-id="e9599-127">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="e9599-127">For example:</span></span>

[!code-csharp[explicit cast](../../../../samples/snippets/csharp/programming-guide/nullable-types/NullableTypesUsage.cs#6)]

<span data-ttu-id="e9599-128">実行時に null 許容値型の値が `null` の場合は、明示的なキャストによって <xref:System.InvalidOperationException> がスローされます。</span><span class="sxs-lookup"><span data-stu-id="e9599-128">At run time, if the value of a nullable value type is `null`, the explicit cast throws an <xref:System.InvalidOperationException>.</span></span>

<span data-ttu-id="e9599-129">Null 非許容値型は、対応する Null 許容型に暗黙的に変換されます。</span><span class="sxs-lookup"><span data-stu-id="e9599-129">A non-nullable value type is implicitly converted to the corresponding nullable type.</span></span>

## <a name="operators"></a><span data-ttu-id="e9599-130">演算子</span><span class="sxs-lookup"><span data-stu-id="e9599-130">Operators</span></span>

<span data-ttu-id="e9599-131">値型向けに存在している定義済みの単項演算子、2 項演算子およびすべてのユーザー定義演算子は、対応する null 許容型でも使用できます。</span><span class="sxs-lookup"><span data-stu-id="e9599-131">The predefined unary and binary operators and any user-defined operators that exist for value types may also be used by corresponding nullable types.</span></span> <span data-ttu-id="e9599-132">これらの演算子では、1 つまたは両方のオペランドが `null` の場合は `null` が生成され、null 以外の場合は、含まれている値に基づいて結果が算出されます。</span><span class="sxs-lookup"><span data-stu-id="e9599-132">These operators produce `null` if one or both operands are `null`; otherwise, the operator uses the contained values to calculate the result.</span></span> <span data-ttu-id="e9599-133">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="e9599-133">For example:</span></span>

[!code-csharp[operators](../../../../samples/snippets/csharp/programming-guide/nullable-types/NullableTypesUsage.cs#7)]

> [!NOTE]
> <span data-ttu-id="e9599-134">`bool?` 型の場合、定義済みの `&` および `|` 演算子は、このセクションで説明されている規則に従わないことに注意してください。オペランドの 1 つが `null` の場合も、演算子の評価の結果は null 以外である可能性があります。</span><span class="sxs-lookup"><span data-stu-id="e9599-134">For the `bool?` type, the predefined `&` and `|` operators don't follow the rules described in this section: the result of an operator evaluation can be non-null even if one of the operands is `null`.</span></span> <span data-ttu-id="e9599-135">詳細については、「[Boolean logical operators (ブール論理演算子)](../../language-reference/operators/boolean-logical-operators.md)」記事の「[Nullable Boolean logical operators (null 許容論理演算子)](../../language-reference/operators/boolean-logical-operators.md#nullable-boolean-logical-operators)」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="e9599-135">For more information, see the [Nullable Boolean logical operators](../../language-reference/operators/boolean-logical-operators.md#nullable-boolean-logical-operators) section of the [Boolean logical operators](../../language-reference/operators/boolean-logical-operators.md) article.</span></span>
  
<span data-ttu-id="e9599-136">関係演算子 (`<`、`>`、`<=`、`>=`) では、1 つまたは両方のオペランドが `null` の場合、結果は `false` になります。</span><span class="sxs-lookup"><span data-stu-id="e9599-136">For the relational operators (`<`, `>`, `<=`, `>=`), if one or both operands are `null`, the result is `false`.</span></span> <span data-ttu-id="e9599-137">ある比較 (たとえば、`<=`) から返される結果が `false` であっても、逆の比較 (`>`) から返される結果が `true` であるとは限りません。</span><span class="sxs-lookup"><span data-stu-id="e9599-137">Do not assume that because a particular comparison (for example, `<=`) returns `false`, the opposite comparison (`>`) returns `true`.</span></span> <span data-ttu-id="e9599-138">次の例は、10 が</span><span class="sxs-lookup"><span data-stu-id="e9599-138">The following example shows that 10 is</span></span>

- <span data-ttu-id="e9599-139">`null` 以上ではなく、</span><span class="sxs-lookup"><span data-stu-id="e9599-139">neither greater than or equal to `null`,</span></span>
- <span data-ttu-id="e9599-140">`null` 未満でもないことを示します。</span><span class="sxs-lookup"><span data-stu-id="e9599-140">nor less than `null`.</span></span>

[!code-csharp-interactive[relational and equality operators](../../../../samples/snippets/csharp/programming-guide/nullable-types/NullableTypesUsage.cs#8)]

<span data-ttu-id="e9599-141">上記の例は、どちらも null である 2 つの null 許容値型を等価比較すると、結果が `true` と評価されることを示しています。</span><span class="sxs-lookup"><span data-stu-id="e9599-141">The above example also shows that an equality comparison of two nullable value types that are both null evaluates to `true`.</span></span>

<span data-ttu-id="e9599-142">詳細については、[C# 言語仕様](~/_csharplang/spec/introduction.md)に関するページの「[リフトされた演算子](~/_csharplang/spec/expressions.md#lifted-operators)」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="e9599-142">For more information, see the [Lifted operators](~/_csharplang/spec/expressions.md#lifted-operators) section of the [C# language specification](~/_csharplang/spec/introduction.md).</span></span>

## <a name="boxing-and-unboxing"></a><span data-ttu-id="e9599-143">ボックス化とボックス化解除</span><span class="sxs-lookup"><span data-stu-id="e9599-143">Boxing and unboxing</span></span>

<span data-ttu-id="e9599-144">Null 許容値型は、次の規則に従って[ボックス化](../types/boxing-and-unboxing.md)されます。</span><span class="sxs-lookup"><span data-stu-id="e9599-144">A nullable value type is [boxed](../types/boxing-and-unboxing.md) by the following rules:</span></span>

- <span data-ttu-id="e9599-145"><xref:System.Nullable%601.HasValue%2A> が `false` を返した場合は、null 参照が生成されます。</span><span class="sxs-lookup"><span data-stu-id="e9599-145">If <xref:System.Nullable%601.HasValue%2A> returns `false`, the null reference is produced.</span></span>
- <span data-ttu-id="e9599-146"><xref:System.Nullable%601.HasValue%2A> が `true` を返した場合は、<xref:System.Nullable%601> のインスタンスではなく、基になる値型 `T` の値がボックス化されます。</span><span class="sxs-lookup"><span data-stu-id="e9599-146">If <xref:System.Nullable%601.HasValue%2A> returns `true`, a value of the underlying value type `T` is boxed, not the instance of <xref:System.Nullable%601>.</span></span>

<span data-ttu-id="e9599-147">次の例に示すように、ボックス化された値型を、対応する Null 許容型にボックス化解除できます。</span><span class="sxs-lookup"><span data-stu-id="e9599-147">You can unbox the boxed value type to the corresponding nullable type, as the following example shows:</span></span>

[!code-csharp-interactive[boxing and unboxing](../../../../samples/snippets/csharp/programming-guide/nullable-types/NullableTypesUsage.cs#9)]

## <a name="see-also"></a><span data-ttu-id="e9599-148">関連項目</span><span class="sxs-lookup"><span data-stu-id="e9599-148">See also</span></span>

- [<span data-ttu-id="e9599-149">null 許容値型</span><span class="sxs-lookup"><span data-stu-id="e9599-149">Nullable value types</span></span>](index.md)
- [<span data-ttu-id="e9599-150">What Exactly Does 'Lifted' mean? ('Lifted' の正確な意味)</span><span class="sxs-lookup"><span data-stu-id="e9599-150">What exactly does 'lifted' mean?</span></span>](https://blogs.msdn.microsoft.com/ericlippert/2007/06/27/what-exactly-does-lifted-mean/)
