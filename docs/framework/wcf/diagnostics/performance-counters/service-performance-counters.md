---
title: サービス パフォーマンス カウンター
ms.date: 03/30/2017
ms.assetid: 4210f549-31f2-4ea7-99bd-69eaffb98ddf
ms.openlocfilehash: dc31e05f82f232095f6560c8fdd9bf75c040e2ca
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59210413"
---
# <a name="service-performance-counters"></a><span data-ttu-id="43060-102">サービス パフォーマンス カウンター</span><span class="sxs-lookup"><span data-stu-id="43060-102">Service Performance Counters</span></span>
<span data-ttu-id="43060-103">サービスのパフォーマンス カウンターはサービス動作全体を測定し、サービス全体のパフォーマンスを診断するために使用できます。</span><span class="sxs-lookup"><span data-stu-id="43060-103">Service performance counters measure the service behavior as a whole and can be used to diagnose the performance of the whole service.</span></span> <span data-ttu-id="43060-104">パフォーマンス モニター (Perfmon.exe) を使用して表示する場合、これらのカウンターは、`ServiceModelService 4.0.0.0` パフォーマンス オブジェクトの下にあります。</span><span class="sxs-lookup"><span data-stu-id="43060-104">They can be found under the `ServiceModelService 4.0.0.0` performance object when viewing with Performance Monitor (Perfmon.exe).</span></span> <span data-ttu-id="43060-105">インスタンスには次のパターンの名前が付けられています。</span><span class="sxs-lookup"><span data-stu-id="43060-105">The instances are named using the following pattern:</span></span>  
  
```  
ServiceName@ServiceBaseAddress  
```  
  
> [!CAUTION]
>  <span data-ttu-id="43060-106">パフォーマンス カウンターのインスタンス名の長さには制限があります。</span><span class="sxs-lookup"><span data-stu-id="43060-106">There is a limit on the length of a performance counter instance's name.</span></span> <span data-ttu-id="43060-107">Windows Communication Foundation (WCF) のカウンター インスタンス名は、最大長を超えています、WCF はインスタンス名の一部をハッシュ値に置き換えます。</span><span class="sxs-lookup"><span data-stu-id="43060-107">When a Windows Communication Foundation (WCF) counter instance name exceeds the maximum length, WCF replaces a portion of the instance name with a hash value.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="43060-108">関連項目</span><span class="sxs-lookup"><span data-stu-id="43060-108">See also</span></span>

- [<span data-ttu-id="43060-109">パフォーマンス カウンター</span><span class="sxs-lookup"><span data-stu-id="43060-109">Performance Counters</span></span>](../../../../../docs/framework/wcf/diagnostics/performance-counters/index.md)
