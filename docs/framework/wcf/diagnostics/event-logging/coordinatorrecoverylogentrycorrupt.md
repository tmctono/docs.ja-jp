---
title: CoordinatorRecoveryLogEntryCorrupt
ms.date: 03/30/2017
ms.assetid: 3cd0c3e3-84c8-4d43-a561-a8851c78e565
ms.openlocfilehash: de9d27e74088b1bac9c8a401c5af2b119fc8e90e
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/07/2019
ms.locfileid: "70797989"
---
# <a name="coordinatorrecoverylogentrycorrupt"></a><span data-ttu-id="8e2aa-102">CoordinatorRecoveryLogEntryCorrupt</span><span class="sxs-lookup"><span data-stu-id="8e2aa-102">CoordinatorRecoveryLogEntryCorrupt</span></span>
<span data-ttu-id="8e2aa-103">Id:139</span><span class="sxs-lookup"><span data-stu-id="8e2aa-103">Id: 139</span></span>  
  
 <span data-ttu-id="8e2aa-104">順Error</span><span class="sxs-lookup"><span data-stu-id="8e2aa-104">Severity: Error</span></span>  
  
 <span data-ttu-id="8e2aa-105">[カテゴリ]:TransactionBridge</span><span class="sxs-lookup"><span data-stu-id="8e2aa-105">Category: TransactionBridge</span></span>  
  
## <a name="description"></a><span data-ttu-id="8e2aa-106">説明</span><span class="sxs-lookup"><span data-stu-id="8e2aa-106">Description</span></span>  
 <span data-ttu-id="8e2aa-107">このイベントは、コーディネーターの回復ログ エントリが破損し、逆シリアル化できなかったことを示します。</span><span class="sxs-lookup"><span data-stu-id="8e2aa-107">This event indicates that a  coordinator recovery log entry was corrupt and could not be deserialized.</span></span> <span data-ttu-id="8e2aa-108">このエラーが原因で、データの損失が発生することがあります。</span><span class="sxs-lookup"><span data-stu-id="8e2aa-108">Data loss may result from this error.</span></span> <span data-ttu-id="8e2aa-109">イベントには、トランザクション ID、回復データ (Base64 エンコード)、例外、プロセス名、およびプロセス ID が表示されます。</span><span class="sxs-lookup"><span data-stu-id="8e2aa-109">The event lists the Transaction ID, Recovery data (Base64 encoded), exception, process name and process ID.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8e2aa-110">関連項目</span><span class="sxs-lookup"><span data-stu-id="8e2aa-110">See also</span></span>

- [<span data-ttu-id="8e2aa-111">イベント ログ</span><span class="sxs-lookup"><span data-stu-id="8e2aa-111">Event Logging</span></span>](index.md)
- [<span data-ttu-id="8e2aa-112">イベント一覧</span><span class="sxs-lookup"><span data-stu-id="8e2aa-112">Events General Reference</span></span>](events-general-reference.md)
