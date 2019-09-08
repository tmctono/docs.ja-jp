---
title: 2 つのシーケンスの積集合の取得
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: d09c344e-3548-4944-a3ed-051880e3f5b8
ms.openlocfilehash: 944d0b2efe1e74f901a493d1c3202d0f180d599d
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/07/2019
ms.locfileid: "70792707"
---
# <a name="return-the-set-intersection-of-two-sequences"></a><span data-ttu-id="8e99e-102">2 つのシーケンスの積集合の取得</span><span class="sxs-lookup"><span data-stu-id="8e99e-102">Return the Set Intersection of Two Sequences</span></span>
<span data-ttu-id="8e99e-103">2 つのシーケンスの積集合を返すには、<xref:System.Linq.Queryable.Intersect%2A> 演算子を使用します。</span><span class="sxs-lookup"><span data-stu-id="8e99e-103">Use the <xref:System.Linq.Queryable.Intersect%2A> operator to return the set intersection of two sequences.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8e99e-104">例</span><span class="sxs-lookup"><span data-stu-id="8e99e-104">Example</span></span>  
 <span data-ttu-id="8e99e-105">この例で<xref:System.Linq.Queryable.Intersect%2A>は、を使用して、と`Employees`の両方`Customers`がライブであるすべての国/地域のシーケンスを返します。</span><span class="sxs-lookup"><span data-stu-id="8e99e-105">This example uses <xref:System.Linq.Queryable.Intersect%2A> to return a sequence of all countries/regions in which both `Customers` and `Employees` live.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#42](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#42)]
 [!code-vb[DLinqQueryExamples#42](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#42)]  
  
 <span data-ttu-id="8e99e-106">[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] では、<xref:System.Linq.Queryable.Intersect%2A> 演算は集合でのみ適切に定義されます。</span><span class="sxs-lookup"><span data-stu-id="8e99e-106">In [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)], the <xref:System.Linq.Queryable.Intersect%2A> operation is well defined only on sets.</span></span> <span data-ttu-id="8e99e-107">マルチセットのセマンティクスは未定義です。</span><span class="sxs-lookup"><span data-stu-id="8e99e-107">The semantics for multisets is undefined.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8e99e-108">関連項目</span><span class="sxs-lookup"><span data-stu-id="8e99e-108">See also</span></span>

- [<span data-ttu-id="8e99e-109">クエリの例</span><span class="sxs-lookup"><span data-stu-id="8e99e-109">Query Examples</span></span>](query-examples.md)
- [<span data-ttu-id="8e99e-110">標準クエリ演算子の変換</span><span class="sxs-lookup"><span data-stu-id="8e99e-110">Standard Query Operator Translation</span></span>](standard-query-operator-translation.md)
