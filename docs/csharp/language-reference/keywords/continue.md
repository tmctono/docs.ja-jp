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
ms.openlocfilehash: 6c70934c3b861e1a1433e5c0b95bb32e9d717c53
ms.sourcegitcommit: eb7e87496f42361b1da98562dd75b516c9d58bbc
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/09/2020
ms.locfileid: "91877653"
---
# <a name="continue-c-reference"></a><span data-ttu-id="dc322-103">continue (C# リファレンス)</span><span class="sxs-lookup"><span data-stu-id="dc322-103">continue (C# Reference)</span></span>

<span data-ttu-id="dc322-104">`continue` ステートメントは、それを囲んでいる [while](./while.md)、[do](./do.md)、[for](./for.md)、または [foreach](./foreach-in.md) ステートメントの次の反復処理にコントロールを渡します。</span><span class="sxs-lookup"><span data-stu-id="dc322-104">The `continue` statement passes control to the next iteration of the enclosing [while](./while.md), [do](./do.md), [for](./for.md), or [foreach](./foreach-in.md) statement in which it appears.</span></span>

## <a name="example"></a><span data-ttu-id="dc322-105">例</span><span class="sxs-lookup"><span data-stu-id="dc322-105">Example</span></span>

<span data-ttu-id="dc322-106">この例では、1 から 10 までカウントするようカウンターが初期化されます。</span><span class="sxs-lookup"><span data-stu-id="dc322-106">In this example, a counter is initialized to count from 1 to 10.</span></span> <span data-ttu-id="dc322-107">`continue` ステートメントと式 `(i < 9)` を組み合わせて使用すると、`for` 本文の `continue` から終わりまでのステートメントが、`i` が 9 未満のイテレーションではスキップされます。</span><span class="sxs-lookup"><span data-stu-id="dc322-107">By using the `continue` statement in conjunction with the expression `(i < 9)`, the statements between `continue` and the end of the `for` body are skipped in the iterations where `i` is less than 9.</span></span> <span data-ttu-id="dc322-108">`for` ループの最後の 2 つのイテレーション (i == 9 と i == 10) では、`continue` ステートメントは実行されず、`i` の値がコンソールに出力されます。</span><span class="sxs-lookup"><span data-stu-id="dc322-108">In the last two iterations of the `for` loop (where i == 9 and i == 10), the `continue` statement is not executed and the value of `i` is printed to the console.</span></span>

[!code-csharp[csrefKeywordsJump#3](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsJump/CS/csrefKeywordsJump.cs#3)]

## <a name="c-language-specification"></a><span data-ttu-id="dc322-109">C# 言語仕様</span><span class="sxs-lookup"><span data-stu-id="dc322-109">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="dc322-110">関連項目</span><span class="sxs-lookup"><span data-stu-id="dc322-110">See also</span></span>

- [<span data-ttu-id="dc322-111">C# リファレンス</span><span class="sxs-lookup"><span data-stu-id="dc322-111">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="dc322-112">C# プログラミング ガイド</span><span class="sxs-lookup"><span data-stu-id="dc322-112">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="dc322-113">C# のキーワード</span><span class="sxs-lookup"><span data-stu-id="dc322-113">C# Keywords</span></span>](./index.md)
- [<span data-ttu-id="dc322-114">break ステートメント</span><span class="sxs-lookup"><span data-stu-id="dc322-114">break Statement</span></span>](/cpp/cpp/break-statement-cpp)
