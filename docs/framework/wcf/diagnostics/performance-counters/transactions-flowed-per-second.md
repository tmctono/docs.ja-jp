---
title: 1 秒あたりのトランザクション フロー
ms.date: 03/30/2017
ms.assetid: b9f661e1-576c-48fc-9fdf-91853e0749e8
ms.openlocfilehash: 8b6077af3f98f7a205772b4883dc122374083e00
ms.sourcegitcommit: 5d769956a04b6d68484dd717077fabc191c21da5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/17/2020
ms.locfileid: "76163827"
---
# <a name="transactions-flowed-per-second"></a><span data-ttu-id="c78cd-102">1 秒あたりのトランザクション フロー</span><span class="sxs-lookup"><span data-stu-id="c78cd-102">Transactions Flowed Per Second</span></span>
<span data-ttu-id="c78cd-103">カウンター名 : 1 秒あたりのトランザクション フロー</span><span class="sxs-lookup"><span data-stu-id="c78cd-103">Counter Name:  Transactions Flowed Per Second</span></span>  
  
## <a name="description"></a><span data-ttu-id="c78cd-104">説明</span><span class="sxs-lookup"><span data-stu-id="c78cd-104">Description</span></span>  
 <span data-ttu-id="c78cd-105">この操作に対して実行された 1 秒あたりのトランザクションの数です。</span><span class="sxs-lookup"><span data-stu-id="c78cd-105">Number of transactions flowed to this operation in a second.</span></span> <span data-ttu-id="c78cd-106">このカウンターは、操作に送信されたメッセージにトランザクション ID が存在する場合にインクリメントされます。</span><span class="sxs-lookup"><span data-stu-id="c78cd-106">This counter is incremented any time a transaction ID is present in a message that is sent to the operation.</span></span>  
  
 <span data-ttu-id="c78cd-107">このカウンターは、次の式を使用して計算された値を持つ、パフォーマンスカウンターの種類[PERF_COUNTER_COUNTER](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2003/cc740048(v=ws.10))です。</span><span class="sxs-lookup"><span data-stu-id="c78cd-107">This counter is of performance counter type [PERF_COUNTER_COUNTER](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2003/cc740048(v=ws.10)), whose value is calculated using the following formula.</span></span>  
  
 <span data-ttu-id="c78cd-108">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span><span class="sxs-lookup"><span data-stu-id="c78cd-108">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span></span>
