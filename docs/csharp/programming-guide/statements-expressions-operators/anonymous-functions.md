---
title: 匿名関数 - C# プログラミング ガイド
description: 匿名関数について説明します。 ラムダ式または匿名メソッドを使って匿名関数を作成できます。
ms.date: 07/20/2015
helpviewer_keywords:
- lambda expressions [C#], as anonymous functions
- anonymous functions [C#]
- anonymous methods [C#]
ms.assetid: 6ce3f04d-0c71-4728-9127-634c7e9a8365
ms.openlocfilehash: 1fde7d535054f09d55018a010468776622ebfba7
ms.sourcegitcommit: 7476c20d2f911a834a00b8a7f5e8926bae6804d9
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/11/2020
ms.locfileid: "88063264"
---
# <a name="anonymous-functions-c-programming-guide"></a><span data-ttu-id="acdce-104">匿名関数 (C# プログラミング ガイド)</span><span class="sxs-lookup"><span data-stu-id="acdce-104">Anonymous functions (C# Programming Guide)</span></span>

<span data-ttu-id="acdce-105">匿名関数は、デリゲート型が必要とされる任意の場所で使用できる "インライン" のステートメントまたは式です。</span><span class="sxs-lookup"><span data-stu-id="acdce-105">An anonymous function is an "inline" statement or expression that can be used wherever a delegate type is expected.</span></span> <span data-ttu-id="acdce-106">名前付きデリゲートを初期化するときや、メソッドのパラメーターとして名前付きデリゲート型の代わりに渡したりするときに使用できます。</span><span class="sxs-lookup"><span data-stu-id="acdce-106">You can use it to initialize a named delegate or pass it instead of a named delegate type as a method parameter.</span></span>

<span data-ttu-id="acdce-107">[ラムダ式](../../language-reference/operators/lambda-expressions.md)または[匿名メソッド](../../language-reference/operators/delegate-operator.md)を使って匿名関数を作成できます。</span><span class="sxs-lookup"><span data-stu-id="acdce-107">You can use a [lambda expression](../../language-reference/operators/lambda-expressions.md) or an [anonymous method](../../language-reference/operators/delegate-operator.md) to create an anonymous function.</span></span> <span data-ttu-id="acdce-108">ラムダ式を使った方がより簡潔で表現性に優れた方法でインライン コードを記述できるため、こちらを使うことをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="acdce-108">We recommend using lambda expressions as they provide more concise and expressive way to write inline code.</span></span> <span data-ttu-id="acdce-109">匿名メソッドとは異なり、一部の型のラムダ式は式ツリー型に変換することができます。</span><span class="sxs-lookup"><span data-stu-id="acdce-109">Unlike anonymous methods, some types of lambda expressions can be converted to the expression tree types.</span></span>

## <a name="the-evolution-of-delegates-in-c"></a><span data-ttu-id="acdce-110">C\# のデリゲートの進化</span><span class="sxs-lookup"><span data-stu-id="acdce-110">The Evolution of Delegates in C\#</span></span>

 <span data-ttu-id="acdce-111">C# 1.0 では、コードのどこかで定義したメソッドを使用して明示的に初期化することで、デリゲートのインスタンスを作成していました。</span><span class="sxs-lookup"><span data-stu-id="acdce-111">In C# 1.0, you created an instance of a delegate by explicitly initializing it with a method that was defined elsewhere in the code.</span></span> <span data-ttu-id="acdce-112">C# 2.0 では、デリゲートの呼び出しで実行できる名前なしのインライン ステートメント ブロックを記述する方法として、匿名メソッドの概念が導入されました。</span><span class="sxs-lookup"><span data-stu-id="acdce-112">C# 2.0 introduced the concept of anonymous methods as a way to write unnamed inline statement blocks that can be executed in a delegate invocation.</span></span> <span data-ttu-id="acdce-113">C# 3.0 では、ラムダ式が導入されました。ラムダ式は、概念的には匿名メソッドと似ていますが、より表現力が豊かで簡潔です。</span><span class="sxs-lookup"><span data-stu-id="acdce-113">C# 3.0 introduced lambda expressions, which are similar in concept to anonymous methods but more expressive and concise.</span></span> <span data-ttu-id="acdce-114">これら 2 つの機能は総称として*匿名関数*と呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="acdce-114">These two features are known collectively as *anonymous functions*.</span></span> <span data-ttu-id="acdce-115">一般的に、.NET Framework 3.5 以降のバージョンを対象とするアプリケーションであれば、ラムダ式を使用することが推奨されます。</span><span class="sxs-lookup"><span data-stu-id="acdce-115">In general, applications that target .NET Framework 3.5 or later should use lambda expressions.</span></span>  
  
 <span data-ttu-id="acdce-116">次の例は、C# 1.0 から C# 3.0 のデリゲート作成の進化を示しています。</span><span class="sxs-lookup"><span data-stu-id="acdce-116">The following example demonstrates the evolution of delegate creation from C# 1.0 to C# 3.0:</span></span>  
  
 [!code-csharp[csProgGuideLINQ#65](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideLINQ/CS/csRef30LangFeatures_2.cs#65)]  
  
## <a name="c-language-specification"></a><span data-ttu-id="acdce-117">C# 言語仕様</span><span class="sxs-lookup"><span data-stu-id="acdce-117">C# language specification</span></span>

<span data-ttu-id="acdce-118">詳細については、「[C# 言語仕様](~/_csharplang/spec/introduction.md)」の[無名関数の式](~/_csharplang/spec/expressions.md#anonymous-function-expressions)に関するセクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="acdce-118">For more information, see the [Anonymous function expressions](~/_csharplang/spec/expressions.md#anonymous-function-expressions) section of the [C# language specification](~/_csharplang/spec/introduction.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="acdce-119">関連項目</span><span class="sxs-lookup"><span data-stu-id="acdce-119">See also</span></span>

- [<span data-ttu-id="acdce-120">ステートメント、式、および演算子</span><span class="sxs-lookup"><span data-stu-id="acdce-120">Statements, Expressions, and Operators</span></span>](./index.md)
- [<span data-ttu-id="acdce-121">ラムダ式</span><span class="sxs-lookup"><span data-stu-id="acdce-121">Lambda Expressions</span></span>](../../language-reference/operators/lambda-expressions.md)
- [<span data-ttu-id="acdce-122">デリゲート</span><span class="sxs-lookup"><span data-stu-id="acdce-122">Delegates</span></span>](../delegates/index.md)
- [<span data-ttu-id="acdce-123">式ツリー (C#)</span><span class="sxs-lookup"><span data-stu-id="acdce-123">Expression Trees (C#)</span></span>](../concepts/expression-trees/index.md)
