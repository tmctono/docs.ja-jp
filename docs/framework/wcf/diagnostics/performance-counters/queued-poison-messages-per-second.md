---
title: 1 秒あたりのキューに置かれた有害メッセージ
ms.date: 03/30/2017
ms.assetid: d193fdd1-02f1-44a0-906e-f632a8f574c3
ms.openlocfilehash: d755b9c9e4c8e7ef9e57a0d93c05f87830d63c5c
ms.sourcegitcommit: 5d769956a04b6d68484dd717077fabc191c21da5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/17/2020
ms.locfileid: "76163996"
---
# <a name="queued-poison-messages-per-second"></a><span data-ttu-id="d9f34-102">1 秒あたりのキューに置かれた有害メッセージ</span><span class="sxs-lookup"><span data-stu-id="d9f34-102">Queued Poison Messages Per Second</span></span>
<span data-ttu-id="d9f34-103">カウンター名 : 1 秒あたりのキューに置かれた有害メッセージ</span><span class="sxs-lookup"><span data-stu-id="d9f34-103">Counter Name: Queued Poison Messages Per Second.</span></span>  
  
## <a name="description"></a><span data-ttu-id="d9f34-104">説明</span><span class="sxs-lookup"><span data-stu-id="d9f34-104">Description</span></span>  
 <span data-ttu-id="d9f34-105">このサービスでキューに置かれたトランスポートによって 1 秒あたりに有害とマークされたメッセージの数です。</span><span class="sxs-lookup"><span data-stu-id="d9f34-105">Number of messages that are marked poisoned by the queued transport at this service in a second.</span></span>  
  
 <span data-ttu-id="d9f34-106">このカウンターは、次の式を使用して計算された値を持つ、パフォーマンスカウンターの種類[PERF_COUNTER_COUNTER](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2003/cc740048(v=ws.10))です。</span><span class="sxs-lookup"><span data-stu-id="d9f34-106">This counter is of performance counter type [PERF_COUNTER_COUNTER](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2003/cc740048(v=ws.10)), whose value is calculated using the following formula.</span></span>  
  
 <span data-ttu-id="d9f34-107">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span><span class="sxs-lookup"><span data-stu-id="d9f34-107">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span></span>
