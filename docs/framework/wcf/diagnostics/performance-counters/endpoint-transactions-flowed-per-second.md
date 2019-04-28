---
title: エンドポイント:1 秒あたりのトランザクション フロー
ms.date: 03/30/2017
ms.assetid: 0f370ff1-a913-450b-bccb-c279ad165b3d
ms.openlocfilehash: 79f50b6706facd040ec2d325c676f210d5327bf8
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61916254"
---
# <a name="endpoint-transactions-flowed-per-second"></a><span data-ttu-id="b2f45-102">エンドポイント:1 秒あたりのトランザクション フロー</span><span class="sxs-lookup"><span data-stu-id="b2f45-102">Endpoint: Transactions Flowed Per Second</span></span>
<span data-ttu-id="b2f45-103">カウンター名:1 秒あたりのトランザクション フロー。</span><span class="sxs-lookup"><span data-stu-id="b2f45-103">Counter Name: Transactions Flowed Per Second.</span></span>  
  
## <a name="description"></a><span data-ttu-id="b2f45-104">説明</span><span class="sxs-lookup"><span data-stu-id="b2f45-104">Description</span></span>  
 <span data-ttu-id="b2f45-105">このエンドポイントでの操作に対して実行された 1 秒あたりのトランザクションの数です。</span><span class="sxs-lookup"><span data-stu-id="b2f45-105">Number of transactions flowed to operations at this endpoint in a second.</span></span> <span data-ttu-id="b2f45-106">このカウンターは、エンドポイントに送信されたメッセージにトランザクション ID が付与されている場合は常にインクリメントされます。</span><span class="sxs-lookup"><span data-stu-id="b2f45-106">This counter is incremented any time a transaction ID is present in a message sent to the endpoint.</span></span>  
  
 <span data-ttu-id="b2f45-107">このカウンターは、パフォーマンス カウンター型[PERF_COUNTER_COUNTER](https://go.microsoft.com/fwlink/?LinkID=94649)、次の数式を使用して、その値が計算されます。</span><span class="sxs-lookup"><span data-stu-id="b2f45-107">This counter is of performance counter type [PERF_COUNTER_COUNTER](https://go.microsoft.com/fwlink/?LinkID=94649), whose value is calculated using the following formula.</span></span>  
  
 <span data-ttu-id="b2f45-108">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span><span class="sxs-lookup"><span data-stu-id="b2f45-108">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span></span>
