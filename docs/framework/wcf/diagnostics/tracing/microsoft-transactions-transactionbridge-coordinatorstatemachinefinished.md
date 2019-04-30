---
title: Microsoft.Transactions.TransactionBridge.CoordinatorStateMachineFinished
ms.date: 03/30/2017
ms.assetid: 16cb428d-d886-4789-a961-6fded4b0dbba
ms.openlocfilehash: bffaed4976d82202eaea9ce50f6d389548fdabfd
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61998011"
---
# <a name="microsofttransactionstransactionbridgecoordinatorstatemachinefinished"></a><span data-ttu-id="8c38a-102">Microsoft.Transactions.TransactionBridge.CoordinatorStateMachineFinished</span><span class="sxs-lookup"><span data-stu-id="8c38a-102">Microsoft.Transactions.TransactionBridge.CoordinatorStateMachineFinished</span></span>
<span data-ttu-id="8c38a-103">コーディネーターの登録リストのステート マシンが完了状態になりました。</span><span class="sxs-lookup"><span data-stu-id="8c38a-103">The state machine for a coordinator enlistment has entered the finished state.</span></span>  
  
## <a name="description"></a><span data-ttu-id="8c38a-104">説明</span><span class="sxs-lookup"><span data-stu-id="8c38a-104">Description</span></span>  
 <span data-ttu-id="8c38a-105">上位のコーディネーターの登録リストが 2PC 処理を完了したとローカル トランザクション マネージャーが判断したときに、トレースされます。</span><span class="sxs-lookup"><span data-stu-id="8c38a-105">Traced when the local Transaction Manager believes a superior coordinator enlistment has completed 2pc processing.</span></span> <span data-ttu-id="8c38a-106">登録リストの結果は、Committed、Aborted、または Forgotten のいずれかです。</span><span class="sxs-lookup"><span data-stu-id="8c38a-106">The outcome for the enlistment can be Committed or Aborted or Forgotten.</span></span> <span data-ttu-id="8c38a-107">ローカル トランザクション マネージャーが準備中に読み取り専用にする場合にもトレースされます。</span><span class="sxs-lookup"><span data-stu-id="8c38a-107">It is also traced if the local Transaction Manager votes ReadOnly during Prepare.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8c38a-108">関連項目</span><span class="sxs-lookup"><span data-stu-id="8c38a-108">See also</span></span>

- [<span data-ttu-id="8c38a-109">トレース</span><span class="sxs-lookup"><span data-stu-id="8c38a-109">Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)
- [<span data-ttu-id="8c38a-110">トレースを使用したアプリケーションのトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="8c38a-110">Using Tracing to Troubleshoot Your Application</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)
- [<span data-ttu-id="8c38a-111">管理と診断</span><span class="sxs-lookup"><span data-stu-id="8c38a-111">Administration and Diagnostics</span></span>](../../../../../docs/framework/wcf/diagnostics/index.md)
