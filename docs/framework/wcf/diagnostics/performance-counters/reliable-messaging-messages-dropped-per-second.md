---
title: 信頼できるメッセージの 1 秒あたりの破棄されたメッセージ
ms.date: 03/30/2017
ms.assetid: a11b0b80-b242-48e1-b0bb-7f756db5486b
ms.openlocfilehash: 946e0408b8b6602bba7824b45e4d6cb91cdaa4eb
ms.sourcegitcommit: 5d769956a04b6d68484dd717077fabc191c21da5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/17/2020
ms.locfileid: "76163957"
---
# <a name="reliable-messaging-messages-dropped-per-second"></a><span data-ttu-id="0b2e5-102">信頼できるメッセージの 1 秒あたりの破棄されたメッセージ</span><span class="sxs-lookup"><span data-stu-id="0b2e5-102">Reliable Messaging Messages Dropped Per Second</span></span>
<span data-ttu-id="0b2e5-103">カウンター名 : 1 秒あたりに破棄された信頼できるメッセージ セッション</span><span class="sxs-lookup"><span data-stu-id="0b2e5-103">Counter Name: Reliable Messaging Sessions Dropped Per Second.</span></span>  
  
## <a name="description"></a><span data-ttu-id="0b2e5-104">説明</span><span class="sxs-lookup"><span data-stu-id="0b2e5-104">Description</span></span>  
 <span data-ttu-id="0b2e5-105">このサービスで 1 秒間に破棄された信頼できるメッセージング メッセージの合計数です。</span><span class="sxs-lookup"><span data-stu-id="0b2e5-105">Total number of reliable messaging messages that have been dropped in this service in a second.</span></span>  
  
 <span data-ttu-id="0b2e5-106">このカウンターは、次の式を使用して計算された値を持つ、パフォーマンスカウンターの種類[PERF_COUNTER_COUNTER](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2003/cc740048(v=ws.10))です。</span><span class="sxs-lookup"><span data-stu-id="0b2e5-106">This counter is of performance counter type [PERF_COUNTER_COUNTER](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2003/cc740048(v=ws.10)), whose value is calculated using the following formula.</span></span>  
  
 <span data-ttu-id="0b2e5-107">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span><span class="sxs-lookup"><span data-stu-id="0b2e5-107">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span></span>
