---
title: System.ServiceModel.Channels.MsmqMessageRejected
ms.date: 03/30/2017
ms.assetid: 9b7c10a7-2af6-44a2-8b1a-90bba0c7cf26
ms.openlocfilehash: c388a9dc3569e20639de09abc5f4941b73c561ad
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/09/2020
ms.locfileid: "84578052"
---
# <a name="systemservicemodelchannelsmsmqmessagerejected"></a><span data-ttu-id="ae37b-102">System.ServiceModel.Channels.MsmqMessageRejected</span><span class="sxs-lookup"><span data-stu-id="ae37b-102">System.ServiceModel.Channels.MsmqMessageRejected</span></span>
<span data-ttu-id="ae37b-103">MSMQ はメッセージを拒否しました。</span><span class="sxs-lookup"><span data-stu-id="ae37b-103">MSMQ rejected the message.</span></span>  
  
## <a name="description"></a><span data-ttu-id="ae37b-104">説明</span><span class="sxs-lookup"><span data-stu-id="ae37b-104">Description</span></span>  
 <span data-ttu-id="ae37b-105">このトレースは、MSMQ メッセージが拒否されたことを示します。</span><span class="sxs-lookup"><span data-stu-id="ae37b-105">This trace indicates that an MSMQ message was rejected.</span></span>  
  
 <span data-ttu-id="ae37b-106">MSMQ メッセージは、Windows Communication Foundation (WCF) (NetMsmqBinding または MsmqIntegrationBinding で使用される) が処理できない場合に拒否されることがあります。</span><span class="sxs-lookup"><span data-stu-id="ae37b-106">MSMQ messages can be rejected when Windows Communication Foundation (WCF) (used with either the NetMsmqBinding or MsmqIntegrationBinding) is unable to process them.</span></span> <span data-ttu-id="ae37b-107">このようなメッセージは、有害メッセージと呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="ae37b-107">Such messages are referred to as poison messages.</span></span> <span data-ttu-id="ae37b-108">有害メッセージは、NetMsmqBinding または MsmqIntegrationBinding の `ReceiveErrorHandling` プロパティが `Reject` に設定されると拒否されます。</span><span class="sxs-lookup"><span data-stu-id="ae37b-108">A poison message is rejected when the `ReceiveErrorHandling` property on the NetMsmqBinding or MsmqIntegrationBinding is set to `Reject`.</span></span> <span data-ttu-id="ae37b-109">拒否されたメッセージは、送信側の[配信不能キュー](https://docs.microsoft.com/dotnet/framework/wcf/feature-details/using-dead-letter-queues-to-handle-message-transfer-failures)に配信されます。</span><span class="sxs-lookup"><span data-stu-id="ae37b-109">A rejected message is delivered back to the sender’s [Dead-Letter Queue](https://docs.microsoft.com/dotnet/framework/wcf/feature-details/using-dead-letter-queues-to-handle-message-transfer-failures).</span></span>  
  
 <span data-ttu-id="ae37b-110">メッセージが有害になった場合の詳細、およびメッセージを適切に処理するようにサービスを構成する方法については、「[有害メッセージの処理](../../feature-details/poison-message-handling.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ae37b-110">For more information on when messages become poison and how to configure your service to handle them appropriately, see [Poison-Message Handling](../../feature-details/poison-message-handling.md).</span></span>  
  
 <span data-ttu-id="ae37b-111">MSMQ での拒否されたメッセージの意味の詳細については、「 [MQMarkMessageRejected](https://docs.microsoft.com/previous-versions/windows/desktop/msmq/ms707071(v%3dvs.85))」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ae37b-111">For more information on what a rejected message means in MSMQ, see [MQMarkMessageRejected](https://docs.microsoft.com/previous-versions/windows/desktop/msmq/ms707071(v%3dvs.85)).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ae37b-112">関連項目</span><span class="sxs-lookup"><span data-stu-id="ae37b-112">See also</span></span>

- [<span data-ttu-id="ae37b-113">トレース</span><span class="sxs-lookup"><span data-stu-id="ae37b-113">Tracing</span></span>](index.md)
- [<span data-ttu-id="ae37b-114">トレースを使用したアプリケーションのトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="ae37b-114">Using Tracing to Troubleshoot Your Application</span></span>](using-tracing-to-troubleshoot-your-application.md)
- [<span data-ttu-id="ae37b-115">管理と診断</span><span class="sxs-lookup"><span data-stu-id="ae37b-115">Administration and Diagnostics</span></span>](../index.md)
- [<span data-ttu-id="ae37b-116">有害メッセージの処理</span><span class="sxs-lookup"><span data-stu-id="ae37b-116">Poison-Message Handling</span></span>](../../feature-details/poison-message-handling.md)
- <span data-ttu-id="ae37b-117">[MQMarkMessageRejected](https://docs.microsoft.com/previous-versions/windows/desktop/msmq/ms707071(v%3dvs.85))</span><span class="sxs-lookup"><span data-stu-id="ae37b-117">[MQMarkMessageRejected](https://docs.microsoft.com/previous-versions/windows/desktop/msmq/ms707071(v%3dvs.85))</span></span>
