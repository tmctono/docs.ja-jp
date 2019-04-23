---
title: インスタンス
ms.date: 03/30/2017
ms.assetid: c8cf3460-0ca1-4411-8262-e9ecaf7f0a31
ms.openlocfilehash: 668cfb3026b9ab7259665f5e53873a512b1e2238
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/22/2019
ms.locfileid: "59975586"
---
# <a name="instances"></a><span data-ttu-id="14f9a-102">インスタンス</span><span class="sxs-lookup"><span data-stu-id="14f9a-102">Instances</span></span>
<span data-ttu-id="14f9a-103">カウンター名:インスタンス。</span><span class="sxs-lookup"><span data-stu-id="14f9a-103">Counter Name: Instances.</span></span>  
  
## <a name="description"></a><span data-ttu-id="14f9a-104">説明</span><span class="sxs-lookup"><span data-stu-id="14f9a-104">Description</span></span>  
 <span data-ttu-id="14f9a-105">現在サービスに含まれているインスタンス コンテキストの数。</span><span class="sxs-lookup"><span data-stu-id="14f9a-105">Number of instance contexts that the service currently contains.</span></span>  
  
 <span data-ttu-id="14f9a-106">多くの場合、インスタンス コンテキストの数とインスタンスの数は同じです。</span><span class="sxs-lookup"><span data-stu-id="14f9a-106">Most of the time, the number of instance contexts is identical to the number of instances.</span></span> <span data-ttu-id="14f9a-107">ただし、次のシナリオではこの規則は当てはまりません。</span><span class="sxs-lookup"><span data-stu-id="14f9a-107">However, the following scenarios are exception to this rule.</span></span>  
  
-   <span data-ttu-id="14f9a-108">サービス メソッドが <xref:System.ServiceModel.Dispatcher.IInstanceProvider.ReleaseInstance%2A> メソッドを明示的に呼び出している場合。</span><span class="sxs-lookup"><span data-stu-id="14f9a-108">A service method calls the <xref:System.ServiceModel.Dispatcher.IInstanceProvider.ReleaseInstance%2A> method explicitly.</span></span>  
  
-   <span data-ttu-id="14f9a-109"><xref:System.ServiceModel.ReleaseInstanceMode> が <xref:System.ServiceModel.OperationBehaviorAttribute> インスタンスに適用されている場合。</span><span class="sxs-lookup"><span data-stu-id="14f9a-109">A <xref:System.ServiceModel.ReleaseInstanceMode> is applied to an <xref:System.ServiceModel.OperationBehaviorAttribute> instance.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="14f9a-110">関連項目</span><span class="sxs-lookup"><span data-stu-id="14f9a-110">See also</span></span>

- <xref:System.ServiceModel.OperationBehaviorAttribute>
