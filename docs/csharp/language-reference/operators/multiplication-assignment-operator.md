---
title: '*= 演算子 - C# リファレンス'
ms.custom: seodec18
ms.date: 02/26/2019
f1_keywords:
- '*=_CSharpKeyword'
helpviewer_keywords:
- '*= operator [C#]'
- binary multiplication assignment operator (*=) [C#]
ms.assetid: 2e472155-59db-4dbf-bb94-bcccfa1a794d
ms.openlocfilehash: 70461f79e714e44354fe4137e5360769fa048d3e
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/28/2019
ms.locfileid: "56967387"
---
# <a name="-operator-c-reference"></a><span data-ttu-id="77e97-102">\*= 演算子 (C# リファレンス)</span><span class="sxs-lookup"><span data-stu-id="77e97-102">\*= Operator (C# Reference)</span></span>

<span data-ttu-id="77e97-103">乗算代入演算子です。</span><span class="sxs-lookup"><span data-stu-id="77e97-103">The multiplication assignment operator.</span></span>

<span data-ttu-id="77e97-104">次のような `*=` 演算子を使用する式があるとします</span><span class="sxs-lookup"><span data-stu-id="77e97-104">An expression using the `*=` operator, such as</span></span>

```csharp
x *= y
```

<span data-ttu-id="77e97-105">上記の式は、次の式と同じです。</span><span class="sxs-lookup"><span data-stu-id="77e97-105">is equivalent to</span></span>

```csharp
x = x * y
```

<span data-ttu-id="77e97-106">ただし、`x` が評価されるのは 1 回だけです。</span><span class="sxs-lookup"><span data-stu-id="77e97-106">except that `x` is only evaluated once.</span></span>

<span data-ttu-id="77e97-107">数値型の場合、[\* 演算子](multiplication-operator.md)によってそのオペランドの積が計算されます。</span><span class="sxs-lookup"><span data-stu-id="77e97-107">For numeric types, the [\* operator](multiplication-operator.md) computes the product of its operands.</span></span>

<span data-ttu-id="77e97-108">`*=` 演算子の使用例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="77e97-108">The following example demonstrates the usage of the `*=` operator:</span></span>

[!code-csharp-interactive[multiply and assign](~/samples/snippets/csharp/language-reference/operators/MultiplicationExamples.cs#MultiplyAndAssign)]

## <a name="operator-overloadability"></a><span data-ttu-id="77e97-109">演算子のオーバーロード可/不可</span><span class="sxs-lookup"><span data-stu-id="77e97-109">Operator overloadability</span></span>

<span data-ttu-id="77e97-110">ユーザー定義型により[乗算演算子](multiplication-operator.md) `*` が[オーバーロード](../keywords/operator.md)される場合、乗算代入演算子 `*=` は暗黙的にオーバーロードされます。</span><span class="sxs-lookup"><span data-stu-id="77e97-110">If a user-defined type [overloads](../keywords/operator.md) the [multiplication operator](multiplication-operator.md) `*`, the multiplication assignment operator `*=` is implicitly overloaded.</span></span> <span data-ttu-id="77e97-111">ユーザー定義型で乗算代入演算子を明示的にオーバー ロードすることはできません。</span><span class="sxs-lookup"><span data-stu-id="77e97-111">A user-defined type cannot explicitly overload the multiplication assignment operator.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="77e97-112">C# 言語仕様</span><span class="sxs-lookup"><span data-stu-id="77e97-112">C# language specification</span></span>

<span data-ttu-id="77e97-113">詳細については、「[C# 言語仕様](../language-specification/index.md)」の[複合代入](~/_csharplang/spec/expressions.md#compound-assignment)に関するセクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="77e97-113">For more information, see the [Compound assignment](~/_csharplang/spec/expressions.md#compound-assignment) section of the [C# language specification](../language-specification/index.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="77e97-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="77e97-114">See also</span></span>

- [<span data-ttu-id="77e97-115">C# リファレンス</span><span class="sxs-lookup"><span data-stu-id="77e97-115">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="77e97-116">C# プログラミングガイド</span><span class="sxs-lookup"><span data-stu-id="77e97-116">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="77e97-117">C# 演算子</span><span class="sxs-lookup"><span data-stu-id="77e97-117">C# Operators</span></span>](index.md)
