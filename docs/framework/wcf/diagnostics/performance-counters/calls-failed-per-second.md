---
title: 1 秒あたりの失敗した呼び出し
ms.date: 03/30/2017
ms.assetid: e4ef3773-f650-4876-99cf-4d0c02aa03d4
ms.openlocfilehash: 8f2337d5ea3eb696c7be5b25d01396676dae2458
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/15/2020
ms.locfileid: "90554118"
---
# <a name="calls-failed-per-second"></a><span data-ttu-id="64a32-102">1 秒あたりの失敗した呼び出し</span><span class="sxs-lookup"><span data-stu-id="64a32-102">Calls Failed Per Second</span></span>
<span data-ttu-id="64a32-103">カウンター名 : 1 秒あたりの失敗した呼び出し</span><span class="sxs-lookup"><span data-stu-id="64a32-103">Counter Name: Calls Failed Per Second</span></span>  
  
## <a name="description"></a><span data-ttu-id="64a32-104">説明</span><span class="sxs-lookup"><span data-stu-id="64a32-104">Description</span></span>  
 <span data-ttu-id="64a32-105">1 秒間にこの操作で未処理の例外が発生した呼び出しの回数です。</span><span class="sxs-lookup"><span data-stu-id="64a32-105">Number of calls with unhandled exceptions in this operation in a second.</span></span>  
  
 <span data-ttu-id="64a32-106">このカウンターは、次の式を使用して計算された値を持つ、パフォーマンスカウンターの種類 [PERF_COUNTER_COUNTER](/previous-versions/windows/it-pro/windows-server-2003/cc740048(v=ws.10))です。</span><span class="sxs-lookup"><span data-stu-id="64a32-106">This counter is of performance counter type [PERF_COUNTER_COUNTER](/previous-versions/windows/it-pro/windows-server-2003/cc740048(v=ws.10)), whose value is calculated using the following formula.</span></span>  
  
 <span data-ttu-id="64a32-107">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span><span class="sxs-lookup"><span data-stu-id="64a32-107">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span></span>  
  
 <span data-ttu-id="64a32-108">このカウンターは、この操作でハンドルされない例外が発生するたびにインクリメントされます。</span><span class="sxs-lookup"><span data-stu-id="64a32-108">This counter is incremented every time there is an unhandled exception in this operation.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="64a32-109">関連項目</span><span class="sxs-lookup"><span data-stu-id="64a32-109">See also</span></span>

- [<span data-ttu-id="64a32-110">コントラクトおよびサービスのエラーの指定と処理</span><span class="sxs-lookup"><span data-stu-id="64a32-110">Specifying and Handling Faults in Contracts and Services</span></span>](../../specifying-and-handling-faults-in-contracts-and-services.md)
