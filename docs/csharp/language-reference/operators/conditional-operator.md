---
description: '?: 演算子 - C# リファレンス'
title: '?: 演算子 - C# リファレンス'
ms.date: 03/06/2020
f1_keywords:
- ?:_CSharpKeyword
- ?_CSharpKeyword
- :_CSharpKeyword
helpviewer_keywords:
- '?: operator [C#]'
- conditional operator (?:) [C#]
ms.assetid: e83a17f1-7500-48ba-8bee-2fbc4c847af4
ms.openlocfilehash: 0efa6de2b537fd3af76807938ac2b50a2716561f
ms.sourcegitcommit: d579fb5e4b46745fd0f1f8874c94c6469ce58604
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/30/2020
ms.locfileid: "89122356"
---
# <a name="-operator-c-reference"></a><span data-ttu-id="4cc57-103">?: 演算子 (C# リファレンス)</span><span class="sxs-lookup"><span data-stu-id="4cc57-103">?: operator (C# reference)</span></span>

<span data-ttu-id="4cc57-104">条件演算子 `?:` は、三項条件演算子とも呼ばれ、ブール式を評価し、ブール式の評価結果 (`true` または `false`) に応じて、2 つの式のいずれかの結果を返します。</span><span class="sxs-lookup"><span data-stu-id="4cc57-104">The conditional operator `?:`, also known as the ternary conditional operator, evaluates a Boolean expression and returns the result of one of the two expressions, depending on whether the Boolean expression evaluates to `true` or `false`.</span></span>

<span data-ttu-id="4cc57-105">この条件演算子の構文は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="4cc57-105">The syntax for the conditional operator is as follows:</span></span>

```csharp
condition ? consequent : alternative
```

<span data-ttu-id="4cc57-106">`condition` 式は `true` または `false` と評価する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4cc57-106">The `condition` expression must evaluate to `true` or `false`.</span></span> <span data-ttu-id="4cc57-107">`condition` が `true` と評価された場合は、`consequent` 式が評価され、その結果が演算の結果になります。</span><span class="sxs-lookup"><span data-stu-id="4cc57-107">If `condition` evaluates to `true`, the `consequent` expression is evaluated, and its result becomes the result of the operation.</span></span> <span data-ttu-id="4cc57-108">`condition` が `false` と評価された場合は、`alternative` 式が評価され、その結果が演算の結果になります。</span><span class="sxs-lookup"><span data-stu-id="4cc57-108">If `condition` evaluates to `false`, the `alternative` expression is evaluated, and its result becomes the result of the operation.</span></span> <span data-ttu-id="4cc57-109">`consequent` または `alternative` のみが評価されます。</span><span class="sxs-lookup"><span data-stu-id="4cc57-109">Only `consequent` or `alternative` is evaluated.</span></span>

<span data-ttu-id="4cc57-110">`consequent` の型と `alternative` の型は同じ型であるか、一方の型から他方の型への暗黙の型変換が存在している必要があります。</span><span class="sxs-lookup"><span data-stu-id="4cc57-110">The type of `consequent` and `alternative` must be the same, or there must be an implicit conversion from one type to the other.</span></span>

<span data-ttu-id="4cc57-111">条件演算子は右結合です。つまり、次の形式の式があるとします。</span><span class="sxs-lookup"><span data-stu-id="4cc57-111">The conditional operator is right-associative, that is, an expression of the form</span></span>

```csharp
a ? b : c ? d : e
```

<span data-ttu-id="4cc57-112">これが次のように評価されます。</span><span class="sxs-lookup"><span data-stu-id="4cc57-112">is evaluated as</span></span>

```csharp
a ? b : (c ? d : e)
```

> [!TIP]
> <span data-ttu-id="4cc57-113">次のニーモニック デバイスを使用して、条件演算子の評価方法を思い出すことができます。</span><span class="sxs-lookup"><span data-stu-id="4cc57-113">You can use the following mnemonic device to remember how the conditional operator is evaluated:</span></span>
>
> ```text
> is this condition true ? yes : no
> ```

<span data-ttu-id="4cc57-114">条件演算子の使用例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="4cc57-114">The following example demonstrates the usage of the conditional operator:</span></span>

[!code-csharp-interactive[non ref conditional](snippets/shared/ConditionalOperator.cs#ConditionalValue)]

## <a name="conditional-ref-expression"></a><span data-ttu-id="4cc57-115">ref 条件式</span><span class="sxs-lookup"><span data-stu-id="4cc57-115">Conditional ref expression</span></span>

<span data-ttu-id="4cc57-116">C# 7.2 以降、[ref ローカル](../keywords/ref.md#ref-locals)または [ref readonly ローカル](../keywords/ref.md#ref-readonly-locals)変数は、条件付き参照式で条件付きで割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="4cc57-116">Beginning with C# 7.2, a [ref local](../keywords/ref.md#ref-locals) or [ref readonly local](../keywords/ref.md#ref-readonly-locals) variable can be assigned conditionally with the conditional ref expression.</span></span> <span data-ttu-id="4cc57-117">条件付き参照式を[参照戻り値](../keywords/ref.md#reference-return-values)または [`ref` メソッドの引数](../keywords/ref.md#passing-an-argument-by-reference)として使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="4cc57-117">You can also use the conditional ref expression as a [reference return value](../keywords/ref.md#reference-return-values) or as a [`ref` method argument](../keywords/ref.md#passing-an-argument-by-reference).</span></span>

<span data-ttu-id="4cc57-118">ref 条件式の構文は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="4cc57-118">The syntax for the conditional ref expression is as follows:</span></span>

```csharp
condition ? ref consequent : ref alternative
```

<span data-ttu-id="4cc57-119">元の条件演算子と同じように、ref 条件式は、2 つの式 (`consequent` または `alternative`) のいずれかのみを評価します。</span><span class="sxs-lookup"><span data-stu-id="4cc57-119">Like the original conditional operator, the conditional ref expression evaluates only one of the two expressions: either `consequent` or `alternative`.</span></span>

<span data-ttu-id="4cc57-120">ref 条件式の場合、`consequent` と`alternative` の型は同じである必要があります。</span><span class="sxs-lookup"><span data-stu-id="4cc57-120">In the case of the conditional ref expression, the type of `consequent` and `alternative` must be the same.</span></span>

<span data-ttu-id="4cc57-121">ref 条件演算子の使用例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="4cc57-121">The following example demonstrates the usage of the conditional ref expression:</span></span>

[!code-csharp-interactive[conditional ref](snippets/shared/ConditionalOperator.cs#ConditionalRef)]

## <a name="conditional-operator-and-an-ifelse-statement"></a><span data-ttu-id="4cc57-122">条件演算子と `if..else` ステートメント</span><span class="sxs-lookup"><span data-stu-id="4cc57-122">Conditional operator and an `if..else` statement</span></span>

<span data-ttu-id="4cc57-123">[if-else](../keywords/if-else.md) ステートメントではなく条件演算子を使用すると、値の計算を条件付きで実行する必要がある場合に、コードをもっと簡潔にできる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="4cc57-123">Use of the conditional operator instead of an [if-else](../keywords/if-else.md) statement might result in more concise code in cases when you need conditionally to compute a value.</span></span> <span data-ttu-id="4cc57-124">次の例では、整数を負の値または負以外の値に分類するための 2 つの方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="4cc57-124">The following example demonstrates two ways to classify an integer as negative or nonnegative:</span></span>

[!code-csharp[conditional and if-else](snippets/shared/ConditionalOperator.cs#CompareWithIf)]

## <a name="operator-overloadability"></a><span data-ttu-id="4cc57-125">演算子のオーバーロード可/不可</span><span class="sxs-lookup"><span data-stu-id="4cc57-125">Operator overloadability</span></span>

<span data-ttu-id="4cc57-126">ユーザー定義型は条件演算子をオーバーロードできません。</span><span class="sxs-lookup"><span data-stu-id="4cc57-126">A user-defined type cannot overload the conditional operator.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="4cc57-127">C# 言語仕様</span><span class="sxs-lookup"><span data-stu-id="4cc57-127">C# language specification</span></span>

<span data-ttu-id="4cc57-128">詳細については、「[C# 言語仕様](~/_csharplang/spec/introduction.md)」の「[条件演算子](~/_csharplang/spec/expressions.md#conditional-operator)」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="4cc57-128">For more information, see the [Conditional operator](~/_csharplang/spec/expressions.md#conditional-operator) section of the [C# language specification](~/_csharplang/spec/introduction.md).</span></span>

<span data-ttu-id="4cc57-129">ref 条件式について詳しくは、[機能提案メモ](~/_csharplang/proposals/csharp-7.2/conditional-ref.md)をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="4cc57-129">For more information about the conditional ref expression, see the [feature proposal note](~/_csharplang/proposals/csharp-7.2/conditional-ref.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="4cc57-130">関連項目</span><span class="sxs-lookup"><span data-stu-id="4cc57-130">See also</span></span>

- [<span data-ttu-id="4cc57-131">C# リファレンス</span><span class="sxs-lookup"><span data-stu-id="4cc57-131">C# reference</span></span>](../index.md)
- [<span data-ttu-id="4cc57-132">C# の演算子と式</span><span class="sxs-lookup"><span data-stu-id="4cc57-132">C# operators and expressions</span></span>](index.md)
- [<span data-ttu-id="4cc57-133">if-else ステートメント</span><span class="sxs-lookup"><span data-stu-id="4cc57-133">if-else statement</span></span>](../keywords/if-else.md)
- <span data-ttu-id="4cc57-134">[?. および ?[] 演算子](member-access-operators.md#null-conditional-operators--and-)</span><span class="sxs-lookup"><span data-stu-id="4cc57-134">[?. and ?[] operators](member-access-operators.md#null-conditional-operators--and-)</span></span>
- [<span data-ttu-id="4cc57-135">?? および ??= 演算子</span><span class="sxs-lookup"><span data-stu-id="4cc57-135">?? and ??= operators</span></span>](null-coalescing-operator.md)
- [<span data-ttu-id="4cc57-136">ref キーワード</span><span class="sxs-lookup"><span data-stu-id="4cc57-136">ref keyword</span></span>](../keywords/ref.md)
