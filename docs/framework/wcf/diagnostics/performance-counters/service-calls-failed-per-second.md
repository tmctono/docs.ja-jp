---
title: 'サービス : 1 秒あたりの失敗した呼び出し'
ms.date: 03/30/2017
ms.assetid: 5a2c7939-107d-4f0c-b43c-e02e079e8a9d
ms.openlocfilehash: e165348a71101b21fa66bd4907c43335b1e476e4
ms.sourcegitcommit: 5d769956a04b6d68484dd717077fabc191c21da5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/17/2020
ms.locfileid: "76163983"
---
# <a name="service-calls-failed-per-second"></a><span data-ttu-id="e0eba-102">サービス : 1 秒あたりの失敗した呼び出し</span><span class="sxs-lookup"><span data-stu-id="e0eba-102">Service: Calls Failed Per Second</span></span>
<span data-ttu-id="e0eba-103">カウンター名 : 1 秒あたりの失敗した呼び出し。</span><span class="sxs-lookup"><span data-stu-id="e0eba-103">Counter Name: Calls Failed Per Second.</span></span>  
  
## <a name="description"></a><span data-ttu-id="e0eba-104">説明</span><span class="sxs-lookup"><span data-stu-id="e0eba-104">Description</span></span>  
 <span data-ttu-id="e0eba-105">このサービスが 1 秒間に受信した未処理の例外を含む呼び出しの回数。</span><span class="sxs-lookup"><span data-stu-id="e0eba-105">Number of calls that have unhandled exceptions, and are received by this service in a second.</span></span>  
  
 <span data-ttu-id="e0eba-106">このカウンターは、次の式を使用して計算された値を持つ、パフォーマンスカウンターの種類[PERF_COUNTER_COUNTER](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2003/cc740048(v=ws.10))です。</span><span class="sxs-lookup"><span data-stu-id="e0eba-106">This counter is of performance counter type [PERF_COUNTER_COUNTER](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2003/cc740048(v=ws.10)), whose value is calculated using the following formula.</span></span>  
  
 <span data-ttu-id="e0eba-107">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span><span class="sxs-lookup"><span data-stu-id="e0eba-107">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span></span>  
  
 <span data-ttu-id="e0eba-108">マネージド コードでは、エラー条件が発生すると例外がスローされます。</span><span class="sxs-lookup"><span data-stu-id="e0eba-108">In managed code, exceptions are thrown when error conditions occur.</span></span>  
  
 <span data-ttu-id="e0eba-109">マネージド コードでは、エラー条件が発生すると例外がスローされます。</span><span class="sxs-lookup"><span data-stu-id="e0eba-109">In managed code, exceptions are thrown when error conditions occur.</span></span>  
  
 <span data-ttu-id="e0eba-110">このカウンターは、このサービスで未処理の例外が発生するたびにインクリメントされます。</span><span class="sxs-lookup"><span data-stu-id="e0eba-110">This counter is incremented every time there is an unhandled exception in this service.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e0eba-111">関連項目</span><span class="sxs-lookup"><span data-stu-id="e0eba-111">See also</span></span>

- [<span data-ttu-id="e0eba-112">コントラクトおよびサービスのエラーの指定と処理</span><span class="sxs-lookup"><span data-stu-id="e0eba-112">Specifying and Handling Faults in Contracts and Services</span></span>](../../specifying-and-handling-faults-in-contracts-and-services.md)
