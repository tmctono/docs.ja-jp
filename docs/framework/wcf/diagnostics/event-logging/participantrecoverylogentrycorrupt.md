---
title: ParticipantRecoveryLogEntryCorrupt
ms.date: 03/30/2017
ms.assetid: ab34785f-f953-4428-93ca-3c50d3f50a4a
ms.openlocfilehash: 566517a122e17078156a61e0d3808ae06d0cf93c
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59075432"
---
# <a name="participantrecoverylogentrycorrupt"></a><span data-ttu-id="97453-102">ParticipantRecoveryLogEntryCorrupt</span><span class="sxs-lookup"><span data-stu-id="97453-102">ParticipantRecoveryLogEntryCorrupt</span></span>
<span data-ttu-id="97453-103">Id:138</span><span class="sxs-lookup"><span data-stu-id="97453-103">Id: 138</span></span>  
  
 <span data-ttu-id="97453-104">重大度:Error</span><span class="sxs-lookup"><span data-stu-id="97453-104">Severity: Error</span></span>  
  
 <span data-ttu-id="97453-105">カテゴリ:TransactionBridge</span><span class="sxs-lookup"><span data-stu-id="97453-105">Category: TransactionBridge</span></span>  
  
## <a name="description"></a><span data-ttu-id="97453-106">説明</span><span class="sxs-lookup"><span data-stu-id="97453-106">Description</span></span>  
 <span data-ttu-id="97453-107">このイベントは、参加要素の回復ログ エントリが破損し、逆シリアル化できなかったことを示します。</span><span class="sxs-lookup"><span data-stu-id="97453-107">This event indicates that a participant recovery log entry was corrupt and could not be deserialized.</span></span> <span data-ttu-id="97453-108">このエラーが原因で、データの損失が発生することがあります。</span><span class="sxs-lookup"><span data-stu-id="97453-108">Data loss may result from this error.</span></span> <span data-ttu-id="97453-109">イベントには、トランザクション ID、回復データ (Base64 エンコード)、例外、プロセス名、およびプロセス ID が表示されます。</span><span class="sxs-lookup"><span data-stu-id="97453-109">The event lists the Transaction ID, Recovery data (Base64 encoded), exception, process name and process ID.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="97453-110">関連項目</span><span class="sxs-lookup"><span data-stu-id="97453-110">See also</span></span>

- [<span data-ttu-id="97453-111">イベント ログ</span><span class="sxs-lookup"><span data-stu-id="97453-111">Event Logging</span></span>](../../../../../docs/framework/wcf/diagnostics/event-logging/index.md)
- [<span data-ttu-id="97453-112">イベント一覧</span><span class="sxs-lookup"><span data-stu-id="97453-112">Events General Reference</span></span>](../../../../../docs/framework/wcf/diagnostics/event-logging/events-general-reference.md)
