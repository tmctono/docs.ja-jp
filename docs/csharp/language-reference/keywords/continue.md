---
description: continue ステートメント - C# リファレンス
title: continue ステートメント - C# リファレンス
ms.date: 07/20/2015
f1_keywords:
- continue_CSharpKeyword
- continue
helpviewer_keywords:
- continue keyword [C#]
ms.assetid: 8a5ac96f-f98a-4519-b32d-345847ed7be0
ms.openlocfilehash: 76578b0ad7e2b969609fbf50df1f9ab7de6e5097
ms.sourcegitcommit: d579fb5e4b46745fd0f1f8874c94c6469ce58604
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/30/2020
ms.locfileid: "89128440"
---
# <a name="continue-c-reference"></a><span data-ttu-id="fabe7-103">continue (C# リファレンス)</span><span class="sxs-lookup"><span data-stu-id="fabe7-103">continue (C# Reference)</span></span>

<span data-ttu-id="fabe7-104">`continue` ステートメントは、それを囲んでいる [while](./while.md)、[do](./do.md)、[for](./for.md)、または [foreach](./foreach-in.md) ステートメントの次の反復処理にコントロールを渡します。</span><span class="sxs-lookup"><span data-stu-id="fabe7-104">The `continue` statement passes control to the next iteration of the enclosing [while](./while.md), [do](./do.md), [for](./for.md), or [foreach](./foreach-in.md) statement in which it appears.</span></span>

## <a name="example"></a><span data-ttu-id="fabe7-105">例</span><span class="sxs-lookup"><span data-stu-id="fabe7-105">Example</span></span>

<span data-ttu-id="fabe7-106">この例では、1 から 10 までカウントするようカウンターが初期化されます。</span><span class="sxs-lookup"><span data-stu-id="fabe7-106">In this example, a counter is initialized to count from 1 to 10.</span></span> <span data-ttu-id="fabe7-107">`continue` ステートメントと式 `(i < 9)` を組み合わせて使用すると、`for` 本文の `continue` から終わりまでのステートメントがスキップされます。</span><span class="sxs-lookup"><span data-stu-id="fabe7-107">By using the `continue` statement in conjunction with the expression `(i < 9)`, the statements between `continue` and the end of the `for` body are skipped.</span></span>

[!code-csharp[csrefKeywordsJump#3](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsJump/CS/csrefKeywordsJump.cs#3)]

## <a name="c-language-specification"></a><span data-ttu-id="fabe7-108">C# 言語仕様</span><span class="sxs-lookup"><span data-stu-id="fabe7-108">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="fabe7-109">関連項目</span><span class="sxs-lookup"><span data-stu-id="fabe7-109">See also</span></span>

- [<span data-ttu-id="fabe7-110">C# リファレンス</span><span class="sxs-lookup"><span data-stu-id="fabe7-110">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="fabe7-111">C# プログラミング ガイド</span><span class="sxs-lookup"><span data-stu-id="fabe7-111">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="fabe7-112">C# のキーワード</span><span class="sxs-lookup"><span data-stu-id="fabe7-112">C# Keywords</span></span>](./index.md)
- [<span data-ttu-id="fabe7-113">break ステートメント</span><span class="sxs-lookup"><span data-stu-id="fabe7-113">break Statement</span></span>](/cpp/cpp/break-statement-cpp)
