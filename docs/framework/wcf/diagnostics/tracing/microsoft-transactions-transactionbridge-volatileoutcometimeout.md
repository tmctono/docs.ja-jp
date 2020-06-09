---
title: Microsoft.Transactions.TransactionBridge.VolatileOutcomeTimeout
ms.date: 03/30/2017
ms.assetid: 2dbe34c5-57c7-4b64-9257-63021911d03c
ms.openlocfilehash: dd2a0b67ec140aa2e6fe1abad8e85c0206abd8ea
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/09/2020
ms.locfileid: "84579022"
---
# <a name="microsofttransactionstransactionbridgevolatileoutcometimeout"></a><span data-ttu-id="a3cb9-102">Microsoft.Transactions.TransactionBridge.VolatileOutcomeTimeout</span><span class="sxs-lookup"><span data-stu-id="a3cb9-102">Microsoft.Transactions.TransactionBridge.VolatileOutcomeTimeout</span></span>
<span data-ttu-id="a3cb9-103">不安定な参加要素からの結果メッセージに対する応答を受信するのを待機しているときに WS-AT プロトコル サービスがタイムアウトしました。</span><span class="sxs-lookup"><span data-stu-id="a3cb9-103">The WS-AT protocol service timed out waiting for a response to an outcome message from a volatile participant.</span></span> <span data-ttu-id="a3cb9-104">受信者が応答した場合、トランザクションの結果が不明である場合があります。</span><span class="sxs-lookup"><span data-stu-id="a3cb9-104">The transaction outcome may be in doubt if the participant returns.</span></span>  
  
## <a name="description"></a><span data-ttu-id="a3cb9-105">説明</span><span class="sxs-lookup"><span data-stu-id="a3cb9-105">Description</span></span>  
 <span data-ttu-id="a3cb9-106">不安定な参加要素がコミットまたは中止を決定したが、一定時間内にコミット要求またはロールバック要求に応答していない場合にトレースされます。</span><span class="sxs-lookup"><span data-stu-id="a3cb9-106">Traced when a Volatile participant has decided to Commit or Abort but has not responded to a Commit or Rollback request within a given amount of time.</span></span>  
  
## <a name="troubleshooting"></a><span data-ttu-id="a3cb9-107">トラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="a3cb9-107">Troubleshooting</span></span>  
 <span data-ttu-id="a3cb9-108">不安定な参加要素がすべて一定時間内に応答できることを確認します。</span><span class="sxs-lookup"><span data-stu-id="a3cb9-108">Ensure that all Volatile participants are able to respond within the given amount of time.</span></span> <span data-ttu-id="a3cb9-109">既定の時間は 180 秒です。</span><span class="sxs-lookup"><span data-stu-id="a3cb9-109">The default time period is 180 seconds.</span></span>  <span data-ttu-id="a3cb9-110">この時間が不十分な場合は、WS-AT の `VolatileOutcomeDelay` タイマー ポリシーを増やします。</span><span class="sxs-lookup"><span data-stu-id="a3cb9-110">If this is insufficient, increase the `VolatileOutcomeDelay` timer policy for WS-AT.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a3cb9-111">関連項目</span><span class="sxs-lookup"><span data-stu-id="a3cb9-111">See also</span></span>

- [<span data-ttu-id="a3cb9-112">トレース</span><span class="sxs-lookup"><span data-stu-id="a3cb9-112">Tracing</span></span>](index.md)
- [<span data-ttu-id="a3cb9-113">トレースを使用したアプリケーションのトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="a3cb9-113">Using Tracing to Troubleshoot Your Application</span></span>](using-tracing-to-troubleshoot-your-application.md)
- [<span data-ttu-id="a3cb9-114">管理と診断</span><span class="sxs-lookup"><span data-stu-id="a3cb9-114">Administration and Diagnostics</span></span>](../index.md)
