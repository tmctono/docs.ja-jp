---
title: Microsoft.Transactions.TransactionBridge.ParticipantStateMachineFinished
ms.date: 03/30/2017
ms.assetid: 54b677f7-03ad-40f2-9c5d-297a8ad9bf90
ms.openlocfilehash: 7f37cb5d9ee3d2d9d56519f785388f278b3333b9
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59170730"
---
# <a name="microsofttransactionstransactionbridgeparticipantstatemachinefinished"></a><span data-ttu-id="60aa0-102">Microsoft.Transactions.TransactionBridge.ParticipantStateMachineFinished</span><span class="sxs-lookup"><span data-stu-id="60aa0-102">Microsoft.Transactions.TransactionBridge.ParticipantStateMachineFinished</span></span>
<span data-ttu-id="60aa0-103">参加要素の登録リストのステート マシンは完了状態になりました。</span><span class="sxs-lookup"><span data-stu-id="60aa0-103">The state machine for a participant enlistment entered the finished state.</span></span>  
  
## <a name="description"></a><span data-ttu-id="60aa0-104">説明</span><span class="sxs-lookup"><span data-stu-id="60aa0-104">Description</span></span>  
 <span data-ttu-id="60aa0-105">下位参加要素登録リストの 2PC 処理が完了したときにトレースされます。</span><span class="sxs-lookup"><span data-stu-id="60aa0-105">Traced when a subordinate participant enlistment has completed 2pc processing.</span></span> <span data-ttu-id="60aa0-106">登録リストの結果は、Committed または Aborted のいずれかです。</span><span class="sxs-lookup"><span data-stu-id="60aa0-106">The outcome for the enlistment can be Committed or Aborted.</span></span> <span data-ttu-id="60aa0-107">準備中、すべての参加要素を読み取り専用にする場合にもトレースされます。</span><span class="sxs-lookup"><span data-stu-id="60aa0-107">It is also traced if any participant votes ReadOnly during Prepare.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="60aa0-108">関連項目</span><span class="sxs-lookup"><span data-stu-id="60aa0-108">See also</span></span>

- [<span data-ttu-id="60aa0-109">トレース</span><span class="sxs-lookup"><span data-stu-id="60aa0-109">Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)
- [<span data-ttu-id="60aa0-110">トレースを使用したアプリケーションのトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="60aa0-110">Using Tracing to Troubleshoot Your Application</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)
- [<span data-ttu-id="60aa0-111">管理と診断</span><span class="sxs-lookup"><span data-stu-id="60aa0-111">Administration and Diagnostics</span></span>](../../../../../docs/framework/wcf/diagnostics/index.md)
