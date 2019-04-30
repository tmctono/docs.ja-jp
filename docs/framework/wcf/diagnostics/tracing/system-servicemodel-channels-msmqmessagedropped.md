---
title: System.ServiceModel.Channels.MsmqMessageDropped
ms.date: 03/30/2017
ms.assetid: 8b6e644d-fa68-4be7-abe9-3659671a37c1
ms.openlocfilehash: 3fa5ec62c5e8ac83f3f81fb406499b7e596b3dac
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61969508"
---
# <a name="systemservicemodelchannelsmsmqmessagedropped"></a><span data-ttu-id="b39d4-102">System.ServiceModel.Channels.MsmqMessageDropped</span><span class="sxs-lookup"><span data-stu-id="b39d4-102">System.ServiceModel.Channels.MsmqMessageDropped</span></span>
<span data-ttu-id="b39d4-103">MSMQ はメッセージを破棄しました。</span><span class="sxs-lookup"><span data-stu-id="b39d4-103">MSMQ dropped the message.</span></span>  
  
## <a name="description"></a><span data-ttu-id="b39d4-104">説明</span><span class="sxs-lookup"><span data-stu-id="b39d4-104">Description</span></span>  
 <span data-ttu-id="b39d4-105">このトレースは、MSMQ メッセージが破棄されたことを示します。</span><span class="sxs-lookup"><span data-stu-id="b39d4-105">The trace indicates that an MSMQ message was dropped.</span></span> <span data-ttu-id="b39d4-106">Windows Communication Foundation (WCF) が (NetMsmqBinding または MsmqIntegrationBinding のいずれかで使用) が、それらを処理できない場合は、MSMQ メッセージを削除することができます。</span><span class="sxs-lookup"><span data-stu-id="b39d4-106">MSMQ messages can be dropped when Windows Communication Foundation (WCF) (used with either the NetMsmqBinding or MsmqIntegrationBinding) is unable to process them.</span></span> <span data-ttu-id="b39d4-107">このようなメッセージは、有害メッセージと呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="b39d4-107">Such messages are referred to as poison messages.</span></span>  
  
 <span data-ttu-id="b39d4-108">有害メッセージは、NetMsmqBinding または MsmqIntegrationBinding の `ReceiveErrorHandling` プロパティが `Drop` に設定されていると破棄されます。</span><span class="sxs-lookup"><span data-stu-id="b39d4-108">A poison message is dropped when the `ReceiveErrorHandling` property on the NetMsmqBinding or MsmqIntegrationBinding is set to `Drop`.</span></span> <span data-ttu-id="b39d4-109">破棄されたメッセージはキューから削除され、元に戻すことはできません。</span><span class="sxs-lookup"><span data-stu-id="b39d4-109">A dropped message is removed from the queue and is no longer recoverable.</span></span>  
  
 <span data-ttu-id="b39d4-110">参照してください[有害メッセージの処理](https://go.microsoft.com/fwlink/?LinkID=99546)メッセージが有害になると、サービスを適切に処理を構成する方法の詳細についてはします。</span><span class="sxs-lookup"><span data-stu-id="b39d4-110">See [Poison-Message Handling](https://go.microsoft.com/fwlink/?LinkID=99546) for more details on when messages become poison and how to configure your service to handle them appropriately.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b39d4-111">関連項目</span><span class="sxs-lookup"><span data-stu-id="b39d4-111">See also</span></span>

- [<span data-ttu-id="b39d4-112">トレース</span><span class="sxs-lookup"><span data-stu-id="b39d4-112">Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)
- [<span data-ttu-id="b39d4-113">トレースを使用したアプリケーションのトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="b39d4-113">Using Tracing to Troubleshoot Your Application</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)
- [<span data-ttu-id="b39d4-114">管理と診断</span><span class="sxs-lookup"><span data-stu-id="b39d4-114">Administration and Diagnostics</span></span>](../../../../../docs/framework/wcf/diagnostics/index.md)
- [<span data-ttu-id="b39d4-115">有害メッセージ処理</span><span class="sxs-lookup"><span data-stu-id="b39d4-115">Poison-Message Handling</span></span>](https://go.microsoft.com/fwlink/?LinkID=99546)
