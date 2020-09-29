---
title: '方法 : シーケンスを配列に変換する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: bf0af444-890d-43e2-aeca-98589dd74ddf
ms.openlocfilehash: 24a813b044bdbee2621cb57a8f34ec818d4533c3
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/24/2020
ms.locfileid: "91164377"
---
# <a name="convert-a-sequence-to-an-array"></a><span data-ttu-id="a2a19-102">方法 : シーケンスを配列に変換する</span><span class="sxs-lookup"><span data-stu-id="a2a19-102">Convert a Sequence to an Array</span></span>

<span data-ttu-id="a2a19-103">シーケンスから配列を作成するには、<xref:System.Linq.Enumerable.ToArray%2A> を使用します。</span><span class="sxs-lookup"><span data-stu-id="a2a19-103">Use <xref:System.Linq.Enumerable.ToArray%2A> to create an array from a sequence.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a2a19-104">例</span><span class="sxs-lookup"><span data-stu-id="a2a19-104">Example</span></span>  

 <span data-ttu-id="a2a19-105">次の例では、<xref:System.Linq.Enumerable.ToArray%2A> を使用して、クエリを直ちに配列に評価し、3 番目の要素を取得します。</span><span class="sxs-lookup"><span data-stu-id="a2a19-105">The following example uses <xref:System.Linq.Enumerable.ToArray%2A> to immediately evaluate a query into an array and to get the third element.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#44](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#44)]
 [!code-vb[DLinqQueryExamples#44](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#44)]  
  
## <a name="see-also"></a><span data-ttu-id="a2a19-106">関連項目</span><span class="sxs-lookup"><span data-stu-id="a2a19-106">See also</span></span>

- [<span data-ttu-id="a2a19-107">クエリの例</span><span class="sxs-lookup"><span data-stu-id="a2a19-107">Query Examples</span></span>](query-examples.md)
