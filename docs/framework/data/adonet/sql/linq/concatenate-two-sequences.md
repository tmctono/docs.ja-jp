---
title: 2 つのシーケンスの連結
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 76767e7c-0607-4e1d-9ca2-a94f311f45eb
ms.openlocfilehash: b802abae9fc2c1731a623209862f61ed5ee51f9c
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/04/2019
ms.locfileid: "70247885"
---
# <a name="concatenate-two-sequences"></a><span data-ttu-id="0a717-102">2 つのシーケンスの連結</span><span class="sxs-lookup"><span data-stu-id="0a717-102">Concatenate Two Sequences</span></span>
<span data-ttu-id="0a717-103">2 つのシーケンスを連結するには、<xref:System.Linq.Queryable.Concat%2A> 演算子を使用します。</span><span class="sxs-lookup"><span data-stu-id="0a717-103">Use the <xref:System.Linq.Queryable.Concat%2A> operator to concatenate two sequences.</span></span>  
  
 <span data-ttu-id="0a717-104"><xref:System.Linq.Queryable.Concat%2A> 演算子は、受信側と引数の順序が同じである、順序付けされたマルチセットに対して定義されます。</span><span class="sxs-lookup"><span data-stu-id="0a717-104">The <xref:System.Linq.Queryable.Concat%2A> operator is defined for ordered multisets where the orders of the receiver and the argument are the same.</span></span>  
  
 <span data-ttu-id="0a717-105">SQL での順序付けは、結果が作成される前の最終段階です。</span><span class="sxs-lookup"><span data-stu-id="0a717-105">Ordering in SQL is the final step before results are produced.</span></span> <span data-ttu-id="0a717-106">このため、<xref:System.Linq.Queryable.Concat%2A> 演算子は `UNION ALL` を使用して実装され、その引数の順序を保持しません。</span><span class="sxs-lookup"><span data-stu-id="0a717-106">For this reason, the <xref:System.Linq.Queryable.Concat%2A> operator is implemented by using `UNION ALL` and does not preserve the order of its arguments.</span></span> <span data-ttu-id="0a717-107">結果内での順序付けを正しく行うには、結果の順序を明示的に指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0a717-107">To make sure ordering is correct in the results, make sure to explicitly order the results.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0a717-108">例</span><span class="sxs-lookup"><span data-stu-id="0a717-108">Example</span></span>  
 <span data-ttu-id="0a717-109">この例では、<xref:System.Linq.Queryable.Concat%2A> を使用して、すべての `Customer` と `Employee` の電話番号と FAX 番号のシーケンスを返します。</span><span class="sxs-lookup"><span data-stu-id="0a717-109">This example uses <xref:System.Linq.Queryable.Concat%2A> to return a sequence of all `Customer` and `Employee` telephone and fax numbers.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#39](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#39)]
 [!code-vb[DLinqQueryExamples#39](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#39)]  
  
## <a name="example"></a><span data-ttu-id="0a717-110">例</span><span class="sxs-lookup"><span data-stu-id="0a717-110">Example</span></span>  
 <span data-ttu-id="0a717-111">この例では、<xref:System.Linq.Queryable.Concat%2A> を使用して、すべての `Customer` と `Employee` の名前と電話番号のマッピングのシーケンスを返します。</span><span class="sxs-lookup"><span data-stu-id="0a717-111">This example uses <xref:System.Linq.Queryable.Concat%2A> to return a sequence of all `Customer` and `Employee` name and telephone number mappings.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#40](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#40)]
 [!code-vb[DLinqQueryExamples#40](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#40)]  
  
## <a name="see-also"></a><span data-ttu-id="0a717-112">関連項目</span><span class="sxs-lookup"><span data-stu-id="0a717-112">See also</span></span>

- [<span data-ttu-id="0a717-113">クエリの例</span><span class="sxs-lookup"><span data-stu-id="0a717-113">Query Examples</span></span>](query-examples.md)
- [<span data-ttu-id="0a717-114">標準クエリ演算子の変換</span><span class="sxs-lookup"><span data-stu-id="0a717-114">Standard Query Operator Translation</span></span>](standard-query-operator-translation.md)
