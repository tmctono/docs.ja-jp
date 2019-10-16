---
title: 1 秒あたりの失敗した呼び出し
ms.date: 03/30/2017
ms.assetid: e4ef3773-f650-4876-99cf-4d0c02aa03d4
ms.openlocfilehash: e7c0b53f4c2b1a7e87a5791b44e452ec9146c459
ms.sourcegitcommit: 628e8147ca10187488e6407dab4c4e6ebe0cac47
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/15/2019
ms.locfileid: "72321119"
---
# <a name="calls-failed-per-second"></a><span data-ttu-id="d5f2b-102">1 秒あたりの失敗した呼び出し</span><span class="sxs-lookup"><span data-stu-id="d5f2b-102">Calls Failed Per Second</span></span>
<span data-ttu-id="d5f2b-103">カウンター名 : 1 秒あたりの失敗した呼び出し</span><span class="sxs-lookup"><span data-stu-id="d5f2b-103">Counter Name: Calls Failed Per Second</span></span>  
  
## <a name="description"></a><span data-ttu-id="d5f2b-104">説明</span><span class="sxs-lookup"><span data-stu-id="d5f2b-104">Description</span></span>  
 <span data-ttu-id="d5f2b-105">1 秒間にこの操作で未処理の例外が発生した呼び出しの回数です。</span><span class="sxs-lookup"><span data-stu-id="d5f2b-105">Number of calls with unhandled exceptions in this operation in a second.</span></span>  
  
 <span data-ttu-id="d5f2b-106">このカウンターは、次の式を使用して計算された値を持つ、パフォーマンスカウンターの種類[PERF_COUNTER_COUNTER](https://go.microsoft.com/fwlink/?LinkID=94649)です。</span><span class="sxs-lookup"><span data-stu-id="d5f2b-106">This counter is of performance counter type [PERF_COUNTER_COUNTER](https://go.microsoft.com/fwlink/?LinkID=94649), whose value is calculated using the following formula.</span></span>  
  
 <span data-ttu-id="d5f2b-107">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span><span class="sxs-lookup"><span data-stu-id="d5f2b-107">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span></span>  
  
 <span data-ttu-id="d5f2b-108">このカウンターは、この操作でハンドルされない例外が発生するたびにインクリメントされます。</span><span class="sxs-lookup"><span data-stu-id="d5f2b-108">This counter is incremented every time there is an unhandled exception in this operation.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d5f2b-109">関連項目</span><span class="sxs-lookup"><span data-stu-id="d5f2b-109">See also</span></span>

- [<span data-ttu-id="d5f2b-110">コントラクトおよびサービスのエラーの指定と処理</span><span class="sxs-lookup"><span data-stu-id="d5f2b-110">Specifying and Handling Faults in Contracts and Services</span></span>](../../specifying-and-handling-faults-in-contracts-and-services.md)
