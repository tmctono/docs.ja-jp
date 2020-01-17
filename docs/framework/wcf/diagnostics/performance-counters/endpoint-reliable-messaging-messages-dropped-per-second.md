---
title: 'エンドポイント: 信頼できるメッセージの 1 秒あたりの破棄されたメッセージ'
ms.date: 03/30/2017
ms.assetid: ea3c4fc0-1e0f-4863-8879-57bc6c113018
ms.openlocfilehash: 7dc52caea0233953dd72e77e4d662083f4a370e4
ms.sourcegitcommit: 5d769956a04b6d68484dd717077fabc191c21da5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/17/2020
ms.locfileid: "76164048"
---
# <a name="endpoint-reliable-messaging-messages-dropped-per-second"></a><span data-ttu-id="033f1-102">エンドポイント: 信頼できるメッセージの 1 秒あたりの破棄されたメッセージ</span><span class="sxs-lookup"><span data-stu-id="033f1-102">Endpoint: Reliable Messaging Messages Dropped Per Second</span></span>
<span data-ttu-id="033f1-103">カウンター名 : 1 秒あたりに破棄された信頼できるメッセージ セッション</span><span class="sxs-lookup"><span data-stu-id="033f1-103">Counter Name: Reliable Messaging Sessions Dropped Per Second.</span></span>  
  
## <a name="description"></a><span data-ttu-id="033f1-104">説明</span><span class="sxs-lookup"><span data-stu-id="033f1-104">Description</span></span>  
 <span data-ttu-id="033f1-105">このエンドポイントで 1 秒間に破棄された信頼できるメッセージング メッセージの合計数です。</span><span class="sxs-lookup"><span data-stu-id="033f1-105">Total number of reliable messaging messages that have been dropped at this endpoint in a second.</span></span>  
  
 <span data-ttu-id="033f1-106">このカウンターは、次の式を使用して計算された値を持つ、パフォーマンスカウンターの種類[PERF_COUNTER_COUNTER](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2003/cc740048(v=ws.10))です。</span><span class="sxs-lookup"><span data-stu-id="033f1-106">This counter is of performance counter type [PERF_COUNTER_COUNTER](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2003/cc740048(v=ws.10)), whose value is calculated using the following formula.</span></span>  
  
 <span data-ttu-id="033f1-107">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span><span class="sxs-lookup"><span data-stu-id="033f1-107">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span></span>
