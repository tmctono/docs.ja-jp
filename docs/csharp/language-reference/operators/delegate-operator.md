---
title: delegate 演算子 - C# リファレンス
ms.date: 07/18/2019
helpviewer_keywords:
- delegate [C#]
- anonymous method [C#]
ms.openlocfilehash: 33c438b88f1e993f4648786da9b20b91961b7ee1
ms.sourcegitcommit: 7476c20d2f911a834a00b8a7f5e8926bae6804d9
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/11/2020
ms.locfileid: "88062991"
---
# <a name="delegate-operator-c-reference"></a><span data-ttu-id="64544-102">delegate 演算子 (C# リファレンス)</span><span class="sxs-lookup"><span data-stu-id="64544-102">delegate operator (C# reference)</span></span>

<span data-ttu-id="64544-103">`delegate` 演算子を使うと、デリゲート型に変換できる匿名メソッドを作成できます。</span><span class="sxs-lookup"><span data-stu-id="64544-103">The `delegate` operator creates an anonymous method that can be converted to a delegate type:</span></span>

[!code-csharp-interactive[anonymous method](snippets/shared/DelegateOperator.cs#AnonymousMethod)]

> [!NOTE]
> <span data-ttu-id="64544-104">C# 3 以降では、匿名関数を作成するためのより簡潔で表現性に優れた方法がラムダ式によって提供されています。</span><span class="sxs-lookup"><span data-stu-id="64544-104">Beginning with C# 3, lambda expressions provide a more concise and expressive way to create an anonymous function.</span></span> <span data-ttu-id="64544-105">ラムダ式を作成するには、[=> 演算子](lambda-operator.md)を使います。</span><span class="sxs-lookup"><span data-stu-id="64544-105">Use the [=> operator](lambda-operator.md) to construct a lambda expression:</span></span>
>
> [!code-csharp-interactive[lambda expression](snippets/shared/DelegateOperator.cs#Lambda)]
>
> <span data-ttu-id="64544-106">外部変数のキャプチャなど、ラムダ式の機能の詳細については、[ラムダ式](lambda-expressions.md)に関するページをご覧ください。</span><span class="sxs-lookup"><span data-stu-id="64544-106">For more information about features of lambda expressions, for example, capturing outer variables, see [Lambda expressions](lambda-expressions.md).</span></span>

<span data-ttu-id="64544-107">`delegate` 演算子を使用する際に、パラメーター リストを省略する場合があります。</span><span class="sxs-lookup"><span data-stu-id="64544-107">When you use the `delegate` operator, you might omit the parameter list.</span></span> <span data-ttu-id="64544-108">そうした場合、次の例に示すように、作成された匿名メソッドは任意のパラメーター リストを持つデリゲート型に変換できます。</span><span class="sxs-lookup"><span data-stu-id="64544-108">If you do that, the created anonymous method can be converted to a delegate type with any list of  parameters, as the following example shows:</span></span>

[!code-csharp-interactive[no parameter list](snippets/shared/DelegateOperator.cs#WithoutParameterList)]

<span data-ttu-id="64544-109">これは、ラムダ式でサポートされていない匿名メソッドの唯一の機能です。</span><span class="sxs-lookup"><span data-stu-id="64544-109">That's the only functionality of anonymous methods that is not supported by lambda expressions.</span></span> <span data-ttu-id="64544-110">それ以外の場合は、すべてラムダ式を使用してインライン コードを書くことをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="64544-110">In all other cases, a lambda expression is a preferred way to write inline code.</span></span>

<span data-ttu-id="64544-111">`delegate` キーワードは、[デリゲート型](../builtin-types/reference-types.md#the-delegate-type)を宣言するためにも使います。</span><span class="sxs-lookup"><span data-stu-id="64544-111">You also use the `delegate` keyword to declare a [delegate type](../builtin-types/reference-types.md#the-delegate-type).</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="64544-112">C# 言語仕様</span><span class="sxs-lookup"><span data-stu-id="64544-112">C# language specification</span></span>

<span data-ttu-id="64544-113">詳細については、「[C# 言語仕様](~/_csharplang/spec/introduction.md)」の[無名関数の式](~/_csharplang/spec/expressions.md#anonymous-function-expressions)に関するセクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="64544-113">For more information, see the [Anonymous function expressions](~/_csharplang/spec/expressions.md#anonymous-function-expressions) section of the [C# language specification](~/_csharplang/spec/introduction.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="64544-114">参照</span><span class="sxs-lookup"><span data-stu-id="64544-114">See also</span></span>

- [<span data-ttu-id="64544-115">C# リファレンス</span><span class="sxs-lookup"><span data-stu-id="64544-115">C# reference</span></span>](../index.md)
- [<span data-ttu-id="64544-116">C# の演算子と式</span><span class="sxs-lookup"><span data-stu-id="64544-116">C# operators and expressions</span></span>](index.md)
- [<span data-ttu-id="64544-117">=> 演算子</span><span class="sxs-lookup"><span data-stu-id="64544-117">=> operator</span></span>](lambda-operator.md)
