---
title: Microsoft.Transactions.TransactionBridge.CoordinatorStateMachineFinished
ms.date: 03/30/2017
ms.assetid: 16cb428d-d886-4789-a961-6fded4b0dbba
ms.openlocfilehash: 3b9a3703e49c3932f62fcfb6994c9028b074bbe8
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/09/2020
ms.locfileid: "84594414"
---
# <a name="microsofttransactionstransactionbridgecoordinatorstatemachinefinished"></a><span data-ttu-id="80e78-102">Microsoft.Transactions.TransactionBridge.CoordinatorStateMachineFinished</span><span class="sxs-lookup"><span data-stu-id="80e78-102">Microsoft.Transactions.TransactionBridge.CoordinatorStateMachineFinished</span></span>
<span data-ttu-id="80e78-103">コーディネーターの登録リストのステート マシンが完了状態になりました。</span><span class="sxs-lookup"><span data-stu-id="80e78-103">The state machine for a coordinator enlistment has entered the finished state.</span></span>  
  
## <a name="description"></a><span data-ttu-id="80e78-104">説明</span><span class="sxs-lookup"><span data-stu-id="80e78-104">Description</span></span>  
 <span data-ttu-id="80e78-105">上位のコーディネーターの登録リストが 2PC 処理を完了したとローカル トランザクション マネージャーが判断したときに、トレースされます。</span><span class="sxs-lookup"><span data-stu-id="80e78-105">Traced when the local Transaction Manager believes a superior coordinator enlistment has completed 2pc processing.</span></span> <span data-ttu-id="80e78-106">登録リストの結果は、Committed、Aborted、または Forgotten のいずれかです。</span><span class="sxs-lookup"><span data-stu-id="80e78-106">The outcome for the enlistment can be Committed or Aborted or Forgotten.</span></span> <span data-ttu-id="80e78-107">ローカル トランザクション マネージャーが準備中に読み取り専用にする場合にもトレースされます。</span><span class="sxs-lookup"><span data-stu-id="80e78-107">It is also traced if the local Transaction Manager votes ReadOnly during Prepare.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="80e78-108">関連項目</span><span class="sxs-lookup"><span data-stu-id="80e78-108">See also</span></span>

- [<span data-ttu-id="80e78-109">トレース</span><span class="sxs-lookup"><span data-stu-id="80e78-109">Tracing</span></span>](index.md)
- [<span data-ttu-id="80e78-110">トレースを使用したアプリケーションのトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="80e78-110">Using Tracing to Troubleshoot Your Application</span></span>](using-tracing-to-troubleshoot-your-application.md)
- [<span data-ttu-id="80e78-111">管理と診断</span><span class="sxs-lookup"><span data-stu-id="80e78-111">Administration and Diagnostics</span></span>](../index.md)
