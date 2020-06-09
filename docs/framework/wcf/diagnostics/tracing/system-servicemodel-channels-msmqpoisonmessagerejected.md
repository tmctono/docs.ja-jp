---
title: System.ServiceModel.Channels.MsmqPoisonMessageRejected
ms.date: 03/30/2017
ms.assetid: 0e64b9bd-1f12-43df-a189-d7be3c2bace1
ms.openlocfilehash: f0e49fcfa13bb9932a88a4e79d617343c080bb3c
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/09/2020
ms.locfileid: "84598373"
---
# <a name="systemservicemodelchannelsmsmqpoisonmessagerejected"></a><span data-ttu-id="b5b10-102">System.ServiceModel.Channels.MsmqPoisonMessageRejected</span><span class="sxs-lookup"><span data-stu-id="b5b10-102">System.ServiceModel.Channels.MsmqPoisonMessageRejected</span></span>
<span data-ttu-id="b5b10-103">有害メッセージは拒否されました。</span><span class="sxs-lookup"><span data-stu-id="b5b10-103">Poison message rejected.</span></span>  
  
## <a name="description"></a><span data-ttu-id="b5b10-104">説明</span><span class="sxs-lookup"><span data-stu-id="b5b10-104">Description</span></span>  

 <span data-ttu-id="b5b10-105">このトレースは、有害メッセージが検出され、続いて拒否されたことを示します。</span><span class="sxs-lookup"><span data-stu-id="b5b10-105">The trace indicates that a poison message was encountered and subsequently rejected.</span></span> <span data-ttu-id="b5b10-106">これは、NetMsmqBinding または MsmqIntegrationBinding の `ReceiveErrorHandling` プロパティが `Reject` に設定されると発生します。</span><span class="sxs-lookup"><span data-stu-id="b5b10-106">This occurs when the `ReceiveErrorHandling` property on the NetMsmqBinding or MsmqIntegrationBinding is set to `Reject`.</span></span> <span data-ttu-id="b5b10-107">拒否されたメッセージは、送信側の[配信不能キュー](../../feature-details/using-dead-letter-queues-to-handle-message-transfer-failures.md)に配信されます。</span><span class="sxs-lookup"><span data-stu-id="b5b10-107">A rejected message is delivered back to the sender’s [Dead-Letter Queue](../../feature-details/using-dead-letter-queues-to-handle-message-transfer-failures.md).</span></span>  
  
 <span data-ttu-id="b5b10-108">メッセージが有害になった場合の詳細、およびメッセージを適切に処理するようにサービスを構成する方法については、「[有害メッセージの処理](../../feature-details/poison-message-handling.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b5b10-108">For more information on when messages become poison and how to configure your service to handle them appropriately, see [Poison-Message Handling](../../feature-details/poison-message-handling.md).</span></span> <span data-ttu-id="b5b10-109">MSMQ での拒否されたメッセージの意味の詳細については、「 [MQMarkMessageRejected](https://docs.microsoft.com/previous-versions/windows/desktop/msmq/ms707071(v%3dvs.85))」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b5b10-109">For more information on what a rejected message means in MSMQ, see [MQMarkMessageRejected](https://docs.microsoft.com/previous-versions/windows/desktop/msmq/ms707071(v%3dvs.85)).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b5b10-110">関連項目</span><span class="sxs-lookup"><span data-stu-id="b5b10-110">See also</span></span>

- [<span data-ttu-id="b5b10-111">トレース</span><span class="sxs-lookup"><span data-stu-id="b5b10-111">Tracing</span></span>](index.md)
- [<span data-ttu-id="b5b10-112">トレースを使用したアプリケーションのトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="b5b10-112">Using Tracing to Troubleshoot Your Application</span></span>](using-tracing-to-troubleshoot-your-application.md)
- [<span data-ttu-id="b5b10-113">管理と診断</span><span class="sxs-lookup"><span data-stu-id="b5b10-113">Administration and Diagnostics</span></span>](../index.md)
- [<span data-ttu-id="b5b10-114">有害メッセージの処理</span><span class="sxs-lookup"><span data-stu-id="b5b10-114">Poison-Message Handling</span></span>](../../feature-details/poison-message-handling.md)
- <span data-ttu-id="b5b10-115">[MQMarkMessageRejected](https://docs.microsoft.com/previous-versions/windows/desktop/msmq/ms707071(v%3dvs.85))</span><span class="sxs-lookup"><span data-stu-id="b5b10-115">[MQMarkMessageRejected](https://docs.microsoft.com/previous-versions/windows/desktop/msmq/ms707071(v%3dvs.85))</span></span>
