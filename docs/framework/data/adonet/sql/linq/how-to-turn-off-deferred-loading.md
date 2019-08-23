---
title: '方法: 遅延読み込みをオフにする'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 1b84b852-3cad-41a7-8077-149a70d50c8b
ms.openlocfilehash: f68db5a5a0092fc4cf37746f2a4dc81e40ee4a9d
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2019
ms.locfileid: "69938677"
---
# <a name="how-to-turn-off-deferred-loading"></a><span data-ttu-id="eefb0-102">方法: 遅延読み込みをオフにする</span><span class="sxs-lookup"><span data-stu-id="eefb0-102">How to: Turn Off Deferred Loading</span></span>
<span data-ttu-id="eefb0-103"><xref:System.Data.Linq.DataContext.DeferredLoadingEnabled%2A> を `false` に設定すると、遅延読み込みをオフにできます。</span><span class="sxs-lookup"><span data-stu-id="eefb0-103">You can turn off deferred loading by setting <xref:System.Data.Linq.DataContext.DeferredLoadingEnabled%2A> to `false`.</span></span> <span data-ttu-id="eefb0-104">詳細については、「[遅延読み込みと即時読み込み](../../../../../../docs/framework/data/adonet/sql/linq/deferred-versus-immediate-loading.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="eefb0-104">For more information, see [Deferred versus Immediate Loading](../../../../../../docs/framework/data/adonet/sql/linq/deferred-versus-immediate-loading.md).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="eefb0-105">遅延読み込みは、オブジェクト トラッキングをオフにすると暗黙でオフになります。</span><span class="sxs-lookup"><span data-stu-id="eefb0-105">Deferred loading is turned off by implication when object tracking is turned off.</span></span> <span data-ttu-id="eefb0-106">詳細については、「[方法 :情報を読み取り](../../../../../../docs/framework/data/adonet/sql/linq/how-to-retrieve-information-as-read-only.md)専用として取得します。</span><span class="sxs-lookup"><span data-stu-id="eefb0-106">For more information, see [How to: Retrieve Information As Read-Only](../../../../../../docs/framework/data/adonet/sql/linq/how-to-retrieve-information-as-read-only.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="eefb0-107">例</span><span class="sxs-lookup"><span data-stu-id="eefb0-107">Example</span></span>  
 <span data-ttu-id="eefb0-108"><xref:System.Data.Linq.DataContext.DeferredLoadingEnabled%2A> を `false` に設定して、遅延読み込みをオフにする方法を次の例に示します。</span><span class="sxs-lookup"><span data-stu-id="eefb0-108">The following example shows how to turn off deferred loading by setting <xref:System.Data.Linq.DataContext.DeferredLoadingEnabled%2A> to `false`.</span></span>  
  
 [!code-csharp[DLinqQuerying#3](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQuerying/cs/Program.cs#3)]
 [!code-vb[DLinqQuerying#3](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQuerying/vb/Module1.vb#3)]  
  
## <a name="see-also"></a><span data-ttu-id="eefb0-109">関連項目</span><span class="sxs-lookup"><span data-stu-id="eefb0-109">See also</span></span>

- [<span data-ttu-id="eefb0-110">クエリの概念</span><span class="sxs-lookup"><span data-stu-id="eefb0-110">Query Concepts</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/query-concepts.md)
- [<span data-ttu-id="eefb0-111">データベースに対するクエリの実行</span><span class="sxs-lookup"><span data-stu-id="eefb0-111">Querying the Database</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/querying-the-database.md)
