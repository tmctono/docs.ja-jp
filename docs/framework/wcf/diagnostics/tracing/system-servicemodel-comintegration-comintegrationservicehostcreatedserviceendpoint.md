---
title: System.ServiceModel.Channels.MsmqMoveOrDeleteAttemptFailed
ms.date: 03/30/2017
ms.assetid: d75d39da-7502-4a6a-91b9-eaa05b8e24d5
ms.openlocfilehash: f89dd1373d67714046f8cb958582c3a5dea04456
ms.sourcegitcommit: 515469828d0f040e01bde01df6b8e4eb43630b06
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/06/2020
ms.locfileid: "78674790"
---
# <a name="systemservicemodelchannelsmsmqmoveordeleteattemptfailed"></a><span data-ttu-id="22719-102">System.ServiceModel.Channels.MsmqMoveOrDeleteAttemptFailed</span><span class="sxs-lookup"><span data-stu-id="22719-102">System.ServiceModel.Channels.MsmqMoveOrDeleteAttemptFailed</span></span>
<span data-ttu-id="22719-103">メッセージを移動または削除できません。</span><span class="sxs-lookup"><span data-stu-id="22719-103">Cannot move or delete message.</span></span>  
  
## <a name="description"></a><span data-ttu-id="22719-104">説明</span><span class="sxs-lookup"><span data-stu-id="22719-104">Description</span></span>  
 <span data-ttu-id="22719-105">このトレースは、MSMQ メッセージの移動、削除、または拒否の試行中にエラーが発生したことを示しています。</span><span class="sxs-lookup"><span data-stu-id="22719-105">The trace indicates that a failure occurred when attempting to move, delete, or reject an MSMQ message.</span></span>  
  
 <span data-ttu-id="22719-106">MSMQ メッセージは、Windows コミュニケーション ファウンデーション (WCF) によって使用されます (NetMsmq バインドまたは Msmq 統合バインドのいずれかで使用される場合)。このトレースは、NetMsmqBinding または`ReceiveErrorHandling`MsmqIntegrationBinding で選択されたプロパティの値に関連付けられています。</span><span class="sxs-lookup"><span data-stu-id="22719-106">MSMQ messages are employed by Windows Communication Foundation (WCF) (when used with either the NetMsmqBinding or the MsmqIntegrationBinding).This trace is related to the chosen value of the `ReceiveErrorHandling` property on the NetMsmqBinding or MsmqIntegrationBinding.</span></span>  
  
 <span data-ttu-id="22719-107">このトレースはシステム全体についてのエラーを示すものではありません。</span><span class="sxs-lookup"><span data-stu-id="22719-107">This trace is not indicative of an overall system failure.</span></span> <span data-ttu-id="22719-108">ただし、選択した有害メッセージの処置に失敗したことを示しています。</span><span class="sxs-lookup"><span data-stu-id="22719-108">However, it indicates that the chosen poison message disposition failed for a message.</span></span> <span data-ttu-id="22719-109">メッセージが有害になるタイミングと、メッセージを適切に処理するようにサービスを設定する方法の詳細については、「 [Poison-Message の処理](../../feature-details/poison-message-handling.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="22719-109">For more information on when messages become poison and how to configure your service to handle them appropriately, see [Poison-Message Handling](../../feature-details/poison-message-handling.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="22719-110">関連項目</span><span class="sxs-lookup"><span data-stu-id="22719-110">See also</span></span>

- [<span data-ttu-id="22719-111">トレース</span><span class="sxs-lookup"><span data-stu-id="22719-111">Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)
- [<span data-ttu-id="22719-112">トレースを使用したアプリケーションのトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="22719-112">Using Tracing to Troubleshoot Your Application</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)
- [<span data-ttu-id="22719-113">管理と診断</span><span class="sxs-lookup"><span data-stu-id="22719-113">Administration and Diagnostics</span></span>](../../../../../docs/framework/wcf/diagnostics/index.md)
