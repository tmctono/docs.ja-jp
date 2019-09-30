---
title: Null 許容値型 - C# プログラミング ガイド
ms.custom: seodec18
description: C# の Null 許容値型とその使用方法について説明します
ms.date: 09/26/2019
helpviewer_keywords:
- nullable value types [C#]
ms.assetid: e473cb01-28ca-42be-9cea-f717055d72c6
ms.openlocfilehash: b8b52e7fb34adf65d5c76d59811ea6dd0ab16a98
ms.sourcegitcommit: da2dd2772fcf32b44eb18b1cbe8affd17b1753c9
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/27/2019
ms.locfileid: "71396218"
---
# <a name="nullable-value-types-c-programming-guide"></a><span data-ttu-id="93573-103">Null 許容値型 (C# プログラミング ガイド)</span><span class="sxs-lookup"><span data-stu-id="93573-103">Nullable value types (C# Programming Guide)</span></span>

<span data-ttu-id="93573-104">Null 許容値型は、<xref:System.Nullable%601?displayProperty=nameWithType> 構造体のインスタンスです。</span><span class="sxs-lookup"><span data-stu-id="93573-104">Nullable value types are instances of the <xref:System.Nullable%601?displayProperty=nameWithType> structure.</span></span> <span data-ttu-id="93573-105">Null 許容値型は、基になる型 `T` のすべての値と、追加の [null](../../language-reference/keywords/null.md) 値を表すことができます。</span><span class="sxs-lookup"><span data-stu-id="93573-105">Nullable value types can represent all the values of an underlying type `T`, and an additional [null](../../language-reference/keywords/null.md) value.</span></span> <span data-ttu-id="93573-106">基になる型 `T` は Null 非許容のあらゆる[値の型](../../language-reference/keywords/value-types.md)にすることができます。</span><span class="sxs-lookup"><span data-stu-id="93573-106">The underlying type `T` can be any non-nullable [value type](../../language-reference/keywords/value-types.md).</span></span> <span data-ttu-id="93573-107">`T` を参照型にすることはできません。</span><span class="sxs-lookup"><span data-stu-id="93573-107">`T` cannot be a reference type.</span></span>

> [!NOTE]
> <span data-ttu-id="93573-108">C# 8.0 で、Null 許容参照型機能が導入されました。</span><span class="sxs-lookup"><span data-stu-id="93573-108">C# 8.0 introduces the nullable reference types feature.</span></span> <span data-ttu-id="93573-109">詳細については、「[null 許容参照型](../../nullable-references.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="93573-109">For more information, see [Nullable reference types](../../nullable-references.md).</span></span> <span data-ttu-id="93573-110">Null 許容値型は、C# 2 から使用できます。</span><span class="sxs-lookup"><span data-stu-id="93573-110">The nullable value types are available starting with C# 2.</span></span>

<span data-ttu-id="93573-111">たとえば、`null` または <xref:System.Int32.MinValue?displayProperty=nameWithType> から <xref:System.Int32.MaxValue?displayProperty=nameWithType> のいずれかの整数値を `Nullable<int>` および [true](../../language-reference/keywords/true-literal.md)、[false](../../language-reference/keywords/false-literal.md) に、または `null` を `Nullable<bool>` に割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="93573-111">For example, you can assign `null` or any integer value from <xref:System.Int32.MinValue?displayProperty=nameWithType> to <xref:System.Int32.MaxValue?displayProperty=nameWithType> to a `Nullable<int>` and [true](../../language-reference/keywords/true-literal.md), [false](../../language-reference/keywords/false-literal.md), or `null` to a `Nullable<bool>`.</span></span>

<span data-ttu-id="93573-112">Null 許容値型は基になる型の未定義の値を表す必要があるときに使用します。</span><span class="sxs-lookup"><span data-stu-id="93573-112">You use a nullable value type when you need to represent the undefined value of an underlying type.</span></span> <span data-ttu-id="93573-113">ブール値変数は `true` と `false` の 2 つの値しか持つことができません。</span><span class="sxs-lookup"><span data-stu-id="93573-113">A Boolean variable can have only two values: `true` and `false`.</span></span> <span data-ttu-id="93573-114">"未定義の" 値はありません。</span><span class="sxs-lookup"><span data-stu-id="93573-114">There is no "undefined" value.</span></span> <span data-ttu-id="93573-115">多くのプログラミング アプリケーションの中でも特にデータベース操作では、変数値が未定義か、ない場合があります。</span><span class="sxs-lookup"><span data-stu-id="93573-115">In many programming applications, most notably database interactions, a variable value can be undefined or missing.</span></span> <span data-ttu-id="93573-116">たとえば、データベース フィールドには、true や false の値が入力されている場合や、値がまったく入力されていない場合があります。</span><span class="sxs-lookup"><span data-stu-id="93573-116">For example, a field in a database may contain the values true or false, or it may contain no value at all.</span></span> <span data-ttu-id="93573-117">その場合は、`Nullable<bool>` 型を使用します。</span><span class="sxs-lookup"><span data-stu-id="93573-117">You use a `Nullable<bool>` type in that case.</span></span>

<span data-ttu-id="93573-118">Null 許容値型には次の特性があります。</span><span class="sxs-lookup"><span data-stu-id="93573-118">Nullable value types have the following characteristics:</span></span>

- <span data-ttu-id="93573-119">Null 許容値型は、`null` 値を割り当てることができる、値型の変数を表します。</span><span class="sxs-lookup"><span data-stu-id="93573-119">Nullable value types represent value-type variables that can be assigned the `null` value.</span></span>

- <span data-ttu-id="93573-120">構文 `T?` は `Nullable<T>` の短縮形です。</span><span class="sxs-lookup"><span data-stu-id="93573-120">The syntax `T?` is shorthand for `Nullable<T>`.</span></span> <span data-ttu-id="93573-121">この 2 つの形式は同義であり、どちらでも使用できます。</span><span class="sxs-lookup"><span data-stu-id="93573-121">The two forms are interchangeable.</span></span>

- <span data-ttu-id="93573-122">Null 許容値型に値を割り当てる方法は、基になる値の型の場合と同じです。たとえば、`int? x = 10;` や `double? d = 4.108;` と指定します。</span><span class="sxs-lookup"><span data-stu-id="93573-122">Assign a value to a nullable value type just as you would for an underlying value type: `int? x = 10;` or `double? d = 4.108;`.</span></span> <span data-ttu-id="93573-123">`null` 値を `int? x = null;` のように割り当てることもできます。</span><span class="sxs-lookup"><span data-stu-id="93573-123">You also can assign the `null` value: `int? x = null;`.</span></span>

- <span data-ttu-id="93573-124">null かどうかを確認して値を取得するには、<xref:System.Nullable%601.HasValue%2A?displayProperty=nameWithType> と <xref:System.Nullable%601.Value%2A?displayProperty=nameWithType> の読み取り専用プロパティを使用します。たとえば、`if (x.HasValue) y = x.Value;` と指定します。</span><span class="sxs-lookup"><span data-stu-id="93573-124">Use the <xref:System.Nullable%601.HasValue%2A?displayProperty=nameWithType> and <xref:System.Nullable%601.Value%2A?displayProperty=nameWithType> readonly properties to test for null and retrieve the value, as shown in the following example: `if (x.HasValue) y = x.Value;`</span></span>

  - <span data-ttu-id="93573-125"><xref:System.Nullable%601.HasValue%2A> プロパティは、変数に値が含まれる場合は `true` を返し、`null` の場合は `false` を返します。</span><span class="sxs-lookup"><span data-stu-id="93573-125">The <xref:System.Nullable%601.HasValue%2A> property returns `true` if the variable contains a value, or `false` if it's `null`.</span></span>

  - <span data-ttu-id="93573-126"><xref:System.Nullable%601.Value%2A> プロパティは、<xref:System.Nullable%601.HasValue%2A> で `true` が返される場合に値を返します。</span><span class="sxs-lookup"><span data-stu-id="93573-126">The <xref:System.Nullable%601.Value%2A> property returns a value if <xref:System.Nullable%601.HasValue%2A> returns `true`.</span></span> <span data-ttu-id="93573-127">それ以外の場合は、<xref:System.InvalidOperationException> がスローされます。</span><span class="sxs-lookup"><span data-stu-id="93573-127">Otherwise, an <xref:System.InvalidOperationException> is thrown.</span></span>

- <span data-ttu-id="93573-128">Null 許容値型では `==` 演算子と `!=` 演算子も使用できます。たとえば、`if (x != null) y = x.Value;` のように指定します。</span><span class="sxs-lookup"><span data-stu-id="93573-128">You can also use the `==` and `!=` operators with a nullable value type, as shown in the following example: `if (x != null) y = x.Value;`.</span></span> <span data-ttu-id="93573-129">`a` と `b` の両方が null の場合、`a == b` は `true` と評価されます。</span><span class="sxs-lookup"><span data-stu-id="93573-129">If `a` and `b` are both null, `a == b` evaluates to `true`.</span></span>

- <span data-ttu-id="93573-130">C# 7.0 以降では、[パターン マッチング](../../pattern-matching.md#the-is-type-pattern-expression)を使用して Null 許容型の値を調べて取得することができます (`if (x is int valueOfX) y = valueOfX;`)。</span><span class="sxs-lookup"><span data-stu-id="93573-130">Beginning with C# 7.0, you can use [pattern matching](../../pattern-matching.md#the-is-type-pattern-expression) to both examine and get a value of a nullable type: `if (x is int valueOfX) y = valueOfX;`.</span></span>

- <span data-ttu-id="93573-131">`T?` の既定値は <xref:System.Nullable%601.HasValue%2A> プロパティが `false` を返すインスタンスです。</span><span class="sxs-lookup"><span data-stu-id="93573-131">The default value of `T?` is an instance whose <xref:System.Nullable%601.HasValue%2A> property returns `false`.</span></span>

- <span data-ttu-id="93573-132">Null 許容型の値が `null` である場合に、基になる値の型の割り当てられた値、または[既定](../../language-reference/keywords/default-values-table.md)値のどちらかを返すには、<xref:System.Nullable%601.GetValueOrDefault> メソッドを使用します。</span><span class="sxs-lookup"><span data-stu-id="93573-132">Use the <xref:System.Nullable%601.GetValueOrDefault> method to return either the assigned value, or the [default](../../language-reference/keywords/default-values-table.md) value of the underlying value type if the value of the nullable type is `null`.</span></span>

- <span data-ttu-id="93573-133">Null 許容型の値が `null` である場合に、割り当てられた値、または指定された既定値のどちらかを返すには、<xref:System.Nullable%601.GetValueOrDefault(%600)> メソッドを使用します。</span><span class="sxs-lookup"><span data-stu-id="93573-133">Use the <xref:System.Nullable%601.GetValueOrDefault(%600)> method to return either the assigned value, or the provided default value if the value of the nullable type is `null`.</span></span>

- <span data-ttu-id="93573-134">Null 許容型の値に基づいて基になる値の型の変数に値を割り当てるには、[Null 合体演算子](../../language-reference/operators/null-coalescing-operator.md) `??` を使用します (例: `int? x = null; int y = x ?? -1;`)。</span><span class="sxs-lookup"><span data-stu-id="93573-134">Use the [null-coalescing operator](../../language-reference/operators/null-coalescing-operator.md), `??`, to assign a value to a variable of an underlying value type based on a nullable-type value: `int? x = null; int y = x ?? -1;`.</span></span> <span data-ttu-id="93573-135">例では、`x` が `null` であるため、`y` の結果値は `-1` です。</span><span class="sxs-lookup"><span data-stu-id="93573-135">In the example, since `x` is `null`, the result value of `y` is `-1`.</span></span>

- <span data-ttu-id="93573-136">2 つの値の型の間でユーザー定義の変換を定義している場合は、それに対応する null 許容型で同じ変換を使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="93573-136">If a user-defined conversion is defined between two value types, the same conversion can also be used with the corresponding nullable types.</span></span>

- <span data-ttu-id="93573-137">入れ子になった Null 許容値型は許可されません。</span><span class="sxs-lookup"><span data-stu-id="93573-137">Nested nullable value types are not allowed.</span></span> <span data-ttu-id="93573-138">次の行はコンパイルされません。`Nullable<Nullable<int>> n;`</span><span class="sxs-lookup"><span data-stu-id="93573-138">The following line doesn't compile: `Nullable<Nullable<int>> n;`</span></span>

<span data-ttu-id="93573-139">詳細については、「[Null 許容値型の使用 (C# プログラミング ガイド)](using-nullable-types.md)」と「[方法: Null 許容値型を識別する (C# プログラミング ガイド)](how-to-identify-a-nullable-type.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="93573-139">For more information, see the [Using nullable value types](using-nullable-types.md) and [How to: identify a nullable value type](how-to-identify-a-nullable-type.md) topics.</span></span>

## <a name="see-also"></a><span data-ttu-id="93573-140">関連項目</span><span class="sxs-lookup"><span data-stu-id="93573-140">See also</span></span>

- [<span data-ttu-id="93573-141">C# プログラミング ガイド</span><span class="sxs-lookup"><span data-stu-id="93573-141">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="93573-142">??演算子</span><span class="sxs-lookup"><span data-stu-id="93573-142">?? Operator</span></span>](../../language-reference/operators/null-coalescing-operator.md)
- [<span data-ttu-id="93573-143">null 許容値型 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="93573-143">Nullable Value Types (Visual Basic)</span></span>](../../../visual-basic/programming-guide/language-features/data-types/nullable-value-types.md)
- <xref:System.Nullable%601?displayProperty=nameWithType>
- <xref:System.Nullable?displayProperty=nameWithType>
