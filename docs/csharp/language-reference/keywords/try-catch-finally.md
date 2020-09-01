---
description: try-catch-finally - C# リファレンス
title: try-catch-finally - C# リファレンス
ms.date: 07/20/2015
f1_keywords:
- catch-finally_CSharpKeyword
- catch-finally
helpviewer_keywords:
- finally blocks [C#]
- try-catch statement [C#]
ms.assetid: a1b443b0-ff7a-43ab-b835-0cc9bfbd15ca
ms.openlocfilehash: 6e85330e12c53e0728ef671530709748090ebe02
ms.sourcegitcommit: d579fb5e4b46745fd0f1f8874c94c6469ce58604
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/30/2020
ms.locfileid: "89142012"
---
# <a name="try-catch-finally-c-reference"></a><span data-ttu-id="37548-103">try-catch-finally (C# リファレンス)</span><span class="sxs-lookup"><span data-stu-id="37548-103">try-catch-finally (C# Reference)</span></span>

<span data-ttu-id="37548-104">通常、`catch` および `finally` は、`try` ブロックのリソースを取得して使用する場合に、対で記述されます。`catch` ブロックで例外的な状況を処理し、`finally` ブロックでリソースを解放します。</span><span class="sxs-lookup"><span data-stu-id="37548-104">A common usage of `catch` and `finally` together is to obtain and use resources in a `try` block, deal with exceptional circumstances in a `catch` block, and release the resources in the `finally` block.</span></span>

 <span data-ttu-id="37548-105">例外の再スローの使用例を含む詳細については、「[try-catch](try-catch.md)」および[例外のスロー](../../../standard/exceptions/index.md)に関するページをご覧ください。</span><span class="sxs-lookup"><span data-stu-id="37548-105">For more information and examples on re-throwing exceptions, see [try-catch](try-catch.md) and [Throwing Exceptions](../../../standard/exceptions/index.md).</span></span> <span data-ttu-id="37548-106">`finally` ブロックの詳細については、「[try-finally](try-finally.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="37548-106">For more information about the `finally` block, see [try-finally](try-finally.md).</span></span>

## <a name="example"></a><span data-ttu-id="37548-107">例</span><span class="sxs-lookup"><span data-stu-id="37548-107">Example</span></span>

[!code-csharp[csrefKeywordsExceptions#1](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsExceptions/CS/csrefKeywordsExceptions.cs#1)]  

## <a name="c-language-specification"></a><span data-ttu-id="37548-108">C# 言語仕様</span><span class="sxs-lookup"><span data-stu-id="37548-108">C# language specification</span></span>

<span data-ttu-id="37548-109">詳細については、「[C# 言語仕様](~/_csharplang/spec/introduction.md)」の「[try ステートメント](~/_csharplang/spec/statements.md#the-try-statement)」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="37548-109">For more information, see [The try statement](~/_csharplang/spec/statements.md#the-try-statement) section of the [C# language specification](~/_csharplang/spec/introduction.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="37548-110">関連項目</span><span class="sxs-lookup"><span data-stu-id="37548-110">See also</span></span>

- [<span data-ttu-id="37548-111">C# リファレンス</span><span class="sxs-lookup"><span data-stu-id="37548-111">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="37548-112">C# プログラミング ガイド</span><span class="sxs-lookup"><span data-stu-id="37548-112">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="37548-113">C# のキーワード</span><span class="sxs-lookup"><span data-stu-id="37548-113">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="37548-114">try、throw、catch ステートメント (C++)</span><span class="sxs-lookup"><span data-stu-id="37548-114">try, throw, and catch Statements (C++)</span></span>](/cpp/cpp/try-throw-and-catch-statements-cpp)
- [<span data-ttu-id="37548-115">throw</span><span class="sxs-lookup"><span data-stu-id="37548-115">throw</span></span>](throw.md)
- [<span data-ttu-id="37548-116">方法: 例外を明示的にスローする</span><span class="sxs-lookup"><span data-stu-id="37548-116">How to: Explicitly Throw Exceptions</span></span>](../../../standard/exceptions/how-to-explicitly-throw-exceptions.md)
- [<span data-ttu-id="37548-117">using ステートメント</span><span class="sxs-lookup"><span data-stu-id="37548-117">using Statement</span></span>](using-statement.md)
