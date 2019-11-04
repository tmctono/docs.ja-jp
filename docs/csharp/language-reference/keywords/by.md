---
title: by コンテキスト キーワード - C# リファレンス
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- by
- by_CSharpKeyword
helpviewer_keywords:
- by keyword [C#]
ms.assetid: efe6f0e3-be40-4df2-a144-c7db968ae052
ms.openlocfilehash: 9f888f170f749eb5aac5cd39cd7c733920581542
ms.sourcegitcommit: 14ad34f7c4564ee0f009acb8bfc0ea7af3bc9541
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/01/2019
ms.locfileid: "73422881"
---
# <a name="by-c-reference"></a><span data-ttu-id="08548-102">by (C# リファレンス)</span><span class="sxs-lookup"><span data-stu-id="08548-102">by (C# Reference)</span></span>

<span data-ttu-id="08548-103">`by` コンテキスト キーワードは、クエリ式の `group` 句で使用され、返される項目をグループ化する方法を指定します。</span><span class="sxs-lookup"><span data-stu-id="08548-103">The `by` contextual keyword is used in the `group` clause in a query expression to specify how the returned items should be grouped.</span></span> <span data-ttu-id="08548-104">詳しくは、「[group 句](./group-clause.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="08548-104">For more information, see [group clause](./group-clause.md).</span></span>

## <a name="example"></a><span data-ttu-id="08548-105">例</span><span class="sxs-lookup"><span data-stu-id="08548-105">Example</span></span>

<span data-ttu-id="08548-106">`group` 句での `by` コンテキスト キーワードの使用例を次に示します。ここでは、各学生の姓の 1 文字目に従って学生をグループ化するように指定しています。</span><span class="sxs-lookup"><span data-stu-id="08548-106">The following example shows the use of the `by` contextual keyword in a `group` clause to specify that the students should be grouped according to the first letter of the last name of each student.</span></span>

[!code-csharp[csrefKeywordsContextual#10](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsContextual/CS/csrefKeywordsContextual.cs#10)]

## <a name="see-also"></a><span data-ttu-id="08548-107">関連項目</span><span class="sxs-lookup"><span data-stu-id="08548-107">See also</span></span>

- [<span data-ttu-id="08548-108">C# での LINQ</span><span class="sxs-lookup"><span data-stu-id="08548-108">LINQ in C#</span></span>](../../linq/index.md)
