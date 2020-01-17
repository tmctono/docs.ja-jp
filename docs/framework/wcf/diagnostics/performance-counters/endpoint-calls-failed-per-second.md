---
title: 'エンドポイント: 1 秒あたりの失敗した呼び出し'
ms.date: 03/30/2017
ms.assetid: bcbe9da4-c8dd-4e27-b630-11611adc7580
ms.openlocfilehash: 25e504221097505e622a3ba60f0c7e85ec455f36
ms.sourcegitcommit: 5d769956a04b6d68484dd717077fabc191c21da5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/17/2020
ms.locfileid: "76163619"
---
# <a name="endpoint-calls-failed-per-second"></a><span data-ttu-id="a4869-102">エンドポイント: 1 秒あたりの失敗した呼び出し</span><span class="sxs-lookup"><span data-stu-id="a4869-102">Endpoint: Calls Failed Per Second</span></span>
<span data-ttu-id="a4869-103">カウンター名 : 1 秒あたりの失敗した呼び出し。</span><span class="sxs-lookup"><span data-stu-id="a4869-103">Counter Name: Calls Failed Per Second.</span></span>  
  
## <a name="description"></a><span data-ttu-id="a4869-104">説明</span><span class="sxs-lookup"><span data-stu-id="a4869-104">Description</span></span>  
 <span data-ttu-id="a4869-105">未処理の例外を伴ってこのエンドポイントに到達した、1 秒あたりの呼び出しの回数。</span><span class="sxs-lookup"><span data-stu-id="a4869-105">Number of calls that have unhandled exceptions and are received by this endpoint in a second.</span></span>  
  
 <span data-ttu-id="a4869-106">このカウンターは、次の式を使用して計算された値を持つ、パフォーマンスカウンターの種類[PERF_COUNTER_COUNTER](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2003/cc740048(v=ws.10))です。</span><span class="sxs-lookup"><span data-stu-id="a4869-106">This counter is of performance counter type [PERF_COUNTER_COUNTER](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2003/cc740048(v=ws.10)), whose value is calculated using the following formula.</span></span>  
  
 <span data-ttu-id="a4869-107">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span><span class="sxs-lookup"><span data-stu-id="a4869-107">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span></span>  
  
 <span data-ttu-id="a4869-108">このカウンターは、このエンドポイントで未処理の例外が発生すると常にインクリメントされます。</span><span class="sxs-lookup"><span data-stu-id="a4869-108">This counter is incremented every time there is an unhandled exception at this endpoint.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a4869-109">関連項目</span><span class="sxs-lookup"><span data-stu-id="a4869-109">See also</span></span>

- [<span data-ttu-id="a4869-110">コントラクトおよびサービスのエラーの指定と処理</span><span class="sxs-lookup"><span data-stu-id="a4869-110">Specifying and Handling Faults in Contracts and Services</span></span>](../../specifying-and-handling-faults-in-contracts-and-services.md)
