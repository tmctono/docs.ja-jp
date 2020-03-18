---
title: 代入演算子 - C# リファレンス
ms.date: 09/10/2019
f1_keywords:
- =_CSharpKeyword
helpviewer_keywords:
- = operator [C#]
ms.assetid: d802a6d5-32f0-42b8-b180-12f5a081bfc1
ms.openlocfilehash: 420b41f586a6980d40cf1171eef00dad37bf5abf
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/14/2020
ms.locfileid: "79398059"
---
# <a name="assignment-operators-c-reference"></a><span data-ttu-id="3a3a7-102">代入演算子 (C# リファレンス)</span><span class="sxs-lookup"><span data-stu-id="3a3a7-102">Assignment operators (C# reference)</span></span>

<span data-ttu-id="3a3a7-103">代入演算子 `=` は、右辺オペランドの値を、左辺オペランドに指定された変数、[プロパティ](../../programming-guide/classes-and-structs/properties.md)、または[インデクサー](../../programming-guide/indexers/index.md)要素に割り当てます。</span><span class="sxs-lookup"><span data-stu-id="3a3a7-103">The assignment operator `=` assigns the value of its right-hand operand to a variable, a [property](../../programming-guide/classes-and-structs/properties.md), or an [indexer](../../programming-guide/indexers/index.md) element given by its left-hand operand.</span></span> <span data-ttu-id="3a3a7-104">代入式の結果は、左辺のオペランドに割り当てられる値です。</span><span class="sxs-lookup"><span data-stu-id="3a3a7-104">The result of an assignment expression is the value assigned to the left-hand operand.</span></span> <span data-ttu-id="3a3a7-105">右辺のオペランドの型は、左辺のオペランドの型と同じであるか、暗黙に変換できる必要があります。</span><span class="sxs-lookup"><span data-stu-id="3a3a7-105">The type of the right-hand operand must be the same as the type of the left-hand operand or implicitly convertible to it.</span></span>

<span data-ttu-id="3a3a7-106">代入演算子 `=` は右結合です。つまり、次の形式の式があるとします</span><span class="sxs-lookup"><span data-stu-id="3a3a7-106">The assignment operator `=` is right-associative, that is, an expression of the form</span></span>

```csharp
a = b = c
```

<span data-ttu-id="3a3a7-107">これが次のように評価されます。</span><span class="sxs-lookup"><span data-stu-id="3a3a7-107">is evaluated as</span></span>

```csharp
a = (b = c)
```

<span data-ttu-id="3a3a7-108">次の例では、左側のオペランドとしてローカル変数、プロパティ、およびインデクサー要素を使用する代入演算子の使用方法を示します。</span><span class="sxs-lookup"><span data-stu-id="3a3a7-108">The following example demonstrates the usage of the assignment operator with a local variable, a property, and an indexer element as its left-hand operand:</span></span>

[!code-csharp-interactive[simple assignment](snippets/AssignmentOperator.cs#Simple)]

## <a name="ref-assignment-operator"></a><span data-ttu-id="3a3a7-109">ref 代入演算子</span><span class="sxs-lookup"><span data-stu-id="3a3a7-109">ref assignment operator</span></span>

<span data-ttu-id="3a3a7-110">C# 7.3 以降では、ref 代入演算子 `= ref` を使用して、[ref ローカル](../keywords/ref.md#ref-locals)変数または [ref 読み取り専用ローカル](../keywords/ref.md#ref-readonly-locals)変数を割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="3a3a7-110">Beginning with C# 7.3, you can use the ref assignment operator `= ref` to reassign a [ref local](../keywords/ref.md#ref-locals) or [ref readonly local](../keywords/ref.md#ref-readonly-locals) variable.</span></span> <span data-ttu-id="3a3a7-111">次の例は、ref 代入演算子の使用方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="3a3a7-111">The following example demonstrates the usage of the ref assignment operator:</span></span>

[!code-csharp[ref assignment operator](snippets/AssignmentOperator.cs#RefAssignment)]

<span data-ttu-id="3a3a7-112">ref 代入演算子の場合、その両方のオペランドの型が同じである必要があります。</span><span class="sxs-lookup"><span data-stu-id="3a3a7-112">In the case of the ref assignment operator, the both of its operands must be of the same type.</span></span>

## <a name="compound-assignment"></a><span data-ttu-id="3a3a7-113">複合代入。</span><span class="sxs-lookup"><span data-stu-id="3a3a7-113">Compound assignment</span></span>

<span data-ttu-id="3a3a7-114">2 項演算子 `op` の場合、フォームの複合代入式</span><span class="sxs-lookup"><span data-stu-id="3a3a7-114">For a binary operator `op`, a compound assignment expression of the form</span></span>

```csharp
x op= y
```

<span data-ttu-id="3a3a7-115">上記の式は、次の式と同じです。</span><span class="sxs-lookup"><span data-stu-id="3a3a7-115">is equivalent to</span></span>

```csharp
x = x op y
```

<span data-ttu-id="3a3a7-116">ただし、`x` が評価されるのは 1 回だけです。</span><span class="sxs-lookup"><span data-stu-id="3a3a7-116">except that `x` is only evaluated once.</span></span>

<span data-ttu-id="3a3a7-117">複合代入は、[算術](arithmetic-operators.md#compound-assignment)、[ブール論理](boolean-logical-operators.md#compound-assignment)、[ビット単位論理およびシフト](bitwise-and-shift-operators.md#compound-assignment)の各演算子でサポートされています。</span><span class="sxs-lookup"><span data-stu-id="3a3a7-117">Compound assignment is supported by [arithmetic](arithmetic-operators.md#compound-assignment), [Boolean logical](boolean-logical-operators.md#compound-assignment), and [bitwise logical and shift](bitwise-and-shift-operators.md#compound-assignment) operators.</span></span>

## <a name="null-coalescing-assignment"></a><span data-ttu-id="3a3a7-118">null 合体割り当て</span><span class="sxs-lookup"><span data-stu-id="3a3a7-118">Null-coalescing assignment</span></span>

<span data-ttu-id="3a3a7-119">C# 8.0 以降では、null 合体割り当て演算子 `??=` を使用して、左側のオペランドが `null` に評価された場合にのみ、右側のオペランドの値を左側のオペランドに割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="3a3a7-119">Beginning with C# 8.0, you can use the null-coalescing assignment operator `??=` to assign the value of its right-hand operand to its left-hand operand only if the left-hand operand evaluates to `null`.</span></span> <span data-ttu-id="3a3a7-120">詳細については、「[?? and ??= 演算子](null-coalescing-operator.md)」の記事を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3a3a7-120">For more information, see the [?? and ??= operators](null-coalescing-operator.md) article.</span></span>

## <a name="operator-overloadability"></a><span data-ttu-id="3a3a7-121">演算子のオーバーロード可/不可</span><span class="sxs-lookup"><span data-stu-id="3a3a7-121">Operator overloadability</span></span>

<span data-ttu-id="3a3a7-122">ユーザー定義型は、代入演算子を[オーバーロード](operator-overloading.md)できません。</span><span class="sxs-lookup"><span data-stu-id="3a3a7-122">A user-defined type cannot [overload](operator-overloading.md) the assignment operator.</span></span> <span data-ttu-id="3a3a7-123">ただし、ユーザー定義型は、別の型への暗黙的な変換を定義できます。</span><span class="sxs-lookup"><span data-stu-id="3a3a7-123">However, a user-defined type can define an implicit conversion to another type.</span></span> <span data-ttu-id="3a3a7-124">この方法により、ユーザー定義型の値を、別の型の変数、プロパティ、またはインデクサー要素に割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="3a3a7-124">That way, the value of a user-defined type can be assigned to a variable, a property, or an indexer element of another type.</span></span> <span data-ttu-id="3a3a7-125">詳細については、[ユーザー定義の変換演算子](user-defined-conversion-operators.md) に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="3a3a7-125">For more information, see [User-defined conversion operators](user-defined-conversion-operators.md).</span></span>

<span data-ttu-id="3a3a7-126">ユーザー定義型は、複合代入演算子を明示的にオーバーロードすることはできません。</span><span class="sxs-lookup"><span data-stu-id="3a3a7-126">A user-defined type cannot explicitly overload a compound assignment operator.</span></span> <span data-ttu-id="3a3a7-127">ただし、ユーザー定義型が二項演算子 `op` をオーバーロードし、`op=` 演算子も存在する場合は、それも暗黙的にオーバーロードされます。</span><span class="sxs-lookup"><span data-stu-id="3a3a7-127">However, if a user-defined type overloads a binary operator `op`, the `op=` operator, if it exists, is also implicitly overloaded.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="3a3a7-128">C# 言語仕様</span><span class="sxs-lookup"><span data-stu-id="3a3a7-128">C# language specification</span></span>

<span data-ttu-id="3a3a7-129">詳細については、[C# 言語仕様](~/_csharplang/spec/expressions.md#assignment-operators)の「[Assignment operators (代入演算子)](~/_csharplang/spec/introduction.md)」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="3a3a7-129">For more information, see the [Assignment operators](~/_csharplang/spec/expressions.md#assignment-operators) section of the [C# language specification](~/_csharplang/spec/introduction.md).</span></span>

<span data-ttu-id="3a3a7-130">ref 代入演算子 `= ref` の詳細については、[機能提案メモ](~/_csharplang/proposals/csharp-7.3/ref-local-reassignment.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3a3a7-130">For more information about the ref assignment operator `= ref`, see the [feature proposal note](~/_csharplang/proposals/csharp-7.3/ref-local-reassignment.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="3a3a7-131">参照</span><span class="sxs-lookup"><span data-stu-id="3a3a7-131">See also</span></span>

- [<span data-ttu-id="3a3a7-132">C# リファレンス</span><span class="sxs-lookup"><span data-stu-id="3a3a7-132">C# reference</span></span>](../index.md)
- [<span data-ttu-id="3a3a7-133">C# 演算子</span><span class="sxs-lookup"><span data-stu-id="3a3a7-133">C# operators</span></span>](index.md)
- [<span data-ttu-id="3a3a7-134">ref キーワード</span><span class="sxs-lookup"><span data-stu-id="3a3a7-134">ref keyword</span></span>](../keywords/ref.md)
