---
title: 既定値式 - C# リファレンス
description: 既定値式を使用して、型の既定値を取得します
ms.date: 03/13/2020
f1_keywords:
- default_CSharpKeyword
helpviewer_keywords:
- default keyword [C#]
ms.openlocfilehash: 92ad8e919567e1f9f57e6875d53c4055eb960829
ms.sourcegitcommit: e078b7540a8293ca1b604c9c0da1ff1506f0170b
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/13/2020
ms.locfileid: "91997640"
---
# <a name="default-value-expressions-c-reference"></a><span data-ttu-id="845bc-103">既定値式 (C# リファレンス)</span><span class="sxs-lookup"><span data-stu-id="845bc-103">default value expressions (C# reference)</span></span>

<span data-ttu-id="845bc-104">既定値式を使用すると、型の[既定値](../builtin-types/default-values.md)が生成されます。</span><span class="sxs-lookup"><span data-stu-id="845bc-104">A default value expression produces the [default value](../builtin-types/default-values.md) of a type.</span></span> <span data-ttu-id="845bc-105">既定値式には、次の 2 種類があります: [default 演算子](#default-operator)の呼び出しと、[default リテラル](#default-literal)です。</span><span class="sxs-lookup"><span data-stu-id="845bc-105">There are two kinds of default value expressions: the [default operator](#default-operator) call and a [default literal](#default-literal).</span></span>

<span data-ttu-id="845bc-106">また、[`switch` ステートメント](../keywords/switch.md)内の既定の case ラベルとして、`default` キーワードを使うこともできます。</span><span class="sxs-lookup"><span data-stu-id="845bc-106">You also use the `default` keyword as the default case label within a [`switch` statement](../keywords/switch.md).</span></span>

## <a name="default-operator"></a><span data-ttu-id="845bc-107">default 演算子</span><span class="sxs-lookup"><span data-stu-id="845bc-107">default operator</span></span>

<span data-ttu-id="845bc-108">`default` 演算子への引数では、次の例で示すように、型または型パラメーターの名前を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="845bc-108">The argument to the `default` operator must be the name of a type or a type parameter, as the following example shows:</span></span>

[!code-csharp-interactive[default of T](snippets/shared/DefaultOperator.cs#WithOperand)]

## <a name="default-literal"></a><span data-ttu-id="845bc-109">default リテラル</span><span class="sxs-lookup"><span data-stu-id="845bc-109">default literal</span></span>

<span data-ttu-id="845bc-110">C# 7.1 以降では、`default` リテラルを使って、コンパイラが式の型を推論できる場合に、型の既定値を生成できます。</span><span class="sxs-lookup"><span data-stu-id="845bc-110">Beginning with C# 7.1, you can use the `default` literal to produce the default value of a type when the compiler can infer the expression type.</span></span> <span data-ttu-id="845bc-111">`default` リテラル式では、`T` が推定型である式 `default(T)` と同じ値が生成されます。</span><span class="sxs-lookup"><span data-stu-id="845bc-111">The `default` literal expression produces the same value as the `default(T)` expression where `T` is the inferred type.</span></span> <span data-ttu-id="845bc-112">`default` リテラルは、次のいずれの場合でも使用できます。</span><span class="sxs-lookup"><span data-stu-id="845bc-112">You can use the `default` literal in any of the following cases:</span></span>

- <span data-ttu-id="845bc-113">変数の代入または初期化。</span><span class="sxs-lookup"><span data-stu-id="845bc-113">In the assignment or initialization of a variable.</span></span>
- <span data-ttu-id="845bc-114">[省略可能なメソッド パラメーター](../../methods.md#optional-parameters-and-arguments)の既定値の宣言。</span><span class="sxs-lookup"><span data-stu-id="845bc-114">In the declaration of the default value for an [optional method parameter](../../methods.md#optional-parameters-and-arguments).</span></span>
- <span data-ttu-id="845bc-115">メソッド呼び出しでの引数値の指定。</span><span class="sxs-lookup"><span data-stu-id="845bc-115">In a method call to provide an argument value.</span></span>
- <span data-ttu-id="845bc-116">[`return` ステートメント](../keywords/return.md)内、または[式のようなメンバー](../../programming-guide/statements-expressions-operators/expression-bodied-members.md)内の式として。</span><span class="sxs-lookup"><span data-stu-id="845bc-116">In a [`return` statement](../keywords/return.md) or as an expression in an [expression-bodied member](../../programming-guide/statements-expressions-operators/expression-bodied-members.md).</span></span>

<span data-ttu-id="845bc-117">`default` リテラルの使い方の例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="845bc-117">The following example shows the usage of the `default` literal:</span></span>

[!code-csharp-interactive[default literal](snippets/shared/DefaultOperator.cs#DefaultLiteral)]

## <a name="c-language-specification"></a><span data-ttu-id="845bc-118">C# 言語仕様</span><span class="sxs-lookup"><span data-stu-id="845bc-118">C# language specification</span></span>

<span data-ttu-id="845bc-119">詳細については、「[C# 言語仕様](~/_csharplang/spec/introduction.md)」の「[既定値の式](~/_csharplang/spec/expressions.md#default-value-expressions)」セクションをご覧ください。</span><span class="sxs-lookup"><span data-stu-id="845bc-119">For more information, see the [Default value expressions](~/_csharplang/spec/expressions.md#default-value-expressions) section of the [C# language specification](~/_csharplang/spec/introduction.md).</span></span>

<span data-ttu-id="845bc-120">`default` リテラルについて詳しくは、[機能提案メモ](~/_csharplang/proposals/csharp-7.1/target-typed-default.md)をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="845bc-120">For more information about the `default` literal, see the [feature proposal note](~/_csharplang/proposals/csharp-7.1/target-typed-default.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="845bc-121">関連項目</span><span class="sxs-lookup"><span data-stu-id="845bc-121">See also</span></span>

- [<span data-ttu-id="845bc-122">C# リファレンス</span><span class="sxs-lookup"><span data-stu-id="845bc-122">C# reference</span></span>](../index.md)
- [<span data-ttu-id="845bc-123">C# の演算子と式</span><span class="sxs-lookup"><span data-stu-id="845bc-123">C# operators and expressions</span></span>](index.md)
- [<span data-ttu-id="845bc-124">C# 型の既定値</span><span class="sxs-lookup"><span data-stu-id="845bc-124">Default values of C# types</span></span>](../builtin-types/default-values.md)
- [<span data-ttu-id="845bc-125">.NET のジェネリック</span><span class="sxs-lookup"><span data-stu-id="845bc-125">Generics in .NET</span></span>](../../../standard/generics/index.md)
