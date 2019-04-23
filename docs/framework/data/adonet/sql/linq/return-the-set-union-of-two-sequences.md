---
title: 2 つのシーケンスの和集合の取得
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 8b8bd3cb-86d4-4a3b-9906-61f68726dd1f
ms.openlocfilehash: 0d0d87e2fe14553d468384dfa2cfde1d3ee0d526
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59210133"
---
# <a name="return-the-set-union-of-two-sequences"></a><span data-ttu-id="20353-102">2 つのシーケンスの和集合の取得</span><span class="sxs-lookup"><span data-stu-id="20353-102">Return the Set Union of Two Sequences</span></span>
<span data-ttu-id="20353-103">2 つのシーケンスの和集合を返すには、<xref:System.Linq.Queryable.Union%2A> 演算子を使用します。</span><span class="sxs-lookup"><span data-stu-id="20353-103">Use the <xref:System.Linq.Queryable.Union%2A> operator to return the set union of two sequences.</span></span>  
  
## <a name="example"></a><span data-ttu-id="20353-104">例</span><span class="sxs-lookup"><span data-stu-id="20353-104">Example</span></span>  
 <span data-ttu-id="20353-105">この例では、<xref:System.Linq.Queryable.Union%2A> を使用して、`Customers` と `Employees` のいずれかが居住しているすべての国のシーケンスを返します。</span><span class="sxs-lookup"><span data-stu-id="20353-105">This example uses <xref:System.Linq.Queryable.Union%2A> to return a sequence of all countries in which there are either `Customers` or `Employees`.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#43](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#43)]
 [!code-vb[DLinqQueryExamples#43](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#43)]  
  
 <span data-ttu-id="20353-106">[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]、<xref:System.Linq.Queryable.Union%2A>として、マルチセットの順序なし連結演算子がマルチセットに対して定義されます (事実上の結果、 [ `UNION ALL` ](https://docs.microsoft.com/sql/t-sql/language-elements/set-operators-union-transact-sql?view=sql-server-2017) SQL 句)。</span><span class="sxs-lookup"><span data-stu-id="20353-106">In [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)], the <xref:System.Linq.Queryable.Union%2A> operator is defined for multisets as the unordered concatenation of the multisets (effectively the result of the [`UNION ALL`](https://docs.microsoft.com/sql/t-sql/language-elements/set-operators-union-transact-sql?view=sql-server-2017) clause in SQL).</span></span>

<span data-ttu-id="20353-107">詳細と例については、次を参照してください。<xref:System.Linq.Queryable.Union%2A?displayProperty=nameWithType>します。</span><span class="sxs-lookup"><span data-stu-id="20353-107">For more info and examples, see <xref:System.Linq.Queryable.Union%2A?displayProperty=nameWithType>.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="20353-108">関連項目</span><span class="sxs-lookup"><span data-stu-id="20353-108">See also</span></span>

- [<span data-ttu-id="20353-109">クエリの例</span><span class="sxs-lookup"><span data-stu-id="20353-109">Query Examples</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/query-examples.md)
- [<span data-ttu-id="20353-110">標準クエリ演算子の変換</span><span class="sxs-lookup"><span data-stu-id="20353-110">Standard Query Operator Translation</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/standard-query-operator-translation.md)
