---
title: サービス:1 秒あたりの呼び出し回数
ms.date: 03/30/2017
ms.assetid: 6261d28d-d449-425a-b9fc-a4ee14079134
ms.openlocfilehash: 5189a78e2655707d165f187e06ac9a60d055eac0
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61773363"
---
# <a name="service-calls-per-second"></a><span data-ttu-id="07ede-102">サービス:1 秒あたりの呼び出し回数</span><span class="sxs-lookup"><span data-stu-id="07ede-102">Service: Calls Per Second</span></span>
<span data-ttu-id="07ede-103">カウンター名:1 秒あたりの呼び出し。</span><span class="sxs-lookup"><span data-stu-id="07ede-103">Counter Name: Calls Per Second.</span></span>  
  
## <a name="description"></a><span data-ttu-id="07ede-104">説明</span><span class="sxs-lookup"><span data-stu-id="07ede-104">Description</span></span>  
 <span data-ttu-id="07ede-105">このサービスが 1 秒あたりに呼び出される回数です。</span><span class="sxs-lookup"><span data-stu-id="07ede-105">Number of calls to this service in a second.</span></span>  
  
 <span data-ttu-id="07ede-106">このカウンターは、パフォーマンス カウンター型[PERF_COUNTER_COUNTER](https://go.microsoft.com/fwlink/?LinkID=94649)、次の数式を使用して、その値が計算されます。</span><span class="sxs-lookup"><span data-stu-id="07ede-106">This counter is of performance counter type [PERF_COUNTER_COUNTER](https://go.microsoft.com/fwlink/?LinkID=94649), whose value is calculated using the following formula.</span></span>  
  
 <span data-ttu-id="07ede-107">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)。ここで、分子 (N) は最後のサンプル間隔中に実行された操作の数を、分母 (D) は最後のサンプル間隔中に経過したタイマー刻み数を、F はタイマー刻みの頻度をそれぞれ表します。</span><span class="sxs-lookup"><span data-stu-id="07ede-107">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F) where the numerator (N) represents the number of operations performed during the last sample interval, the denominator (D) represents the number of ticks elapsed during the last sample interval, and F is the frequency of the ticks.</span></span>
