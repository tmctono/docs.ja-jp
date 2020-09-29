---
title: '方法: DataContext レベルでフィルター処理する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 15505cd7-0df2-427a-9f86-e0f96f60ee2e
ms.openlocfilehash: 6fe79febd41c040e430dd772b87ca5624824bb65
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/24/2020
ms.locfileid: "91173472"
---
# <a name="how-to-filter-at-the-datacontext-level"></a><span data-ttu-id="62d3b-102">方法: DataContext レベルでフィルター処理する</span><span class="sxs-lookup"><span data-stu-id="62d3b-102">How to: Filter at the DataContext Level</span></span>

<span data-ttu-id="62d3b-103">`EntitySets` を `DataContext` レベルでフィルター処理できます。</span><span class="sxs-lookup"><span data-stu-id="62d3b-103">You can filter `EntitySets` at the `DataContext` level.</span></span> <span data-ttu-id="62d3b-104">このフィルター処理は、対象の <xref:System.Data.Linq.DataContext> インスタンスを使って実行されたすべてのクエリに適用されます。</span><span class="sxs-lookup"><span data-stu-id="62d3b-104">Such filters apply to all queries done with that <xref:System.Data.Linq.DataContext> instance.</span></span>  
  
## <a name="example"></a><span data-ttu-id="62d3b-105">例</span><span class="sxs-lookup"><span data-stu-id="62d3b-105">Example</span></span>  

 <span data-ttu-id="62d3b-106">次の例では、あらかじめ読み込まれた顧客からの注文を <xref:System.Data.Linq.DataLoadOptions.AssociateWith%28System.Linq.Expressions.LambdaExpression%29?displayProperty=nameWithType> に基づいてフィルター処理するために `ShippedDate` が使用されます。</span><span class="sxs-lookup"><span data-stu-id="62d3b-106">In the following example, <xref:System.Data.Linq.DataLoadOptions.AssociateWith%28System.Linq.Expressions.LambdaExpression%29?displayProperty=nameWithType> is used to filter the pre-loaded orders for customers by `ShippedDate`.</span></span>  
  
 [!code-csharp[DLinqQueryConcepts#10](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryConcepts/cs/Program.cs#10)]
 [!code-vb[DLinqQueryConcepts#10](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryConcepts/vb/Module1.vb#10)]  
  
## <a name="see-also"></a><span data-ttu-id="62d3b-107">関連項目</span><span class="sxs-lookup"><span data-stu-id="62d3b-107">See also</span></span>

- [<span data-ttu-id="62d3b-108">クエリの概念</span><span class="sxs-lookup"><span data-stu-id="62d3b-108">Query Concepts</span></span>](query-concepts.md)
