---
title: エンドポイントのパフォーマンス カウンター
ms.date: 03/30/2017
ms.assetid: 7d44d576-bd4e-453b-8b76-a818ce90b806
ms.openlocfilehash: 1b0f7462fea8843bcb0a0938a8034f405f30a6fb
ms.sourcegitcommit: 628e8147ca10187488e6407dab4c4e6ebe0cac47
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/15/2019
ms.locfileid: "72320512"
---
# <a name="endpoint-performance-counters"></a><span data-ttu-id="66eeb-102">エンドポイントのパフォーマンス カウンター</span><span class="sxs-lookup"><span data-stu-id="66eeb-102">Endpoint Performance Counters</span></span>
<span data-ttu-id="66eeb-103">エンドポイントのパフォーマンス カウンターは、エンドポイントがどのようにメッセージを受信しているかを示すデータをキャプチャします。</span><span class="sxs-lookup"><span data-stu-id="66eeb-103">Endpoint performance counters capture data that reveals how an endpoint is accepting messages.</span></span> <span data-ttu-id="66eeb-104">パフォーマンス モニターを使用して表示する場合、これらのカウンターは、`ServiceModelEndpoint 4.0.0.0` パフォーマンス オブジェクトの下にあります。</span><span class="sxs-lookup"><span data-stu-id="66eeb-104">They can be found under the `ServiceModelEndpoint 4.0.0.0` performance object when viewing with the Performance Monitor.</span></span> <span data-ttu-id="66eeb-105">インスタンスの名前には次のパターンが使用されます。</span><span class="sxs-lookup"><span data-stu-id="66eeb-105">The instances are named using this pattern:</span></span>  
  
`(ServiceName).(ContractName)@(endpoint listener address)`  
  
 <span data-ttu-id="66eeb-106">このデータは、個々の操作で収集されるデータに似ていますが、そのエンドポイントだけで集約されたデータです。</span><span class="sxs-lookup"><span data-stu-id="66eeb-106">The data is similar to that collected for individual operations, but is only aggregated across the endpoint.</span></span>  
  
> [!CAUTION]
> <span data-ttu-id="66eeb-107">パフォーマンス カウンターのインスタンス名の長さには制限があります。</span><span class="sxs-lookup"><span data-stu-id="66eeb-107">There is a limit on the length of a performance counter instance's name.</span></span> <span data-ttu-id="66eeb-108">Windows Communication Foundation (WCF) カウンターインスタンス名が最大長を超えると、WCF はインスタンス名の一部をハッシュ値に置き換えます。</span><span class="sxs-lookup"><span data-stu-id="66eeb-108">When a Windows Communication Foundation (WCF) counter instance name exceeds the maximum length, WCF replaces a portion of the instance name with a hash value.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="66eeb-109">関連項目</span><span class="sxs-lookup"><span data-stu-id="66eeb-109">See also</span></span>

- [<span data-ttu-id="66eeb-110">Performance Counters</span><span class="sxs-lookup"><span data-stu-id="66eeb-110">Performance Counters</span></span>](index.md)
