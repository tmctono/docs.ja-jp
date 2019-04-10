---
title: System.ServiceModel.TxCompletionStatusCompletedForAsyncAbort
ms.date: 03/30/2017
ms.assetid: 155c3203-2e17-4709-b896-2254e22da45e
ms.openlocfilehash: f84cc9336d6cce7d8c477a1feb6caf45b0662177
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2019
ms.locfileid: "59188475"
---
# <a name="systemservicemodeltxcompletionstatuscompletedforasyncabort"></a><span data-ttu-id="93b4a-102">System.ServiceModel.TxCompletionStatusCompletedForAsyncAbort</span><span class="sxs-lookup"><span data-stu-id="93b4a-102">System.ServiceModel.TxCompletionStatusCompletedForAsyncAbort</span></span>
<span data-ttu-id="93b4a-103">非同期中止が実行されたため、指定された操作の指定のトランザクションは完了されました。</span><span class="sxs-lookup"><span data-stu-id="93b4a-103">The specified transaction for the specified operation was completed due to asynchronous abort.</span></span>  
  
## <a name="description"></a><span data-ttu-id="93b4a-104">説明</span><span class="sxs-lookup"><span data-stu-id="93b4a-104">Description</span></span>  
 <span data-ttu-id="93b4a-105">別の参加要素による中止、タイムアウト、またはトランザクションの参加要素内での別のエラーが発生したため、現在のトランザクションが中止されました。</span><span class="sxs-lookup"><span data-stu-id="93b4a-105">The current transaction was aborted due to another participant voting for Abort, time-outs occurring, or another error inside the participant of a transaction.</span></span>  
  
## <a name="troubleshooting"></a><span data-ttu-id="93b4a-106">トラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="93b4a-106">Troubleshooting</span></span>  
 <span data-ttu-id="93b4a-107">予期された中止ではない場合は、すべてのシステム ログを調べて中止の原因を確認してください。</span><span class="sxs-lookup"><span data-stu-id="93b4a-107">If this abort is unexpected, check all system logs to determine the real reason for the abort.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="93b4a-108">関連項目</span><span class="sxs-lookup"><span data-stu-id="93b4a-108">See also</span></span>

- [<span data-ttu-id="93b4a-109">トレース</span><span class="sxs-lookup"><span data-stu-id="93b4a-109">Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)
- [<span data-ttu-id="93b4a-110">トレースを使用したアプリケーションのトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="93b4a-110">Using Tracing to Troubleshoot Your Application</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)
- [<span data-ttu-id="93b4a-111">管理と診断</span><span class="sxs-lookup"><span data-stu-id="93b4a-111">Administration and Diagnostics</span></span>](../../../../../docs/framework/wcf/diagnostics/index.md)
