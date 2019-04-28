---
title: サービス:承認されていないセキュリティ呼び出し
ms.date: 03/30/2017
ms.assetid: 3024b20a-5250-4bd1-a38c-c6d79f89610b
ms.openlocfilehash: a38b5e0eb467a5cad698fd6e3e01c0adef825d2f
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61773369"
---
# <a name="service-security-calls-not-authorized"></a><span data-ttu-id="f5edd-102">サービス:承認されていないセキュリティ呼び出し</span><span class="sxs-lookup"><span data-stu-id="f5edd-102">Service: Security Calls Not Authorized</span></span>
<span data-ttu-id="f5edd-103">カウンター名:承認されていないセキュリティ呼び出し。</span><span class="sxs-lookup"><span data-stu-id="f5edd-103">Counter Name: Security Calls Not Authorized.</span></span>  
  
## <a name="description"></a><span data-ttu-id="f5edd-104">説明</span><span class="sxs-lookup"><span data-stu-id="f5edd-104">Description</span></span>  
 <span data-ttu-id="f5edd-105">このカウンターは <xref:System.ServiceModel.ServiceAuthorizationManager.CheckAccess%2A> メソッドで `false` が返された場合にインクリメントされます。</span><span class="sxs-lookup"><span data-stu-id="f5edd-105">This counter is incremented when the <xref:System.ServiceModel.ServiceAuthorizationManager.CheckAccess%2A> method returns `false`.</span></span> <span data-ttu-id="f5edd-106">受信メッセージが有効なユーザーから適切な保護を適用して送信されたものであり、その一方でそのユーザーが特定のタスクの実行を許可されていないことを示します。</span><span class="sxs-lookup"><span data-stu-id="f5edd-106">It indicates that the incoming message is from a valid user and protected properly, but the user is not authorized to do specific tasks.</span></span>
