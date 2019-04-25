---
title: '方法: DataContext レベルでフィルター処理する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 15505cd7-0df2-427a-9f86-e0f96f60ee2e
ms.openlocfilehash: 343cffa9b1c034068e5abcc652e936f89ee6a992
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61903007"
---
# <a name="how-to-filter-at-the-datacontext-level"></a><span data-ttu-id="aa693-102">方法: DataContext レベルでフィルター処理する</span><span class="sxs-lookup"><span data-stu-id="aa693-102">How to: Filter at the DataContext Level</span></span>
<span data-ttu-id="aa693-103">`EntitySets` を `DataContext` レベルでフィルター処理できます。</span><span class="sxs-lookup"><span data-stu-id="aa693-103">You can filter `EntitySets` at the `DataContext` level.</span></span> <span data-ttu-id="aa693-104">このフィルター処理は、対象の <xref:System.Data.Linq.DataContext> インスタンスを使って実行されたすべてのクエリに適用されます。</span><span class="sxs-lookup"><span data-stu-id="aa693-104">Such filters apply to all queries done with that <xref:System.Data.Linq.DataContext> instance.</span></span>  
  
## <a name="example"></a><span data-ttu-id="aa693-105">例</span><span class="sxs-lookup"><span data-stu-id="aa693-105">Example</span></span>  
 <span data-ttu-id="aa693-106">次の例では、あらかじめ読み込まれた顧客からの注文を <xref:System.Data.Linq.DataLoadOptions.AssociateWith%28System.Linq.Expressions.LambdaExpression%29?displayProperty=nameWithType> に基づいてフィルター処理するために `ShippedDate` が使用されます。</span><span class="sxs-lookup"><span data-stu-id="aa693-106">In the following example, <xref:System.Data.Linq.DataLoadOptions.AssociateWith%28System.Linq.Expressions.LambdaExpression%29?displayProperty=nameWithType> is used to filter the pre-loaded orders for customers by `ShippedDate`.</span></span>  
  
 [!code-csharp[DLinqQueryConcepts#10](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryConcepts/cs/Program.cs#10)]
 [!code-vb[DLinqQueryConcepts#10](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryConcepts/vb/Module1.vb#10)]  
  
## <a name="see-also"></a><span data-ttu-id="aa693-107">関連項目</span><span class="sxs-lookup"><span data-stu-id="aa693-107">See also</span></span>

- [<span data-ttu-id="aa693-108">クエリの概念</span><span class="sxs-lookup"><span data-stu-id="aa693-108">Query Concepts</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/query-concepts.md)
