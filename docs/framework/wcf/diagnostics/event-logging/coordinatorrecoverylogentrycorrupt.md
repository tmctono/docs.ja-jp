---
title: CoordinatorRecoveryLogEntryCorrupt
ms.date: 03/30/2017
ms.assetid: 3cd0c3e3-84c8-4d43-a561-a8851c78e565
ms.openlocfilehash: faf4a07badb71588c601cd9390e4d8e3f187e629
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59121629"
---
# <a name="coordinatorrecoverylogentrycorrupt"></a><span data-ttu-id="841d1-102">CoordinatorRecoveryLogEntryCorrupt</span><span class="sxs-lookup"><span data-stu-id="841d1-102">CoordinatorRecoveryLogEntryCorrupt</span></span>
<span data-ttu-id="841d1-103">Id:139</span><span class="sxs-lookup"><span data-stu-id="841d1-103">Id: 139</span></span>  
  
 <span data-ttu-id="841d1-104">重大度:Error</span><span class="sxs-lookup"><span data-stu-id="841d1-104">Severity: Error</span></span>  
  
 <span data-ttu-id="841d1-105">カテゴリ:TransactionBridge</span><span class="sxs-lookup"><span data-stu-id="841d1-105">Category: TransactionBridge</span></span>  
  
## <a name="description"></a><span data-ttu-id="841d1-106">説明</span><span class="sxs-lookup"><span data-stu-id="841d1-106">Description</span></span>  
 <span data-ttu-id="841d1-107">このイベントは、コーディネーターの回復ログ エントリが破損し、逆シリアル化できなかったことを示します。</span><span class="sxs-lookup"><span data-stu-id="841d1-107">This event indicates that a  coordinator recovery log entry was corrupt and could not be deserialized.</span></span> <span data-ttu-id="841d1-108">このエラーが原因で、データの損失が発生することがあります。</span><span class="sxs-lookup"><span data-stu-id="841d1-108">Data loss may result from this error.</span></span> <span data-ttu-id="841d1-109">イベントには、トランザクション ID、回復データ (Base64 エンコード)、例外、プロセス名、およびプロセス ID が表示されます。</span><span class="sxs-lookup"><span data-stu-id="841d1-109">The event lists the Transaction ID, Recovery data (Base64 encoded), exception, process name and process ID.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="841d1-110">関連項目</span><span class="sxs-lookup"><span data-stu-id="841d1-110">See also</span></span>

- [<span data-ttu-id="841d1-111">イベント ログ</span><span class="sxs-lookup"><span data-stu-id="841d1-111">Event Logging</span></span>](../../../../../docs/framework/wcf/diagnostics/event-logging/index.md)
- [<span data-ttu-id="841d1-112">イベント一覧</span><span class="sxs-lookup"><span data-stu-id="841d1-112">Events General Reference</span></span>](../../../../../docs/framework/wcf/diagnostics/event-logging/events-general-reference.md)
