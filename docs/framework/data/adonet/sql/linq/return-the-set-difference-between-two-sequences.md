---
title: 2 つのシーケンスの差集合の取得
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 62efb546-c898-408f-af21-36e7c6fed217
ms.openlocfilehash: 49a8d22377ef1f7d0fde16880a82002754e1bbc4
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/24/2020
ms.locfileid: "91200330"
---
# <a name="return-the-set-difference-between-two-sequences"></a><span data-ttu-id="b9d2b-102">2 つのシーケンスの差集合の取得</span><span class="sxs-lookup"><span data-stu-id="b9d2b-102">Return the Set Difference Between Two Sequences</span></span>

<span data-ttu-id="b9d2b-103">2 つのシーケンスの差集合を返すには、<xref:System.Linq.Queryable.Except%2A> 演算子を使用します。</span><span class="sxs-lookup"><span data-stu-id="b9d2b-103">Use the <xref:System.Linq.Queryable.Except%2A> operator to return the set difference between two sequences.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b9d2b-104">例</span><span class="sxs-lookup"><span data-stu-id="b9d2b-104">Example</span></span>  

 <span data-ttu-id="b9d2b-105">この例では、<xref:System.Linq.Queryable.Except%2A> を使用して、`Customers` は居住しているが `Employees` は居住していないすべての国/リージョンのシーケンスを返します。</span><span class="sxs-lookup"><span data-stu-id="b9d2b-105">This example uses <xref:System.Linq.Queryable.Except%2A> to return a sequence of all countries/regions in which `Customers` live but in which no `Employees` live.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#41](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#41)]
 [!code-vb[DLinqQueryExamples#41](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#41)]  
  
 <span data-ttu-id="b9d2b-106">[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] では、<xref:System.Linq.Queryable.Except%2A> 演算は集合でのみ適切に定義されます。</span><span class="sxs-lookup"><span data-stu-id="b9d2b-106">In [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)], the <xref:System.Linq.Queryable.Except%2A> operation is well defined only on sets.</span></span> <span data-ttu-id="b9d2b-107">マルチセットのセマンティクスは未定義です。</span><span class="sxs-lookup"><span data-stu-id="b9d2b-107">The semantics for multisets is undefined.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b9d2b-108">関連項目</span><span class="sxs-lookup"><span data-stu-id="b9d2b-108">See also</span></span>

- [<span data-ttu-id="b9d2b-109">クエリの例</span><span class="sxs-lookup"><span data-stu-id="b9d2b-109">Query Examples</span></span>](query-examples.md)
- [<span data-ttu-id="b9d2b-110">標準クエリ演算子の変換</span><span class="sxs-lookup"><span data-stu-id="b9d2b-110">Standard Query Operator Translation</span></span>](standard-query-operator-translation.md)
