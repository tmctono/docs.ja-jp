---
title: '方法: クエリで複合キーを処理する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: ce2f14fd-1038-458a-91e3-a078c61f0d10
ms.openlocfilehash: 2621ab4db207d1b868fbe3778c30c744201b0506
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62033814"
---
# <a name="how-to-handle-composite-keys-in-queries"></a><span data-ttu-id="e4d61-102">方法: クエリで複合キーを処理する</span><span class="sxs-lookup"><span data-stu-id="e4d61-102">How to: Handle Composite Keys in Queries</span></span>
<span data-ttu-id="e4d61-103">演算子によっては、引数を 1 つしか受け取らないものがあります。</span><span class="sxs-lookup"><span data-stu-id="e4d61-103">Some operators can take only one argument.</span></span> <span data-ttu-id="e4d61-104">1 つの演算子にデータベースの複数の列を含めるには、その組み合わせを表す匿名型を作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e4d61-104">If your argument must include more than one column from the database, you must create an anonymous type to represent the combination.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e4d61-105">例</span><span class="sxs-lookup"><span data-stu-id="e4d61-105">Example</span></span>  
 <span data-ttu-id="e4d61-106">`GroupBy` 演算子を使用するクエリを次の例に示します。この演算子は、1 つの `key` 引数だけを受け取ることができます。</span><span class="sxs-lookup"><span data-stu-id="e4d61-106">The following example shows a query that invokes the `GroupBy` operator, which can take only one `key` argument.</span></span>  
  
 [!code-csharp[DLinqCompositeKeys#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqCompositeKeys/cs/Program.cs#1)]
 [!code-vb[DLinqCompositeKeys#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqCompositeKeys/vb/Module1.vb#1)]  
  
## <a name="example"></a><span data-ttu-id="e4d61-107">例</span><span class="sxs-lookup"><span data-stu-id="e4d61-107">Example</span></span>  
 <span data-ttu-id="e4d61-108">次の例に示すように、結合の場合も同様です。</span><span class="sxs-lookup"><span data-stu-id="e4d61-108">The same situation pertains to joins, as in the following example:</span></span>  
  
 [!code-csharp[DLinqCompositeKeys#2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqCompositeKeys/cs/Program.cs#2)]
 [!code-vb[DLinqCompositeKeys#2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqCompositeKeys/vb/Module1.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="e4d61-109">関連項目</span><span class="sxs-lookup"><span data-stu-id="e4d61-109">See also</span></span>

- [<span data-ttu-id="e4d61-110">クエリの概念</span><span class="sxs-lookup"><span data-stu-id="e4d61-110">Query Concepts</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/query-concepts.md)
