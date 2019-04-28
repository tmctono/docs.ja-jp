---
title: Microsoft.Transactions.TransactionBridge.EnlistTransactionFailure
ms.date: 03/30/2017
ms.assetid: 1b9f5139-e122-4716-9ef7-2f38e1813993
ms.openlocfilehash: 93c96d94aaeddeb7e7b04ea80645b8de95b0343e
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61666795"
---
# <a name="microsofttransactionstransactionbridgeenlisttransactionfailure"></a><span data-ttu-id="36e6f-102">Microsoft.Transactions.TransactionBridge.EnlistTransactionFailure</span><span class="sxs-lookup"><span data-stu-id="36e6f-102">Microsoft.Transactions.TransactionBridge.EnlistTransactionFailure</span></span>
<span data-ttu-id="36e6f-103">WS-AT プロトコル サービスは、指定されたコーディネーション コンテキストを使用してトランザクションに参加することができませんでした。</span><span class="sxs-lookup"><span data-stu-id="36e6f-103">The WS-AT protocol service failed to enlist on a transaction using the provided coordination context.</span></span>  
  
## <a name="description"></a><span data-ttu-id="36e6f-104">説明</span><span class="sxs-lookup"><span data-stu-id="36e6f-104">Description</span></span>  
 <span data-ttu-id="36e6f-105">指定された 2PC プロトコルのトランザクションに MSDTC が参加できない場合にトレースされます。</span><span class="sxs-lookup"><span data-stu-id="36e6f-105">Traced when MSDTC is unable to enlist on a transaction for a given 2pc protocol.</span></span>  <span data-ttu-id="36e6f-106">これは、トランザクションが存在しなくなった場合、参加が許可されなくなった場合、または既に参加が多すぎる場合に発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="36e6f-106">This can happen because the transaction no longer exists, enlisting is no longer allowed, or too many enlistments are already present.</span></span>  
  
## <a name="troubleshooting"></a><span data-ttu-id="36e6f-107">トラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="36e6f-107">Troubleshooting</span></span>  
 <span data-ttu-id="36e6f-108">トレース メッセージ内のステータス文字列を調べて、アクション可能な項目が存在するかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="36e6f-108">Inspect the status string within the trace message to determine if any actionable item exists.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="36e6f-109">関連項目</span><span class="sxs-lookup"><span data-stu-id="36e6f-109">See also</span></span>

- [<span data-ttu-id="36e6f-110">トレース</span><span class="sxs-lookup"><span data-stu-id="36e6f-110">Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)
- [<span data-ttu-id="36e6f-111">トレースを使用したアプリケーションのトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="36e6f-111">Using Tracing to Troubleshoot Your Application</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)
- [<span data-ttu-id="36e6f-112">管理と診断</span><span class="sxs-lookup"><span data-stu-id="36e6f-112">Administration and Diagnostics</span></span>](../../../../../docs/framework/wcf/diagnostics/index.md)
