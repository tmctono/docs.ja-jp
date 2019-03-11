---
title: = 演算子 - C# リファレンス
ms.custom: seodec18
ms.date: 11/26/2018
f1_keywords:
- =_CSharpKeyword
helpviewer_keywords:
- = operator [C#]
ms.assetid: d802a6d5-32f0-42b8-b180-12f5a081bfc1
ms.openlocfilehash: 40dc844f2a4b6411ea82aa2f029b36d7dd8f6e5a
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/09/2019
ms.locfileid: "57716319"
---
# <a name="-operator-c-reference"></a><span data-ttu-id="6121a-102">= 演算子 (C# リファレンス)</span><span class="sxs-lookup"><span data-stu-id="6121a-102">= Operator (C# Reference)</span></span>

<span data-ttu-id="6121a-103">代入演算子 `=` は、右辺オペランドの値を、左辺オペランドに指定された変数、[プロパティ](../../programming-guide/classes-and-structs/properties.md)、または[インデクサー](../../../csharp/programming-guide/indexers/index.md)要素に割り当てます。</span><span class="sxs-lookup"><span data-stu-id="6121a-103">The assignment operator `=` assigns the value of its right-hand operand to a variable, a [property](../../programming-guide/classes-and-structs/properties.md), or an [indexer](../../../csharp/programming-guide/indexers/index.md) element given by its left-hand operand.</span></span> <span data-ttu-id="6121a-104">代入式の結果は、左辺のオペランドに割り当てられる値です。</span><span class="sxs-lookup"><span data-stu-id="6121a-104">The result of an assignment expression is the value assigned to the left-hand operand.</span></span> <span data-ttu-id="6121a-105">右辺のオペランドの型は、左辺のオペランドの型と同じであるか、暗黙に変換できる必要があります。</span><span class="sxs-lookup"><span data-stu-id="6121a-105">The type of the right-hand operand must be the same as the type of the left-hand operand or implicitly convertible to it.</span></span>

<span data-ttu-id="6121a-106">代入演算子は右結合です。つまり、次の形式の式があるとします。</span><span class="sxs-lookup"><span data-stu-id="6121a-106">The assignment operator is right-associative, that is, an expression of the form</span></span>

```csharp
a = b = c
```

<span data-ttu-id="6121a-107">これが次のように評価されます。</span><span class="sxs-lookup"><span data-stu-id="6121a-107">is evaluated as</span></span>

```csharp
a = (b = c)
```

<span data-ttu-id="6121a-108">次の例では、ローカル変数、プロパティ、およびインデクサー要素に値を割り当てるための、代入演算子の使用方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="6121a-108">The following example demonstrates the usage of the assignment operator to assign values to a local variable, a property, and an indexer element:</span></span>

[!code-csharp-interactive[assignment operator](~/samples/snippets/csharp/language-reference/operators/AssignmentExamples.cs#Assignments)]

## <a name="ref-assignment-operator"></a><span data-ttu-id="6121a-109">ref 代入演算子</span><span class="sxs-lookup"><span data-stu-id="6121a-109">ref assignment operator</span></span>

<span data-ttu-id="6121a-110">C# 7.3 以降では、ref 代入演算子 `= ref` を使用して、[ref ローカル](../keywords/ref.md#ref-locals)変数または [ref 読み取り専用ローカル](../keywords/ref.md#ref-readonly-locals)変数を割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="6121a-110">Beginning with C# 7.3, you can use the ref assignment operator `= ref` to reassign a [ref local](../keywords/ref.md#ref-locals) or [ref readonly local](../keywords/ref.md#ref-readonly-locals) variable.</span></span> <span data-ttu-id="6121a-111">次の例は、ref 代入演算子の使用方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="6121a-111">The following example demonstrates the usage of the ref assignment operator:</span></span>

[!code-csharp[ref assignment operator](~/samples/snippets/csharp/language-reference/operators/AssignmentExamples.cs#RefAssignment)]

<span data-ttu-id="6121a-112">ref 代入演算子の場合、左辺オペランドの型と右辺オペランドの型が同じであることが必要です。</span><span class="sxs-lookup"><span data-stu-id="6121a-112">In the case of the ref assignment operator, the type of the left operand and the right operand must be the same.</span></span>

<span data-ttu-id="6121a-113">詳しくは、[機能提案メモ](../../../../_csharplang/proposals/csharp-7.3/ref-local-reassignment.md)をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="6121a-113">For more information, see the [feature proposal note](../../../../_csharplang/proposals/csharp-7.3/ref-local-reassignment.md).</span></span>

## <a name="operator-overloadability"></a><span data-ttu-id="6121a-114">演算子のオーバーロード可/不可</span><span class="sxs-lookup"><span data-stu-id="6121a-114">Operator overloadability</span></span>

<span data-ttu-id="6121a-115">ユーザー定義型は、代入演算子をオーバー ロードできません。</span><span class="sxs-lookup"><span data-stu-id="6121a-115">A user-defined type cannot overload the assignment operator.</span></span> <span data-ttu-id="6121a-116">ただし、ユーザー定義型は、別の型への暗黙的な変換を定義できます。</span><span class="sxs-lookup"><span data-stu-id="6121a-116">However, a user-defined type can define an implicit conversion to another type.</span></span> <span data-ttu-id="6121a-117">この方法により、ユーザー定義型の値を、別の型の変数、プロパティ、またはインデクサー要素に割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="6121a-117">That way, the value of a user-defined type can be assigned to a variable, a property, or an indexer element of another type.</span></span> <span data-ttu-id="6121a-118">詳しくは、[implicit](../keywords/implicit.md) キーワードに関する記事をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="6121a-118">For more information, see the [implicit](../keywords/implicit.md) keyword article.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="6121a-119">C# 言語仕様</span><span class="sxs-lookup"><span data-stu-id="6121a-119">C# language specification</span></span>

<span data-ttu-id="6121a-120">詳細については、「[C# 言語仕様](../language-specification/index.md)」の[単純な代入](~/_csharplang/spec/expressions.md#simple-assignment)に関するセクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="6121a-120">For more information, see the [Simple assignment](~/_csharplang/spec/expressions.md#simple-assignment) section of the [C# language specification](../language-specification/index.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="6121a-121">関連項目</span><span class="sxs-lookup"><span data-stu-id="6121a-121">See also</span></span>

- [<span data-ttu-id="6121a-122">C# リファレンス</span><span class="sxs-lookup"><span data-stu-id="6121a-122">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="6121a-123">C# プログラミングガイド</span><span class="sxs-lookup"><span data-stu-id="6121a-123">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="6121a-124">C# 演算子</span><span class="sxs-lookup"><span data-stu-id="6121a-124">C# Operators</span></span>](index.md)
- [<span data-ttu-id="6121a-125">ref キーワード</span><span class="sxs-lookup"><span data-stu-id="6121a-125">ref keyword</span></span>](../keywords/ref.md)
