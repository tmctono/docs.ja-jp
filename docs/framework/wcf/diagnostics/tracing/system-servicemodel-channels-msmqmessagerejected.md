---
title: System.ServiceModel.Channels.MsmqMessageRejected
ms.date: 03/30/2017
ms.assetid: 9b7c10a7-2af6-44a2-8b1a-90bba0c7cf26
ms.openlocfilehash: 8f783dcd4b966ed89c24d724918a3923c5a2d0b1
ms.sourcegitcommit: 515469828d0f040e01bde01df6b8e4eb43630b06
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/06/2020
ms.locfileid: "78674770"
---
# <a name="systemservicemodelchannelsmsmqmessagerejected"></a><span data-ttu-id="c3fc6-102">System.ServiceModel.Channels.MsmqMessageRejected</span><span class="sxs-lookup"><span data-stu-id="c3fc6-102">System.ServiceModel.Channels.MsmqMessageRejected</span></span>
<span data-ttu-id="c3fc6-103">MSMQ はメッセージを拒否しました。</span><span class="sxs-lookup"><span data-stu-id="c3fc6-103">MSMQ rejected the message.</span></span>  
  
## <a name="description"></a><span data-ttu-id="c3fc6-104">説明</span><span class="sxs-lookup"><span data-stu-id="c3fc6-104">Description</span></span>  
 <span data-ttu-id="c3fc6-105">このトレースは、MSMQ メッセージが拒否されたことを示します。</span><span class="sxs-lookup"><span data-stu-id="c3fc6-105">This trace indicates that an MSMQ message was rejected.</span></span>  
  
 <span data-ttu-id="c3fc6-106">MSMQ メッセージは、Windows 通信ファウンデーション (WCF) (NetMsmqBinding または MsmqIntegrationBinding で使用される) がメッセージを処理できない場合に拒否できます。</span><span class="sxs-lookup"><span data-stu-id="c3fc6-106">MSMQ messages can be rejected when Windows Communication Foundation (WCF) (used with either the NetMsmqBinding or MsmqIntegrationBinding) is unable to process them.</span></span> <span data-ttu-id="c3fc6-107">このようなメッセージは、有害メッセージと呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="c3fc6-107">Such messages are referred to as poison messages.</span></span> <span data-ttu-id="c3fc6-108">有害メッセージは、NetMsmqBinding または MsmqIntegrationBinding の `ReceiveErrorHandling` プロパティが `Reject` に設定されると拒否されます。</span><span class="sxs-lookup"><span data-stu-id="c3fc6-108">A poison message is rejected when the `ReceiveErrorHandling` property on the NetMsmqBinding or MsmqIntegrationBinding is set to `Reject`.</span></span> <span data-ttu-id="c3fc6-109">拒否されたメッセージは、送信者の[配信不能キュー](https://docs.microsoft.com/dotnet/framework/wcf/feature-details/using-dead-letter-queues-to-handle-message-transfer-failures)に戻されます。</span><span class="sxs-lookup"><span data-stu-id="c3fc6-109">A rejected message is delivered back to the sender’s [Dead-Letter Queue](https://docs.microsoft.com/dotnet/framework/wcf/feature-details/using-dead-letter-queues-to-handle-message-transfer-failures).</span></span>  
  
 <span data-ttu-id="c3fc6-110">メッセージが有害になるタイミングと、メッセージを適切に処理するようにサービスを設定する方法の詳細については、「 [Poison-Message の処理](../../feature-details/poison-message-handling.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c3fc6-110">For more information on when messages become poison and how to configure your service to handle them appropriately, see [Poison-Message Handling](../../feature-details/poison-message-handling.md).</span></span>  
  
 <span data-ttu-id="c3fc6-111">拒否されたメッセージが MSMQ で何を意味するかの詳細については[、「MQMarkMessageRejected」を参照](https://docs.microsoft.com/previous-versions/windows/desktop/msmq/ms707071(v%3dvs.85))してください。</span><span class="sxs-lookup"><span data-stu-id="c3fc6-111">For more information on what a rejected message means in MSMQ, see [MQMarkMessageRejected](https://docs.microsoft.com/previous-versions/windows/desktop/msmq/ms707071(v%3dvs.85)).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c3fc6-112">関連項目</span><span class="sxs-lookup"><span data-stu-id="c3fc6-112">See also</span></span>

- [<span data-ttu-id="c3fc6-113">トレース</span><span class="sxs-lookup"><span data-stu-id="c3fc6-113">Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)
- [<span data-ttu-id="c3fc6-114">トレースを使用したアプリケーションのトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="c3fc6-114">Using Tracing to Troubleshoot Your Application</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)
- [<span data-ttu-id="c3fc6-115">管理と診断</span><span class="sxs-lookup"><span data-stu-id="c3fc6-115">Administration and Diagnostics</span></span>](../../../../../docs/framework/wcf/diagnostics/index.md)
- [<span data-ttu-id="c3fc6-116">有害メッセージの処理</span><span class="sxs-lookup"><span data-stu-id="c3fc6-116">Poison-Message Handling</span></span>](../../feature-details/poison-message-handling.md)
- <span data-ttu-id="c3fc6-117">[拒否されたメッセージ](https://docs.microsoft.com/previous-versions/windows/desktop/msmq/ms707071(v%3dvs.85))</span><span class="sxs-lookup"><span data-stu-id="c3fc6-117">[MQMarkMessageRejected](https://docs.microsoft.com/previous-versions/windows/desktop/msmq/ms707071(v%3dvs.85))</span></span>
