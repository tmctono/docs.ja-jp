---
title: 1 秒あたりの承認されていないセキュリティ呼び出し
ms.date: 03/30/2017
ms.assetid: 0f189767-8c05-478a-8f0b-9228e5d351e5
ms.openlocfilehash: 8aed9f6b8c60c8aecd1b576c13a7063e3a492046
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/15/2020
ms.locfileid: "90552506"
---
# <a name="security-calls-not-authorized-per-second"></a><span data-ttu-id="264fa-102">1 秒あたりの承認されていないセキュリティ呼び出し</span><span class="sxs-lookup"><span data-stu-id="264fa-102">Security Calls Not Authorized Per Second</span></span>
<span data-ttu-id="264fa-103">カウンター名 : 1 秒あたりの承認されていないセキュリティ呼び出し。</span><span class="sxs-lookup"><span data-stu-id="264fa-103">Counter Name: Security Calls Not Authorized Per Second.</span></span>  
  
## <a name="description"></a><span data-ttu-id="264fa-104">説明</span><span class="sxs-lookup"><span data-stu-id="264fa-104">Description</span></span>  
 <span data-ttu-id="264fa-105">この操作で 1 秒あたりに承認に失敗した呼び出しの数です。</span><span class="sxs-lookup"><span data-stu-id="264fa-105">Number of calls that failed authorization in this operation in a second.</span></span>  
  
 <span data-ttu-id="264fa-106">このカウンターは <xref:System.ServiceModel.ServiceAuthorizationManager.CheckAccess%2A> メソッドで `false` が返された場合にインクリメントされます。</span><span class="sxs-lookup"><span data-stu-id="264fa-106">This counter is incremented when the <xref:System.ServiceModel.ServiceAuthorizationManager.CheckAccess%2A> method returns `false`.</span></span> <span data-ttu-id="264fa-107">受信メッセージが有効なユーザーから適切な保護を適用して送信されたものであり、その一方でそのユーザーが特定のタスクの実行を許可されていないことを示します。</span><span class="sxs-lookup"><span data-stu-id="264fa-107">It indicates that the incoming message is from a valid user and protected properly, but the user is not authorized to do specific tasks.</span></span>  
  
 <span data-ttu-id="264fa-108">このカウンターは、次の式を使用して計算された値を持つ、パフォーマンスカウンターの種類 [PERF_COUNTER_COUNTER](/previous-versions/windows/it-pro/windows-server-2003/cc740048(v=ws.10))です。</span><span class="sxs-lookup"><span data-stu-id="264fa-108">This counter is of performance counter type [PERF_COUNTER_COUNTER](/previous-versions/windows/it-pro/windows-server-2003/cc740048(v=ws.10)), whose value is calculated using the following formula.</span></span>  
  
 <span data-ttu-id="264fa-109">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span><span class="sxs-lookup"><span data-stu-id="264fa-109">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span></span>
