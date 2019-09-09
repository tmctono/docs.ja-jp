---
title: PiiLoggingNotAllowed
ms.date: 03/30/2017
ms.assetid: fc34a0b6-fee7-4da4-b146-b0c1c8b7519a
ms.openlocfilehash: 24b31c33b31bb0ef763de30ce24fbc28f03aa039
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/07/2019
ms.locfileid: "70797656"
---
# <a name="piiloggingnotallowed"></a><span data-ttu-id="e69c8-102">PiiLoggingNotAllowed</span><span class="sxs-lookup"><span data-stu-id="e69c8-102">PiiLoggingNotAllowed</span></span>
<span data-ttu-id="e69c8-103">Id:108</span><span class="sxs-lookup"><span data-stu-id="e69c8-103">Id: 108</span></span>  
  
 <span data-ttu-id="e69c8-104">順Error</span><span class="sxs-lookup"><span data-stu-id="e69c8-104">Severity: Error</span></span>  
  
 <span data-ttu-id="e69c8-105">[カテゴリ]:トレース</span><span class="sxs-lookup"><span data-stu-id="e69c8-105">Category: Tracing</span></span>  
  
## <a name="description"></a><span data-ttu-id="e69c8-106">説明</span><span class="sxs-lookup"><span data-stu-id="e69c8-106">Description</span></span>  
 <span data-ttu-id="e69c8-107">このイベントは、既知の PII がログ記録されていないことを示します。</span><span class="sxs-lookup"><span data-stu-id="e69c8-107">This event indicates that no known PII is being logged.</span></span> <span data-ttu-id="e69c8-108">既知の PII はログ記録できません。</span><span class="sxs-lookup"><span data-stu-id="e69c8-108">Logging of known PII is not allowed.</span></span> <span data-ttu-id="e69c8-109">既知の PII をログ記録できるようにするには、Machine.config の "enableLoggingKnownPii" を `true` に設定します。イベントには、プロセス名とプロセス ID が表示されます。</span><span class="sxs-lookup"><span data-stu-id="e69c8-109">To allow logging of known PII, set "enableLoggingKnownPii" to `true` in Machine.config. The event lists the process name and process ID.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e69c8-110">関連項目</span><span class="sxs-lookup"><span data-stu-id="e69c8-110">See also</span></span>

- [<span data-ttu-id="e69c8-111">イベント ログ</span><span class="sxs-lookup"><span data-stu-id="e69c8-111">Event Logging</span></span>](index.md)
- [<span data-ttu-id="e69c8-112">イベント一覧</span><span class="sxs-lookup"><span data-stu-id="e69c8-112">Events General Reference</span></span>](events-general-reference.md)
