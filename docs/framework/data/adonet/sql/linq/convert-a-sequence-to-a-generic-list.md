---
title: ジェネリック リストへのシーケンスの変換
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 7ab76d93-6898-4e75-b76f-290a66ecead8
ms.openlocfilehash: 43960d100cde7f746a56c023d305795e13bc04e7
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/04/2019
ms.locfileid: "70247865"
---
# <a name="convert-a-sequence-to-a-generic-list"></a><span data-ttu-id="ca1f0-102">ジェネリック リストへのシーケンスの変換</span><span class="sxs-lookup"><span data-stu-id="ca1f0-102">Convert a Sequence to a Generic List</span></span>
<span data-ttu-id="ca1f0-103">シーケンスからジェネリック リストを作成するには、<xref:System.Linq.Enumerable.ToList%2A> を使用します。</span><span class="sxs-lookup"><span data-stu-id="ca1f0-103">Use <xref:System.Linq.Enumerable.ToList%2A> to create a generic List from a sequence.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ca1f0-104">例</span><span class="sxs-lookup"><span data-stu-id="ca1f0-104">Example</span></span>  
 <span data-ttu-id="ca1f0-105">次のサンプルでは、<xref:System.Linq.Enumerable.ToList%2A> を使用して、クエリを直ちにジェネリック <xref:System.Collections.Generic.List%601> に評価します。</span><span class="sxs-lookup"><span data-stu-id="ca1f0-105">The following sample uses <xref:System.Linq.Enumerable.ToList%2A> to immediately evaluate a query into a generic <xref:System.Collections.Generic.List%601>.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#45](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#45)]
 [!code-vb[DLinqQueryExamples#45](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#45)]  
  
## <a name="see-also"></a><span data-ttu-id="ca1f0-106">関連項目</span><span class="sxs-lookup"><span data-stu-id="ca1f0-106">See also</span></span>

- [<span data-ttu-id="ca1f0-107">クエリの例</span><span class="sxs-lookup"><span data-stu-id="ca1f0-107">Query Examples</span></span>](query-examples.md)
