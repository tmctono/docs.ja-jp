---
title: エンドポイント:1 秒あたりの失敗した呼び出し
ms.date: 03/30/2017
ms.assetid: bcbe9da4-c8dd-4e27-b630-11611adc7580
ms.openlocfilehash: 52419f45adde768d19d6b46642d52ad0a1844197
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2019
ms.locfileid: "59100029"
---
# <a name="endpoint-calls-failed-per-second"></a><span data-ttu-id="45946-102">エンドポイント:1 秒あたりの失敗した呼び出し</span><span class="sxs-lookup"><span data-stu-id="45946-102">Endpoint: Calls Failed Per Second</span></span>
<span data-ttu-id="45946-103">カウンター名:1 秒あたりの呼び出しに失敗しました。</span><span class="sxs-lookup"><span data-stu-id="45946-103">Counter Name: Calls Failed Per Second.</span></span>  
  
## <a name="description"></a><span data-ttu-id="45946-104">説明</span><span class="sxs-lookup"><span data-stu-id="45946-104">Description</span></span>  
 <span data-ttu-id="45946-105">未処理の例外を伴ってこのエンドポイントに到達した、1 秒あたりの呼び出しの回数。</span><span class="sxs-lookup"><span data-stu-id="45946-105">Number of calls that have unhandled exceptions and are received by this endpoint in a second.</span></span>  
  
 <span data-ttu-id="45946-106">このカウンターは、パフォーマンス カウンター型[PERF_COUNTER_COUNTER](https://go.microsoft.com/fwlink/?LinkID=94649)、次の数式を使用して、その値が計算されます。</span><span class="sxs-lookup"><span data-stu-id="45946-106">This counter is of performance counter type [PERF_COUNTER_COUNTER](https://go.microsoft.com/fwlink/?LinkID=94649), whose value is calculated using the following formula.</span></span>  
  
 <span data-ttu-id="45946-107">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span><span class="sxs-lookup"><span data-stu-id="45946-107">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span></span>  
  
 <span data-ttu-id="45946-108">このカウンターは、このエンドポイントで未処理の例外が発生すると常にインクリメントされます。</span><span class="sxs-lookup"><span data-stu-id="45946-108">This counter is incremented every time there is an unhandled exception at this endpoint.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="45946-109">関連項目</span><span class="sxs-lookup"><span data-stu-id="45946-109">See also</span></span>

- [<span data-ttu-id="45946-110">コントラクトおよびサービスのエラーの指定と処理</span><span class="sxs-lookup"><span data-stu-id="45946-110">Specifying and Handling Faults in Contracts and Services</span></span>](../../../../../docs/framework/wcf/specifying-and-handling-faults-in-contracts-and-services.md)
