---
title: 1 秒あたりの破棄されたメッセージのキュー
ms.date: 03/30/2017
ms.assetid: 74540f52-8762-4147-b5ba-e171180515a3
ms.openlocfilehash: f15b2db08ac4486377189a1533b653260d79024a
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61916163"
---
# <a name="queue-dropped-messages-per-second"></a><span data-ttu-id="3798a-102">1 秒あたりの破棄されたメッセージのキュー</span><span class="sxs-lookup"><span data-stu-id="3798a-102">Queue Dropped Messages Per Second</span></span>
<span data-ttu-id="3798a-103">カウンター名:1 秒あたりの破棄されたメッセージはキューに置かれました。</span><span class="sxs-lookup"><span data-stu-id="3798a-103">Counter Name: Queued Messages Dropped Per Second.</span></span>  
  
## <a name="description"></a><span data-ttu-id="3798a-104">説明</span><span class="sxs-lookup"><span data-stu-id="3798a-104">Description</span></span>  
 <span data-ttu-id="3798a-105">このサービスでキューに置かれたトランスポートによって 1 秒あたりに破棄されたメッセージの数です。</span><span class="sxs-lookup"><span data-stu-id="3798a-105">Number of messages that are dropped by the queued transport at this service in a second.</span></span>  
  
 <span data-ttu-id="3798a-106">このカウンターは、パフォーマンス カウンター型[PERF_COUNTER_COUNTER](https://go.microsoft.com/fwlink/?LinkID=94649)、次の数式を使用して、その値が計算されます。</span><span class="sxs-lookup"><span data-stu-id="3798a-106">This counter is of performance counter type [PERF_COUNTER_COUNTER](https://go.microsoft.com/fwlink/?LinkID=94649), whose value is calculated using the following formula.</span></span>  
  
 <span data-ttu-id="3798a-107">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span><span class="sxs-lookup"><span data-stu-id="3798a-107">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span></span>
