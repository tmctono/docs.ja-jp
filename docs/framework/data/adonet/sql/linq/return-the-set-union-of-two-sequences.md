---
title: 2 つのシーケンスの和集合の取得
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 8b8bd3cb-86d4-4a3b-9906-61f68726dd1f
ms.openlocfilehash: 9ade12c42ac6a307c341bc5be26430fb56e51ee5
ms.sourcegitcommit: 4735bb7741555bcb870d7b42964d3774f4897a6e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/30/2019
ms.locfileid: "66380039"
---
# <a name="return-the-set-union-of-two-sequences"></a><span data-ttu-id="79073-102">2 つのシーケンスの和集合の取得</span><span class="sxs-lookup"><span data-stu-id="79073-102">Return the Set Union of Two Sequences</span></span>
<span data-ttu-id="79073-103">2 つのシーケンスの和集合を返すには、<xref:System.Linq.Queryable.Union%2A> 演算子を使用します。</span><span class="sxs-lookup"><span data-stu-id="79073-103">Use the <xref:System.Linq.Queryable.Union%2A> operator to return the set union of two sequences.</span></span>  
  
## <a name="example"></a><span data-ttu-id="79073-104">例</span><span class="sxs-lookup"><span data-stu-id="79073-104">Example</span></span>  
 <span data-ttu-id="79073-105">この例では<xref:System.Linq.Queryable.Union%2A>をすべての国/地域のいずれかがシーケンスを返します`Customers`または`Employees`します。</span><span class="sxs-lookup"><span data-stu-id="79073-105">This example uses <xref:System.Linq.Queryable.Union%2A> to return a sequence of all countries/regions in which there are either `Customers` or `Employees`.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#43](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#43)]
 [!code-vb[DLinqQueryExamples#43](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#43)]  
  
 <span data-ttu-id="79073-106">[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]、<xref:System.Linq.Queryable.Union%2A>として、マルチセットの順序なし連結演算子がマルチセットに対して定義されます (事実上の結果、 [ `UNION ALL` ](https://docs.microsoft.com/sql/t-sql/language-elements/set-operators-union-transact-sql?view=sql-server-2017) SQL 句)。</span><span class="sxs-lookup"><span data-stu-id="79073-106">In [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)], the <xref:System.Linq.Queryable.Union%2A> operator is defined for multisets as the unordered concatenation of the multisets (effectively the result of the [`UNION ALL`](https://docs.microsoft.com/sql/t-sql/language-elements/set-operators-union-transact-sql?view=sql-server-2017) clause in SQL).</span></span>

<span data-ttu-id="79073-107">詳細と例については、次を参照してください。<xref:System.Linq.Queryable.Union%2A?displayProperty=nameWithType>します。</span><span class="sxs-lookup"><span data-stu-id="79073-107">For more info and examples, see <xref:System.Linq.Queryable.Union%2A?displayProperty=nameWithType>.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="79073-108">関連項目</span><span class="sxs-lookup"><span data-stu-id="79073-108">See also</span></span>

- [<span data-ttu-id="79073-109">クエリの例</span><span class="sxs-lookup"><span data-stu-id="79073-109">Query Examples</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/query-examples.md)
- [<span data-ttu-id="79073-110">標準クエリ演算子の変換</span><span class="sxs-lookup"><span data-stu-id="79073-110">Standard Query Operator Translation</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/standard-query-operator-translation.md)
