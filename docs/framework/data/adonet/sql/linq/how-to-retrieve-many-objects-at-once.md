---
title: '方法: 多くのオブジェクトを一度に取得する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 18aff4d8-bde8-461b-9960-ccabb24e9d22
ms.openlocfilehash: 98827989f72b7922a325a9e13b5f46cb18ac5395
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/24/2020
ms.locfileid: "91197314"
---
# <a name="how-to-retrieve-many-objects-at-once"></a><span data-ttu-id="f17c7-102">方法: 多くのオブジェクトを一度に取得する</span><span class="sxs-lookup"><span data-stu-id="f17c7-102">How to: Retrieve Many Objects At Once</span></span>

<span data-ttu-id="f17c7-103">多くのオブジェクトを 1 つのクエリで取得するには、<xref:System.Data.Linq.DataLoadOptions.LoadWith%2A> を使用します。</span><span class="sxs-lookup"><span data-stu-id="f17c7-103">You can retrieve many objects in one query by using <xref:System.Data.Linq.DataLoadOptions.LoadWith%2A>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f17c7-104">例</span><span class="sxs-lookup"><span data-stu-id="f17c7-104">Example</span></span>  

 <span data-ttu-id="f17c7-105"><xref:System.Data.Linq.DataLoadOptions.LoadWith%2A> メソッドを使用して、`Customer` と `Order` の両方を取得するコードの例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="f17c7-105">The following code uses the <xref:System.Data.Linq.DataLoadOptions.LoadWith%2A> method to retrieve both `Customer` and `Order` objects.</span></span>  
  
 [!code-csharp[DLinqQueryConcepts#9](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryConcepts/cs/Program.cs#9)]
 [!code-vb[DLinqQueryConcepts#9](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryConcepts/vb/Module1.vb#9)]  
  
## <a name="see-also"></a><span data-ttu-id="f17c7-106">関連項目</span><span class="sxs-lookup"><span data-stu-id="f17c7-106">See also</span></span>

- [<span data-ttu-id="f17c7-107">クエリの概念</span><span class="sxs-lookup"><span data-stu-id="f17c7-107">Query Concepts</span></span>](query-concepts.md)
