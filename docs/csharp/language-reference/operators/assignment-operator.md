---
title: = 演算子 - C# リファレンス
ms.custom: seodec18
ms.date: 09/10/2019
f1_keywords:
- =_CSharpKeyword
helpviewer_keywords:
- = operator [C#]
ms.assetid: d802a6d5-32f0-42b8-b180-12f5a081bfc1
ms.openlocfilehash: a450a55524f33f4f06ed077aba864e8f641a458d
ms.sourcegitcommit: 33c8d6f7342a4bb2c577842b7f075b0e20a2fa40
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/12/2019
ms.locfileid: "70924661"
---
# <a name="-operator-c-reference"></a><span data-ttu-id="b79e3-102">= 演算子 (C# リファレンス)</span><span class="sxs-lookup"><span data-stu-id="b79e3-102">= operator (C# reference)</span></span>

<span data-ttu-id="b79e3-103">代入演算子 `=` は、右辺オペランドの値を、左辺オペランドに指定された変数、[プロパティ](../../programming-guide/classes-and-structs/properties.md)、または[インデクサー](../../programming-guide/indexers/index.md)要素に割り当てます。</span><span class="sxs-lookup"><span data-stu-id="b79e3-103">The assignment operator `=` assigns the value of its right-hand operand to a variable, a [property](../../programming-guide/classes-and-structs/properties.md), or an [indexer](../../programming-guide/indexers/index.md) element given by its left-hand operand.</span></span> <span data-ttu-id="b79e3-104">代入式の結果は、左辺のオペランドに割り当てられる値です。</span><span class="sxs-lookup"><span data-stu-id="b79e3-104">The result of an assignment expression is the value assigned to the left-hand operand.</span></span> <span data-ttu-id="b79e3-105">右辺のオペランドの型は、左辺のオペランドの型と同じであるか、暗黙に変換できる必要があります。</span><span class="sxs-lookup"><span data-stu-id="b79e3-105">The type of the right-hand operand must be the same as the type of the left-hand operand or implicitly convertible to it.</span></span>

<span data-ttu-id="b79e3-106">代入演算子は右結合です。つまり、次の形式の式があるとします。</span><span class="sxs-lookup"><span data-stu-id="b79e3-106">The assignment operator is right-associative, that is, an expression of the form</span></span>

```csharp
a = b = c
```

<span data-ttu-id="b79e3-107">これが次のように評価されます。</span><span class="sxs-lookup"><span data-stu-id="b79e3-107">is evaluated as</span></span>

```csharp
a = (b = c)
```

<span data-ttu-id="b79e3-108">次の例では、左側のオペランドとしてローカル変数、プロパティ、およびインデクサー要素を使用する代入演算子の使用方法を示します。</span><span class="sxs-lookup"><span data-stu-id="b79e3-108">The following example demonstrates the usage of the assignment operator with a local variable, a property, and an indexer element as its left-hand operand:</span></span>

[!code-csharp-interactive[simple assignment](~/samples/csharp/language-reference/operators/AssignmentOperator.cs#Simple)]

## <a name="ref-assignment-operator"></a><span data-ttu-id="b79e3-109">ref 代入演算子</span><span class="sxs-lookup"><span data-stu-id="b79e3-109">ref assignment operator</span></span>

<span data-ttu-id="b79e3-110">C# 7.3 以降では、ref 代入演算子 `= ref` を使用して、[ref ローカル](../keywords/ref.md#ref-locals)変数または [ref 読み取り専用ローカル](../keywords/ref.md#ref-readonly-locals)変数を割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="b79e3-110">Beginning with C# 7.3, you can use the ref assignment operator `= ref` to reassign a [ref local](../keywords/ref.md#ref-locals) or [ref readonly local](../keywords/ref.md#ref-readonly-locals) variable.</span></span> <span data-ttu-id="b79e3-111">次の例は、ref 代入演算子の使用方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="b79e3-111">The following example demonstrates the usage of the ref assignment operator:</span></span>

[!code-csharp[ref assignment operator](~/samples/csharp/language-reference/operators/AssignmentOperator.cs#RefAssignment)]

<span data-ttu-id="b79e3-112">ref 代入演算子の場合、その両方のオペランドの型が同じである必要があります。</span><span class="sxs-lookup"><span data-stu-id="b79e3-112">In the case of the ref assignment operator, the type of both its operands must be the same.</span></span>

<span data-ttu-id="b79e3-113">詳しくは、[機能提案メモ](~/_csharplang/proposals/csharp-7.3/ref-local-reassignment.md)をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="b79e3-113">For more information, see the [feature proposal note](~/_csharplang/proposals/csharp-7.3/ref-local-reassignment.md).</span></span>

## <a name="compound-assignment"></a><span data-ttu-id="b79e3-114">複合代入。</span><span class="sxs-lookup"><span data-stu-id="b79e3-114">Compound assignment</span></span>

<span data-ttu-id="b79e3-115">2 項演算子 `op` の場合、フォームの複合代入式</span><span class="sxs-lookup"><span data-stu-id="b79e3-115">For a binary operator `op`, a compound assignment expression of the form</span></span>

```csharp
x op= y
```

<span data-ttu-id="b79e3-116">上記の式は、次の式と同じです。</span><span class="sxs-lookup"><span data-stu-id="b79e3-116">is equivalent to</span></span>

```csharp
x = x op y
```

<span data-ttu-id="b79e3-117">ただし、`x` が評価されるのは 1 回だけです。</span><span class="sxs-lookup"><span data-stu-id="b79e3-117">except that `x` is only evaluated once.</span></span>

<span data-ttu-id="b79e3-118">複合代入は、[算術](arithmetic-operators.md#compound-assignment)、[ブール論理](boolean-logical-operators.md#compound-assignment)、[ビット単位論理およびシフト](bitwise-and-shift-operators.md#compound-assignment)の各演算子でサポートされています。</span><span class="sxs-lookup"><span data-stu-id="b79e3-118">Compound assignment is supported by [arithmetic](arithmetic-operators.md#compound-assignment), [Boolean logical](boolean-logical-operators.md#compound-assignment), and [bitwise logical and shift](bitwise-and-shift-operators.md#compound-assignment) operators.</span></span>

## <a name="null-coalescing-assignment"></a><span data-ttu-id="b79e3-119">null 合体割り当て</span><span class="sxs-lookup"><span data-stu-id="b79e3-119">Null-coalescing assignment</span></span>

<span data-ttu-id="b79e3-120">C# 8.0 以降では、null 合体割り当て演算子 `??=` を使用して、左側のオペランドが `null` に評価された場合にのみ、右側のオペランドの値を左側のオペランドに割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="b79e3-120">Beginning with C# 8.0, you can use the null-coalescing assignment operator `??=` to assign the value of its right-hand operand to its left-hand operand only if the left-hand operand evaluates to `null`.</span></span> <span data-ttu-id="b79e3-121">詳細については、[?? および ??= 演算子](null-coalescing-operator.md)の記事を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b79e3-121">For more information, see the [?? and ??= operators](null-coalescing-operator.md) article.</span></span>

## <a name="operator-overloadability"></a><span data-ttu-id="b79e3-122">演算子のオーバーロード可/不可</span><span class="sxs-lookup"><span data-stu-id="b79e3-122">Operator overloadability</span></span>

<span data-ttu-id="b79e3-123">ユーザー定義型は、代入演算子をオーバー ロードできません。</span><span class="sxs-lookup"><span data-stu-id="b79e3-123">A user-defined type cannot overload the assignment operator.</span></span> <span data-ttu-id="b79e3-124">ただし、ユーザー定義型は、別の型への暗黙的な変換を定義できます。</span><span class="sxs-lookup"><span data-stu-id="b79e3-124">However, a user-defined type can define an implicit conversion to another type.</span></span> <span data-ttu-id="b79e3-125">この方法により、ユーザー定義型の値を、別の型の変数、プロパティ、またはインデクサー要素に割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="b79e3-125">That way, the value of a user-defined type can be assigned to a variable, a property, or an indexer element of another type.</span></span> <span data-ttu-id="b79e3-126">詳細については、[ユーザー定義の変換演算子](user-defined-conversion-operators.md) に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="b79e3-126">For more information, see [User-defined conversion operators](user-defined-conversion-operators.md).</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="b79e3-127">C# 言語仕様</span><span class="sxs-lookup"><span data-stu-id="b79e3-127">C# language specification</span></span>

<span data-ttu-id="b79e3-128">詳細については、[C# 言語仕様](../language-specification/index.md)の「[Assignment operators (代入演算子)](~/_csharplang/spec/expressions.md#assignment-operators)」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="b79e3-128">For more information, see the [Assignment operators](~/_csharplang/spec/expressions.md#assignment-operators) section of the [C# language specification](../language-specification/index.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="b79e3-129">関連項目</span><span class="sxs-lookup"><span data-stu-id="b79e3-129">See also</span></span>

- [<span data-ttu-id="b79e3-130">C# リファレンス</span><span class="sxs-lookup"><span data-stu-id="b79e3-130">C# reference</span></span>](../index.md)
- [<span data-ttu-id="b79e3-131">C# 演算子</span><span class="sxs-lookup"><span data-stu-id="b79e3-131">C# operators</span></span>](index.md)
- [<span data-ttu-id="b79e3-132">ref キーワード</span><span class="sxs-lookup"><span data-stu-id="b79e3-132">ref keyword</span></span>](../keywords/ref.md)
