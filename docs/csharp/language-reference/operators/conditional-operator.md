---
title: ?:演算子 - C# リファレンス
ms.custom: seodec18
ms.date: 11/20/2018
f1_keywords:
- ?:_CSharpKeyword
- ?_CSharpKeyword
- :_CSharpKeyword
helpviewer_keywords:
- '?: operator [C#]'
- conditional operator (?:) [C#]
ms.assetid: e83a17f1-7500-48ba-8bee-2fbc4c847af4
ms.openlocfilehash: 210b7cabb658c6f068d9ab34c83050ad6267e426
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/09/2019
ms.locfileid: "57704909"
---
# <a name="-operator-c-reference"></a><span data-ttu-id="83e07-102">?:演算子 (C# リファレンス)</span><span class="sxs-lookup"><span data-stu-id="83e07-102">?: Operator (C# Reference)</span></span>

<span data-ttu-id="83e07-103">条件演算子 `?:` は、一般に三項条件演算子と呼ばれ、ブール式を評価し、ブール式の評価結果 (`true` または `false`) に応じて、2 つの式のいずれかの評価結果を返します。</span><span class="sxs-lookup"><span data-stu-id="83e07-103">The conditional operator `?:`, commonly known as the ternary conditional operator, evaluates a Boolean expression, and returns the result of evaluating one of two expressions, depending on whether the Boolean expression evaluates to `true` or `false`.</span></span> <span data-ttu-id="83e07-104">C# 7.2 以降、[ref 条件式](#conditional-ref-expression)は、2 つの式のいずれかの結果への参照を返します。</span><span class="sxs-lookup"><span data-stu-id="83e07-104">Beginning with C# 7.2, the [conditional ref expression](#conditional-ref-expression) returns the reference to the result of one of the two expressions.</span></span>

<span data-ttu-id="83e07-105">この条件演算子の構文は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="83e07-105">The syntax for the conditional operator is as follows:</span></span>

```csharp
condition ? consequence : alternative
```

<span data-ttu-id="83e07-106">`condition` 式は `true` または `false` と評価する必要があります。</span><span class="sxs-lookup"><span data-stu-id="83e07-106">The `condition` expression must evaluate to `true` or `false`.</span></span> <span data-ttu-id="83e07-107">`condition` が `true` と評価された場合は、`consequence` 式が評価され、その結果が演算の結果になります。</span><span class="sxs-lookup"><span data-stu-id="83e07-107">If `condition` evaluates to `true`, the `consequence` expression is evaluated, and its result becomes the result of the operation.</span></span> <span data-ttu-id="83e07-108">`condition` が `false` と評価された場合は、`alternative` 式が評価され、その結果が演算の結果になります。</span><span class="sxs-lookup"><span data-stu-id="83e07-108">If `condition` evaluates to `false`, the `alternative` expression is evaluated, and its result becomes the result of the operation.</span></span> <span data-ttu-id="83e07-109">`consequence` または `alternative` のみが評価されます。</span><span class="sxs-lookup"><span data-stu-id="83e07-109">Only `consequence` or `alternative` is evaluated.</span></span>

<span data-ttu-id="83e07-110">`consequence` の型と `alternative` の型は同じ型であるか、一方の型から他方の型への暗黙の型変換が存在している必要があります。</span><span class="sxs-lookup"><span data-stu-id="83e07-110">The type of `consequence` and `alternative` must be the same, or there must be an implicit conversion from one type to the other.</span></span>

<span data-ttu-id="83e07-111">条件演算子は右結合です。つまり、次の形式の式があるとします。</span><span class="sxs-lookup"><span data-stu-id="83e07-111">The conditional operator is right-associative, that is, an expression of the form</span></span>

```csharp
a ? b : c ? d : e
```

<span data-ttu-id="83e07-112">これが次のように評価されます。</span><span class="sxs-lookup"><span data-stu-id="83e07-112">is evaluated as</span></span>

```csharp
a ? b : (c ? d : e)
```

<span data-ttu-id="83e07-113">条件演算子の使用例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="83e07-113">The following example demonstrates the usage of the conditional operator:</span></span>

[!code-csharp[non ref conditional](~/samples/snippets/csharp/language-reference/operators/ConditionalExamples.cs#ConditionalValue)]

## <a name="conditional-ref-expression"></a><span data-ttu-id="83e07-114">ref 条件式</span><span class="sxs-lookup"><span data-stu-id="83e07-114">Conditional ref expression</span></span>

<span data-ttu-id="83e07-115">C# 7.2 以降、ref 条件式を使用して、2 つの式のいずれかの結果に対する参照を返すことができます。</span><span class="sxs-lookup"><span data-stu-id="83e07-115">Beginning with C# 7.2, you can use the conditional ref expression to return the reference to the result of one of the two expressions.</span></span> <span data-ttu-id="83e07-116">この参照を [ref ローカル](../keywords/ref.md#ref-locals)または [ref readonly ローカル](../keywords/ref.md#ref-readonly-locals)変数に代入できます。または、[参照の戻り値](../keywords/ref.md#reference-return-values)または [`ref` メソッドのパラメーター](../keywords/ref.md#passing-an-argument-by-reference)として使用できます。</span><span class="sxs-lookup"><span data-stu-id="83e07-116">You can assign that reference to a [ref local](../keywords/ref.md#ref-locals) or [ref readonly local](../keywords/ref.md#ref-readonly-locals) variable, or use it as a [reference return value](../keywords/ref.md#reference-return-values) or as a [`ref` method parameter](../keywords/ref.md#passing-an-argument-by-reference).</span></span>

<span data-ttu-id="83e07-117">ref 条件式の構文は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="83e07-117">The syntax for the conditional ref expression is as follows:</span></span>

```csharp
condition ? ref consequence : ref alternative
```

<span data-ttu-id="83e07-118">元の条件演算子と同じように、ref 条件式は、2 つの式 (`consequence` または `alternative`) のいずれかのみを評価します。</span><span class="sxs-lookup"><span data-stu-id="83e07-118">Like the original conditional operator, the conditional ref expression evaluates only one of the two expressions: either `consequence` or `alternative`.</span></span>

<span data-ttu-id="83e07-119">ref 条件式の場合、`consequence` と`alternative` の型は同じである必要があります。</span><span class="sxs-lookup"><span data-stu-id="83e07-119">In the case of the conditional ref expression, the type of `consequence` and `alternative` must be the same.</span></span>

<span data-ttu-id="83e07-120">ref 条件演算子の使用例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="83e07-120">The following example demonstrates the usage of the conditional ref expression:</span></span>

[!code-csharp[conditional ref](~/samples/snippets/csharp/language-reference/operators/ConditionalExamples.cs#ConditionalRef)]

<span data-ttu-id="83e07-121">詳細については、[機能提案メモ](../../../../_csharplang/proposals/csharp-7.2/conditional-ref.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="83e07-121">For more information, see the [feature proposal note](../../../../_csharplang/proposals/csharp-7.2/conditional-ref.md).</span></span>

## <a name="conditional-operator-and-an-ifelse-statement"></a><span data-ttu-id="83e07-122">条件演算子と `if..else` ステートメント</span><span class="sxs-lookup"><span data-stu-id="83e07-122">Conditional operator and an `if..else` statement</span></span>

<span data-ttu-id="83e07-123">条件演算子を [if-else](../keywords/if-else.md) ステートメントで使用すると、値の計算を条件付きで実行する必要がある場合に、コードをもっと簡潔にできる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="83e07-123">Use of the conditional operator over an [if-else](../keywords/if-else.md) statement might result in more concise code in cases when you need conditionally to compute a value.</span></span> <span data-ttu-id="83e07-124">次の例では、整数を負の値または負以外の値に分類するための 2 つの方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="83e07-124">The following example demonstrates two ways to classify an integer as negative or nonnegative:</span></span>

[!code-csharp[conditional and if-else](~/samples/snippets/csharp/language-reference/operators/ConditionalExamples.cs#CompareWithIf)]

## <a name="operator-overloadability"></a><span data-ttu-id="83e07-125">演算子のオーバーロード可/不可</span><span class="sxs-lookup"><span data-stu-id="83e07-125">Operator overloadability</span></span>

<span data-ttu-id="83e07-126">条件演算子は、オーバーロードできません。</span><span class="sxs-lookup"><span data-stu-id="83e07-126">The conditional operator cannot be overloaded.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="83e07-127">C# 言語仕様</span><span class="sxs-lookup"><span data-stu-id="83e07-127">C# language specification</span></span>

<span data-ttu-id="83e07-128">詳細については、「[C# 言語仕様](../language-specification/index.md)」の「[条件演算子](~/_csharplang/spec/expressions.md#conditional-operator)」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="83e07-128">For more information, see the [Conditional operator](~/_csharplang/spec/expressions.md#conditional-operator) section of the [C# language specification](../language-specification/index.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="83e07-129">関連項目</span><span class="sxs-lookup"><span data-stu-id="83e07-129">See also</span></span>

- [<span data-ttu-id="83e07-130">C# リファレンス</span><span class="sxs-lookup"><span data-stu-id="83e07-130">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="83e07-131">C# プログラミングガイド</span><span class="sxs-lookup"><span data-stu-id="83e07-131">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="83e07-132">C# 演算子</span><span class="sxs-lookup"><span data-stu-id="83e07-132">C# Operators</span></span>](index.md)
- [<span data-ttu-id="83e07-133">if-else ステートメント</span><span class="sxs-lookup"><span data-stu-id="83e07-133">if-else statement</span></span>](../keywords/if-else.md)
- <span data-ttu-id="83e07-134">[?. 演算子と ?[] 演算子](null-conditional-operators.md)</span><span class="sxs-lookup"><span data-stu-id="83e07-134">[?. and ?[] Operators](null-conditional-operators.md)</span></span>
- [<span data-ttu-id="83e07-135">??演算子</span><span class="sxs-lookup"><span data-stu-id="83e07-135">?? Operator</span></span>](null-coalescing-operator.md)
- [<span data-ttu-id="83e07-136">ref キーワード</span><span class="sxs-lookup"><span data-stu-id="83e07-136">ref keyword</span></span>](../keywords/ref.md)
