---
title: '方法: エンティティの競合情報を取得する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 9a02b608-e7bb-4041-a452-a7fed26fd008
ms.openlocfilehash: 766ede90b14f07e2799c2715daf62aaeeeaa83f4
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/07/2019
ms.locfileid: "70782241"
---
# <a name="how-to-retrieve-entity-conflict-information"></a><span data-ttu-id="57af0-102">方法: エンティティの競合情報を取得する</span><span class="sxs-lookup"><span data-stu-id="57af0-102">How to: Retrieve Entity Conflict Information</span></span>
<span data-ttu-id="57af0-103"><xref:System.Data.Linq.ObjectChangeConflict> クラスのオブジェクトを使用して、<xref:System.Data.Linq.ChangeConflictException> 例外によって発生する競合に関する情報を提供できます。</span><span class="sxs-lookup"><span data-stu-id="57af0-103">You can use objects of the <xref:System.Data.Linq.ObjectChangeConflict> class to provide information about conflicts revealed by <xref:System.Data.Linq.ChangeConflictException> exceptions.</span></span> <span data-ttu-id="57af0-104">詳細については[、「オプティミスティック同時実行制御」を参照してください。概要](optimistic-concurrency-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="57af0-104">For more information, see [Optimistic Concurrency: Overview](optimistic-concurrency-overview.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="57af0-105">例</span><span class="sxs-lookup"><span data-stu-id="57af0-105">Example</span></span>  
 <span data-ttu-id="57af0-106">次の例では、累積した競合のリストを反復処理します。</span><span class="sxs-lookup"><span data-stu-id="57af0-106">The following example iterates through a list of accumulated conflicts.</span></span>  
  
 [!code-csharp[System.Data.Linq.ObjectChangeConflict#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/system.data.linq.objectchangeconflict/cs/program.cs#1)]
 [!code-vb[System.Data.Linq.ObjectChangeConflict#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/system.data.linq.objectchangeconflict/vb/module1.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="57af0-107">関連項目</span><span class="sxs-lookup"><span data-stu-id="57af0-107">See also</span></span>

- [<span data-ttu-id="57af0-108">方法: 変更の競合を管理する</span><span class="sxs-lookup"><span data-stu-id="57af0-108">How to: Manage Change Conflicts</span></span>](how-to-manage-change-conflicts.md)
