---
title: 2 つのシーケンスの差集合の取得
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 62efb546-c898-408f-af21-36e7c6fed217
ms.openlocfilehash: 92513ed33e2afb785edbdd462ba7bc14923aa6b0
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/07/2019
ms.locfileid: "70781142"
---
# <a name="return-the-set-difference-between-two-sequences"></a><span data-ttu-id="55d44-102">2 つのシーケンスの差集合の取得</span><span class="sxs-lookup"><span data-stu-id="55d44-102">Return the Set Difference Between Two Sequences</span></span>
<span data-ttu-id="55d44-103">2 つのシーケンスの差集合を返すには、<xref:System.Linq.Queryable.Except%2A> 演算子を使用します。</span><span class="sxs-lookup"><span data-stu-id="55d44-103">Use the <xref:System.Linq.Queryable.Except%2A> operator to return the set difference between two sequences.</span></span>  
  
## <a name="example"></a><span data-ttu-id="55d44-104">例</span><span class="sxs-lookup"><span data-stu-id="55d44-104">Example</span></span>  
 <span data-ttu-id="55d44-105">この例で<xref:System.Linq.Queryable.Except%2A>は、を使用して、 `Customers`住んでいてもライブではない`Employees`すべての国/地域のシーケンスを返します。</span><span class="sxs-lookup"><span data-stu-id="55d44-105">This example uses <xref:System.Linq.Queryable.Except%2A> to return a sequence of all countries/regions in which `Customers` live but in which no `Employees` live.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#41](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#41)]
 [!code-vb[DLinqQueryExamples#41](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#41)]  
  
 <span data-ttu-id="55d44-106">[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] では、<xref:System.Linq.Queryable.Except%2A> 演算は集合でのみ適切に定義されます。</span><span class="sxs-lookup"><span data-stu-id="55d44-106">In [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)], the <xref:System.Linq.Queryable.Except%2A> operation is well defined only on sets.</span></span> <span data-ttu-id="55d44-107">マルチセットのセマンティクスは未定義です。</span><span class="sxs-lookup"><span data-stu-id="55d44-107">The semantics for multisets is undefined.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="55d44-108">関連項目</span><span class="sxs-lookup"><span data-stu-id="55d44-108">See also</span></span>

- [<span data-ttu-id="55d44-109">クエリの例</span><span class="sxs-lookup"><span data-stu-id="55d44-109">Query Examples</span></span>](query-examples.md)
- [<span data-ttu-id="55d44-110">標準クエリ演算子の変換</span><span class="sxs-lookup"><span data-stu-id="55d44-110">Standard Query Operator Translation</span></span>](standard-query-operator-translation.md)
