---
title: Microsoft.Transactions.TransactionBridge.VolatileParticipantInDoubt
ms.date: 03/30/2017
ms.assetid: 3e8fc825-9f22-47e7-9c16-d64ef291c932
ms.openlocfilehash: ab1c2c8afe3a66536810a614cc6deac12519cb9b
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/09/2020
ms.locfileid: "84599634"
---
# <a name="microsofttransactionstransactionbridgevolatileparticipantindoubt"></a><span data-ttu-id="d19ca-102">Microsoft.Transactions.TransactionBridge.VolatileParticipantInDoubt</span><span class="sxs-lookup"><span data-stu-id="d19ca-102">Microsoft.Transactions.TransactionBridge.VolatileParticipantInDoubt</span></span>
<span data-ttu-id="d19ca-103">WS-AT プロトコル サービスは、認識されない不安定な参加要素からの準備メッセージまたはリプレイ メッセージを受信しました。</span><span class="sxs-lookup"><span data-stu-id="d19ca-103">The WS-AT protocol service received a Prepared or Replay message from an unrecognized volatile participant.</span></span> <span data-ttu-id="d19ca-104">参加要素にエラーが返されました。この結果、トランザクションの結果が不明であると宣言します。</span><span class="sxs-lookup"><span data-stu-id="d19ca-104">A fault was returned to the participant, declares that the transaction's outcome is in doubt.</span></span>  
  
## <a name="description"></a><span data-ttu-id="d19ca-105">説明</span><span class="sxs-lookup"><span data-stu-id="d19ca-105">Description</span></span>  
 <span data-ttu-id="d19ca-106">ローカル トランザクション マネージャーが、既に認識していない揮発性参加リストからの準備メッセージまたはリプレイ メッセージを受信するとトレースされます。</span><span class="sxs-lookup"><span data-stu-id="d19ca-106">Traced when the local Transaction Manager receives a Prepared or Replay message from a Volatile enlistment that it has already forgotten.</span></span>  
  
## <a name="troubleshooting"></a><span data-ttu-id="d19ca-107">トラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="d19ca-107">Troubleshooting</span></span>  
 <span data-ttu-id="d19ca-108">不安定な参加要素からメッセージが遅れて届く原因を調査してください。</span><span class="sxs-lookup"><span data-stu-id="d19ca-108">Investigate potential causes of late messages coming from the Volatile participant.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d19ca-109">関連項目</span><span class="sxs-lookup"><span data-stu-id="d19ca-109">See also</span></span>

- [<span data-ttu-id="d19ca-110">トレース</span><span class="sxs-lookup"><span data-stu-id="d19ca-110">Tracing</span></span>](index.md)
- [<span data-ttu-id="d19ca-111">トレースを使用したアプリケーションのトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="d19ca-111">Using Tracing to Troubleshoot Your Application</span></span>](using-tracing-to-troubleshoot-your-application.md)
- [<span data-ttu-id="d19ca-112">管理と診断</span><span class="sxs-lookup"><span data-stu-id="d19ca-112">Administration and Diagnostics</span></span>](../index.md)
