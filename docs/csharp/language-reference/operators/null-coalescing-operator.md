---
title: ?? 演算子 - C# リファレンス
ms.custom: seodec18
ms.date: 06/07/2019
f1_keywords:
- ??_CSharpKeyword
helpviewer_keywords:
- null-coalescing operator [C#]
- ?? operator [C#]
ms.assetid: 088b1f0d-c1af-4fe1-b4b8-196fd5ea9132
ms.openlocfilehash: a19b5558da36ffb11dabd1b9bec419a3623a0f17
ms.sourcegitcommit: 5bc85ad81d96b8dc2a90ce53bada475ee5662c44
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/12/2019
ms.locfileid: "67024993"
---
# <a name="-operator-c-reference"></a><span data-ttu-id="22407-103">??</span><span class="sxs-lookup"><span data-stu-id="22407-103">??</span></span> <span data-ttu-id="22407-104">演算子 (C# リファレンス)</span><span class="sxs-lookup"><span data-stu-id="22407-104">operator (C# reference)</span></span>

<span data-ttu-id="22407-105">null 合体演算子 `??` では、それが `null` ではない場合、その左側のオペランドの値が返されます。それ以外の場合は、右側のオペランドが評価され、その結果が返されます。</span><span class="sxs-lookup"><span data-stu-id="22407-105">The null-coalescing operator `??` returns the value of its left-hand operand if it isn't `null`; otherwise, it evaluates the right-hand operand and returns its result.</span></span> <span data-ttu-id="22407-106">`??` 演算子では、左側のオペランドが null 値以外に評価された場合は、その右側のオペランドは評価されません。</span><span class="sxs-lookup"><span data-stu-id="22407-106">The `??` operator doesn't evaluate its right-hand operand if the left-hand operand evaluates to non-null.</span></span>

<span data-ttu-id="22407-107">null 合体演算子は右結合です。つまり、次のフォームの式は</span><span class="sxs-lookup"><span data-stu-id="22407-107">The null-coalescing operator is right-associative, that is, an expression of the form</span></span>

```csharp
a ?? b ?? c
```

<span data-ttu-id="22407-108">これが次のように評価されます。</span><span class="sxs-lookup"><span data-stu-id="22407-108">is evaluated as</span></span>

```csharp
a ?? (b ?? c)
```

<span data-ttu-id="22407-109">`??` 演算子は、次のシナリオで役立つことがあります。</span><span class="sxs-lookup"><span data-stu-id="22407-109">The `??` operator can be useful in the following scenarios:</span></span>

- <span data-ttu-id="22407-110">[null 条件演算子 ?. および ?[]](member-access-operators.md#null-conditional-operators--and-) を含む式は、null 条件演算の式の結果が `null` の場合に評価する代替の式を指定するために、null 合体演算子を使用することができます。</span><span class="sxs-lookup"><span data-stu-id="22407-110">In expressions with the [null-conditional operators ?. and ?[]](member-access-operators.md#null-conditional-operators--and-), you can use the null-coalescing operator to provide an alternative expression to evaluate in case the result of the expression with null-conditional operations is `null`:</span></span>

  [!code-csharp-interactive[with null-conditional](~/samples/csharp/language-reference/operators/NullCoalescingOperator.cs#WithNullConditional)]

- <span data-ttu-id="22407-111">[null 値許容型](../../programming-guide/nullable-types/index.md)を使用して、基になる値の型の値を提供する必要がある場合、null 合体演算子を使用して、null 値許容型が `null` の場合に提供する値を指定します。</span><span class="sxs-lookup"><span data-stu-id="22407-111">When you work with [nullable value types](../../programming-guide/nullable-types/index.md) and need to provide a value of an underlying value type, use the null-coalescing operator to specify the value to provide in case a nullable type value is `null`:</span></span>

  [!code-csharp-interactive[with nullable types](~/samples/csharp/language-reference/operators/NullCoalescingOperator.cs#WithNullableTypes)]

  <span data-ttu-id="22407-112">null 値許容型が `null` の場合に使用される値を、基になる値型の既定値にする場合は、<xref:System.Nullable%601.GetValueOrDefault?displayProperty=nameWithType> メソッドを使用します。</span><span class="sxs-lookup"><span data-stu-id="22407-112">Use the <xref:System.Nullable%601.GetValueOrDefault?displayProperty=nameWithType> method if the value to be used when a nullable type value is `null` should be the default value of the underlying value type.</span></span>

- <span data-ttu-id="22407-113">C# 7.0 以降、null 合体演算子の右側のオペランドとして [`throw` 式](../keywords/throw.md#the-throw-expression)を使用し、引数のチェック コードをより簡潔にすることができます。</span><span class="sxs-lookup"><span data-stu-id="22407-113">Starting with C# 7.0, you can use a [`throw` expression](../keywords/throw.md#the-throw-expression) as the right-hand operand of the null-coalescing operator to make the argument-checking code more concise:</span></span>

  [!code-csharp[with throw expression](~/samples/csharp/language-reference/operators/NullCoalescingOperator.cs#WithThrowExpression)]

  <span data-ttu-id="22407-114">上記の例は、[式のようなメンバー](../../programming-guide/statements-expressions-operators/expression-bodied-members.md)を使用してプロパティを定義する方法も示しています。</span><span class="sxs-lookup"><span data-stu-id="22407-114">The preceding example also demonstrates how to use [expression-bodied members](../../programming-guide/statements-expressions-operators/expression-bodied-members.md) to define a property.</span></span>

## <a name="operator-overloadability"></a><span data-ttu-id="22407-115">演算子のオーバーロード可/不可</span><span class="sxs-lookup"><span data-stu-id="22407-115">Operator overloadability</span></span>

<span data-ttu-id="22407-116">null 合体演算子はオーバーロードできません。</span><span class="sxs-lookup"><span data-stu-id="22407-116">The null-coalescing operator cannot be overloaded.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="22407-117">C# 言語仕様</span><span class="sxs-lookup"><span data-stu-id="22407-117">C# language specification</span></span>

<span data-ttu-id="22407-118">詳細については、[C# 言語仕様](~/_csharplang/spec/introduction.md)の [null 合体演算子](~/_csharplang/spec/expressions.md#the-null-coalescing-operator)に関するセクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="22407-118">For more information, see [The null coalescing operator](~/_csharplang/spec/expressions.md#the-null-coalescing-operator) section of the [C# language specification](~/_csharplang/spec/introduction.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="22407-119">関連項目</span><span class="sxs-lookup"><span data-stu-id="22407-119">See also</span></span>

- [<span data-ttu-id="22407-120">C# リファレンス</span><span class="sxs-lookup"><span data-stu-id="22407-120">C# reference</span></span>](../index.md)
- [<span data-ttu-id="22407-121">C# 演算子</span><span class="sxs-lookup"><span data-stu-id="22407-121">C# operators</span></span>](index.md)
- <span data-ttu-id="22407-122">[?. および ?[] 演算子](member-access-operators.md#null-conditional-operators--and-)</span><span class="sxs-lookup"><span data-stu-id="22407-122">[?. and ?[] operators](member-access-operators.md#null-conditional-operators--and-)</span></span>
- [<span data-ttu-id="22407-123">?:演算子 (C# リファレンス)</span><span class="sxs-lookup"><span data-stu-id="22407-123">?: operator</span></span>](conditional-operator.md)
