---
description: goto ステートメント - C# リファレンス
title: goto ステートメント - C# リファレンス
ms.date: 07/20/2015
f1_keywords:
- goto_CSharpKeyword
- goto
helpviewer_keywords:
- goto keyword [C#]
ms.assetid: 2c03c9c1-8119-44ef-b740-fb3d287a42fe
ms.openlocfilehash: de95e477bd7e76f549130643c8d4b70a0e2f015c
ms.sourcegitcommit: d579fb5e4b46745fd0f1f8874c94c6469ce58604
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/30/2020
ms.locfileid: "89128427"
---
# <a name="goto-c-reference"></a><span data-ttu-id="0d33d-103">goto (C# リファレンス)</span><span class="sxs-lookup"><span data-stu-id="0d33d-103">goto (C# Reference)</span></span>

<span data-ttu-id="0d33d-104">`goto` ステートメントは、プログラムの制御をラベル付きステートメントに直接移します。</span><span class="sxs-lookup"><span data-stu-id="0d33d-104">The `goto` statement transfers the program control directly to a labeled statement.</span></span>

<span data-ttu-id="0d33d-105">`goto` の一般的な用途は、特定の switch-case ラベルまたは `switch` ステートメントの既定のラベルに、制御を移動することです。</span><span class="sxs-lookup"><span data-stu-id="0d33d-105">A common use of `goto` is to transfer control to a specific switch-case label or the default label in a `switch` statement.</span></span>

<span data-ttu-id="0d33d-106">`goto` ステートメントは、深い入れ子のループから抜ける場合にも便利です。</span><span class="sxs-lookup"><span data-stu-id="0d33d-106">The `goto` statement is also useful to get out of deeply nested loops.</span></span>

## <a name="example"></a><span data-ttu-id="0d33d-107">例</span><span class="sxs-lookup"><span data-stu-id="0d33d-107">Example</span></span>

<span data-ttu-id="0d33d-108">次の例では、[switch](switch.md) ステートメントでの `goto` の使い方を示します。</span><span class="sxs-lookup"><span data-stu-id="0d33d-108">The following example demonstrates using `goto` in a [switch](switch.md) statement.</span></span>

[!code-csharp[csrefKeywordsJump#4](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsJump/CS/csrefKeywordsJump.cs#4)]

## <a name="example"></a><span data-ttu-id="0d33d-109">例</span><span class="sxs-lookup"><span data-stu-id="0d33d-109">Example</span></span>

<span data-ttu-id="0d33d-110">次の例では、`goto` を使って入れ子になったループから抜け出す方法を示します。</span><span class="sxs-lookup"><span data-stu-id="0d33d-110">The following example demonstrates using `goto` to break out from nested loops.</span></span>

[!code-csharp[csrefKeywordsJump#5](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsJump/CS/csrefKeywordsJump.cs#5)]

## <a name="c-language-specification"></a><span data-ttu-id="0d33d-111">C# 言語仕様</span><span class="sxs-lookup"><span data-stu-id="0d33d-111">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="0d33d-112">関連項目</span><span class="sxs-lookup"><span data-stu-id="0d33d-112">See also</span></span>

- [<span data-ttu-id="0d33d-113">C# リファレンス</span><span class="sxs-lookup"><span data-stu-id="0d33d-113">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="0d33d-114">C# プログラミング ガイド</span><span class="sxs-lookup"><span data-stu-id="0d33d-114">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="0d33d-115">C# のキーワード</span><span class="sxs-lookup"><span data-stu-id="0d33d-115">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="0d33d-116">goto ステートメント (C++)</span><span class="sxs-lookup"><span data-stu-id="0d33d-116">goto Statement (C++)</span></span>](/cpp/cpp/goto-statement-cpp)
