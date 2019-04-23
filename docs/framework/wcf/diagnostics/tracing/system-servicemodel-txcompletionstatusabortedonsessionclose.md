---
title: System.ServiceModel.TxCompletionStatusAbortedOnSessionClose
ms.date: 03/30/2017
ms.assetid: 7e142e9d-e81b-4309-974a-02e9cc064ea0
ms.openlocfilehash: 7b1f6a2f4a344b566c76d0095942b84a8a4e76f6
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59166505"
---
# <a name="systemservicemodeltxcompletionstatusabortedonsessionclose"></a><span data-ttu-id="ddaea-102">System.ServiceModel.TxCompletionStatusAbortedOnSessionClose</span><span class="sxs-lookup"><span data-stu-id="ddaea-102">System.ServiceModel.TxCompletionStatusAbortedOnSessionClose</span></span>
<span data-ttu-id="ddaea-103">指定されたトランザクションは、セッションが終了したときにまだ完了しておらず、TransactionAutoCompleteOnSessionClose OperationBehaviorAttribute が false に設定されているため、中止されました。</span><span class="sxs-lookup"><span data-stu-id="ddaea-103">The specified transaction was aborted because it was uncompleted when the session was closed and the TransactionAutoCompleteOnSessionClose OperationBehaviorAttribute was set to false.</span></span>  
  
## <a name="description"></a><span data-ttu-id="ddaea-104">説明</span><span class="sxs-lookup"><span data-stu-id="ddaea-104">Description</span></span>  
 <span data-ttu-id="ddaea-105">現在のアクティブなセッションが終了した時点でトランザクションが完了しておらず、TransactionAutoCompleteOnSessionClose が `false` に設定されている場合にトレースされます。</span><span class="sxs-lookup"><span data-stu-id="ddaea-105">Traced if the current active session was closed, and the transaction was not completed, and TransactionAutoCompleteOnSessionClose is set to `false`.</span></span>  
  
## <a name="troubleshooting"></a><span data-ttu-id="ddaea-106">トラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="ddaea-106">Troubleshooting</span></span>  
 <span data-ttu-id="ddaea-107">このトレースは、アプリケーションに調査が必要なバグが含まれている可能性があることを示します。</span><span class="sxs-lookup"><span data-stu-id="ddaea-107">This trace indicates a potential application bug that should be investigated.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ddaea-108">関連項目</span><span class="sxs-lookup"><span data-stu-id="ddaea-108">See also</span></span>

- [<span data-ttu-id="ddaea-109">トレース</span><span class="sxs-lookup"><span data-stu-id="ddaea-109">Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)
- [<span data-ttu-id="ddaea-110">トレースを使用したアプリケーションのトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="ddaea-110">Using Tracing to Troubleshoot Your Application</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)
- [<span data-ttu-id="ddaea-111">管理と診断</span><span class="sxs-lookup"><span data-stu-id="ddaea-111">Administration and Diagnostics</span></span>](../../../../../docs/framework/wcf/diagnostics/index.md)
