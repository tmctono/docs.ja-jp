---
title: System.ServiceModel.ManualFlowThrottleLimitReached
ms.date: 03/30/2017
ms.assetid: 9aba851f-1830-493b-8e3e-60f454eb923e
ms.openlocfilehash: fb69c3c737a0e77b05e08ab8d8282069feb069bb
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2019
ms.locfileid: "59095686"
---
# <a name="systemservicemodelmanualflowthrottlelimitreached"></a><span data-ttu-id="baae0-102">System.ServiceModel.ManualFlowThrottleLimitReached</span><span class="sxs-lookup"><span data-stu-id="baae0-102">System.ServiceModel.ManualFlowThrottleLimitReached</span></span>
<span data-ttu-id="baae0-103">System.ServiceModel.ManualFlowThrottleLimitReached</span><span class="sxs-lookup"><span data-stu-id="baae0-103">System.ServiceModel.ManualFlowThrottleLimitReached</span></span>  
  
## <a name="description"></a><span data-ttu-id="baae0-104">説明</span><span class="sxs-lookup"><span data-stu-id="baae0-104">Description</span></span>  
 <span data-ttu-id="baae0-105">システムは ManualFlowControlLimit スロットルに設定された制限値に達しました。</span><span class="sxs-lookup"><span data-stu-id="baae0-105">The system reached the limit set for the ManualFlowControlLimit throttle.</span></span> <span data-ttu-id="baae0-106">スロットル値を変更するには、ServiceHost または InstanceContext の ManualFlowControlLimit プロパティを適宜変更します。</span><span class="sxs-lookup"><span data-stu-id="baae0-106">The throttle value can be changed by modifying the ManualFlowControlLimit property on either the ServiceHost or InstanceContext, as applicable.</span></span>  
  
 <span data-ttu-id="baae0-107">このトレースは、マニュアル フロー制御制限が初めて 0 に減少したときに出力されます。</span><span class="sxs-lookup"><span data-stu-id="baae0-107">This trace is emitted when the manual flow control limit is initially reduced to 0.</span></span> <span data-ttu-id="baae0-108">それ以降は、0 に変更されてもトレースされません。</span><span class="sxs-lookup"><span data-stu-id="baae0-108">Subsequent changes to 0 are not traced.</span></span> <span data-ttu-id="baae0-109">インスタンス コンテキストに対するフロー制御制限は、コンテキストごとに 1 回トレースされます。</span><span class="sxs-lookup"><span data-stu-id="baae0-109">Flow control limit on the instance context is traced once for each context.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="baae0-110">関連項目</span><span class="sxs-lookup"><span data-stu-id="baae0-110">See also</span></span>

- [<span data-ttu-id="baae0-111">トレース</span><span class="sxs-lookup"><span data-stu-id="baae0-111">Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)
- [<span data-ttu-id="baae0-112">トレースを使用したアプリケーションのトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="baae0-112">Using Tracing to Troubleshoot Your Application</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)
- [<span data-ttu-id="baae0-113">管理と診断</span><span class="sxs-lookup"><span data-stu-id="baae0-113">Administration and Diagnostics</span></span>](../../../../../docs/framework/wcf/diagnostics/index.md)
