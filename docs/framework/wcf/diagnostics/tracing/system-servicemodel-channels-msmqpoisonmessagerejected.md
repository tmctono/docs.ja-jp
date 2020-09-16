---
title: System.ServiceModel.Channels.MsmqPoisonMessageRejected
ms.date: 03/30/2017
ms.assetid: 0e64b9bd-1f12-43df-a189-d7be3c2bace1
ms.openlocfilehash: c5401bae1d8e7f61939d8de321353f59f412f966
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/15/2020
ms.locfileid: "90535334"
---
# <a name="systemservicemodelchannelsmsmqpoisonmessagerejected"></a><span data-ttu-id="f6e6d-102">System.ServiceModel.Channels.MsmqPoisonMessageRejected</span><span class="sxs-lookup"><span data-stu-id="f6e6d-102">System.ServiceModel.Channels.MsmqPoisonMessageRejected</span></span>
<span data-ttu-id="f6e6d-103">有害メッセージは拒否されました。</span><span class="sxs-lookup"><span data-stu-id="f6e6d-103">Poison message rejected.</span></span>  
  
## <a name="description"></a><span data-ttu-id="f6e6d-104">[説明]</span><span class="sxs-lookup"><span data-stu-id="f6e6d-104">Description</span></span>  

 <span data-ttu-id="f6e6d-105">このトレースは、有害メッセージが検出され、続いて拒否されたことを示します。</span><span class="sxs-lookup"><span data-stu-id="f6e6d-105">The trace indicates that a poison message was encountered and subsequently rejected.</span></span> <span data-ttu-id="f6e6d-106">これは、NetMsmqBinding または MsmqIntegrationBinding の `ReceiveErrorHandling` プロパティが `Reject` に設定されると発生します。</span><span class="sxs-lookup"><span data-stu-id="f6e6d-106">This occurs when the `ReceiveErrorHandling` property on the NetMsmqBinding or MsmqIntegrationBinding is set to `Reject`.</span></span> <span data-ttu-id="f6e6d-107">拒否されたメッセージは、送信側の [配信不能キュー](../../feature-details/using-dead-letter-queues-to-handle-message-transfer-failures.md)に配信されます。</span><span class="sxs-lookup"><span data-stu-id="f6e6d-107">A rejected message is delivered back to the sender’s [Dead-Letter Queue](../../feature-details/using-dead-letter-queues-to-handle-message-transfer-failures.md).</span></span>  
  
 <span data-ttu-id="f6e6d-108">メッセージが有害になった場合の詳細、およびメッセージを適切に処理するようにサービスを構成する方法については、「 [有害メッセージの処理](../../feature-details/poison-message-handling.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f6e6d-108">For more information on when messages become poison and how to configure your service to handle them appropriately, see [Poison-Message Handling](../../feature-details/poison-message-handling.md).</span></span> <span data-ttu-id="f6e6d-109">MSMQ での拒否されたメッセージの意味の詳細については、「 [MQMarkMessageRejected](/previous-versions/windows/desktop/msmq/ms707071(v=vs.85))」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f6e6d-109">For more information on what a rejected message means in MSMQ, see [MQMarkMessageRejected](/previous-versions/windows/desktop/msmq/ms707071(v=vs.85)).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f6e6d-110">関連項目</span><span class="sxs-lookup"><span data-stu-id="f6e6d-110">See also</span></span>

- [<span data-ttu-id="f6e6d-111">トレース</span><span class="sxs-lookup"><span data-stu-id="f6e6d-111">Tracing</span></span>](index.md)
- [<span data-ttu-id="f6e6d-112">トレースを使用したアプリケーションのトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="f6e6d-112">Using Tracing to Troubleshoot Your Application</span></span>](using-tracing-to-troubleshoot-your-application.md)
- [<span data-ttu-id="f6e6d-113">管理と診断</span><span class="sxs-lookup"><span data-stu-id="f6e6d-113">Administration and Diagnostics</span></span>](../index.md)
- [<span data-ttu-id="f6e6d-114">有害メッセージの処理</span><span class="sxs-lookup"><span data-stu-id="f6e6d-114">Poison-Message Handling</span></span>](../../feature-details/poison-message-handling.md)
- <span data-ttu-id="f6e6d-115">[MQMarkMessageRejected](/previous-versions/windows/desktop/msmq/ms707071(v=vs.85))</span><span class="sxs-lookup"><span data-stu-id="f6e6d-115">[MQMarkMessageRejected](/previous-versions/windows/desktop/msmq/ms707071(v=vs.85))</span></span>
