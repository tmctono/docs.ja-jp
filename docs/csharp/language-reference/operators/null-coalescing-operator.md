---
title: ?? および ??= 演算子 - C# リファレンス
ms.date: 09/10/2019
f1_keywords:
- ??_CSharpKeyword
- ??=_CSharpKeyword
helpviewer_keywords:
- null-coalescing operator [C#]
- ?? operator [C#]
- null-coalescing assignment [C#]
- ??= operator [C#]
ms.assetid: 088b1f0d-c1af-4fe1-b4b8-196fd5ea9132
ms.openlocfilehash: 69294f0fb706868b48b8d7fe8b95fa345af169b1
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/14/2020
ms.locfileid: "78847314"
---
# <a name="-and--operators-c-reference"></a><span data-ttu-id="74f3a-103">??</span><span class="sxs-lookup"><span data-stu-id="74f3a-103">??</span></span> <span data-ttu-id="74f3a-104">および ?? 演算子 (C# リファレンス)</span><span class="sxs-lookup"><span data-stu-id="74f3a-104">and ??= operators (C# reference)</span></span>

<span data-ttu-id="74f3a-105">null 合体演算子 `??` では、それが `null` ではない場合、その左側のオペランドの値が返されます。それ以外の場合は、右側のオペランドが評価され、その結果が返されます。</span><span class="sxs-lookup"><span data-stu-id="74f3a-105">The null-coalescing operator `??` returns the value of its left-hand operand if it isn't `null`; otherwise, it evaluates the right-hand operand and returns its result.</span></span> <span data-ttu-id="74f3a-106">`??` 演算子では、左側のオペランドが null 値以外に評価された場合は、その右側のオペランドは評価されません。</span><span class="sxs-lookup"><span data-stu-id="74f3a-106">The `??` operator doesn't evaluate its right-hand operand if the left-hand operand evaluates to non-null.</span></span>

<span data-ttu-id="74f3a-107">C# 8.0 以降では、左側のオペランドが `??=` に評価された場合にのみ、右側のオペランドの値を左側のオペランドに割り当てる null 合体割り当て演算子 `null` を使用できます。</span><span class="sxs-lookup"><span data-stu-id="74f3a-107">Available in C# 8.0 and later, the null-coalescing assignment operator `??=` assigns the value of its right-hand operand to its left-hand operand only if the left-hand operand evaluates to `null`.</span></span> <span data-ttu-id="74f3a-108">`??=` 演算子では、左側のオペランドが null 値以外に評価された場合は、その右側のオペランドは評価されません。</span><span class="sxs-lookup"><span data-stu-id="74f3a-108">The `??=` operator doesn't evaluate its right-hand operand if the left-hand operand evaluates to non-null.</span></span>

[!code-csharp[null-coalescing assignment](snippets/NullCoalescingOperator.cs#Assignment)]

<span data-ttu-id="74f3a-109">`??=` 演算子の左側のオペランドは、変数、[プロパティ](../../programming-guide/classes-and-structs/properties.md)、または[インデクサー](../../programming-guide/indexers/index.md)要素である必要があります。</span><span class="sxs-lookup"><span data-stu-id="74f3a-109">The left-hand operand of the `??=` operator must be a variable, a [property](../../programming-guide/classes-and-structs/properties.md), or an [indexer](../../programming-guide/indexers/index.md) element.</span></span>

<span data-ttu-id="74f3a-110">C# 7.3 以前では、`??` 演算子の左側のオペランドの型は、[参照型](../keywords/reference-types.md)または [null 許容値型](../builtin-types/nullable-value-types.md)である必要があります。</span><span class="sxs-lookup"><span data-stu-id="74f3a-110">In C# 7.3 and earlier, the type of the left-hand operand of the `??` operator must be either a [reference type](../keywords/reference-types.md) or a [nullable value type](../builtin-types/nullable-value-types.md).</span></span> <span data-ttu-id="74f3a-111">C# 8.0 以降では、その要件は次に置き換えられます。`??` 演算子と `??=` 演算子の左側のオペランドの型は、null 非許容値型にすることはできません。</span><span class="sxs-lookup"><span data-stu-id="74f3a-111">Beginning with C# 8.0, that requirement is replaced with the following: the type of the left-hand operand of the `??` and `??=` operators cannot be a non-nullable value type.</span></span> <span data-ttu-id="74f3a-112">特に、C# 8.0 以降では、null 合体演算子を制約のない型パラメーターと共に使用できます。</span><span class="sxs-lookup"><span data-stu-id="74f3a-112">In particular, beginning with C# 8.0, you can use the null-coalescing operators with unconstrained type parameters:</span></span>

[!code-csharp[unconstrained type parameter](snippets/NullCoalescingOperator.cs#UnconstrainedType)]

<span data-ttu-id="74f3a-113">null 合体演算子は、右結合です。</span><span class="sxs-lookup"><span data-stu-id="74f3a-113">The null-coalescing operators are right-associative.</span></span> <span data-ttu-id="74f3a-114">つまり、フォームの式</span><span class="sxs-lookup"><span data-stu-id="74f3a-114">That is, expressions of the form</span></span>

```csharp
a ?? b ?? c
d ??= e ??= f
```

<span data-ttu-id="74f3a-115">は次のように評価されます。</span><span class="sxs-lookup"><span data-stu-id="74f3a-115">are evaluated as</span></span>

```csharp
a ?? (b ?? c)
d ??= (e ??= f)
```

## <a name="examples"></a><span data-ttu-id="74f3a-116">例</span><span class="sxs-lookup"><span data-stu-id="74f3a-116">Examples</span></span>

<span data-ttu-id="74f3a-117">`??` 演算子および `??=` 演算子は、次のシナリオで役立つことがあります。</span><span class="sxs-lookup"><span data-stu-id="74f3a-117">The `??` and `??=` operators can be useful in the following scenarios:</span></span>

- <span data-ttu-id="74f3a-118">[null 条件演算子 ?. および ?[]](member-access-operators.md#null-conditional-operators--and-) を含む式は、null 条件演算の式の結果が `??` の場合に評価する代替の式を指定するために、`null` 演算子を使用することができます。</span><span class="sxs-lookup"><span data-stu-id="74f3a-118">In expressions with the [null-conditional operators ?. and ?[]](member-access-operators.md#null-conditional-operators--and-), you can use the `??` operator to provide an alternative expression to evaluate in case the result of the expression with null-conditional operations is `null`:</span></span>

  [!code-csharp-interactive[with null-conditional](snippets/NullCoalescingOperator.cs#WithNullConditional)]

- <span data-ttu-id="74f3a-119">[null 値許容型](../builtin-types/nullable-value-types.md)を使用して、基になる値の型の値を提供する必要がある場合、`??` 演算子を使用して、null 値許容型が `null` の場合に提供する値を指定します。</span><span class="sxs-lookup"><span data-stu-id="74f3a-119">When you work with [nullable value types](../builtin-types/nullable-value-types.md) and need to provide a value of an underlying value type, use the `??` operator to specify the value to provide in case a nullable type value is `null`:</span></span>

  [!code-csharp-interactive[with nullable types](snippets/NullCoalescingOperator.cs#WithNullableTypes)]

  <span data-ttu-id="74f3a-120">null 値許容型が <xref:System.Nullable%601.GetValueOrDefault?displayProperty=nameWithType> の場合に使用される値を、基になる値型の既定値にする場合は、`null` メソッドを使用します。</span><span class="sxs-lookup"><span data-stu-id="74f3a-120">Use the <xref:System.Nullable%601.GetValueOrDefault?displayProperty=nameWithType> method if the value to be used when a nullable type value is `null` should be the default value of the underlying value type.</span></span>

- <span data-ttu-id="74f3a-121">C# 7.0 以降では、[ 演算子の右側のオペランドとして `throw`](../keywords/throw.md#the-throw-expression) 式`??`を使用し、引数のチェック コードをより簡潔にすることができます。</span><span class="sxs-lookup"><span data-stu-id="74f3a-121">Beginning with C# 7.0, you can use a [`throw` expression](../keywords/throw.md#the-throw-expression) as the right-hand operand of the `??` operator to make the argument-checking code more concise:</span></span>

  [!code-csharp[with throw expression](snippets/NullCoalescingOperator.cs#WithThrowExpression)]

  <span data-ttu-id="74f3a-122">上記の例は、[式のようなメンバー](../../programming-guide/statements-expressions-operators/expression-bodied-members.md)を使用してプロパティを定義する方法も示しています。</span><span class="sxs-lookup"><span data-stu-id="74f3a-122">The preceding example also demonstrates how to use [expression-bodied members](../../programming-guide/statements-expressions-operators/expression-bodied-members.md) to define a property.</span></span>

- <span data-ttu-id="74f3a-123">C# 8.0 以降では、`??=` 演算子を使用して、フォームのコード</span><span class="sxs-lookup"><span data-stu-id="74f3a-123">Beginning with C# 8.0, you can use the `??=` operator to replace the code of the form</span></span>

  ```csharp
  if (variable is null)
  {
      variable = expression;
  }
  ```

  <span data-ttu-id="74f3a-124">を、以下のコードに置き換えます。</span><span class="sxs-lookup"><span data-stu-id="74f3a-124">with the following code:</span></span>

  ```csharp
  variable ??= expression;
  ```

## <a name="operator-overloadability"></a><span data-ttu-id="74f3a-125">演算子のオーバーロード可/不可</span><span class="sxs-lookup"><span data-stu-id="74f3a-125">Operator overloadability</span></span>

<span data-ttu-id="74f3a-126">演算子 `??` および `??=` はオーバーロードできません。</span><span class="sxs-lookup"><span data-stu-id="74f3a-126">The operators `??` and `??=` cannot be overloaded.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="74f3a-127">C# 言語仕様</span><span class="sxs-lookup"><span data-stu-id="74f3a-127">C# language specification</span></span>

<span data-ttu-id="74f3a-128">`??` 演算子の詳細については、[C# 言語仕様](~/_csharplang/spec/expressions.md#the-null-coalescing-operator)の [null 合体演算子](~/_csharplang/spec/introduction.md)に関するセクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="74f3a-128">For more information about the `??` operator, see [The null coalescing operator](~/_csharplang/spec/expressions.md#the-null-coalescing-operator) section of the [C# language specification](~/_csharplang/spec/introduction.md).</span></span>

<span data-ttu-id="74f3a-129">`??=` リテラルの詳細については、[機能提案メモ](~/_csharplang/proposals/csharp-8.0/null-coalescing-assignment.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="74f3a-129">For more information about the `??=` operator, see the [feature proposal note](~/_csharplang/proposals/csharp-8.0/null-coalescing-assignment.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="74f3a-130">参照</span><span class="sxs-lookup"><span data-stu-id="74f3a-130">See also</span></span>

- [<span data-ttu-id="74f3a-131">C# リファレンス</span><span class="sxs-lookup"><span data-stu-id="74f3a-131">C# reference</span></span>](../index.md)
- [<span data-ttu-id="74f3a-132">C# 演算子</span><span class="sxs-lookup"><span data-stu-id="74f3a-132">C# operators</span></span>](index.md)
- <span data-ttu-id="74f3a-133">[?. および ?[] 演算子](member-access-operators.md#null-conditional-operators--and-)</span><span class="sxs-lookup"><span data-stu-id="74f3a-133">[?. and ?[] operators](member-access-operators.md#null-conditional-operators--and-)</span></span>
- [<span data-ttu-id="74f3a-134">?:演算子 (C# リファレンス)</span><span class="sxs-lookup"><span data-stu-id="74f3a-134">?: operator</span></span>](conditional-operator.md)
