---
title: 1 秒あたりのトランザクション フロー
ms.date: 03/30/2017
ms.assetid: b9f661e1-576c-48fc-9fdf-91853e0749e8
ms.openlocfilehash: d55856a5d820df2c668863a2a3e853995a113143
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/15/2020
ms.locfileid: "90552207"
---
# <a name="transactions-flowed-per-second"></a><span data-ttu-id="74c2a-102">1 秒あたりのトランザクション フロー</span><span class="sxs-lookup"><span data-stu-id="74c2a-102">Transactions Flowed Per Second</span></span>
<span data-ttu-id="74c2a-103">カウンター名 : 1 秒あたりのトランザクション フロー</span><span class="sxs-lookup"><span data-stu-id="74c2a-103">Counter Name:  Transactions Flowed Per Second</span></span>  
  
## <a name="description"></a><span data-ttu-id="74c2a-104">説明</span><span class="sxs-lookup"><span data-stu-id="74c2a-104">Description</span></span>  
 <span data-ttu-id="74c2a-105">この操作に対して実行された 1 秒あたりのトランザクションの数です。</span><span class="sxs-lookup"><span data-stu-id="74c2a-105">Number of transactions flowed to this operation in a second.</span></span> <span data-ttu-id="74c2a-106">このカウンターは、操作に送信されたメッセージにトランザクション ID が存在する場合にインクリメントされます。</span><span class="sxs-lookup"><span data-stu-id="74c2a-106">This counter is incremented any time a transaction ID is present in a message that is sent to the operation.</span></span>  
  
 <span data-ttu-id="74c2a-107">このカウンターは、次の式を使用して計算された値を持つ、パフォーマンスカウンターの種類 [PERF_COUNTER_COUNTER](/previous-versions/windows/it-pro/windows-server-2003/cc740048(v=ws.10))です。</span><span class="sxs-lookup"><span data-stu-id="74c2a-107">This counter is of performance counter type [PERF_COUNTER_COUNTER](/previous-versions/windows/it-pro/windows-server-2003/cc740048(v=ws.10)), whose value is calculated using the following formula.</span></span>  
  
 <span data-ttu-id="74c2a-108">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span><span class="sxs-lookup"><span data-stu-id="74c2a-108">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span></span>
