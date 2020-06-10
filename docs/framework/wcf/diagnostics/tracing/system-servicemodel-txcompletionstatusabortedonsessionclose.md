---
title: System.ServiceModel.TxCompletionStatusAbortedOnSessionClose
ms.date: 03/30/2017
ms.assetid: 7e142e9d-e81b-4309-974a-02e9cc064ea0
ms.openlocfilehash: c398fc52d5924c033500b95924f9287b43cc9e9d
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/09/2020
ms.locfileid: "84576604"
---
# <a name="systemservicemodeltxcompletionstatusabortedonsessionclose"></a><span data-ttu-id="aa3b9-102">System.ServiceModel.TxCompletionStatusAbortedOnSessionClose</span><span class="sxs-lookup"><span data-stu-id="aa3b9-102">System.ServiceModel.TxCompletionStatusAbortedOnSessionClose</span></span>
<span data-ttu-id="aa3b9-103">指定されたトランザクションは、セッションが終了したときにまだ完了しておらず、TransactionAutoCompleteOnSessionClose OperationBehaviorAttribute が false に設定されているため、中止されました。</span><span class="sxs-lookup"><span data-stu-id="aa3b9-103">The specified transaction was aborted because it was uncompleted when the session was closed and the TransactionAutoCompleteOnSessionClose OperationBehaviorAttribute was set to false.</span></span>  
  
## <a name="description"></a><span data-ttu-id="aa3b9-104">説明</span><span class="sxs-lookup"><span data-stu-id="aa3b9-104">Description</span></span>  
 <span data-ttu-id="aa3b9-105">現在のアクティブなセッションが終了した時点でトランザクションが完了しておらず、TransactionAutoCompleteOnSessionClose が `false` に設定されている場合にトレースされます。</span><span class="sxs-lookup"><span data-stu-id="aa3b9-105">Traced if the current active session was closed, and the transaction was not completed, and TransactionAutoCompleteOnSessionClose is set to `false`.</span></span>  
  
## <a name="troubleshooting"></a><span data-ttu-id="aa3b9-106">トラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="aa3b9-106">Troubleshooting</span></span>  
 <span data-ttu-id="aa3b9-107">このトレースは、アプリケーションに調査が必要なバグが含まれている可能性があることを示します。</span><span class="sxs-lookup"><span data-stu-id="aa3b9-107">This trace indicates a potential application bug that should be investigated.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="aa3b9-108">関連項目</span><span class="sxs-lookup"><span data-stu-id="aa3b9-108">See also</span></span>

- [<span data-ttu-id="aa3b9-109">トレース</span><span class="sxs-lookup"><span data-stu-id="aa3b9-109">Tracing</span></span>](index.md)
- [<span data-ttu-id="aa3b9-110">トレースを使用したアプリケーションのトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="aa3b9-110">Using Tracing to Troubleshoot Your Application</span></span>](using-tracing-to-troubleshoot-your-application.md)
- [<span data-ttu-id="aa3b9-111">管理と診断</span><span class="sxs-lookup"><span data-stu-id="aa3b9-111">Administration and Diagnostics</span></span>](../index.md)
