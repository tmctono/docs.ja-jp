---
title: goto ステートメント - C# リファレンス
ms.date: 07/20/2015
f1_keywords:
- goto_CSharpKeyword
- goto
helpviewer_keywords:
- goto keyword [C#]
ms.assetid: 2c03c9c1-8119-44ef-b740-fb3d287a42fe
ms.openlocfilehash: 076f793e880a7b4d1e8872d80e88c44cdf077541
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/14/2020
ms.locfileid: "75715272"
---
# <a name="goto-c-reference"></a><span data-ttu-id="368e7-102">goto (C# リファレンス)</span><span class="sxs-lookup"><span data-stu-id="368e7-102">goto (C# Reference)</span></span>

<span data-ttu-id="368e7-103">`goto` ステートメントは、プログラムの制御をラベル付きステートメントに直接移します。</span><span class="sxs-lookup"><span data-stu-id="368e7-103">The `goto` statement transfers the program control directly to a labeled statement.</span></span>

<span data-ttu-id="368e7-104">`goto` の一般的な用途は、特定の switch-case ラベルまたは `switch` ステートメントの既定のラベルに、制御を移動することです。</span><span class="sxs-lookup"><span data-stu-id="368e7-104">A common use of `goto` is to transfer control to a specific switch-case label or the default label in a `switch` statement.</span></span>

<span data-ttu-id="368e7-105">`goto` ステートメントは、深い入れ子のループから抜ける場合にも便利です。</span><span class="sxs-lookup"><span data-stu-id="368e7-105">The `goto` statement is also useful to get out of deeply nested loops.</span></span>

## <a name="example"></a><span data-ttu-id="368e7-106">例</span><span class="sxs-lookup"><span data-stu-id="368e7-106">Example</span></span>

<span data-ttu-id="368e7-107">次の例では、`goto`switch[ ステートメントでの ](switch.md) の使い方を示します。</span><span class="sxs-lookup"><span data-stu-id="368e7-107">The following example demonstrates using `goto` in a [switch](switch.md) statement.</span></span>

[!code-csharp[csrefKeywordsJump#4](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsJump/CS/csrefKeywordsJump.cs#4)]

## <a name="example"></a><span data-ttu-id="368e7-108">例</span><span class="sxs-lookup"><span data-stu-id="368e7-108">Example</span></span>

<span data-ttu-id="368e7-109">次の例では、`goto` を使って入れ子になったループから抜け出す方法を示します。</span><span class="sxs-lookup"><span data-stu-id="368e7-109">The following example demonstrates using `goto` to break out from nested loops.</span></span>

[!code-csharp[csrefKeywordsJump#5](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsJump/CS/csrefKeywordsJump.cs#5)]

## <a name="c-language-specification"></a><span data-ttu-id="368e7-110">C# 言語仕様</span><span class="sxs-lookup"><span data-stu-id="368e7-110">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="368e7-111">参照</span><span class="sxs-lookup"><span data-stu-id="368e7-111">See also</span></span>

- [<span data-ttu-id="368e7-112">C# リファレンス</span><span class="sxs-lookup"><span data-stu-id="368e7-112">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="368e7-113">C# プログラミングガイド</span><span class="sxs-lookup"><span data-stu-id="368e7-113">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="368e7-114">C# のキーワード</span><span class="sxs-lookup"><span data-stu-id="368e7-114">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="368e7-115">goto ステートメント (C++)</span><span class="sxs-lookup"><span data-stu-id="368e7-115">goto Statement (C++)</span></span>](/cpp/cpp/goto-statement-cpp)
