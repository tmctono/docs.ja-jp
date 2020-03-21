---
title: System.ServiceModel.Channels.MsmqPoisonMessageRejected
ms.date: 03/30/2017
ms.assetid: 0e64b9bd-1f12-43df-a189-d7be3c2bace1
ms.openlocfilehash: 6b0e6e3ebcf5d414e9dbbcecd09ba2e8bb3ddd3a
ms.sourcegitcommit: 515469828d0f040e01bde01df6b8e4eb43630b06
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/06/2020
ms.locfileid: "78674808"
---
# <a name="systemservicemodelchannelsmsmqpoisonmessagerejected"></a><span data-ttu-id="bcf3b-102">System.ServiceModel.Channels.MsmqPoisonMessageRejected</span><span class="sxs-lookup"><span data-stu-id="bcf3b-102">System.ServiceModel.Channels.MsmqPoisonMessageRejected</span></span>
<span data-ttu-id="bcf3b-103">有害メッセージは拒否されました。</span><span class="sxs-lookup"><span data-stu-id="bcf3b-103">Poison message rejected.</span></span>  
  
## <a name="description"></a><span data-ttu-id="bcf3b-104">説明</span><span class="sxs-lookup"><span data-stu-id="bcf3b-104">Description</span></span>  

 <span data-ttu-id="bcf3b-105">このトレースは、有害メッセージが検出され、続いて拒否されたことを示します。</span><span class="sxs-lookup"><span data-stu-id="bcf3b-105">The trace indicates that a poison message was encountered and subsequently rejected.</span></span> <span data-ttu-id="bcf3b-106">これは、NetMsmqBinding または MsmqIntegrationBinding の `ReceiveErrorHandling` プロパティが `Reject` に設定されると発生します。</span><span class="sxs-lookup"><span data-stu-id="bcf3b-106">This occurs when the `ReceiveErrorHandling` property on the NetMsmqBinding or MsmqIntegrationBinding is set to `Reject`.</span></span> <span data-ttu-id="bcf3b-107">拒否されたメッセージは、送信者の[配信不能キュー](../../feature-details/using-dead-letter-queues-to-handle-message-transfer-failures.md)に戻されます。</span><span class="sxs-lookup"><span data-stu-id="bcf3b-107">A rejected message is delivered back to the sender’s [Dead-Letter Queue](../../feature-details/using-dead-letter-queues-to-handle-message-transfer-failures.md).</span></span>  
  
 <span data-ttu-id="bcf3b-108">メッセージが有害になるタイミングと、メッセージを適切に処理するようにサービスを設定する方法の詳細については、「 [Poison-Message の処理](../../feature-details/poison-message-handling.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="bcf3b-108">For more information on when messages become poison and how to configure your service to handle them appropriately, see [Poison-Message Handling](../../feature-details/poison-message-handling.md).</span></span> <span data-ttu-id="bcf3b-109">拒否されたメッセージが MSMQ で何を意味するかの詳細については[、「MQMarkMessageRejected」を参照](https://docs.microsoft.com/previous-versions/windows/desktop/msmq/ms707071(v%3dvs.85))してください。</span><span class="sxs-lookup"><span data-stu-id="bcf3b-109">For more information on what a rejected message means in MSMQ, see [MQMarkMessageRejected](https://docs.microsoft.com/previous-versions/windows/desktop/msmq/ms707071(v%3dvs.85)).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bcf3b-110">関連項目</span><span class="sxs-lookup"><span data-stu-id="bcf3b-110">See also</span></span>

- [<span data-ttu-id="bcf3b-111">トレース</span><span class="sxs-lookup"><span data-stu-id="bcf3b-111">Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)
- [<span data-ttu-id="bcf3b-112">トレースを使用したアプリケーションのトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="bcf3b-112">Using Tracing to Troubleshoot Your Application</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)
- [<span data-ttu-id="bcf3b-113">管理と診断</span><span class="sxs-lookup"><span data-stu-id="bcf3b-113">Administration and Diagnostics</span></span>](../../../../../docs/framework/wcf/diagnostics/index.md)
- [<span data-ttu-id="bcf3b-114">有害メッセージの処理</span><span class="sxs-lookup"><span data-stu-id="bcf3b-114">Poison-Message Handling</span></span>](../../feature-details/poison-message-handling.md)
- <span data-ttu-id="bcf3b-115">[拒否されたメッセージ](https://docs.microsoft.com/previous-versions/windows/desktop/msmq/ms707071(v%3dvs.85))</span><span class="sxs-lookup"><span data-stu-id="bcf3b-115">[MQMarkMessageRejected](https://docs.microsoft.com/previous-versions/windows/desktop/msmq/ms707071(v%3dvs.85))</span></span>
