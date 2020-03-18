---
title: default 演算子 - C# リファレンス
description: 型の既定値を生成するには、default 演算子を使います
ms.date: 08/01/2019
helpviewer_keywords:
- default keyword [C#]
ms.openlocfilehash: 0d37fe952e71e74f014872231a2e58663dea9d18
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/14/2020
ms.locfileid: "79398185"
---
# <a name="default-operator-c-reference"></a><span data-ttu-id="67e1f-103">default 演算子 (C# リファレンス)</span><span class="sxs-lookup"><span data-stu-id="67e1f-103">default operator (C# reference)</span></span>

<span data-ttu-id="67e1f-104">`default` 演算子では、型の[既定値](../builtin-types/default-values.md)が生成されます。</span><span class="sxs-lookup"><span data-stu-id="67e1f-104">The `default` operator produces the [default value](../builtin-types/default-values.md) of a type.</span></span> <span data-ttu-id="67e1f-105">`default` 演算子への引数では、型または型パラメーターの名前を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="67e1f-105">The argument to the `default` operator must be the name of a type or a type parameter.</span></span>

<span data-ttu-id="67e1f-106">`default` 演算子の使い方を次の例に示します。</span><span class="sxs-lookup"><span data-stu-id="67e1f-106">The following example shows the usage of the `default` operator:</span></span>

[!code-csharp-interactive[default of T](snippets/DefaultOperator.cs#WithOperand)]

<span data-ttu-id="67e1f-107">また、`default`[ ステートメント`switch`内の既定の case ラベルとして、](../keywords/switch.md) キーワードを使うこともできます。</span><span class="sxs-lookup"><span data-stu-id="67e1f-107">You also use the `default` keyword as the default case label within a [`switch` statement](../keywords/switch.md).</span></span>

## <a name="default-literal"></a><span data-ttu-id="67e1f-108">default リテラル</span><span class="sxs-lookup"><span data-stu-id="67e1f-108">default literal</span></span>

<span data-ttu-id="67e1f-109">C# 7.1 以降では、`default` リテラルを使って、コンパイラが式の型を推論できる場合に、型の既定値を生成できます。</span><span class="sxs-lookup"><span data-stu-id="67e1f-109">Beginning with C# 7.1, you can use the `default` literal to produce the default value of a type when the compiler can infer the expression type.</span></span> <span data-ttu-id="67e1f-110">`default` リテラル式では、`default(T)` が推定型である式 `T` と同じ値が生成されます。</span><span class="sxs-lookup"><span data-stu-id="67e1f-110">The `default` literal expression produces the same value as the `default(T)` expression where `T` is the inferred type.</span></span> <span data-ttu-id="67e1f-111">`default` リテラルは、次のいずれの場合でも使用できます。</span><span class="sxs-lookup"><span data-stu-id="67e1f-111">You can use the `default` literal in any of the following cases:</span></span>

- <span data-ttu-id="67e1f-112">変数の代入または初期化。</span><span class="sxs-lookup"><span data-stu-id="67e1f-112">In the assignment or initialization of a variable.</span></span>
- <span data-ttu-id="67e1f-113">[省略可能なメソッド パラメーター](../../methods.md#optional-parameters-and-arguments)の既定値の宣言。</span><span class="sxs-lookup"><span data-stu-id="67e1f-113">In the declaration of the default value for an [optional method parameter](../../methods.md#optional-parameters-and-arguments).</span></span>
- <span data-ttu-id="67e1f-114">メソッド呼び出しでの引数値の指定。</span><span class="sxs-lookup"><span data-stu-id="67e1f-114">In a method call to provide an argument value.</span></span>
- <span data-ttu-id="67e1f-115">[`return` ステートメント](../keywords/return.md)内、または[式のようなメンバー](../../programming-guide/statements-expressions-operators/expression-bodied-members.md)内の式として。</span><span class="sxs-lookup"><span data-stu-id="67e1f-115">In a [`return` statement](../keywords/return.md) or as an expression in an [expression-bodied member](../../programming-guide/statements-expressions-operators/expression-bodied-members.md).</span></span>

<span data-ttu-id="67e1f-116">`default` リテラルの使い方の例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="67e1f-116">The following example shows the usage of the `default` literal:</span></span>

[!code-csharp-interactive[default literal](snippets/DefaultOperator.cs#DefaultLiteral)]

## <a name="c-language-specification"></a><span data-ttu-id="67e1f-117">C# 言語仕様</span><span class="sxs-lookup"><span data-stu-id="67e1f-117">C# language specification</span></span>

<span data-ttu-id="67e1f-118">詳細については、「[C# 言語仕様](~/_csharplang/spec/expressions.md#default-value-expressions)」の「[既定値の式](~/_csharplang/spec/introduction.md)」セクションをご覧ください。</span><span class="sxs-lookup"><span data-stu-id="67e1f-118">For more information, see the [Default value expressions](~/_csharplang/spec/expressions.md#default-value-expressions) section of the [C# language specification](~/_csharplang/spec/introduction.md).</span></span>

<span data-ttu-id="67e1f-119">`default` リテラルについて詳しくは、[機能提案メモ](~/_csharplang/proposals/csharp-7.1/target-typed-default.md)をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="67e1f-119">For more information about the `default` literal, see the [feature proposal note](~/_csharplang/proposals/csharp-7.1/target-typed-default.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="67e1f-120">参照</span><span class="sxs-lookup"><span data-stu-id="67e1f-120">See also</span></span>

- [<span data-ttu-id="67e1f-121">C# リファレンス</span><span class="sxs-lookup"><span data-stu-id="67e1f-121">C# reference</span></span>](../index.md)
- [<span data-ttu-id="67e1f-122">C# 演算子</span><span class="sxs-lookup"><span data-stu-id="67e1f-122">C# operators</span></span>](index.md)
- [<span data-ttu-id="67e1f-123">C# 型の既定値</span><span class="sxs-lookup"><span data-stu-id="67e1f-123">Default values of C# types</span></span>](../builtin-types/default-values.md)
- [<span data-ttu-id="67e1f-124">.NET のジェネリック</span><span class="sxs-lookup"><span data-stu-id="67e1f-124">Generics in .NET</span></span>](../../../standard/generics/index.md)
