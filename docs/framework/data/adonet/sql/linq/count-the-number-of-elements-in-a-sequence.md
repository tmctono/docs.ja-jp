---
title: シーケンス内の要素数のカウント
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: ccbe5d54-c9eb-4b14-b0ab-f628483c5f99
ms.openlocfilehash: 74e24aeb64b0097cba3975e76475034e6bb9544d
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/04/2019
ms.locfileid: "70247700"
---
# <a name="count-the-number-of-elements-in-a-sequence"></a><span data-ttu-id="4a898-102">シーケンス内の要素数のカウント</span><span class="sxs-lookup"><span data-stu-id="4a898-102">Count the Number of Elements in a Sequence</span></span>
<span data-ttu-id="4a898-103"><xref:System.Linq.Enumerable.Count%2A> 演算子を使用すると、シーケンス内の要素数をカウントできます。</span><span class="sxs-lookup"><span data-stu-id="4a898-103">Use the <xref:System.Linq.Enumerable.Count%2A> operator to count the number of elements in a sequence.</span></span>  
  
 <span data-ttu-id="4a898-104">Northwind サンプル データベースに対してこのクエリを実行すると、出力は `91` になります。</span><span class="sxs-lookup"><span data-stu-id="4a898-104">Running this query against the Northwind sample database produces an output of `91`.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4a898-105">例</span><span class="sxs-lookup"><span data-stu-id="4a898-105">Example</span></span>  
 <span data-ttu-id="4a898-106">データベース内の `Customers` の数をカウントする例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="4a898-106">The following example counts the number of `Customers` in the database.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#4](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#4)]
 [!code-vb[DLinqQueryExamples#4](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#4)]  
  
## <a name="example"></a><span data-ttu-id="4a898-107">例</span><span class="sxs-lookup"><span data-stu-id="4a898-107">Example</span></span>  
 <span data-ttu-id="4a898-108">データベース内の製品のうち、生産中止になっていない製品の数をカウントする例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="4a898-108">The following example counts the number of products in the database that have not been discontinued.</span></span>  
  
 <span data-ttu-id="4a898-109">Northwind サンプル データベースに対してこのクエリを実行すると、出力は `69` になります。</span><span class="sxs-lookup"><span data-stu-id="4a898-109">Running this example against the Northwind sample database produces an output of `69`.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#5](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#5)]
 [!code-vb[DLinqQueryExamples#5](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#5)]  
  
## <a name="see-also"></a><span data-ttu-id="4a898-110">関連項目</span><span class="sxs-lookup"><span data-stu-id="4a898-110">See also</span></span>

- [<span data-ttu-id="4a898-111">集計クエリ</span><span class="sxs-lookup"><span data-stu-id="4a898-111">Aggregate Queries</span></span>](aggregate-queries.md)
- [<span data-ttu-id="4a898-112">サンプル データベースのダウンロード</span><span class="sxs-lookup"><span data-stu-id="4a898-112">Downloading Sample Databases</span></span>](downloading-sample-databases.md)
