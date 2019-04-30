---
title: 1 秒あたりの中止されたトランザクション操作
ms.date: 03/30/2017
ms.assetid: 19fc993f-2b3d-4898-852e-3b98ec2153a5
ms.openlocfilehash: 6369fea6def5ebb6b62274caed31d5fb63b3b0e1
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61998193"
---
# <a name="transacted-operations-aborted-per-second"></a><span data-ttu-id="f97be-102">1 秒あたりの中止されたトランザクション操作</span><span class="sxs-lookup"><span data-stu-id="f97be-102">Transacted Operations Aborted Per Second</span></span>
<span data-ttu-id="f97be-103">カウンター名:1 秒あたりにトランザクション操作が中止されました。</span><span class="sxs-lookup"><span data-stu-id="f97be-103">Counter Name: Transacted Operations Aborted Per Second.</span></span>  
  
## <a name="description"></a><span data-ttu-id="f97be-104">説明</span><span class="sxs-lookup"><span data-stu-id="f97be-104">Description</span></span>  
 <span data-ttu-id="f97be-105">1 秒あたりに、このサービスで中止されたトランザクション処理の数です。</span><span class="sxs-lookup"><span data-stu-id="f97be-105">Number of transactional operations that have been aborted in this service in a second.</span></span>  
  
 <span data-ttu-id="f97be-106">このカウンターは、パフォーマンス カウンター型[PERF_COUNTER_COUNTER](https://go.microsoft.com/fwlink/?LinkID=94649)、次の数式を使用して、その値が計算されます。</span><span class="sxs-lookup"><span data-stu-id="f97be-106">This counter is of performance counter type [PERF_COUNTER_COUNTER](https://go.microsoft.com/fwlink/?LinkID=94649), whose value is calculated using the following formula.</span></span>  
  
 <span data-ttu-id="f97be-107">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span><span class="sxs-lookup"><span data-stu-id="f97be-107">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span></span>
