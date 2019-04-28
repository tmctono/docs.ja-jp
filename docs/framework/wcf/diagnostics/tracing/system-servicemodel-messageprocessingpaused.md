---
title: System.ServiceModel.MessageProcessingPaused
ms.date: 03/30/2017
ms.assetid: 36b5302a-93cc-478a-9bb2-8a1601fba1df
ms.openlocfilehash: ac1dacef94d6446aa407e4a390b9561d033af1bb
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61927024"
---
# <a name="systemservicemodelmessageprocessingpaused"></a><span data-ttu-id="3ae62-102">System.ServiceModel.MessageProcessingPaused</span><span class="sxs-lookup"><span data-stu-id="3ae62-102">System.ServiceModel.MessageProcessingPaused</span></span>
<span data-ttu-id="3ae62-103">System.ServiceModel.MessageProcessingPaused</span><span class="sxs-lookup"><span data-stu-id="3ae62-103">System.ServiceModel.MessageProcessingPaused</span></span>  
  
## <a name="description"></a><span data-ttu-id="3ae62-104">説明</span><span class="sxs-lookup"><span data-stu-id="3ae62-104">Description</span></span>  
 <span data-ttu-id="3ae62-105">メッセージの処理中にスレッドが切り替わりました。</span><span class="sxs-lookup"><span data-stu-id="3ae62-105">The threads were switched while processing a message.</span></span>  
  
 <span data-ttu-id="3ae62-106">メッセージ処理は、次の理由によって一時停止することがあります。</span><span class="sxs-lookup"><span data-stu-id="3ae62-106">Message processing can be paused by the following reasons:</span></span>  
  
- <span data-ttu-id="3ae62-107">ConcurrencyMode が単一または再入可能で、サービスが別のメッセージを処理している。</span><span class="sxs-lookup"><span data-stu-id="3ae62-107">ConcurrencyMode is single or reentrant, and the service is processing another message.</span></span>  
  
- <span data-ttu-id="3ae62-108">トランザクションが有効で、サービスが別のトランザクションを処理している。</span><span class="sxs-lookup"><span data-stu-id="3ae62-108">Transaction is enabled and the service is processing another transaction.</span></span>  
  
- <span data-ttu-id="3ae62-109">同期コンテキストが最新ではない。</span><span class="sxs-lookup"><span data-stu-id="3ae62-109">Synchronization context is not current.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3ae62-110">関連項目</span><span class="sxs-lookup"><span data-stu-id="3ae62-110">See also</span></span>

- [<span data-ttu-id="3ae62-111">トレース</span><span class="sxs-lookup"><span data-stu-id="3ae62-111">Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)
- [<span data-ttu-id="3ae62-112">トレースを使用したアプリケーションのトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="3ae62-112">Using Tracing to Troubleshoot Your Application</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)
- [<span data-ttu-id="3ae62-113">管理と診断</span><span class="sxs-lookup"><span data-stu-id="3ae62-113">Administration and Diagnostics</span></span>](../../../../../docs/framework/wcf/diagnostics/index.md)
