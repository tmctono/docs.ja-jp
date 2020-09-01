---
description: by コンテキスト キーワード - C# リファレンス
title: by コンテキスト キーワード - C# リファレンス
ms.date: 07/20/2015
f1_keywords:
- by
- by_CSharpKeyword
helpviewer_keywords:
- by keyword [C#]
ms.assetid: efe6f0e3-be40-4df2-a144-c7db968ae052
ms.openlocfilehash: 2bc62f6f7f9e8a6d434ea254d5b04e563c41bc26
ms.sourcegitcommit: d579fb5e4b46745fd0f1f8874c94c6469ce58604
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/30/2020
ms.locfileid: "89134693"
---
# <a name="by-c-reference"></a><span data-ttu-id="8857d-103">by (C# リファレンス)</span><span class="sxs-lookup"><span data-stu-id="8857d-103">by (C# Reference)</span></span>

<span data-ttu-id="8857d-104">`by` コンテキスト キーワードは、クエリ式の `group` 句で使用され、返される項目をグループ化する方法を指定します。</span><span class="sxs-lookup"><span data-stu-id="8857d-104">The `by` contextual keyword is used in the `group` clause in a query expression to specify how the returned items should be grouped.</span></span> <span data-ttu-id="8857d-105">詳しくは、「[group 句](./group-clause.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="8857d-105">For more information, see [group clause](./group-clause.md).</span></span>

## <a name="example"></a><span data-ttu-id="8857d-106">例</span><span class="sxs-lookup"><span data-stu-id="8857d-106">Example</span></span>

<span data-ttu-id="8857d-107">`group` 句での `by` コンテキスト キーワードの使用例を次に示します。ここでは、各学生の姓の 1 文字目に従って学生をグループ化するように指定しています。</span><span class="sxs-lookup"><span data-stu-id="8857d-107">The following example shows the use of the `by` contextual keyword in a `group` clause to specify that the students should be grouped according to the first letter of the last name of each student.</span></span>

[!code-csharp[csrefKeywordsContextual#10](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsContextual/CS/csrefKeywordsContextual.cs#10)]

## <a name="see-also"></a><span data-ttu-id="8857d-108">関連項目</span><span class="sxs-lookup"><span data-stu-id="8857d-108">See also</span></span>

- [<span data-ttu-id="8857d-109">C# での LINQ</span><span class="sxs-lookup"><span data-stu-id="8857d-109">LINQ in C#</span></span>](../../linq/index.md)
