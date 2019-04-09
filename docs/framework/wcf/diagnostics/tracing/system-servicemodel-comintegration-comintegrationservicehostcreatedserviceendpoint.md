---
title: System.ServiceModel.Channels.MsmqMoveOrDeleteAttemptFailed
ms.date: 03/30/2017
ms.assetid: d75d39da-7502-4a6a-91b9-eaa05b8e24d5
ms.openlocfilehash: d56bbf145c85902d8e5f1fd21f760633121da6da
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2019
ms.locfileid: "59115285"
---
# <a name="systemservicemodelchannelsmsmqmoveordeleteattemptfailed"></a><span data-ttu-id="d5391-102">System.ServiceModel.Channels.MsmqMoveOrDeleteAttemptFailed</span><span class="sxs-lookup"><span data-stu-id="d5391-102">System.ServiceModel.Channels.MsmqMoveOrDeleteAttemptFailed</span></span>
<span data-ttu-id="d5391-103">メッセージを移動または削除できません。</span><span class="sxs-lookup"><span data-stu-id="d5391-103">Cannot move or delete message.</span></span>  
  
## <a name="description"></a><span data-ttu-id="d5391-104">説明</span><span class="sxs-lookup"><span data-stu-id="d5391-104">Description</span></span>  
 <span data-ttu-id="d5391-105">このトレースは、MSMQ メッセージの移動、削除、または拒否の試行中にエラーが発生したことを示しています。</span><span class="sxs-lookup"><span data-stu-id="d5391-105">The trace indicates that a failure occurred when attempting to move, delete, or reject an MSMQ message.</span></span>  
  
 <span data-ttu-id="d5391-106">MSMQ メッセージは、Windows Communication Foundation (WCF) によって (NetMsmqBinding または MsmqIntegrationBinding のいずれかを使用) する場合に使用されます。このトレースは選択された値の関連する、 `ReceiveErrorHandling` NetMsmqBinding または MsmqIntegrationBinding のプロパティ。</span><span class="sxs-lookup"><span data-stu-id="d5391-106">MSMQ messages are employed by Windows Communication Foundation (WCF) (when used with either the NetMsmqBinding or the MsmqIntegrationBinding).This trace is related to the chosen value of the `ReceiveErrorHandling` property on the NetMsmqBinding or MsmqIntegrationBinding.</span></span>  
  
 <span data-ttu-id="d5391-107">このトレースはシステム全体についてのエラーを示すものではありません。</span><span class="sxs-lookup"><span data-stu-id="d5391-107">This trace is not indicative of an overall system failure.</span></span> <span data-ttu-id="d5391-108">ただし、選択した有害メッセージの処置に失敗したことを示しています。</span><span class="sxs-lookup"><span data-stu-id="d5391-108">However, it indicates that the chosen poison message disposition failed for a message.</span></span> <span data-ttu-id="d5391-109">参照してください[有害メッセージの処理](https://go.microsoft.com/fwlink/?LinkID=99546)メッセージが有害になると、サービスを適切に処理を構成する方法の詳細についてはします。</span><span class="sxs-lookup"><span data-stu-id="d5391-109">See [Poison-Message Handling](https://go.microsoft.com/fwlink/?LinkID=99546) for more details on when messages become poison and how to configure your service to handle them appropriately.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d5391-110">関連項目</span><span class="sxs-lookup"><span data-stu-id="d5391-110">See also</span></span>

- [<span data-ttu-id="d5391-111">トレース</span><span class="sxs-lookup"><span data-stu-id="d5391-111">Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)
- [<span data-ttu-id="d5391-112">トレースを使用したアプリケーションのトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="d5391-112">Using Tracing to Troubleshoot Your Application</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)
- [<span data-ttu-id="d5391-113">管理と診断</span><span class="sxs-lookup"><span data-stu-id="d5391-113">Administration and Diagnostics</span></span>](../../../../../docs/framework/wcf/diagnostics/index.md)
