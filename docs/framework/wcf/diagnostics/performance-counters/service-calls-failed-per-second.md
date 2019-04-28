---
title: サービス:1 秒あたりの失敗した呼び出し
ms.date: 03/30/2017
ms.assetid: 5a2c7939-107d-4f0c-b43c-e02e079e8a9d
ms.openlocfilehash: d87d5f06d0c9a3849ec80a3d1c7badefde7cf372
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61915682"
---
# <a name="service-calls-failed-per-second"></a><span data-ttu-id="3c75b-102">サービス:1 秒あたりの失敗した呼び出し</span><span class="sxs-lookup"><span data-stu-id="3c75b-102">Service: Calls Failed Per Second</span></span>
<span data-ttu-id="3c75b-103">カウンター名:1 秒あたりの呼び出しに失敗しました。</span><span class="sxs-lookup"><span data-stu-id="3c75b-103">Counter Name: Calls Failed Per Second.</span></span>  
  
## <a name="description"></a><span data-ttu-id="3c75b-104">説明</span><span class="sxs-lookup"><span data-stu-id="3c75b-104">Description</span></span>  
 <span data-ttu-id="3c75b-105">このサービスが 1 秒間に受信した未処理の例外を含む呼び出しの回数。</span><span class="sxs-lookup"><span data-stu-id="3c75b-105">Number of calls that have unhandled exceptions, and are received by this service in a second.</span></span>  
  
 <span data-ttu-id="3c75b-106">このカウンターは、パフォーマンス カウンター型[PERF_COUNTER_COUNTER](https://go.microsoft.com/fwlink/?LinkID=94649)、次の数式を使用して、その値が計算されます。</span><span class="sxs-lookup"><span data-stu-id="3c75b-106">This counter is of performance counter type [PERF_COUNTER_COUNTER](https://go.microsoft.com/fwlink/?LinkID=94649), whose value is calculated using the following formula.</span></span>  
  
 <span data-ttu-id="3c75b-107">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span><span class="sxs-lookup"><span data-stu-id="3c75b-107">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span></span>  
  
 <span data-ttu-id="3c75b-108">マネージド コードでは、エラー条件が発生すると例外がスローされます。</span><span class="sxs-lookup"><span data-stu-id="3c75b-108">In managed code, exceptions are thrown when error conditions occur.</span></span>  
  
 <span data-ttu-id="3c75b-109">マネージド コードでは、エラー条件が発生すると例外がスローされます。</span><span class="sxs-lookup"><span data-stu-id="3c75b-109">In managed code, exceptions are thrown when error conditions occur.</span></span>  
  
 <span data-ttu-id="3c75b-110">このカウンターは、このサービスで未処理の例外が発生するたびにインクリメントされます。</span><span class="sxs-lookup"><span data-stu-id="3c75b-110">This counter is incremented every time there is an unhandled exception in this service.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3c75b-111">関連項目</span><span class="sxs-lookup"><span data-stu-id="3c75b-111">See also</span></span>

- [<span data-ttu-id="3c75b-112">コントラクトおよびサービスのエラーの指定と処理</span><span class="sxs-lookup"><span data-stu-id="3c75b-112">Specifying and Handling Faults in Contracts and Services</span></span>](../../../../../docs/framework/wcf/specifying-and-handling-faults-in-contracts-and-services.md)
