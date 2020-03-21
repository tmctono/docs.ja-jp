---
title: System.ServiceModel.Channels.MsmqMessageDropped
ms.date: 03/30/2017
ms.assetid: 8b6e644d-fa68-4be7-abe9-3659671a37c1
ms.openlocfilehash: e80fecf508158dcb53f08b75c8f9486c13e403a4
ms.sourcegitcommit: 515469828d0f040e01bde01df6b8e4eb43630b06
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/06/2020
ms.locfileid: "78674796"
---
# <a name="systemservicemodelchannelsmsmqmessagedropped"></a><span data-ttu-id="cef41-102">System.ServiceModel.Channels.MsmqMessageDropped</span><span class="sxs-lookup"><span data-stu-id="cef41-102">System.ServiceModel.Channels.MsmqMessageDropped</span></span>
<span data-ttu-id="cef41-103">MSMQ はメッセージを破棄しました。</span><span class="sxs-lookup"><span data-stu-id="cef41-103">MSMQ dropped the message.</span></span>  
  
## <a name="description"></a><span data-ttu-id="cef41-104">説明</span><span class="sxs-lookup"><span data-stu-id="cef41-104">Description</span></span>  
 <span data-ttu-id="cef41-105">このトレースは、MSMQ メッセージが破棄されたことを示します。</span><span class="sxs-lookup"><span data-stu-id="cef41-105">The trace indicates that an MSMQ message was dropped.</span></span> <span data-ttu-id="cef41-106">MSMQ メッセージは、Windows 通信ファウンデーション (WCF) (NetMsmqBinding または MsmqIntegrationBinding で使用される) がそれらを処理できない場合にドロップできます。</span><span class="sxs-lookup"><span data-stu-id="cef41-106">MSMQ messages can be dropped when Windows Communication Foundation (WCF) (used with either the NetMsmqBinding or MsmqIntegrationBinding) is unable to process them.</span></span> <span data-ttu-id="cef41-107">このようなメッセージは、有害メッセージと呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="cef41-107">Such messages are referred to as poison messages.</span></span>  
  
 <span data-ttu-id="cef41-108">有害メッセージは、NetMsmqBinding または MsmqIntegrationBinding の `ReceiveErrorHandling` プロパティが `Drop` に設定されていると破棄されます。</span><span class="sxs-lookup"><span data-stu-id="cef41-108">A poison message is dropped when the `ReceiveErrorHandling` property on the NetMsmqBinding or MsmqIntegrationBinding is set to `Drop`.</span></span> <span data-ttu-id="cef41-109">破棄されたメッセージはキューから削除され、元に戻すことはできません。</span><span class="sxs-lookup"><span data-stu-id="cef41-109">A dropped message is removed from the queue and is no longer recoverable.</span></span>  
  
 <span data-ttu-id="cef41-110">メッセージが有害になるタイミングと、メッセージを適切に処理するようにサービスを設定する方法の詳細については、「 [Poison-Message の処理](../../feature-details/poison-message-handling.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="cef41-110">For more information on when messages become poison and how to configure your service to handle them appropriately, see [Poison-Message Handling](../../feature-details/poison-message-handling.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cef41-111">関連項目</span><span class="sxs-lookup"><span data-stu-id="cef41-111">See also</span></span>

- [<span data-ttu-id="cef41-112">トレース</span><span class="sxs-lookup"><span data-stu-id="cef41-112">Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)
- [<span data-ttu-id="cef41-113">トレースを使用したアプリケーションのトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="cef41-113">Using Tracing to Troubleshoot Your Application</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)
- [<span data-ttu-id="cef41-114">管理と診断</span><span class="sxs-lookup"><span data-stu-id="cef41-114">Administration and Diagnostics</span></span>](../../../../../docs/framework/wcf/diagnostics/index.md)
- [<span data-ttu-id="cef41-115">有害メッセージの処理</span><span class="sxs-lookup"><span data-stu-id="cef41-115">Poison-Message Handling</span></span>](../../feature-details/poison-message-handling.md)
