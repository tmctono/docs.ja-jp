---
title: 匿名関数 - C# プログラミング ガイド
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- lambda expressions [C#], as anonymous functions
- anonymous functions [C#]
- anonymous methods [C#]
ms.assetid: 6ce3f04d-0c71-4728-9127-634c7e9a8365
ms.openlocfilehash: 338f4b34a5de84d4ce2eb9e0bd6f4c9ebe360fa4
ms.sourcegitcommit: c7a7e1468bf0fa7f7065de951d60dfc8d5ba89f5
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/14/2019
ms.locfileid: "65584280"
---
# <a name="anonymous-functions-c-programming-guide"></a><span data-ttu-id="e48ce-102">匿名関数 (C# プログラミング ガイド)</span><span class="sxs-lookup"><span data-stu-id="e48ce-102">Anonymous Functions (C# Programming Guide)</span></span>
<span data-ttu-id="e48ce-103">匿名関数は、デリゲート型が必要とされる任意の場所で使用できる "インライン" のステートメントまたは式です。</span><span class="sxs-lookup"><span data-stu-id="e48ce-103">An anonymous function is an "inline" statement or expression that can be used wherever a delegate type is expected.</span></span> <span data-ttu-id="e48ce-104">名前付きデリゲートを初期化するときや、メソッドのパラメーターとして名前付きデリゲート型の代わりに渡したりするときに使用できます。</span><span class="sxs-lookup"><span data-stu-id="e48ce-104">You can use it to initialize a named delegate or pass it instead of a named delegate type as a method parameter.</span></span>  
  
 <span data-ttu-id="e48ce-105">ここでは、2 種類ある匿名関数について説明します。</span><span class="sxs-lookup"><span data-stu-id="e48ce-105">There are two kinds of anonymous functions, which are discussed individually in the following topics:</span></span>  
  
- <span data-ttu-id="e48ce-106">[ラムダ式](../../../csharp/programming-guide/statements-expressions-operators/lambda-expressions.md)</span><span class="sxs-lookup"><span data-stu-id="e48ce-106">[Lambda Expressions](../../../csharp/programming-guide/statements-expressions-operators/lambda-expressions.md).</span></span>  
  
- [<span data-ttu-id="e48ce-107">匿名メソッド</span><span class="sxs-lookup"><span data-stu-id="e48ce-107">Anonymous Methods</span></span>](../../../csharp/programming-guide/statements-expressions-operators/anonymous-methods.md)  
  
    > [!NOTE]
    >  <span data-ttu-id="e48ce-108">ラムダ式は、式ツリーとデリゲートにバインドできます。</span><span class="sxs-lookup"><span data-stu-id="e48ce-108">Lambda expressions can be bound to expression trees and also to delegates.</span></span>  
  
## <a name="the-evolution-of-delegates-in-c"></a><span data-ttu-id="e48ce-109">C\# のデリゲートの進化</span><span class="sxs-lookup"><span data-stu-id="e48ce-109">The Evolution of Delegates in C\#</span></span>
 <span data-ttu-id="e48ce-110">C# 1.0 では、コードのどこかで定義したメソッドを使用して明示的に初期化することで、デリゲートのインスタンスを作成していました。</span><span class="sxs-lookup"><span data-stu-id="e48ce-110">In C# 1.0, you created an instance of a delegate by explicitly initializing it with a method that was defined elsewhere in the code.</span></span> <span data-ttu-id="e48ce-111">C# 2.0 では、デリゲートの呼び出しで実行できる名前なしのインライン ステートメント ブロックを記述する方法として、匿名メソッドの概念が導入されました。</span><span class="sxs-lookup"><span data-stu-id="e48ce-111">C# 2.0 introduced the concept of anonymous methods as a way to write unnamed inline statement blocks that can be executed in a delegate invocation.</span></span> <span data-ttu-id="e48ce-112">C# 3.0 では、ラムダ式が導入されました。ラムダ式は、概念的には匿名メソッドと似ていますが、より表現力が豊かで簡潔です。</span><span class="sxs-lookup"><span data-stu-id="e48ce-112">C# 3.0 introduced lambda expressions, which are similar in concept to anonymous methods but more expressive and concise.</span></span> <span data-ttu-id="e48ce-113">これら 2 つの機能は総称として*匿名関数*と呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="e48ce-113">These two features are known collectively as *anonymous functions*.</span></span> <span data-ttu-id="e48ce-114">一般的に、バージョン 3.5 以降の .NET Framework をターゲットとするアプリケーションであれば、ラムダ式を使用することが推奨されます。</span><span class="sxs-lookup"><span data-stu-id="e48ce-114">In general, applications that target version 3.5 and later of the .NET Framework should use lambda expressions.</span></span>  
  
 <span data-ttu-id="e48ce-115">次の例は、C# 1.0 から C# 3.0 のデリゲート作成の進化を示しています。</span><span class="sxs-lookup"><span data-stu-id="e48ce-115">The following example demonstrates the evolution of delegate creation from C# 1.0 to C# 3.0:</span></span>  
  
 [!code-csharp[csProgGuideLINQ#65](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideLINQ/CS/csRef30LangFeatures_2.cs#65)]  
  
## <a name="c-language-specification"></a><span data-ttu-id="e48ce-116">C# 言語仕様</span><span class="sxs-lookup"><span data-stu-id="e48ce-116">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="e48ce-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="e48ce-117">See also</span></span>

- [<span data-ttu-id="e48ce-118">ステートメント、式、および演算子</span><span class="sxs-lookup"><span data-stu-id="e48ce-118">Statements, Expressions, and Operators</span></span>](../../../csharp/programming-guide/statements-expressions-operators/index.md)
- [<span data-ttu-id="e48ce-119">ラムダ式</span><span class="sxs-lookup"><span data-stu-id="e48ce-119">Lambda Expressions</span></span>](../../../csharp/programming-guide/statements-expressions-operators/lambda-expressions.md)
- [<span data-ttu-id="e48ce-120">デリゲート</span><span class="sxs-lookup"><span data-stu-id="e48ce-120">Delegates</span></span>](../../../csharp/programming-guide/delegates/index.md)
- [<span data-ttu-id="e48ce-121">式ツリー (C#)</span><span class="sxs-lookup"><span data-stu-id="e48ce-121">Expression Trees (C#)</span></span>](../concepts/expression-trees/index.md)
