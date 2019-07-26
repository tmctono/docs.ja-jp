---
title: delegate 演算子 - C# リファレンス
ms.date: 07/18/2019
helpviewer_keywords:
- delegate [C#]
- anonymous method [C#]
ms.openlocfilehash: 1fe281776bd75d8fa869065cd24e85f04fec849d
ms.sourcegitcommit: 09d699aca28ae9723399bbd9d3d44aa0cbd3848d
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/19/2019
ms.locfileid: "68331831"
---
# <a name="delegate-operator-c-reference"></a><span data-ttu-id="549cd-102">delegate 演算子 (C# リファレンス)</span><span class="sxs-lookup"><span data-stu-id="549cd-102">delegate operator (C# reference)</span></span>

<span data-ttu-id="549cd-103">`delegate` 演算子を使うと、デリゲート型に変換できる匿名メソッドを作成できます。</span><span class="sxs-lookup"><span data-stu-id="549cd-103">The `delegate` operator creates an anonymous method that can be converted to a delegate type:</span></span>

[!code-csharp-interactive[anonymous method](~/samples/csharp/language-reference/operators/DelegateOperator.cs#AnonymousMethod)]

<span data-ttu-id="549cd-104">C# 3 からは、匿名関数を作成するためのより簡潔で表現性に優れた方法が[ラムダ式](../../programming-guide/statements-expressions-operators/lambda-expressions.md)によって提供されています。</span><span class="sxs-lookup"><span data-stu-id="549cd-104">Beginning with C# 3, [lambda expressions](../../programming-guide/statements-expressions-operators/lambda-expressions.md) provide a more concise and expressive way to create an anonymous function.</span></span> <span data-ttu-id="549cd-105">ラムダ式を作成するには、[=> 演算子](lambda-operator.md)を使います。</span><span class="sxs-lookup"><span data-stu-id="549cd-105">Use the [=> operator](lambda-operator.md) to construct a lambda expression:</span></span>

[!code-csharp-interactive[lambda expression](~/samples/csharp/language-reference/operators/DelegateOperator.cs#Lambda)]

<span data-ttu-id="549cd-106">`delegate` 演算子を使用する際に、パラメーター リストを省略する場合があります。</span><span class="sxs-lookup"><span data-stu-id="549cd-106">When you use the `delegate` operator, you might omit the parameter list.</span></span> <span data-ttu-id="549cd-107">そうした場合、次の例に示すように、作成された匿名メソッドは任意のパラメーター リストを持つデリゲート型に変換できます。</span><span class="sxs-lookup"><span data-stu-id="549cd-107">If you do that, the created anonymous method can be converted to a delegate type with any list of  parameters, as the following example shows:</span></span>

[!code-csharp-interactive[no parameter list](~/samples/csharp/language-reference/operators/DelegateOperator.cs#WithoutParameterList)]

<span data-ttu-id="549cd-108">これは、ラムダ式でサポートされていない匿名メソッドの唯一の機能です。</span><span class="sxs-lookup"><span data-stu-id="549cd-108">That's the only functionality of anonymous methods that is not supported by lambda expressions.</span></span> <span data-ttu-id="549cd-109">それ以外の場合は、すべてラムダ式を使用してインライン コードを書くことをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="549cd-109">In all other cases, a lambda expression is a preferred way to write inline code.</span></span> <span data-ttu-id="549cd-110">外部変数のキャプチャなど、ラムダ式の機能の詳細については、[ラムダ式](../../programming-guide/statements-expressions-operators/lambda-expressions.md)に関するページをご覧ください。</span><span class="sxs-lookup"><span data-stu-id="549cd-110">For more information about features of lambda expressions, for example, capturing outer variables, see [Lambda expressions](../../programming-guide/statements-expressions-operators/lambda-expressions.md).</span></span>

<span data-ttu-id="549cd-111">`delegate` キーワードは、[デリゲート型](../builtin-types/reference-types.md#the-delegate-type)を宣言するためにも使います。</span><span class="sxs-lookup"><span data-stu-id="549cd-111">You also use the `delegate` keyword to declare a [delegate type](../builtin-types/reference-types.md#the-delegate-type).</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="549cd-112">C# 言語仕様</span><span class="sxs-lookup"><span data-stu-id="549cd-112">C# language specification</span></span>

<span data-ttu-id="549cd-113">詳細については、「[C# 言語仕様](~/_csharplang/spec/introduction.md)」の[無名関数の式](~/_csharplang/spec/expressions.md#anonymous-function-expressions)に関するセクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="549cd-113">For more information, see the [Anonymous function expressions](~/_csharplang/spec/expressions.md#anonymous-function-expressions) section of the [C# language specification](~/_csharplang/spec/introduction.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="549cd-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="549cd-114">See also</span></span>

- [<span data-ttu-id="549cd-115">C# リファレンス</span><span class="sxs-lookup"><span data-stu-id="549cd-115">C# reference</span></span>](../index.md)
- [<span data-ttu-id="549cd-116">C# 演算子</span><span class="sxs-lookup"><span data-stu-id="549cd-116">C# operators</span></span>](index.md)
