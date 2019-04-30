---
title: Microsoft.Transactions.TransactionBridge.CommitMessageRetry
ms.date: 03/30/2017
ms.assetid: 4abe01f0-6398-4fba-b2f3-c054b7f7e971
ms.openlocfilehash: 3c398aa13a8cd2b87068216d3c07fb29e1a27c3f
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61997962"
---
# <a name="microsofttransactionstransactionbridgecommitmessageretry"></a><span data-ttu-id="61cc8-102">Microsoft.Transactions.TransactionBridge.CommitMessageRetry</span><span class="sxs-lookup"><span data-stu-id="61cc8-102">Microsoft.Transactions.TransactionBridge.CommitMessageRetry</span></span>
<span data-ttu-id="61cc8-103">コミット メッセージの再試行は、応答しない参加要素に送信されました。</span><span class="sxs-lookup"><span data-stu-id="61cc8-103">A commit message retry was sent to an unresponsive participant.</span></span>  
  
## <a name="description"></a><span data-ttu-id="61cc8-104">説明</span><span class="sxs-lookup"><span data-stu-id="61cc8-104">Description</span></span>  
 <span data-ttu-id="61cc8-105">ローカル トランザクション マネージャーが一定時間内に応答を受信せず、下位の参加要素にコミット メッセージを再送信する必要があった場合にトレースされます。</span><span class="sxs-lookup"><span data-stu-id="61cc8-105">Traced if the local Transaction Manager needed to resend a Commit message to a subordinate participant because it did not receive a response in a given amount of time.</span></span>  
  
## <a name="troubleshooting"></a><span data-ttu-id="61cc8-106">トラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="61cc8-106">Troubleshooting</span></span>  
 <span data-ttu-id="61cc8-107">応答が時間どおりに配信されない原因となっている可能性のあるネットワークや製品の問題について調査します。</span><span class="sxs-lookup"><span data-stu-id="61cc8-107">Investigate potential network or product issues that prevent the response from being delivered on time.</span></span>  <span data-ttu-id="61cc8-108">このメッセージが多数表示される場合、インフラストラクチャに問題があるか、または応答時間が異常にかかっていることを示します。</span><span class="sxs-lookup"><span data-stu-id="61cc8-108">If many of these messages are seen, it can indicate infrastructure problems or abnormally long response times.</span></span> <span data-ttu-id="61cc8-109">いずれの問題によっても、システム内のトランザクションのスループットが大幅に低下します。</span><span class="sxs-lookup"><span data-stu-id="61cc8-109">Both issues will drastically reduce the throughput of transactions within the system.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="61cc8-110">関連項目</span><span class="sxs-lookup"><span data-stu-id="61cc8-110">See also</span></span>

- [<span data-ttu-id="61cc8-111">トレース</span><span class="sxs-lookup"><span data-stu-id="61cc8-111">Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)
- [<span data-ttu-id="61cc8-112">トレースを使用したアプリケーションのトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="61cc8-112">Using Tracing to Troubleshoot Your Application</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)
- [<span data-ttu-id="61cc8-113">管理と診断</span><span class="sxs-lookup"><span data-stu-id="61cc8-113">Administration and Diagnostics</span></span>](../../../../../docs/framework/wcf/diagnostics/index.md)
