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
ms.openlocfilehash: 8ca97261b348b7813ab179abbc1f2c5f535966a1
ms.sourcegitcommit: 5ae6affa0b171be3bb5f4729fb68ea4fe799f959
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/10/2019
ms.locfileid: "66816011"
---
# <a name="-operator-c-reference"></a><span data-ttu-id="72c58-103">??</span><span class="sxs-lookup"><span data-stu-id="72c58-103">??</span></span> <span data-ttu-id="72c58-104">演算子 (C# リファレンス)</span><span class="sxs-lookup"><span data-stu-id="72c58-104">operator (C# Reference)</span></span>

<span data-ttu-id="72c58-105">Null 合体演算子`??`でない場合は、左側のオペランドの値を返します`null`。 そうしないと、右側のオペランドを評価し、その結果を返します。</span><span class="sxs-lookup"><span data-stu-id="72c58-105">The null-coalescing operator `??` returns the value of its left-hand operand if it isn't `null`; otherwise, it evaluates the right-hand operand and returns its result.</span></span> <span data-ttu-id="72c58-106">`??`左側のオペランドが null 以外に評価された場合、演算子は、右辺のオペランドを評価しません。</span><span class="sxs-lookup"><span data-stu-id="72c58-106">The `??` operator doesn't evaluate its right-hand operand if the left-hand operand evaluates to non-null.</span></span>

<span data-ttu-id="72c58-107">Null 合体演算子は右から左、形式の式は、</span><span class="sxs-lookup"><span data-stu-id="72c58-107">The null-coalescing operator is right-associative, that is, an expression of the form</span></span>

```csharp
a ?? b ?? c
```

<span data-ttu-id="72c58-108">これが次のように評価されます。</span><span class="sxs-lookup"><span data-stu-id="72c58-108">is evaluated as</span></span>

```csharp
a ?? (b ?? c)
```

<span data-ttu-id="72c58-109">`??`演算子は、次のシナリオで役に立ちます。</span><span class="sxs-lookup"><span data-stu-id="72c58-109">The `??` operator can be useful in the following scenarios:</span></span>

- <span data-ttu-id="72c58-110">含む式で、 [null 条件演算子?. およびですか?](member-access-operators.md#null-conditional-operators--and-)、null 合体演算子を使用するには代替場合に、null 条件操作を使用して式の結果を評価する式を指定する`null`:</span><span class="sxs-lookup"><span data-stu-id="72c58-110">In expressions with the [null-conditional operators ?. and ?[]](member-access-operators.md#null-conditional-operators--and-), you can use the null-coalescing operator to provide an alternative expression to evaluate in case the result of the expression with null-conditional operations is `null`:</span></span>

  [!code-csharp-interactive[with null-conditional](~/samples/csharp/language-reference/operators/NullCoalescingOperator.cs#WithNullConditional)]

- <span data-ttu-id="72c58-111">操作が[null 許容値型](../../programming-guide/nullable-types/index.md)場合に、null 許容型の値を提供する値を指定する null 合体演算子を使用して、基になる値型の値を指定する必要があると`null`:</span><span class="sxs-lookup"><span data-stu-id="72c58-111">When you work with [nullable value types](../../programming-guide/nullable-types/index.md) and need to provide a value of an underlying value type, use the null-coalescing operator to specify the value to provide in case a nullable type value is `null`:</span></span>

  [!code-csharp-interactive[with nullable types](~/samples/csharp/language-reference/operators/NullCoalescingOperator.cs#WithNullableTypes)]

  <span data-ttu-id="72c58-112">使用して、<xref:System.Nullable%601.GetValueOrDefault?displayProperty=nameWithType>メソッド場合、null 許容型の値は、ときに使用される値`null`基になる値型の既定値である必要があります。</span><span class="sxs-lookup"><span data-stu-id="72c58-112">Use the <xref:System.Nullable%601.GetValueOrDefault?displayProperty=nameWithType> method if the value to be used when a nullable type value is `null` should be the default value of the underlying value type.</span></span>

- <span data-ttu-id="72c58-113">以降でC#使用することができます、7.0、 [ `throw`式](../keywords/throw.md#the-throw-expression)引数チェック コードを簡潔にするため null 合体演算子の右側のオペランドとして。</span><span class="sxs-lookup"><span data-stu-id="72c58-113">Starting with C# 7.0, you can use a [`throw` expression](../keywords/throw.md#the-throw-expression) as the right-hand operand of the null-coalescing operator to make the argument-checking code more concise:</span></span>

  [!code-csharp[with throw expression](~/samples/csharp/language-reference/operators/NullCoalescingOperator.cs#WithThrowExpression)]

  <span data-ttu-id="72c58-114">上記の例では、使用する方法も示しています[に式形式メンバー](../../programming-guide/statements-expressions-operators/expression-bodied-members.md)プロパティを定義します。</span><span class="sxs-lookup"><span data-stu-id="72c58-114">The preceding example also demonstrates how to use [expression-bodied members](../../programming-guide/statements-expressions-operators/expression-bodied-members.md) to define a property.</span></span>

## <a name="operator-overloadability"></a><span data-ttu-id="72c58-115">演算子のオーバーロード可/不可</span><span class="sxs-lookup"><span data-stu-id="72c58-115">Operator overloadability</span></span>

<span data-ttu-id="72c58-116">Null 合体演算子はオーバー ロードすることはできません。</span><span class="sxs-lookup"><span data-stu-id="72c58-116">The null-coalescing operator cannot be overloaded.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="72c58-117">C# 言語仕様</span><span class="sxs-lookup"><span data-stu-id="72c58-117">C# language specification</span></span>

<span data-ttu-id="72c58-118">詳細については、次を参照してください。 [null 合体演算子](~/_csharplang/spec/expressions.md#the-null-coalescing-operator)のセクション、 [ C#言語仕様](~/_csharplang/spec/introduction.md)します。</span><span class="sxs-lookup"><span data-stu-id="72c58-118">For more information, see [The null coalescing operator](~/_csharplang/spec/expressions.md#the-null-coalescing-operator) section of the [C# language specification](~/_csharplang/spec/introduction.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="72c58-119">関連項目</span><span class="sxs-lookup"><span data-stu-id="72c58-119">See also</span></span>

- [<span data-ttu-id="72c58-120">C# リファレンス</span><span class="sxs-lookup"><span data-stu-id="72c58-120">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="72c58-121">C# プログラミング ガイド</span><span class="sxs-lookup"><span data-stu-id="72c58-121">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="72c58-122">C# 演算子</span><span class="sxs-lookup"><span data-stu-id="72c58-122">C# operators</span></span>](index.md)
- <span data-ttu-id="72c58-123">[?. および ?[] 演算子](member-access-operators.md#null-conditional-operators--and-)</span><span class="sxs-lookup"><span data-stu-id="72c58-123">[?. and ?[] operators](member-access-operators.md#null-conditional-operators--and-)</span></span>
- [<span data-ttu-id="72c58-124">?:演算子 (C# リファレンス)</span><span class="sxs-lookup"><span data-stu-id="72c58-124">?: operator</span></span>](conditional-operator.md)
