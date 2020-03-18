---
title: continue ステートメント - C# リファレンス
ms.date: 07/20/2015
f1_keywords:
- continue_CSharpKeyword
- continue
helpviewer_keywords:
- continue keyword [C#]
ms.assetid: 8a5ac96f-f98a-4519-b32d-345847ed7be0
ms.openlocfilehash: 83b43b31eacf0ed835ee3d7a919538eb9f1dd1e8
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/14/2020
ms.locfileid: "75713658"
---
# <a name="continue-c-reference"></a><span data-ttu-id="d8997-102">continue (C# リファレンス)</span><span class="sxs-lookup"><span data-stu-id="d8997-102">continue (C# Reference)</span></span>

<span data-ttu-id="d8997-103">`continue` ステートメントは、それを囲んでいる [while](./while.md)、[do](./do.md)、[for](./for.md)、または [foreach](./foreach-in.md) ステートメントの次の反復処理にコントロールを渡します。</span><span class="sxs-lookup"><span data-stu-id="d8997-103">The `continue` statement passes control to the next iteration of the enclosing [while](./while.md), [do](./do.md), [for](./for.md), or [foreach](./foreach-in.md) statement in which it appears.</span></span>

## <a name="example"></a><span data-ttu-id="d8997-104">例</span><span class="sxs-lookup"><span data-stu-id="d8997-104">Example</span></span>

<span data-ttu-id="d8997-105">この例では、1 から 10 までカウントするようカウンターが初期化されます。</span><span class="sxs-lookup"><span data-stu-id="d8997-105">In this example, a counter is initialized to count from 1 to 10.</span></span> <span data-ttu-id="d8997-106">`continue` ステートメントと式 `(i < 9)` を組み合わせて使用すると、`continue` 本文の `for` から終わりまでのステートメントがスキップされます。</span><span class="sxs-lookup"><span data-stu-id="d8997-106">By using the `continue` statement in conjunction with the expression `(i < 9)`, the statements between `continue` and the end of the `for` body are skipped.</span></span>

[!code-csharp[csrefKeywordsJump#3](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsJump/CS/csrefKeywordsJump.cs#3)]

## <a name="c-language-specification"></a><span data-ttu-id="d8997-107">C# 言語仕様</span><span class="sxs-lookup"><span data-stu-id="d8997-107">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="d8997-108">参照</span><span class="sxs-lookup"><span data-stu-id="d8997-108">See also</span></span>

- [<span data-ttu-id="d8997-109">C# リファレンス</span><span class="sxs-lookup"><span data-stu-id="d8997-109">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="d8997-110">C# プログラミングガイド</span><span class="sxs-lookup"><span data-stu-id="d8997-110">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="d8997-111">C# のキーワード</span><span class="sxs-lookup"><span data-stu-id="d8997-111">C# Keywords</span></span>](./index.md)
- [<span data-ttu-id="d8997-112">break ステートメント</span><span class="sxs-lookup"><span data-stu-id="d8997-112">break Statement</span></span>](/cpp/cpp/break-statement-cpp)
