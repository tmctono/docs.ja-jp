---
description: '?: 演算子 - C# リファレンス'
title: '?: 演算子 - C# リファレンス'
ms.date: 09/17/2020
f1_keywords:
- ?:_CSharpKeyword
- ?_CSharpKeyword
- :_CSharpKeyword
helpviewer_keywords:
- '?: operator [C#]'
- conditional operator (?:) [C#]
ms.assetid: e83a17f1-7500-48ba-8bee-2fbc4c847af4
ms.openlocfilehash: b6add045983619169bed0cd9f32eb27dba0a0338
ms.sourcegitcommit: a8730298170b8d96b4272e0c3dfc9819c606947b
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/17/2020
ms.locfileid: "90738880"
---
# <a name="-operator-c-reference"></a><span data-ttu-id="bd59a-103">?: 演算子 (C# リファレンス)</span><span class="sxs-lookup"><span data-stu-id="bd59a-103">?: operator (C# reference)</span></span>

<span data-ttu-id="bd59a-104">条件演算子 `?:` は、三項条件演算子とも呼ばれ、ブール式を評価し、ブール式の評価結果 (`true` または `false`) に応じて、2 つの式のいずれかの結果を返します。</span><span class="sxs-lookup"><span data-stu-id="bd59a-104">The conditional operator `?:`, also known as the ternary conditional operator, evaluates a Boolean expression and returns the result of one of the two expressions, depending on whether the Boolean expression evaluates to `true` or `false`.</span></span>

<span data-ttu-id="bd59a-105">この条件演算子の構文は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="bd59a-105">The syntax for the conditional operator is as follows:</span></span>

```csharp
condition ? consequent : alternative
```

<span data-ttu-id="bd59a-106">`condition` 式は `true` または `false` と評価する必要があります。</span><span class="sxs-lookup"><span data-stu-id="bd59a-106">The `condition` expression must evaluate to `true` or `false`.</span></span> <span data-ttu-id="bd59a-107">`condition` が `true` と評価された場合は、`consequent` 式が評価され、その結果が演算の結果になります。</span><span class="sxs-lookup"><span data-stu-id="bd59a-107">If `condition` evaluates to `true`, the `consequent` expression is evaluated, and its result becomes the result of the operation.</span></span> <span data-ttu-id="bd59a-108">`condition` が `false` と評価された場合は、`alternative` 式が評価され、その結果が演算の結果になります。</span><span class="sxs-lookup"><span data-stu-id="bd59a-108">If `condition` evaluates to `false`, the `alternative` expression is evaluated, and its result becomes the result of the operation.</span></span> <span data-ttu-id="bd59a-109">`consequent` または `alternative` のみが評価されます。</span><span class="sxs-lookup"><span data-stu-id="bd59a-109">Only `consequent` or `alternative` is evaluated.</span></span>

<span data-ttu-id="bd59a-110">C# 9.0 以降、条件式はターゲット型になっています。</span><span class="sxs-lookup"><span data-stu-id="bd59a-110">Beginning with C# 9.0, conditional expressions are target-typed.</span></span> <span data-ttu-id="bd59a-111">つまり、条件式のターゲット型がわかっている場合、次の例に示すように、`consequent` と `alternative` の型は、暗黙的にターゲット型に変換できる必要があります。</span><span class="sxs-lookup"><span data-stu-id="bd59a-111">That is, if a target type of a conditional expression is known, the types of `consequent` and `alternative` must be implicitly convertible to the target type, as the following example shows:</span></span>

[!code-csharp[target-typed conditional](snippets/shared/ConditionalOperator.cs#TargetTyped)]

<span data-ttu-id="bd59a-112">条件式のターゲット型が不明な場合 (たとえば、[`var`](../keywords/var.md) キーワードを使用する場合) または C# 8.0 以前の場合、`consequent` と `alternative` の型は同じであるか、またはある型から別の型に暗黙的に変換される必要があります。</span><span class="sxs-lookup"><span data-stu-id="bd59a-112">If a target type of a conditional expression is unknown (for example, when you use the [`var`](../keywords/var.md) keyword) or in C# 8.0 and earlier, the type of `consequent` and `alternative` must be the same or there must be an implicit conversion from one type to the other:</span></span>

[!code-csharp[not target-typed conditional](snippets/shared/ConditionalOperator.cs#NotTargetTyped)]

<span data-ttu-id="bd59a-113">条件演算子は右結合です。つまり、次の形式の式があるとします。</span><span class="sxs-lookup"><span data-stu-id="bd59a-113">The conditional operator is right-associative, that is, an expression of the form</span></span>

```csharp
a ? b : c ? d : e
```

<span data-ttu-id="bd59a-114">これが次のように評価されます。</span><span class="sxs-lookup"><span data-stu-id="bd59a-114">is evaluated as</span></span>

```csharp
a ? b : (c ? d : e)
```

> [!TIP]
> <span data-ttu-id="bd59a-115">次のニーモニック デバイスを使用して、条件演算子の評価方法を思い出すことができます。</span><span class="sxs-lookup"><span data-stu-id="bd59a-115">You can use the following mnemonic device to remember how the conditional operator is evaluated:</span></span>
>
> ```text
> is this condition true ? yes : no
> ```

<span data-ttu-id="bd59a-116">条件演算子の使用例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="bd59a-116">The following example demonstrates the usage of the conditional operator:</span></span>

[!code-csharp-interactive[non ref conditional](snippets/shared/ConditionalOperator.cs#ConditionalValue)]

## <a name="conditional-ref-expression"></a><span data-ttu-id="bd59a-117">ref 条件式</span><span class="sxs-lookup"><span data-stu-id="bd59a-117">Conditional ref expression</span></span>

<span data-ttu-id="bd59a-118">C# 7.2 以降、ref 条件式は、[ref ローカル](../keywords/ref.md#ref-locals)または [ref readonly ローカル](../keywords/ref.md#ref-readonly-locals)変数を使用して条件付きで割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="bd59a-118">Beginning with C# 7.2, a [ref local](../keywords/ref.md#ref-locals) or [ref readonly local](../keywords/ref.md#ref-readonly-locals) variable can be assigned conditionally with a conditional ref expression.</span></span> <span data-ttu-id="bd59a-119">ref 条件式を[参照戻り値](../keywords/ref.md#reference-return-values)または [`ref` メソッドの引数](../keywords/ref.md#passing-an-argument-by-reference)として使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="bd59a-119">You can also use a conditional ref expression as a [reference return value](../keywords/ref.md#reference-return-values) or as a [`ref` method argument](../keywords/ref.md#passing-an-argument-by-reference).</span></span>

<span data-ttu-id="bd59a-120">ref 条件式の構文は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="bd59a-120">The syntax for a conditional ref expression is as follows:</span></span>

```csharp
condition ? ref consequent : ref alternative
```

<span data-ttu-id="bd59a-121">ref 条件式では、元の条件演算子と同じように、2 つの式 (`consequent` または `alternative`) のいずれかのみが評価されます。</span><span class="sxs-lookup"><span data-stu-id="bd59a-121">Like the original conditional operator, a conditional ref expression evaluates only one of the two expressions: either `consequent` or `alternative`.</span></span>

<span data-ttu-id="bd59a-122">ref 条件式の場合、`consequent` と `alternative` の型は同じである必要があります。</span><span class="sxs-lookup"><span data-stu-id="bd59a-122">In the case of a conditional ref expression, the type of `consequent` and `alternative` must be the same.</span></span> <span data-ttu-id="bd59a-123">ref 条件式は、ターゲット型ではありません。</span><span class="sxs-lookup"><span data-stu-id="bd59a-123">Conditional ref expressions are not target-typed.</span></span>

<span data-ttu-id="bd59a-124">ref 条件演算子の使用例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="bd59a-124">The following example demonstrates the usage of a conditional ref expression:</span></span>

[!code-csharp-interactive[conditional ref](snippets/shared/ConditionalOperator.cs#ConditionalRef)]

## <a name="conditional-operator-and-an-ifelse-statement"></a><span data-ttu-id="bd59a-125">条件演算子と `if..else` ステートメント</span><span class="sxs-lookup"><span data-stu-id="bd59a-125">Conditional operator and an `if..else` statement</span></span>

<span data-ttu-id="bd59a-126">[if-else](../keywords/if-else.md) ステートメントではなく条件演算子を使用すると、値の計算を条件付きで実行する必要がある場合に、コードをもっと簡潔にできる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="bd59a-126">Use of the conditional operator instead of an [if-else](../keywords/if-else.md) statement might result in more concise code in cases when you need conditionally to compute a value.</span></span> <span data-ttu-id="bd59a-127">次の例では、整数を負の値または負以外の値に分類するための 2 つの方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="bd59a-127">The following example demonstrates two ways to classify an integer as negative or nonnegative:</span></span>

[!code-csharp[conditional and if-else](snippets/shared/ConditionalOperator.cs#CompareWithIf)]

## <a name="operator-overloadability"></a><span data-ttu-id="bd59a-128">演算子のオーバーロード可/不可</span><span class="sxs-lookup"><span data-stu-id="bd59a-128">Operator overloadability</span></span>

<span data-ttu-id="bd59a-129">ユーザー定義型は条件演算子をオーバーロードできません。</span><span class="sxs-lookup"><span data-stu-id="bd59a-129">A user-defined type cannot overload the conditional operator.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="bd59a-130">C# 言語仕様</span><span class="sxs-lookup"><span data-stu-id="bd59a-130">C# language specification</span></span>

<span data-ttu-id="bd59a-131">詳細については、「[C# 言語仕様](~/_csharplang/spec/introduction.md)」の「[条件演算子](~/_csharplang/spec/expressions.md#conditional-operator)」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="bd59a-131">For more information, see the [Conditional operator](~/_csharplang/spec/expressions.md#conditional-operator) section of the [C# language specification](~/_csharplang/spec/introduction.md).</span></span>

<span data-ttu-id="bd59a-132">C# 7.2 以降に追加された機能の詳細については、機能の提案に関する次の記述を参照してください。</span><span class="sxs-lookup"><span data-stu-id="bd59a-132">For more information about features added in C# 7.2 and later, see the following feature proposal notes:</span></span>

- [<span data-ttu-id="bd59a-133">ref 条件式 (C# 7.2)</span><span class="sxs-lookup"><span data-stu-id="bd59a-133">Conditional ref expressions (C# 7.2)</span></span>](~/_csharplang/proposals/csharp-7.2/conditional-ref.md)
- [<span data-ttu-id="bd59a-134">ターゲット型の条件式 (C# 9.0)</span><span class="sxs-lookup"><span data-stu-id="bd59a-134">Target-typed conditional expression (C# 9.0)</span></span>](~/_csharplang/proposals/csharp-9.0/target-typed-conditional-expression.md)

## <a name="see-also"></a><span data-ttu-id="bd59a-135">関連項目</span><span class="sxs-lookup"><span data-stu-id="bd59a-135">See also</span></span>

- [<span data-ttu-id="bd59a-136">C# リファレンス</span><span class="sxs-lookup"><span data-stu-id="bd59a-136">C# reference</span></span>](../index.md)
- [<span data-ttu-id="bd59a-137">C# の演算子と式</span><span class="sxs-lookup"><span data-stu-id="bd59a-137">C# operators and expressions</span></span>](index.md)
- [<span data-ttu-id="bd59a-138">if-else ステートメント</span><span class="sxs-lookup"><span data-stu-id="bd59a-138">if-else statement</span></span>](../keywords/if-else.md)
- <span data-ttu-id="bd59a-139">[?. および ?[] 演算子](member-access-operators.md#null-conditional-operators--and-)</span><span class="sxs-lookup"><span data-stu-id="bd59a-139">[?. and ?[] operators](member-access-operators.md#null-conditional-operators--and-)</span></span>
- [<span data-ttu-id="bd59a-140">?? および ??= 演算子</span><span class="sxs-lookup"><span data-stu-id="bd59a-140">?? and ??= operators</span></span>](null-coalescing-operator.md)
- [<span data-ttu-id="bd59a-141">ref キーワード</span><span class="sxs-lookup"><span data-stu-id="bd59a-141">ref keyword</span></span>](../keywords/ref.md)
