---
title: Microsoft.Transactions.TransactionBridge.VolatileParticipantInDoubt
ms.date: 03/30/2017
ms.assetid: 3e8fc825-9f22-47e7-9c16-d64ef291c932
ms.openlocfilehash: 9434f2f902a50a37fb3efee22fd3b18b33af9129
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61997453"
---
# <a name="microsofttransactionstransactionbridgevolatileparticipantindoubt"></a><span data-ttu-id="98545-102">Microsoft.Transactions.TransactionBridge.VolatileParticipantInDoubt</span><span class="sxs-lookup"><span data-stu-id="98545-102">Microsoft.Transactions.TransactionBridge.VolatileParticipantInDoubt</span></span>
<span data-ttu-id="98545-103">WS-AT プロトコル サービスは、認識されない不安定な参加要素からの準備メッセージまたはリプレイ メッセージを受信しました。</span><span class="sxs-lookup"><span data-stu-id="98545-103">The WS-AT protocol service received a Prepared or Replay message from an unrecognized volatile participant.</span></span> <span data-ttu-id="98545-104">参加要素にエラーが返されました。この結果、トランザクションの結果が不明であると宣言します。</span><span class="sxs-lookup"><span data-stu-id="98545-104">A fault was returned to the participant, declares that the transaction's outcome is in doubt.</span></span>  
  
## <a name="description"></a><span data-ttu-id="98545-105">説明</span><span class="sxs-lookup"><span data-stu-id="98545-105">Description</span></span>  
 <span data-ttu-id="98545-106">ローカル トランザクション マネージャーが、既に認識していない揮発性参加リストからの準備メッセージまたはリプレイ メッセージを受信するとトレースされます。</span><span class="sxs-lookup"><span data-stu-id="98545-106">Traced when the local Transaction Manager receives a Prepared or Replay message from a Volatile enlistment that it has already forgotten.</span></span>  
  
## <a name="troubleshooting"></a><span data-ttu-id="98545-107">トラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="98545-107">Troubleshooting</span></span>  
 <span data-ttu-id="98545-108">不安定な参加要素からメッセージが遅れて届く原因を調査してください。</span><span class="sxs-lookup"><span data-stu-id="98545-108">Investigate potential causes of late messages coming from the Volatile participant.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="98545-109">関連項目</span><span class="sxs-lookup"><span data-stu-id="98545-109">See also</span></span>

- [<span data-ttu-id="98545-110">トレース</span><span class="sxs-lookup"><span data-stu-id="98545-110">Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)
- [<span data-ttu-id="98545-111">トレースを使用したアプリケーションのトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="98545-111">Using Tracing to Troubleshoot Your Application</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)
- [<span data-ttu-id="98545-112">管理と診断</span><span class="sxs-lookup"><span data-stu-id="98545-112">Administration and Diagnostics</span></span>](../../../../../docs/framework/wcf/diagnostics/index.md)
