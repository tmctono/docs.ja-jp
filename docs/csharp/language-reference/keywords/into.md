---
title: into - C# リファレンス
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- into_CSharpKeyword
- into
helpviewer_keywords:
- into keyword [C#]
ms.assetid: 81ec62c1-f0b1-4755-8a31-959876e77f65
ms.openlocfilehash: dc1e2ee004c21bb3d05155eec3e42ea80bf641a1
ms.sourcegitcommit: 986f836f72ef10876878bd6217174e41464c145a
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/19/2019
ms.locfileid: "69608636"
---
# <a name="into-c-reference"></a><span data-ttu-id="5e975-102">into (C# リファレンス)</span><span class="sxs-lookup"><span data-stu-id="5e975-102">into (C# Reference)</span></span>

<span data-ttu-id="5e975-103">`into` コンテキスト キーワードは、[group](group-clause.md)、[join](join-clause.md)、または [select](select-clause.md) 句の結果を新しい識別子に保存するための一時的な識別子を作成するために使用できます。</span><span class="sxs-lookup"><span data-stu-id="5e975-103">The `into` contextual keyword can be used to create a temporary identifier to store the results of a [group](group-clause.md), [join](join-clause.md) or [select](select-clause.md) clause into a new identifier.</span></span> <span data-ttu-id="5e975-104">この識別子自体を追加のクエリ コマンドのジェネレーターにすることができます。</span><span class="sxs-lookup"><span data-stu-id="5e975-104">This identifier can itself be a generator for additional query commands.</span></span> <span data-ttu-id="5e975-105">`group` または `select` 句で使用する場合、新しい識別子の使用は*継続*と呼ばれることもあります。</span><span class="sxs-lookup"><span data-stu-id="5e975-105">When used in a `group` or `select` clause, the use of the new identifier is sometimes referred to as a *continuation*.</span></span>

## <a name="example"></a><span data-ttu-id="5e975-106">例</span><span class="sxs-lookup"><span data-stu-id="5e975-106">Example</span></span>

<span data-ttu-id="5e975-107">次の例では、`into` キーワードを使用して、推定の型 `IGrouping` を持つ一時的な識別子 `fruitGroup` を有効にする方法を示します。</span><span class="sxs-lookup"><span data-stu-id="5e975-107">The following example shows the use of the `into` keyword to enable a temporary identifier `fruitGroup` which has an inferred type of `IGrouping`.</span></span> <span data-ttu-id="5e975-108">識別子を使用すると、各グループに対して <xref:System.Linq.Enumerable.Count%2A> メソッドを呼び出し、2 つ以上の単語を含むグループのみを選択することができます。</span><span class="sxs-lookup"><span data-stu-id="5e975-108">By using the identifier, you can invoke the <xref:System.Linq.Enumerable.Count%2A> method on each group and select only those groups that contain two or more words.</span></span>

[!code-csharp[cscsrefQueryKeywords#18](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsCsrefQueryKeywords/CS/Into.cs#18)]

<span data-ttu-id="5e975-109">`group` 句での `into` の使用は、各グループに対して追加のクエリ操作を実行する場合にのみ必要です。</span><span class="sxs-lookup"><span data-stu-id="5e975-109">The use of `into` in a `group` clause is only necessary when you want to perform additional query operations on each group.</span></span> <span data-ttu-id="5e975-110">詳しくは、「[group 句](group-clause.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="5e975-110">For more information, see [group clause](group-clause.md).</span></span>

<span data-ttu-id="5e975-111">`join` 句での `into` の使用例については、「[join 句](join-clause.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5e975-111">For an example of the use of `into` in a `join` clause, see [join clause](join-clause.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="5e975-112">関連項目</span><span class="sxs-lookup"><span data-stu-id="5e975-112">See also</span></span>

- [<span data-ttu-id="5e975-113">クエリ キーワード (LINQ)</span><span class="sxs-lookup"><span data-stu-id="5e975-113">Query Keywords (LINQ)</span></span>](query-keywords.md)
- [<span data-ttu-id="5e975-114">LINQ クエリ式</span><span class="sxs-lookup"><span data-stu-id="5e975-114">LINQ Query Expressions</span></span>](../../programming-guide/linq-query-expressions/index.md)
- [<span data-ttu-id="5e975-115">group 句</span><span class="sxs-lookup"><span data-stu-id="5e975-115">group clause</span></span>](group-clause.md)
