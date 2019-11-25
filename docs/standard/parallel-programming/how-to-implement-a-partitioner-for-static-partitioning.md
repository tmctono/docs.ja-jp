---
title: '方法: 静的パーティション分割用にパーティショナーを実装する'
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- tasks, how to create a static partitioner
ms.assetid: f4410508-cac6-4ba7-bef1-c5e68b2794f3
ms.openlocfilehash: 94fbb681b20b9c920c20df2a9017f75a9aa9a6ea
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73091530"
---
# <a name="how-to-implement-a-partitioner-for-static-partitioning"></a><span data-ttu-id="00e22-102">方法: 静的パーティション分割用にパーティショナーを実装する</span><span class="sxs-lookup"><span data-stu-id="00e22-102">How to: Implement a Partitioner for Static Partitioning</span></span>
<span data-ttu-id="00e22-103">次の例は、静的なパーティション分割を行う PLINQ 用の単純なカスタム パーティショナーを実装する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="00e22-103">The following example shows one way to implement a simple custom partitioner for PLINQ that performs static partitioning.</span></span> <span data-ttu-id="00e22-104">パーティショナーは動的なパーティションをサポートしていないため、<xref:System.Threading.Tasks.Parallel.ForEach%2A?displayProperty=nameWithType> からは利用することはできません。</span><span class="sxs-lookup"><span data-stu-id="00e22-104">Because the partitioner does not support dynamic partitions, it is not consumable from <xref:System.Threading.Tasks.Parallel.ForEach%2A?displayProperty=nameWithType>.</span></span> <span data-ttu-id="00e22-105">この特定のパーティショナーは、各要素が大量の処理時間を必要とするデータ ソースで、既定の範囲のパーティショナーよりも処理速度を向上させることができる場合があります。</span><span class="sxs-lookup"><span data-stu-id="00e22-105">This particular partitioner might provide speedup over the default range partitioner for data sources for which each element requires an increasing amount of processing time.</span></span>  
  
## <a name="example"></a><span data-ttu-id="00e22-106">例</span><span class="sxs-lookup"><span data-stu-id="00e22-106">Example</span></span>  
 [!code-csharp[TPL_Partitioners#05](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_partitioners/cs/partitioners.cs#05)]  
  
 <span data-ttu-id="00e22-107">この例のパーティションでは、各要素の処理時間が直線的に増加することが前提となっています。</span><span class="sxs-lookup"><span data-stu-id="00e22-107">The partitions in this example are based on the assumption of a linear increase in processing time for each element.</span></span> <span data-ttu-id="00e22-108">実際には、この方法で処理時間を予測するのは難しい場合があります。</span><span class="sxs-lookup"><span data-stu-id="00e22-108">In the real world, it might be difficult to predict processing times in this way.</span></span> <span data-ttu-id="00e22-109">特定のデータ ソースで静的パーティショナーを使用している場合、ソースのパーティション分割の数式を最適化したり、負荷分散のロジックを追加したり、チャンク パーティション分割の手法を使用したりすることができます。その手法については「[方法: 動的パーティションを実装する](../../../docs/standard/parallel-programming/how-to-implement-dynamic-partitions.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="00e22-109">If you are using a static partitioner with a specific data source, you can optimize the partitioning formula for the source, add load-balancing logic, or use a chunk partitioning approach as demonstrated in [How to: Implement Dynamic Partitions](../../../docs/standard/parallel-programming/how-to-implement-dynamic-partitions.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="00e22-110">関連項目</span><span class="sxs-lookup"><span data-stu-id="00e22-110">See also</span></span>

- [<span data-ttu-id="00e22-111">PLINQ および TPL 用のカスタム パーティショナー</span><span class="sxs-lookup"><span data-stu-id="00e22-111">Custom Partitioners for PLINQ and TPL</span></span>](../../../docs/standard/parallel-programming/custom-partitioners-for-plinq-and-tpl.md)
