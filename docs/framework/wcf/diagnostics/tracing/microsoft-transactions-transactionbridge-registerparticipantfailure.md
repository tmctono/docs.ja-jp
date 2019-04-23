---
title: Microsoft.Transactions.TransactionBridge.RegisterParticipantFailure
ms.date: 03/30/2017
ms.assetid: 3a4ead79-8550-4037-84e3-fd70ff56e001
ms.openlocfilehash: e56a9ed1d837af27d481282e0e106d537ec41ee3
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59164295"
---
# <a name="microsofttransactionstransactionbridgeregisterparticipantfailure"></a><span data-ttu-id="8067a-102">Microsoft.Transactions.TransactionBridge.RegisterParticipantFailure</span><span class="sxs-lookup"><span data-stu-id="8067a-102">Microsoft.Transactions.TransactionBridge.RegisterParticipantFailure</span></span>
<span data-ttu-id="8067a-103">WS-AT プロトコル サービスは、制御プロトコルの参加要素の登録に失敗しました。</span><span class="sxs-lookup"><span data-stu-id="8067a-103">The WS-AT protocol service failed to register a participant for a control protocol.</span></span>  
  
## <a name="description"></a><span data-ttu-id="8067a-104">説明</span><span class="sxs-lookup"><span data-stu-id="8067a-104">Description</span></span>  
 <span data-ttu-id="8067a-105">MSDTC により無効な登録要求が検出された場合にトレースされます。</span><span class="sxs-lookup"><span data-stu-id="8067a-105">Traced if MSDTC detects an invalid Registration request.</span></span> <span data-ttu-id="8067a-106">これは、複数の完了登録要求や内部エラーによって発生することがあります。</span><span class="sxs-lookup"><span data-stu-id="8067a-106">This can be caused by  multiple Completion registration requests and internal errors.</span></span>  
  
## <a name="troubleshooting"></a><span data-ttu-id="8067a-107">トラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="8067a-107">Troubleshooting</span></span>  
 <span data-ttu-id="8067a-108">完了を複数回登録しないでください。</span><span class="sxs-lookup"><span data-stu-id="8067a-108">Do not try to Register for Completion more than once.</span></span>  <span data-ttu-id="8067a-109">また、トレース メッセージ内のステータス文字列を調べて、アクション可能な項目が存在するかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="8067a-109">Also, inspect the status string within the trace message to determine if any actionable item exists.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8067a-110">関連項目</span><span class="sxs-lookup"><span data-stu-id="8067a-110">See also</span></span>

- [<span data-ttu-id="8067a-111">トレース</span><span class="sxs-lookup"><span data-stu-id="8067a-111">Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)
- [<span data-ttu-id="8067a-112">トレースを使用したアプリケーションのトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="8067a-112">Using Tracing to Troubleshoot Your Application</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)
- [<span data-ttu-id="8067a-113">管理と診断</span><span class="sxs-lookup"><span data-stu-id="8067a-113">Administration and Diagnostics</span></span>](../../../../../docs/framework/wcf/diagnostics/index.md)
