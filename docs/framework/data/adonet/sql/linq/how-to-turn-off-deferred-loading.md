---
title: '方法: 遅延読み込みをオフにする'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 1b84b852-3cad-41a7-8077-149a70d50c8b
ms.openlocfilehash: 6559392527bb02afe9cea61e704f1f371c6d5470
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/07/2019
ms.locfileid: "70781657"
---
# <a name="how-to-turn-off-deferred-loading"></a><span data-ttu-id="38076-102">方法: 遅延読み込みをオフにする</span><span class="sxs-lookup"><span data-stu-id="38076-102">How to: Turn Off Deferred Loading</span></span>
<span data-ttu-id="38076-103"><xref:System.Data.Linq.DataContext.DeferredLoadingEnabled%2A> を `false` に設定すると、遅延読み込みをオフにできます。</span><span class="sxs-lookup"><span data-stu-id="38076-103">You can turn off deferred loading by setting <xref:System.Data.Linq.DataContext.DeferredLoadingEnabled%2A> to `false`.</span></span> <span data-ttu-id="38076-104">詳細については、「[遅延読み込みと即時読み込み](deferred-versus-immediate-loading.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="38076-104">For more information, see [Deferred versus Immediate Loading](deferred-versus-immediate-loading.md).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="38076-105">遅延読み込みは、オブジェクト トラッキングをオフにすると暗黙でオフになります。</span><span class="sxs-lookup"><span data-stu-id="38076-105">Deferred loading is turned off by implication when object tracking is turned off.</span></span> <span data-ttu-id="38076-106">詳細については、「[方法 :情報を読み取り](how-to-retrieve-information-as-read-only.md)専用として取得します。</span><span class="sxs-lookup"><span data-stu-id="38076-106">For more information, see [How to: Retrieve Information As Read-Only](how-to-retrieve-information-as-read-only.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="38076-107">例</span><span class="sxs-lookup"><span data-stu-id="38076-107">Example</span></span>  
 <span data-ttu-id="38076-108"><xref:System.Data.Linq.DataContext.DeferredLoadingEnabled%2A> を `false` に設定して、遅延読み込みをオフにする方法を次の例に示します。</span><span class="sxs-lookup"><span data-stu-id="38076-108">The following example shows how to turn off deferred loading by setting <xref:System.Data.Linq.DataContext.DeferredLoadingEnabled%2A> to `false`.</span></span>  
  
 [!code-csharp[DLinqQuerying#3](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQuerying/cs/Program.cs#3)]
 [!code-vb[DLinqQuerying#3](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQuerying/vb/Module1.vb#3)]  
  
## <a name="see-also"></a><span data-ttu-id="38076-109">関連項目</span><span class="sxs-lookup"><span data-stu-id="38076-109">See also</span></span>

- [<span data-ttu-id="38076-110">クエリの概念</span><span class="sxs-lookup"><span data-stu-id="38076-110">Query Concepts</span></span>](query-concepts.md)
- [<span data-ttu-id="38076-111">データベースに対するクエリの実行</span><span class="sxs-lookup"><span data-stu-id="38076-111">Querying the Database</span></span>](querying-the-database.md)
