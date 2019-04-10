---
title: System.ServiceModel.Channels.PeerFlooderReceiveMessageQuotaExceeded
ms.date: 03/30/2017
ms.assetid: b8371d0a-843e-440b-b86a-6996db131cb0
ms.openlocfilehash: 0ca3d198ce225221348ac7b405ea91ad215cd298
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2019
ms.locfileid: "59190900"
---
# <a name="systemservicemodelchannelspeerflooderreceivemessagequotaexceeded"></a><span data-ttu-id="660d2-102">System.ServiceModel.Channels.PeerFlooderReceiveMessageQuotaExceeded</span><span class="sxs-lookup"><span data-stu-id="660d2-102">System.ServiceModel.Channels.PeerFlooderReceiveMessageQuotaExceeded</span></span>
<span data-ttu-id="660d2-103">メッセージの受信速度が速すぎます。</span><span class="sxs-lookup"><span data-stu-id="660d2-103">The inbound receive rate of messages is too high.</span></span>  
  
## <a name="description"></a><span data-ttu-id="660d2-104">説明</span><span class="sxs-lookup"><span data-stu-id="660d2-104">Description</span></span>  
 <span data-ttu-id="660d2-105">このトレースは、受信メッセージの処理を試みたときに行われます。</span><span class="sxs-lookup"><span data-stu-id="660d2-105">This trace occurs when attempting to process inbound messages.</span></span> <span data-ttu-id="660d2-106">特定の近隣ノードでクォータ セットが超過しているため、メッセージをその近隣ノードに転送できません。</span><span class="sxs-lookup"><span data-stu-id="660d2-106">A message could not be forwarded to a specific neighbor because the quota set for that neighbor has been exceeded.</span></span> <span data-ttu-id="660d2-107">応答しない近隣ノードが、メッセージ保留のバックログをクリアできなかった場合にこの状態が発生します。</span><span class="sxs-lookup"><span data-stu-id="660d2-107">This occurs when an unresponsive neighbor fails to clear a backlog of messages pending for that neighbor.</span></span>  
  
## <a name="troubleshooting"></a><span data-ttu-id="660d2-108">トラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="660d2-108">Troubleshooting</span></span>  
 <span data-ttu-id="660d2-109">メッシュ内でメッセージが送信される速度を遅くしてください。</span><span class="sxs-lookup"><span data-stu-id="660d2-109">Reduce the rate at which messages are sent within the mesh.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="660d2-110">関連項目</span><span class="sxs-lookup"><span data-stu-id="660d2-110">See also</span></span>

- [<span data-ttu-id="660d2-111">トレース</span><span class="sxs-lookup"><span data-stu-id="660d2-111">Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)
- [<span data-ttu-id="660d2-112">トレースを使用したアプリケーションのトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="660d2-112">Using Tracing to Troubleshoot Your Application</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)
- [<span data-ttu-id="660d2-113">管理と診断</span><span class="sxs-lookup"><span data-stu-id="660d2-113">Administration and Diagnostics</span></span>](../../../../../docs/framework/wcf/diagnostics/index.md)
