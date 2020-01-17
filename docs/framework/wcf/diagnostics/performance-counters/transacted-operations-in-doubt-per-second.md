---
title: 1 秒あたりの不明なトランザクション操作
ms.date: 03/30/2017
ms.assetid: 7e6b0716-c107-42e5-a21d-31d988e7a691
ms.openlocfilehash: bc978f5b45352fa9fcce5aee5a616c9f86f56aeb
ms.sourcegitcommit: 5d769956a04b6d68484dd717077fabc191c21da5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/17/2020
ms.locfileid: "76163840"
---
# <a name="transacted-operations-in-doubt-per-second"></a><span data-ttu-id="2b892-102">1 秒あたりの不明なトランザクション操作</span><span class="sxs-lookup"><span data-stu-id="2b892-102">Transacted Operations In Doubt Per Second</span></span>
<span data-ttu-id="2b892-103">カウンター名 : 1 秒あたりの不明なトランザクション操作。</span><span class="sxs-lookup"><span data-stu-id="2b892-103">Counter Name: Transacted Operations In Doubt Per Second.</span></span>  
  
## <a name="description"></a><span data-ttu-id="2b892-104">説明</span><span class="sxs-lookup"><span data-stu-id="2b892-104">Description</span></span>  
 <span data-ttu-id="2b892-105">このサービスでの 1 秒あたりの結果が不明なランザクション操作の数です。</span><span class="sxs-lookup"><span data-stu-id="2b892-105">Number of transactional operations with an in-doubt outcome in this service in a second.</span></span>  
  
 <span data-ttu-id="2b892-106">このカウンターは、次の式を使用して計算された値を持つ、パフォーマンスカウンターの種類[PERF_COUNTER_COUNTER](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2003/cc740048(v=ws.10))です。</span><span class="sxs-lookup"><span data-stu-id="2b892-106">This counter is of performance counter type [PERF_COUNTER_COUNTER](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2003/cc740048(v=ws.10)), whose value is calculated using the following formula.</span></span>  
  
 <span data-ttu-id="2b892-107">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span><span class="sxs-lookup"><span data-stu-id="2b892-107">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span></span>
