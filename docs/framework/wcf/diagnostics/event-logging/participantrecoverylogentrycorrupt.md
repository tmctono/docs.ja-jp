---
title: ParticipantRecoveryLogEntryCorrupt
ms.date: 03/30/2017
ms.assetid: ab34785f-f953-4428-93ca-3c50d3f50a4a
ms.openlocfilehash: 61ab172a3924e3c0ca00ffc25ef96446e33c5142
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/07/2019
ms.locfileid: "70796226"
---
# <a name="participantrecoverylogentrycorrupt"></a><span data-ttu-id="59e30-102">ParticipantRecoveryLogEntryCorrupt</span><span class="sxs-lookup"><span data-stu-id="59e30-102">ParticipantRecoveryLogEntryCorrupt</span></span>
<span data-ttu-id="59e30-103">Id:138</span><span class="sxs-lookup"><span data-stu-id="59e30-103">Id: 138</span></span>  
  
 <span data-ttu-id="59e30-104">順Error</span><span class="sxs-lookup"><span data-stu-id="59e30-104">Severity: Error</span></span>  
  
 <span data-ttu-id="59e30-105">[カテゴリ]:TransactionBridge</span><span class="sxs-lookup"><span data-stu-id="59e30-105">Category: TransactionBridge</span></span>  
  
## <a name="description"></a><span data-ttu-id="59e30-106">説明</span><span class="sxs-lookup"><span data-stu-id="59e30-106">Description</span></span>  
 <span data-ttu-id="59e30-107">このイベントは、参加要素の回復ログ エントリが破損し、逆シリアル化できなかったことを示します。</span><span class="sxs-lookup"><span data-stu-id="59e30-107">This event indicates that a participant recovery log entry was corrupt and could not be deserialized.</span></span> <span data-ttu-id="59e30-108">このエラーが原因で、データの損失が発生することがあります。</span><span class="sxs-lookup"><span data-stu-id="59e30-108">Data loss may result from this error.</span></span> <span data-ttu-id="59e30-109">イベントには、トランザクション ID、回復データ (Base64 エンコード)、例外、プロセス名、およびプロセス ID が表示されます。</span><span class="sxs-lookup"><span data-stu-id="59e30-109">The event lists the Transaction ID, Recovery data (Base64 encoded), exception, process name and process ID.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="59e30-110">関連項目</span><span class="sxs-lookup"><span data-stu-id="59e30-110">See also</span></span>

- [<span data-ttu-id="59e30-111">イベント ログ</span><span class="sxs-lookup"><span data-stu-id="59e30-111">Event Logging</span></span>](index.md)
- [<span data-ttu-id="59e30-112">イベント一覧</span><span class="sxs-lookup"><span data-stu-id="59e30-112">Events General Reference</span></span>](events-general-reference.md)
