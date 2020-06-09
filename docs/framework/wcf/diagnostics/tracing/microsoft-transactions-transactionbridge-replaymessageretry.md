---
title: Microsoft.Transactions.TransactionBridge.ReplayMessageRetry
ms.date: 03/30/2017
ms.assetid: e5b820ae-504d-405a-926a-9effa41d2369
ms.openlocfilehash: 162452d5d12859571d78ef19cf1d838953ee7acd
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/09/2020
ms.locfileid: "84596208"
---
# <a name="microsofttransactionstransactionbridgereplaymessageretry"></a><span data-ttu-id="f0614-102">Microsoft.Transactions.TransactionBridge.ReplayMessageRetry</span><span class="sxs-lookup"><span data-stu-id="f0614-102">Microsoft.Transactions.TransactionBridge.ReplayMessageRetry</span></span>
<span data-ttu-id="f0614-103">リプレイ メッセージの再試行は、応答しないコーディネーターに送信されました。</span><span class="sxs-lookup"><span data-stu-id="f0614-103">A replay message retry was sent to an unresponsive coordinator.</span></span>  
  
## <a name="description"></a><span data-ttu-id="f0614-104">説明</span><span class="sxs-lookup"><span data-stu-id="f0614-104">Description</span></span>  
 <span data-ttu-id="f0614-105">ローカル トランザクション マネージャーが一定時間内に応答を受信せず、上位のコーディネーターにリプレイ メッセージを再送信する必要があった場合にトレースされます。</span><span class="sxs-lookup"><span data-stu-id="f0614-105">Traced if the local Transaction Manager needed to resend a Replay message to a superior coordinator because it did not receive a response in a given amount of time.</span></span>  
  
## <a name="troubleshooting"></a><span data-ttu-id="f0614-106">トラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="f0614-106">Troubleshooting</span></span>  
 <span data-ttu-id="f0614-107">応答が時間どおりに配信されない原因となっている可能性のあるネットワークや製品の問題について調査します。</span><span class="sxs-lookup"><span data-stu-id="f0614-107">Investigate potential network or product issues that prevent the response from being delivered on time.</span></span>  <span data-ttu-id="f0614-108">このメッセージが多数表示される場合、インフラストラクチャに問題があるか、または応答時間が異常にかかっていることを示します。</span><span class="sxs-lookup"><span data-stu-id="f0614-108">If many of these messages are seen, it can indicate infrastructure problems or abnormally long response times.</span></span> <span data-ttu-id="f0614-109">いずれの問題によっても、システム内のトランザクションのスループットが大幅に低下します。</span><span class="sxs-lookup"><span data-stu-id="f0614-109">Both issues will drastically reduce the throughput of transactions within the system.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f0614-110">関連項目</span><span class="sxs-lookup"><span data-stu-id="f0614-110">See also</span></span>

- [<span data-ttu-id="f0614-111">トレース</span><span class="sxs-lookup"><span data-stu-id="f0614-111">Tracing</span></span>](index.md)
- [<span data-ttu-id="f0614-112">トレースを使用したアプリケーションのトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="f0614-112">Using Tracing to Troubleshoot Your Application</span></span>](using-tracing-to-troubleshoot-your-application.md)
- [<span data-ttu-id="f0614-113">管理と診断</span><span class="sxs-lookup"><span data-stu-id="f0614-113">Administration and Diagnostics</span></span>](../index.md)
