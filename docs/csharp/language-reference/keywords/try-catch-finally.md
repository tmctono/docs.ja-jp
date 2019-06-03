---
title: try-catch-finally - C# リファレンス
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- catch-finally_CSharpKeyword
- catch-finally
helpviewer_keywords:
- finally blocks [C#]
- try-catch statement [C#]
ms.assetid: a1b443b0-ff7a-43ab-b835-0cc9bfbd15ca
ms.openlocfilehash: 787005ec09a2c5c4f0e5033c83fd6a7ab7875b7e
ms.sourcegitcommit: 10986410e59ff29f2ec55c6759bde3eb4d1a00cb
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/31/2019
ms.locfileid: "66422156"
---
# <a name="try-catch-finally-c-reference"></a><span data-ttu-id="29f26-102">try-catch-finally (C# リファレンス)</span><span class="sxs-lookup"><span data-stu-id="29f26-102">try-catch-finally (C# Reference)</span></span>

<span data-ttu-id="29f26-103">通常、`catch` および `finally` は、`try` ブロックのリソースを取得して使用する場合に、対で記述されます。`catch` ブロックで例外的な状況を処理し、`finally` ブロックでリソースを解放します。</span><span class="sxs-lookup"><span data-stu-id="29f26-103">A common usage of `catch` and `finally` together is to obtain and use resources in a `try` block, deal with exceptional circumstances in a `catch` block, and release the resources in the `finally` block.</span></span>

 <span data-ttu-id="29f26-104">例外の再スローの使用例を含む詳細については、「[try-catch](try-catch.md)」および[例外のスロー](../../../standard/exceptions/index.md)に関するページをご覧ください。</span><span class="sxs-lookup"><span data-stu-id="29f26-104">For more information and examples on re-throwing exceptions, see [try-catch](try-catch.md) and [Throwing Exceptions](../../../standard/exceptions/index.md).</span></span> <span data-ttu-id="29f26-105">`finally` ブロックの詳細については、「[try-finally](try-finally.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="29f26-105">For more information about the `finally` block, see [try-finally](try-finally.md).</span></span>

## <a name="example"></a><span data-ttu-id="29f26-106">例</span><span class="sxs-lookup"><span data-stu-id="29f26-106">Example</span></span>

[!code-csharp[csrefKeywordsExceptions#1](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsExceptions/CS/csrefKeywordsExceptions.cs#1)]  

## <a name="c-language-specification"></a><span data-ttu-id="29f26-107">C# 言語仕様</span><span class="sxs-lookup"><span data-stu-id="29f26-107">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="29f26-108">関連項目</span><span class="sxs-lookup"><span data-stu-id="29f26-108">See also</span></span>

- [<span data-ttu-id="29f26-109">C# リファレンス</span><span class="sxs-lookup"><span data-stu-id="29f26-109">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="29f26-110">C# プログラミング ガイド</span><span class="sxs-lookup"><span data-stu-id="29f26-110">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="29f26-111">C# のキーワード</span><span class="sxs-lookup"><span data-stu-id="29f26-111">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="29f26-112">try、throw、catch ステートメント (C++)</span><span class="sxs-lookup"><span data-stu-id="29f26-112">try, throw, and catch Statements (C++)</span></span>](/cpp/cpp/try-throw-and-catch-statements-cpp)
- [<span data-ttu-id="29f26-113">throw</span><span class="sxs-lookup"><span data-stu-id="29f26-113">throw</span></span>](throw.md)
- [<span data-ttu-id="29f26-114">方法: 例外を明示的にスローする</span><span class="sxs-lookup"><span data-stu-id="29f26-114">How to: Explicitly Throw Exceptions</span></span>](../../../standard/exceptions/how-to-explicitly-throw-exceptions.md)
- [<span data-ttu-id="29f26-115">using ステートメント</span><span class="sxs-lookup"><span data-stu-id="29f26-115">using Statement</span></span>](using-statement.md)
