---
title: true 演算子と false 演算子 - C# リファレンス
ms.date: 12/10/2018
helpviewer_keywords:
- false operator [C#]
- true operator [C#]
ms.assetid: 81a888fd-011e-4589-b242-6c261fea505e
ms.openlocfilehash: 5ccd08a348478902bbbac36e99acf7ffc1fc814b
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/14/2020
ms.locfileid: "78846220"
---
# <a name="true-and-false-operators-c-reference"></a><span data-ttu-id="c8509-102">true 演算子と false 演算子 (C# リファレンス)</span><span class="sxs-lookup"><span data-stu-id="c8509-102">true and false operators (C# reference)</span></span>

<span data-ttu-id="c8509-103">`true` 演算子は、オペランドが確実に true であることを示す[ブール](../builtin-types/bool.md)値 `true` を返します。</span><span class="sxs-lookup"><span data-stu-id="c8509-103">The `true` operator returns the [bool](../builtin-types/bool.md) value `true` to indicate that its operand is definitely true.</span></span> <span data-ttu-id="c8509-104">`false` 演算子は、オペランドが確実に false であることを示す `bool` 値 `true` を返します。</span><span class="sxs-lookup"><span data-stu-id="c8509-104">The `false` operator returns the `bool` value `true` to indicate that its operand is definitely false.</span></span> <span data-ttu-id="c8509-105">`true` および `false` 演算子が互いに補完することは保証されていません。</span><span class="sxs-lookup"><span data-stu-id="c8509-105">The `true` and `false` operators are not guaranteed to complement each other.</span></span> <span data-ttu-id="c8509-106">つまり、`true` と `false` 演算子の両方が同じオペランドに対して `bool` 値 `false` を返す場合があります。</span><span class="sxs-lookup"><span data-stu-id="c8509-106">That is, both the `true` and `false` operator might return the `bool` value `false` for the same operand.</span></span> <span data-ttu-id="c8509-107">ある型でこの 2 つの演算子の 1 つを定義する場合は、もう 1 つの演算子も定義する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c8509-107">If a type defines one of the two operators, it must also define another operator.</span></span>

> [!TIP]
> <span data-ttu-id="c8509-108">3 値ロジックをサポートする必要がある場合は、`bool?` 型を使用します。たとえば、3 値ブール型をサポートするデータベースを操作する場合などです。</span><span class="sxs-lookup"><span data-stu-id="c8509-108">Use the `bool?` type, if you need to support the three-valued logic (for example, when you work with databases that support a three-valued Boolean type).</span></span> <span data-ttu-id="c8509-109">C# には、`&` オペランドを使用して 3 値ロジックをサポートする `|` および `bool?` 演算子があります。</span><span class="sxs-lookup"><span data-stu-id="c8509-109">C# provides the `&` and `|` operators that support the three-valued logic with the `bool?` operands.</span></span> <span data-ttu-id="c8509-110">詳細については、「[Boolean logical operators (ブール論理演算子)](boolean-logical-operators.md#nullable-boolean-logical-operators)」記事の「[Nullable Boolean logical operators (null 許容論理演算子)](boolean-logical-operators.md)」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="c8509-110">For more information, see the [Nullable Boolean logical operators](boolean-logical-operators.md#nullable-boolean-logical-operators) section of the [Boolean logical operators](boolean-logical-operators.md) article.</span></span>

## <a name="boolean-expressions"></a><span data-ttu-id="c8509-111">ブール式</span><span class="sxs-lookup"><span data-stu-id="c8509-111">Boolean expressions</span></span>

<span data-ttu-id="c8509-112">`true` 演算子が定義された型は、[if](../keywords/if-else.md)、[do](../keywords/do.md)、[while](../keywords/while.md)、および [for](../keywords/for.md) ステートメントと、[条件演算子 `?:`](conditional-operator.md) の制御条件式の結果の型にすることができます。</span><span class="sxs-lookup"><span data-stu-id="c8509-112">A type with the defined `true` operator can be the type of a result of a controlling conditional expression in the [if](../keywords/if-else.md), [do](../keywords/do.md), [while](../keywords/while.md), and [for](../keywords/for.md) statements and in the [conditional operator `?:`](conditional-operator.md).</span></span> <span data-ttu-id="c8509-113">詳細については、「[C# 言語仕様](~/_csharplang/spec/expressions.md#boolean-expressions)」の[ブール型の式](~/_csharplang/spec/introduction.md)に関するセクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="c8509-113">For more information, see the [Boolean expressions](~/_csharplang/spec/expressions.md#boolean-expressions) section of the [C# language specification](~/_csharplang/spec/introduction.md).</span></span>

## <a name="user-defined-conditional-logical-operators"></a><span data-ttu-id="c8509-114">ユーザー定義の条件付き論理演算子</span><span class="sxs-lookup"><span data-stu-id="c8509-114">User-defined conditional logical operators</span></span>

<span data-ttu-id="c8509-115">`true` と `false` 演算子が定義された型によって、[論理 OR 演算子](operator-overloading.md) [ または](boolean-logical-operators.md#logical-or-operator-)論理 AND 演算子`|` [ が特定の方法で](boolean-logical-operators.md#logical-and-operator-)オーバーロード`&`される場合、[条件付き論理 OR 演算子](boolean-logical-operators.md#conditional-logical-or-operator-) `||` または [条件付き論理 AND 演算子](boolean-logical-operators.md#conditional-logical-and-operator-) `&&` を、それぞれ、その型のオペランドに対して評価することができます。</span><span class="sxs-lookup"><span data-stu-id="c8509-115">If a type with the defined `true` and `false` operators [overloads](operator-overloading.md) the [logical OR operator](boolean-logical-operators.md#logical-or-operator-) `|` or the [logical AND operator](boolean-logical-operators.md#logical-and-operator-) `&` in a certain way, the [conditional logical OR operator](boolean-logical-operators.md#conditional-logical-or-operator-) `||` or [conditional logical AND operator](boolean-logical-operators.md#conditional-logical-and-operator-) `&&`, respectively, can be evaluated for the operands of that type.</span></span> <span data-ttu-id="c8509-116">詳細については、「[C# 言語仕様](~/_csharplang/spec/expressions.md#user-defined-conditional-logical-operators)」の[ユーザー定義型条件論理演算子](~/_csharplang/spec/introduction.md)に関するセクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="c8509-116">For more information, see the [User-defined conditional logical operators](~/_csharplang/spec/expressions.md#user-defined-conditional-logical-operators) section of the [C# language specification](~/_csharplang/spec/introduction.md).</span></span>

## <a name="example"></a><span data-ttu-id="c8509-117">例</span><span class="sxs-lookup"><span data-stu-id="c8509-117">Example</span></span>

<span data-ttu-id="c8509-118">次の例では、`true` と `false` 演算子の両方を定義する型を示します。</span><span class="sxs-lookup"><span data-stu-id="c8509-118">The following example presents the type that defines both `true` and `false` operators.</span></span> <span data-ttu-id="c8509-119">この型により、論理 AND 演算子 `&` もオーバーロードされ、演算子 `&&` もその型のオペランドで評価できるようになります。</span><span class="sxs-lookup"><span data-stu-id="c8509-119">The type also overloads the logical AND operator `&` in such a way that the `&&` operator also can be evaluated for the operands of that type.</span></span>

[!code-csharp[true and false operators example](snippets/TrueFalseOperators.cs)]

<span data-ttu-id="c8509-120">`&&` 演算子のショートサーキット動作に注意してください。</span><span class="sxs-lookup"><span data-stu-id="c8509-120">Notice the short-circuiting behavior of the `&&` operator.</span></span> <span data-ttu-id="c8509-121">`GetFuelLaunchStatus` メソッドから `LaunchStatus.Red` が返されると、`&&` 演算子の右側のオペランドは評価されません。</span><span class="sxs-lookup"><span data-stu-id="c8509-121">When the `GetFuelLaunchStatus` method returns `LaunchStatus.Red`, the right-hand operand of the `&&` operator is not evaluated.</span></span> <span data-ttu-id="c8509-122">これは、`LaunchStatus.Red` が確実に false であるためです。</span><span class="sxs-lookup"><span data-stu-id="c8509-122">That is because `LaunchStatus.Red` is definitely false.</span></span> <span data-ttu-id="c8509-123">したがって、論理 AND の結果は右側のオペランドの値に依存しません。</span><span class="sxs-lookup"><span data-stu-id="c8509-123">Then the result of the logical AND doesn't depend on the value of the right-hand operand.</span></span> <span data-ttu-id="c8509-124">この例の出力は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="c8509-124">The output of the example is as follows:</span></span>

```console
Getting fuel launch status...
Wait!
```

## <a name="see-also"></a><span data-ttu-id="c8509-125">参照</span><span class="sxs-lookup"><span data-stu-id="c8509-125">See also</span></span>

- [<span data-ttu-id="c8509-126">C# リファレンス</span><span class="sxs-lookup"><span data-stu-id="c8509-126">C# reference</span></span>](../index.md)
- [<span data-ttu-id="c8509-127">C# 演算子</span><span class="sxs-lookup"><span data-stu-id="c8509-127">C# operators</span></span>](index.md)
