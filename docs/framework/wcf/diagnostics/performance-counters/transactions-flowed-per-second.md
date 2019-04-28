---
title: 1 秒あたりのトランザクション フロー
ms.date: 03/30/2017
ms.assetid: b9f661e1-576c-48fc-9fdf-91853e0749e8
ms.openlocfilehash: e77aef4cfff1e64f112e720183675dfb7aa25d27
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61927193"
---
# <a name="transactions-flowed-per-second"></a><span data-ttu-id="031bd-102">1 秒あたりのトランザクション フロー</span><span class="sxs-lookup"><span data-stu-id="031bd-102">Transactions Flowed Per Second</span></span>
<span data-ttu-id="031bd-103">カウンター名:1 秒あたりのトランザクション フロー</span><span class="sxs-lookup"><span data-stu-id="031bd-103">Counter Name:  Transactions Flowed Per Second</span></span>  
  
## <a name="description"></a><span data-ttu-id="031bd-104">説明</span><span class="sxs-lookup"><span data-stu-id="031bd-104">Description</span></span>  
 <span data-ttu-id="031bd-105">この操作に対して実行された 1 秒あたりのトランザクションの数です。</span><span class="sxs-lookup"><span data-stu-id="031bd-105">Number of transactions flowed to this operation in a second.</span></span> <span data-ttu-id="031bd-106">このカウンターは、操作に送信されたメッセージにトランザクション ID が存在する場合にインクリメントされます。</span><span class="sxs-lookup"><span data-stu-id="031bd-106">This counter is incremented any time a transaction ID is present in a message that is sent to the operation.</span></span>  
  
 <span data-ttu-id="031bd-107">このカウンターは、パフォーマンス カウンター型[PERF_COUNTER_COUNTER](https://go.microsoft.com/fwlink/?LinkID=94649)、次の数式を使用して、その値が計算されます。</span><span class="sxs-lookup"><span data-stu-id="031bd-107">This counter is of performance counter type [PERF_COUNTER_COUNTER](https://go.microsoft.com/fwlink/?LinkID=94649), whose value is calculated using the following formula.</span></span>  
  
 <span data-ttu-id="031bd-108">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span><span class="sxs-lookup"><span data-stu-id="031bd-108">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span></span>
