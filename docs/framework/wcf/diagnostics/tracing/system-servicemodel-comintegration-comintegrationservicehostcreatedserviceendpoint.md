---
title: System.ServiceModel.Channels.MsmqMoveOrDeleteAttemptFailed
ms.date: 03/30/2017
ms.assetid: d75d39da-7502-4a6a-91b9-eaa05b8e24d5
ms.openlocfilehash: 8b81cdcaf74aca044260495867b2c4f1de517682
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/09/2020
ms.locfileid: "84593751"
---
# <a name="systemservicemodelchannelsmsmqmoveordeleteattemptfailed"></a><span data-ttu-id="36c79-102">System.ServiceModel.Channels.MsmqMoveOrDeleteAttemptFailed</span><span class="sxs-lookup"><span data-stu-id="36c79-102">System.ServiceModel.Channels.MsmqMoveOrDeleteAttemptFailed</span></span>
<span data-ttu-id="36c79-103">メッセージを移動または削除できません。</span><span class="sxs-lookup"><span data-stu-id="36c79-103">Cannot move or delete message.</span></span>  
  
## <a name="description"></a><span data-ttu-id="36c79-104">説明</span><span class="sxs-lookup"><span data-stu-id="36c79-104">Description</span></span>  
 <span data-ttu-id="36c79-105">このトレースは、MSMQ メッセージの移動、削除、または拒否の試行中にエラーが発生したことを示しています。</span><span class="sxs-lookup"><span data-stu-id="36c79-105">The trace indicates that a failure occurred when attempting to move, delete, or reject an MSMQ message.</span></span>  
  
 <span data-ttu-id="36c79-106">MSMQ メッセージは Windows Communication Foundation (WCF) によって採用されています (NetMsmqBinding または MsmqIntegrationBinding のいずれかと共に使用する場合)。このトレースは `ReceiveErrorHandling` 、NetMsmqBinding または MsmqIntegrationBinding で選択されたプロパティの値に関連しています。</span><span class="sxs-lookup"><span data-stu-id="36c79-106">MSMQ messages are employed by Windows Communication Foundation (WCF) (when used with either the NetMsmqBinding or the MsmqIntegrationBinding).This trace is related to the chosen value of the `ReceiveErrorHandling` property on the NetMsmqBinding or MsmqIntegrationBinding.</span></span>  
  
 <span data-ttu-id="36c79-107">このトレースはシステム全体についてのエラーを示すものではありません。</span><span class="sxs-lookup"><span data-stu-id="36c79-107">This trace is not indicative of an overall system failure.</span></span> <span data-ttu-id="36c79-108">ただし、選択した有害メッセージの処置に失敗したことを示しています。</span><span class="sxs-lookup"><span data-stu-id="36c79-108">However, it indicates that the chosen poison message disposition failed for a message.</span></span> <span data-ttu-id="36c79-109">メッセージが有害になった場合の詳細、およびメッセージを適切に処理するようにサービスを構成する方法については、「[有害メッセージの処理](../../feature-details/poison-message-handling.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="36c79-109">For more information on when messages become poison and how to configure your service to handle them appropriately, see [Poison-Message Handling](../../feature-details/poison-message-handling.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="36c79-110">関連項目</span><span class="sxs-lookup"><span data-stu-id="36c79-110">See also</span></span>

- [<span data-ttu-id="36c79-111">トレース</span><span class="sxs-lookup"><span data-stu-id="36c79-111">Tracing</span></span>](index.md)
- [<span data-ttu-id="36c79-112">トレースを使用したアプリケーションのトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="36c79-112">Using Tracing to Troubleshoot Your Application</span></span>](using-tracing-to-troubleshoot-your-application.md)
- [<span data-ttu-id="36c79-113">管理と診断</span><span class="sxs-lookup"><span data-stu-id="36c79-113">Administration and Diagnostics</span></span>](../index.md)
