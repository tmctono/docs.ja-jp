---
title: System.ServiceModel.MessageProcessingPaused
ms.date: 03/30/2017
ms.assetid: 36b5302a-93cc-478a-9bb2-8a1601fba1df
ms.openlocfilehash: ac1dacef94d6446aa407e4a390b9561d033af1bb
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2019
ms.locfileid: "59087481"
---
# <a name="systemservicemodelmessageprocessingpaused"></a><span data-ttu-id="26f9a-102">System.ServiceModel.MessageProcessingPaused</span><span class="sxs-lookup"><span data-stu-id="26f9a-102">System.ServiceModel.MessageProcessingPaused</span></span>
<span data-ttu-id="26f9a-103">System.ServiceModel.MessageProcessingPaused</span><span class="sxs-lookup"><span data-stu-id="26f9a-103">System.ServiceModel.MessageProcessingPaused</span></span>  
  
## <a name="description"></a><span data-ttu-id="26f9a-104">説明</span><span class="sxs-lookup"><span data-stu-id="26f9a-104">Description</span></span>  
 <span data-ttu-id="26f9a-105">メッセージの処理中にスレッドが切り替わりました。</span><span class="sxs-lookup"><span data-stu-id="26f9a-105">The threads were switched while processing a message.</span></span>  
  
 <span data-ttu-id="26f9a-106">メッセージ処理は、次の理由によって一時停止することがあります。</span><span class="sxs-lookup"><span data-stu-id="26f9a-106">Message processing can be paused by the following reasons:</span></span>  
  
-   <span data-ttu-id="26f9a-107">ConcurrencyMode が単一または再入可能で、サービスが別のメッセージを処理している。</span><span class="sxs-lookup"><span data-stu-id="26f9a-107">ConcurrencyMode is single or reentrant, and the service is processing another message.</span></span>  
  
-   <span data-ttu-id="26f9a-108">トランザクションが有効で、サービスが別のトランザクションを処理している。</span><span class="sxs-lookup"><span data-stu-id="26f9a-108">Transaction is enabled and the service is processing another transaction.</span></span>  
  
-   <span data-ttu-id="26f9a-109">同期コンテキストが最新ではない。</span><span class="sxs-lookup"><span data-stu-id="26f9a-109">Synchronization context is not current.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="26f9a-110">関連項目</span><span class="sxs-lookup"><span data-stu-id="26f9a-110">See also</span></span>

- [<span data-ttu-id="26f9a-111">トレース</span><span class="sxs-lookup"><span data-stu-id="26f9a-111">Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)
- [<span data-ttu-id="26f9a-112">トレースを使用したアプリケーションのトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="26f9a-112">Using Tracing to Troubleshoot Your Application</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)
- [<span data-ttu-id="26f9a-113">管理と診断</span><span class="sxs-lookup"><span data-stu-id="26f9a-113">Administration and Diagnostics</span></span>](../../../../../docs/framework/wcf/diagnostics/index.md)
