---
title: 型テストとキャスト演算子 - C# リファレンス
description: 式の結果の型を確認し、必要に応じて別の型に変換することができる、C# の演算子について説明します。
ms.date: 06/21/2019
author: pkulikov
f1_keywords:
- is_CSharpKeyword
- as_CSharpKeyword
- ()_CSharpKeyword
- typeof_CSharpKeyword
helpviewer_keywords:
- type-testing operators [C#]
- conversion operators [C#]
- type conversion [C#]
- is operator [C#]
- as operator [C#]
- cast operator [C#]
- cast expression [C#]
- () operator [C#]
- typeof operator [C#]
ms.openlocfilehash: 037ddc8eeda418b2e4858ab98be6cd362ca0e1e2
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/14/2020
ms.locfileid: "79398173"
---
# <a name="type-testing-and-cast-operators-c-reference"></a><span data-ttu-id="7b9f0-103">型テストとキャスト演算子 (C# リファレンス)</span><span class="sxs-lookup"><span data-stu-id="7b9f0-103">Type-testing and cast operators (C# reference)</span></span>

<span data-ttu-id="7b9f0-104">次の演算子を使って、型のチェックまたは型の変換を実行できます。</span><span class="sxs-lookup"><span data-stu-id="7b9f0-104">You can use the following operators to perform type checking or type conversion:</span></span>

- <span data-ttu-id="7b9f0-105">[is 演算子](#is-operator): 式のランタイム型と指定された型の間に互換性があるかどうかを確認します</span><span class="sxs-lookup"><span data-stu-id="7b9f0-105">[is operator](#is-operator): to check if the runtime type of an expression is compatible with a given type</span></span>
- <span data-ttu-id="7b9f0-106">[as 演算子](#as-operator): 式のランタイム型と指定された型の間に互換性がある場合、式を指定された型に明示的に変換します</span><span class="sxs-lookup"><span data-stu-id="7b9f0-106">[as operator](#as-operator): to explicitly convert an expression to a given type if its runtime type is compatible with that type</span></span>
- <span data-ttu-id="7b9f0-107">[キャスト演算子 ()](#cast-operator-): 明示的な変換を実行します</span><span class="sxs-lookup"><span data-stu-id="7b9f0-107">[cast operator ()](#cast-operator-): to perform an explicit conversion</span></span>
- <span data-ttu-id="7b9f0-108">[typeof 演算子](#typeof-operator): 型の <xref:System.Type?displayProperty=nameWithType> インスタンスを取得します</span><span class="sxs-lookup"><span data-stu-id="7b9f0-108">[typeof operator](#typeof-operator): to obtain the <xref:System.Type?displayProperty=nameWithType> instance for a type</span></span>

## <a name="is-operator"></a><span data-ttu-id="7b9f0-109">is 演算子</span><span class="sxs-lookup"><span data-stu-id="7b9f0-109">is operator</span></span>

<span data-ttu-id="7b9f0-110">`is` 演算子では、式の結果のランタイム型と指定された型の間に互換性があるかどうかが調べられます。</span><span class="sxs-lookup"><span data-stu-id="7b9f0-110">The `is` operator checks if the runtime type of an expression result is compatible with a given type.</span></span> <span data-ttu-id="7b9f0-111">C# 7.0 以降の `is` 演算子では、パターンに対する式の結果のテストも行われます。</span><span class="sxs-lookup"><span data-stu-id="7b9f0-111">Beginning with C# 7.0, the `is` operator also tests an expression result against a pattern.</span></span>

<span data-ttu-id="7b9f0-112">`is` 型テスト演算子を使用する式の形式は次のとおりです</span><span class="sxs-lookup"><span data-stu-id="7b9f0-112">The expression with the type-testing `is` operator has the following form</span></span>

```csharp
E is T
```

<span data-ttu-id="7b9f0-113">`E` は値を返す式であり、`T` は型または型パラメーターの名前です。</span><span class="sxs-lookup"><span data-stu-id="7b9f0-113">where `E` is an expression that returns a value and `T` is the name of a type or a type parameter.</span></span> <span data-ttu-id="7b9f0-114">`E` を匿名メソッドまたはラムダ式にすることはできません。</span><span class="sxs-lookup"><span data-stu-id="7b9f0-114">`E` cannot be an anonymous method or a lambda expression.</span></span>

<span data-ttu-id="7b9f0-115">式 `E is T` では、`true` の結果が null ではなく、参照変換、ボックス化変換、またはボックス化解除変換によって型 `E` に変換できる場合は `T` が返され、それ以外の場合は `false` が返されます。</span><span class="sxs-lookup"><span data-stu-id="7b9f0-115">The `E is T` expression returns `true` if the result of `E` is non-null and can be converted to type `T` by a reference conversion, a boxing conversion, or an unboxing conversion; otherwise, it returns `false`.</span></span> <span data-ttu-id="7b9f0-116">`is` 演算子では、ユーザー定義変換は考慮されません。</span><span class="sxs-lookup"><span data-stu-id="7b9f0-116">The `is` operator doesn't consider user-defined conversions.</span></span>

<span data-ttu-id="7b9f0-117">次の例で示す `is` 演算子では、式の結果のランタイム型が指定された型から派生する場合、つまり型の間に参照変換が存在する場合は、`true` が返されます。</span><span class="sxs-lookup"><span data-stu-id="7b9f0-117">The following example demonstrates that the `is` operator returns `true` if the runtime type of an expression result derives from a given type, that is, there exists a reference conversion between types:</span></span>

[!code-csharp[is with reference conversion](snippets/TypeTestingAndConversionOperators.cs#IsWithReferenceConversion)]

<span data-ttu-id="7b9f0-118">次の例で示す `is` 演算子では、ボックス化変換とボックス化解除変換は考慮されますが、[数値変換](../builtin-types/numeric-conversions.md)は考慮されません。</span><span class="sxs-lookup"><span data-stu-id="7b9f0-118">The next example shows that the `is` operator takes into account boxing and unboxing conversions but doesn't consider [numeric conversions](../builtin-types/numeric-conversions.md):</span></span>

[!code-csharp-interactive[is with int](snippets/TypeTestingAndConversionOperators.cs#IsWithInt)]

<span data-ttu-id="7b9f0-119">C# の変換については、[C# 言語仕様](~/_csharplang/spec/conversions.md)の「[Conversions (変換)](~/_csharplang/spec/introduction.md)」の章をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="7b9f0-119">For information about C# conversions, see the [Conversions](~/_csharplang/spec/conversions.md) chapter of the [C# language specification](~/_csharplang/spec/introduction.md).</span></span>

### <a name="type-testing-with-pattern-matching"></a><span data-ttu-id="7b9f0-120">パターン マッチングを使用する型テスト</span><span class="sxs-lookup"><span data-stu-id="7b9f0-120">Type testing with pattern matching</span></span>

<span data-ttu-id="7b9f0-121">C# 7.0 以降の `is` 演算子では、パターンに対する式の結果のテストも行われます。</span><span class="sxs-lookup"><span data-stu-id="7b9f0-121">Beginning with C# 7.0, the `is` operator also tests an expression result against a pattern.</span></span> <span data-ttu-id="7b9f0-122">具体的には、次の形式の型パターンがサポートされます。</span><span class="sxs-lookup"><span data-stu-id="7b9f0-122">In particular, it supports the type pattern in the following form:</span></span>

```csharp
E is T v
```

<span data-ttu-id="7b9f0-123">`E` は値を返す式、`T` は型または型パラメーターの名前、`v` は `T` 型の新しいローカル変数です。</span><span class="sxs-lookup"><span data-stu-id="7b9f0-123">where `E` is an expression that returns a value, `T` is the name of a type or a type parameter, and `v` is a new local variable of type `T`.</span></span> <span data-ttu-id="7b9f0-124">`E` の結果が null ではなく、参照変換、ボックス化変換、またはボックス化解除変換によって `T` に変換できる場合、式 `E is T v` から `true` が返され、`E` の結果の変換された値が変数 `v` に代入されます。</span><span class="sxs-lookup"><span data-stu-id="7b9f0-124">If the result of `E` is non-null and can be converted to `T` by a reference, boxing, or unboxing conversion, the `E is T v` expression returns `true` and the converted value of the result of `E` is assigned to variable `v`.</span></span>

<span data-ttu-id="7b9f0-125">次の例では、型パターンによる `is` 演算子の使用方法を示します。</span><span class="sxs-lookup"><span data-stu-id="7b9f0-125">The following example demonstrates the usage of the `is` operator with the type pattern:</span></span>

[!code-csharp-interactive[is with type pattern](snippets/TypeTestingAndConversionOperators.cs#IsTypePattern)]

<span data-ttu-id="7b9f0-126">型パターンおよび他のサポートされるパターンについて詳しくは、「[is を使用したパターン マッチング](../keywords/is.md#pattern-matching-with-is)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="7b9f0-126">For more information about the type pattern and other supported patterns, see [Pattern matching with is](../keywords/is.md#pattern-matching-with-is).</span></span>

## <a name="as-operator"></a><span data-ttu-id="7b9f0-127">as 演算子</span><span class="sxs-lookup"><span data-stu-id="7b9f0-127">as operator</span></span>

<span data-ttu-id="7b9f0-128">`as` 演算子では、式の結果が、指定された参照型または null 許容値型に明示的に変換されます。</span><span class="sxs-lookup"><span data-stu-id="7b9f0-128">The `as` operator explicitly converts the result of an expression to a given reference or nullable value type.</span></span> <span data-ttu-id="7b9f0-129">変換できない場合、`as` 演算子からは `null` が返されます。</span><span class="sxs-lookup"><span data-stu-id="7b9f0-129">If the conversion is not possible, the `as` operator returns `null`.</span></span> <span data-ttu-id="7b9f0-130">[キャスト演算子 ()](#cast-operator-) とは異なり、`as` 演算子では例外はスローされません。</span><span class="sxs-lookup"><span data-stu-id="7b9f0-130">Unlike the [cast operator ()](#cast-operator-), the `as` operator never throws an exception.</span></span>

<span data-ttu-id="7b9f0-131">式の形式は次のとおりです</span><span class="sxs-lookup"><span data-stu-id="7b9f0-131">The expression of the form</span></span>

```csharp
E as T
```

<span data-ttu-id="7b9f0-132">`E` は値を返す式であり、`T` は型または型パラメーターの名前です。次の式と同じ結果が生成されます</span><span class="sxs-lookup"><span data-stu-id="7b9f0-132">where `E` is an expression that returns a value and `T` is the name of a type or a type parameter, produces the same result as</span></span>

```csharp
E is T ? (T)(E) : (T)null
```

<span data-ttu-id="7b9f0-133">ただし、`E` が評価されるのは 1 回だけです。</span><span class="sxs-lookup"><span data-stu-id="7b9f0-133">except that `E` is only evaluated once.</span></span>

<span data-ttu-id="7b9f0-134">`as` 演算子では、参照、null 許容、ボックス化、およびボックス化解除の各変換だけが考慮されます。</span><span class="sxs-lookup"><span data-stu-id="7b9f0-134">The `as` operator considers only reference, nullable, boxing, and unboxing conversions.</span></span> <span data-ttu-id="7b9f0-135">`as` 演算子を使って、ユーザー定義の変換を実行することはできません。</span><span class="sxs-lookup"><span data-stu-id="7b9f0-135">You cannot use the `as` operator to perform a user-defined conversion.</span></span> <span data-ttu-id="7b9f0-136">それを行うには、[キャスト演算子 ()](#cast-operator-) を使います。</span><span class="sxs-lookup"><span data-stu-id="7b9f0-136">To do that, use the [cast operator ()](#cast-operator-).</span></span>

<span data-ttu-id="7b9f0-137">`as` 演算子の使用例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="7b9f0-137">The following example demonstrates the usage of the `as` operator:</span></span>

[!code-csharp-interactive[as operator](snippets/TypeTestingAndConversionOperators.cs#AsOperator)]

> [!NOTE]
> <span data-ttu-id="7b9f0-138">上の例のように、変換が成功したかどうかを確認するには、`as` 式の結果を `null` と比較する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7b9f0-138">As the preceding example shows, you need to compare the result of the `as` expression with `null` to check if the conversion is successful.</span></span> <span data-ttu-id="7b9f0-139">C# 7.0 以降では、変換が成功するかどうかのテストと、成功する場合の新しい変数への結果の代入の両方を、[is 演算子](#type-testing-with-pattern-matching)を使って行うことができます。</span><span class="sxs-lookup"><span data-stu-id="7b9f0-139">Beginning with C# 7.0, you can use the [is operator](#type-testing-with-pattern-matching) both to test if the conversion succeeds and, if it succeeds, assign its result to a new variable.</span></span>

## <a name="cast-operator-"></a><span data-ttu-id="7b9f0-140">キャスト演算子 ()</span><span class="sxs-lookup"><span data-stu-id="7b9f0-140">Cast operator ()</span></span>

<span data-ttu-id="7b9f0-141">`(T)E` という形式のキャスト式では、式 `E` の結果が、型 `T` に明示的に変換されます。</span><span class="sxs-lookup"><span data-stu-id="7b9f0-141">A cast expression of the form `(T)E` performs an explicit conversion of the result of expression `E` to type `T`.</span></span> <span data-ttu-id="7b9f0-142">型 `E` から型 `T` への明示的な変換が存在しない場合は、コンパイル時エラーが発生します。</span><span class="sxs-lookup"><span data-stu-id="7b9f0-142">If no explicit conversion exists from the type of `E` to type `T`, a compile-time error occurs.</span></span> <span data-ttu-id="7b9f0-143">実行時に、明示的な変換が成功せず、キャスト式で例外がスローされる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="7b9f0-143">At run time, an explicit conversion might not succeed and a cast expression might throw an exception.</span></span>

<span data-ttu-id="7b9f0-144">次の例では、数値と参照の明示的な変換を示します。</span><span class="sxs-lookup"><span data-stu-id="7b9f0-144">The following example demonstrates explicit numeric and reference conversions:</span></span>

[!code-csharp-interactive[cast expression](snippets/TypeTestingAndConversionOperators.cs#Cast)]

<span data-ttu-id="7b9f0-145">サポートされる明示的な変換については、[C# 言語仕様](~/_csharplang/spec/conversions.md#explicit-conversions)の「[Explicit conversions (明示的な変換)](~/_csharplang/spec/introduction.md)」セクションをご覧ください。</span><span class="sxs-lookup"><span data-stu-id="7b9f0-145">For information about supported explicit conversions, see the [Explicit conversions](~/_csharplang/spec/conversions.md#explicit-conversions) section of the [C# language specification](~/_csharplang/spec/introduction.md).</span></span> <span data-ttu-id="7b9f0-146">カスタムの明示的または暗黙的な型変換を定義する方法については、「[User-defined conversion operators](user-defined-conversion-operators.md)」(ユーザー定義の変換演算子) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7b9f0-146">For information about how to define a custom explicit or implicit type conversion, see [User-defined conversion operators](user-defined-conversion-operators.md).</span></span>

### <a name="other-usages-of-"></a><span data-ttu-id="7b9f0-147">() の他の使用方法</span><span class="sxs-lookup"><span data-stu-id="7b9f0-147">Other usages of ()</span></span>

<span data-ttu-id="7b9f0-148">かっこは、[メソッドまたはデリゲートを呼び出すとき](member-access-operators.md#invocation-operator-)にも使います。</span><span class="sxs-lookup"><span data-stu-id="7b9f0-148">You also use parentheses to [call a method or invoke a delegate](member-access-operators.md#invocation-operator-).</span></span>

<span data-ttu-id="7b9f0-149">他には、式に含まれる演算を評価する順序を調整する場合にもかっこを使います。</span><span class="sxs-lookup"><span data-stu-id="7b9f0-149">Other use of parentheses is to adjust the order in which to evaluate operations in an expression.</span></span> <span data-ttu-id="7b9f0-150">詳細については、[C# 演算子](index.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="7b9f0-150">For more information, see [C# operators](index.md).</span></span>

## <a name="typeof-operator"></a><span data-ttu-id="7b9f0-151">typeof 演算子</span><span class="sxs-lookup"><span data-stu-id="7b9f0-151">typeof operator</span></span>

<span data-ttu-id="7b9f0-152">`typeof` 演算子では、型の <xref:System.Type?displayProperty=nameWithType> インスタンスが取得されます。</span><span class="sxs-lookup"><span data-stu-id="7b9f0-152">The `typeof` operator obtains the <xref:System.Type?displayProperty=nameWithType> instance for a type.</span></span> <span data-ttu-id="7b9f0-153">`typeof` 演算子への引数では、次の例で示すように、型または型パラメーターの名前を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7b9f0-153">The argument to the `typeof` operator must be the name of a type or a type parameter, as the following example shows:</span></span>

[!code-csharp-interactive[typeof operator](snippets/TypeTestingAndConversionOperators.cs#TypeOf)]

<span data-ttu-id="7b9f0-154">バインドされていないジェネリック型で `typeof` 演算子を使うこともできます。</span><span class="sxs-lookup"><span data-stu-id="7b9f0-154">You also can use the `typeof` operator with unbound generic types.</span></span> <span data-ttu-id="7b9f0-155">バインドされていないジェネリック型の名前には、適切な数のコンマが含まれる必要があります。これは、型パラメーターの数より 1 だけ少ない数です。</span><span class="sxs-lookup"><span data-stu-id="7b9f0-155">The name of an unbound generic type must contain the appropriate number of commas, which is one less than the number of type parameters.</span></span> <span data-ttu-id="7b9f0-156">次の例では、バインドされていないジェネリック型での `typeof` 演算子の使用方法を示します。</span><span class="sxs-lookup"><span data-stu-id="7b9f0-156">The following example shows the usage of the `typeof` operator with an unbound generic type:</span></span>

[!code-csharp-interactive[typeof unbound generic](snippets/TypeTestingAndConversionOperators.cs#TypeOfUnboundGeneric)]

<span data-ttu-id="7b9f0-157">式を `typeof` 演算子の引数にすることはできません。</span><span class="sxs-lookup"><span data-stu-id="7b9f0-157">An expression cannot be an argument of the `typeof` operator.</span></span> <span data-ttu-id="7b9f0-158">式の結果のランタイム型に対する <xref:System.Type?displayProperty=nameWithType> インスタンスを取得するには、<xref:System.Object.GetType%2A?displayProperty=nameWithType> メソッドを使います。</span><span class="sxs-lookup"><span data-stu-id="7b9f0-158">To get the <xref:System.Type?displayProperty=nameWithType> instance for the runtime type of an expression result, use the <xref:System.Object.GetType%2A?displayProperty=nameWithType> method.</span></span>

### <a name="type-testing-with-the-typeof-operator"></a><span data-ttu-id="7b9f0-159">`typeof` 演算子での型テスト</span><span class="sxs-lookup"><span data-stu-id="7b9f0-159">Type testing with the `typeof` operator</span></span>

<span data-ttu-id="7b9f0-160">`typeof` 演算子を使って、式の結果のランタイム型が指定された型と完全に一致するかどうかを調べます。</span><span class="sxs-lookup"><span data-stu-id="7b9f0-160">Use the `typeof` operator to check if the runtime type of the expression result exactly matches a given type.</span></span> <span data-ttu-id="7b9f0-161">次の例では、`typeof` 演算子と [is 演算子](#is-operator)で実行される型チェックの違いを示します。</span><span class="sxs-lookup"><span data-stu-id="7b9f0-161">The following example demonstrates the difference between type checking performed with the `typeof` operator and the [is operator](#is-operator):</span></span>

[!code-csharp[typeof vs is](snippets/TypeTestingAndConversionOperators.cs#TypeCheckWithTypeOf)]

## <a name="operator-overloadability"></a><span data-ttu-id="7b9f0-162">演算子のオーバーロード可/不可</span><span class="sxs-lookup"><span data-stu-id="7b9f0-162">Operator overloadability</span></span>

<span data-ttu-id="7b9f0-163">`is`、`as`、および `typeof` の各演算子はオーバーロードできません。</span><span class="sxs-lookup"><span data-stu-id="7b9f0-163">The `is`, `as`, and `typeof` operators cannot be overloaded.</span></span>

<span data-ttu-id="7b9f0-164">ユーザー定義型で `()` 演算子をオーバーロードすることはできませんが、キャスト式で実行できるカスタム型変換を定義することはできます。</span><span class="sxs-lookup"><span data-stu-id="7b9f0-164">A user-defined type cannot overload the `()` operator, but can define custom type conversions that can be performed by a cast expression.</span></span> <span data-ttu-id="7b9f0-165">詳細については、[ユーザー定義の変換演算子](user-defined-conversion-operators.md) に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="7b9f0-165">For more information, see [User-defined conversion operators](user-defined-conversion-operators.md).</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="7b9f0-166">C# 言語仕様</span><span class="sxs-lookup"><span data-stu-id="7b9f0-166">C# language specification</span></span>

<span data-ttu-id="7b9f0-167">詳細については、「[C# 言語仕様](~/_csharplang/spec/introduction.md)」の次のセクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="7b9f0-167">For more information, see the following sections of the [C# language specification](~/_csharplang/spec/introduction.md):</span></span>

- [<span data-ttu-id="7b9f0-168">is 演算子</span><span class="sxs-lookup"><span data-stu-id="7b9f0-168">The is operator</span></span>](~/_csharplang/spec/expressions.md#the-is-operator)
- [<span data-ttu-id="7b9f0-169">as 演算子</span><span class="sxs-lookup"><span data-stu-id="7b9f0-169">The as operator</span></span>](~/_csharplang/spec/expressions.md#the-as-operator)
- [<span data-ttu-id="7b9f0-170">キャスト式</span><span class="sxs-lookup"><span data-stu-id="7b9f0-170">Cast expressions</span></span>](~/_csharplang/spec/expressions.md#cast-expressions)
- [<span data-ttu-id="7b9f0-171">typeof 演算子</span><span class="sxs-lookup"><span data-stu-id="7b9f0-171">The typeof operator</span></span>](~/_csharplang/spec/expressions.md#the-typeof-operator)

## <a name="see-also"></a><span data-ttu-id="7b9f0-172">参照</span><span class="sxs-lookup"><span data-stu-id="7b9f0-172">See also</span></span>

- [<span data-ttu-id="7b9f0-173">C# リファレンス</span><span class="sxs-lookup"><span data-stu-id="7b9f0-173">C# reference</span></span>](../index.md)
- [<span data-ttu-id="7b9f0-174">C# 演算子</span><span class="sxs-lookup"><span data-stu-id="7b9f0-174">C# operators</span></span>](index.md)
- [<span data-ttu-id="7b9f0-175">パターン マッチング、is 演算子、as 演算子を使用して安全にキャストする方法</span><span class="sxs-lookup"><span data-stu-id="7b9f0-175">How to safely cast by using pattern matching and the is and as operators</span></span>](../../how-to/safely-cast-using-pattern-matching-is-and-as-operators.md)
- [<span data-ttu-id="7b9f0-176">.NET のジェネリック</span><span class="sxs-lookup"><span data-stu-id="7b9f0-176">Generics in .NET</span></span>](../../../standard/generics/index.md)
