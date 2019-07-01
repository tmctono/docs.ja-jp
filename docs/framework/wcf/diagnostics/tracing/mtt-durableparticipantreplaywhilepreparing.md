---
title: Microsoft.Transactions.TransactionBridge.DurableParticipantReplayWhilePreparing
ms.date: 03/30/2017
ms.assetid: 10ef3876-6f8e-4d4e-8444-f47847b64795
ms.openlocfilehash: 93354fbdd0c1726280526ca07a8b3dd1c57c8a25
ms.sourcegitcommit: 2d42b7ae4252cfe1232777f501ea9ac97df31b63
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/01/2019
ms.locfileid: "67486768"
---
# <a name="microsofttransactionstransactionbridgedurableparticipantreplaywhilepreparing"></a><span data-ttu-id="9d03b-102">Microsoft.Transactions.TransactionBridge.DurableParticipantReplayWhilePreparing</span><span class="sxs-lookup"><span data-stu-id="9d03b-102">Microsoft.Transactions.TransactionBridge.DurableParticipantReplayWhilePreparing</span></span>
<span data-ttu-id="9d03b-103">WS-AT プロトコル サービスは、準備メッセージに応答していない永続的な参加要素から、リプレイ メッセージを受信しました。</span><span class="sxs-lookup"><span data-stu-id="9d03b-103">The WS-AT protocol service received a Replay message from a durable participant, which did not respond to Prepare.</span></span> <span data-ttu-id="9d03b-104">そのため、トランザクションが中止されました。</span><span class="sxs-lookup"><span data-stu-id="9d03b-104">Consequently, the transaction was aborted.</span></span>  
  
## <a name="description"></a><span data-ttu-id="9d03b-105">説明</span><span class="sxs-lookup"><span data-stu-id="9d03b-105">Description</span></span>  
 <span data-ttu-id="9d03b-106">永続的な参加要素がまだ準備している間にリプレイ メッセージが受信された場合は、トレースされます。</span><span class="sxs-lookup"><span data-stu-id="9d03b-106">Traced if a Replay message is received while a Durable participant is still Preparing.</span></span> <span data-ttu-id="9d03b-107">これは、この状態に対して無効なメッセージであり、トランザクションは中止されます。</span><span class="sxs-lookup"><span data-stu-id="9d03b-107">This is an illegal message for this state and the transaction is going to be aborted.</span></span>  
  
## <a name="troubleshooting"></a><span data-ttu-id="9d03b-108">トラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="9d03b-108">Troubleshooting</span></span>

<span data-ttu-id="9d03b-109">このエラーを受信 (下位トランザクション マネージャーを含む)、永続参加要素が障害から回復したことを示すことができますただし、トランザクションの結果がわからないし、その状態を要求します。</span><span class="sxs-lookup"><span data-stu-id="9d03b-109">Receiving this error can indicate that a Durable participant (including Subordinate TransactionManagers) has recovered from failure; however, it is unsure of the transaction outcome and requests its status.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9d03b-110">関連項目</span><span class="sxs-lookup"><span data-stu-id="9d03b-110">See also</span></span>

- [<span data-ttu-id="9d03b-111">トレース</span><span class="sxs-lookup"><span data-stu-id="9d03b-111">Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)
- [<span data-ttu-id="9d03b-112">トレースを使用したアプリケーションのトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="9d03b-112">Using Tracing to Troubleshoot Your Application</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)
- [<span data-ttu-id="9d03b-113">管理と診断</span><span class="sxs-lookup"><span data-stu-id="9d03b-113">Administration and Diagnostics</span></span>](../../../../../docs/framework/wcf/diagnostics/index.md)
