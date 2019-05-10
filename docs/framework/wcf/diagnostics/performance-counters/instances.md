---
title: インスタンス
ms.date: 03/30/2017
ms.assetid: c8cf3460-0ca1-4411-8262-e9ecaf7f0a31
ms.openlocfilehash: e0be9c93b5efe17235dbccd426cdd73fbb739361
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/28/2019
ms.locfileid: "64651836"
---
# <a name="instances"></a><span data-ttu-id="4be4d-102">インスタンス</span><span class="sxs-lookup"><span data-stu-id="4be4d-102">Instances</span></span>
<span data-ttu-id="4be4d-103">カウンター名:インスタンス。</span><span class="sxs-lookup"><span data-stu-id="4be4d-103">Counter Name: Instances.</span></span>  
  
## <a name="description"></a><span data-ttu-id="4be4d-104">説明</span><span class="sxs-lookup"><span data-stu-id="4be4d-104">Description</span></span>  
 <span data-ttu-id="4be4d-105">現在サービスに含まれているインスタンス コンテキストの数。</span><span class="sxs-lookup"><span data-stu-id="4be4d-105">Number of instance contexts that the service currently contains.</span></span>  
  
 <span data-ttu-id="4be4d-106">多くの場合、インスタンス コンテキストの数とインスタンスの数は同じです。</span><span class="sxs-lookup"><span data-stu-id="4be4d-106">Most of the time, the number of instance contexts is identical to the number of instances.</span></span> <span data-ttu-id="4be4d-107">ただし、次のシナリオではこの規則は当てはまりません。</span><span class="sxs-lookup"><span data-stu-id="4be4d-107">However, the following scenarios are exception to this rule.</span></span>  
  
- <span data-ttu-id="4be4d-108">サービス メソッドが <xref:System.ServiceModel.Dispatcher.IInstanceProvider.ReleaseInstance%2A> メソッドを明示的に呼び出している場合。</span><span class="sxs-lookup"><span data-stu-id="4be4d-108">A service method calls the <xref:System.ServiceModel.Dispatcher.IInstanceProvider.ReleaseInstance%2A> method explicitly.</span></span>  
  
- <span data-ttu-id="4be4d-109"><xref:System.ServiceModel.ReleaseInstanceMode> が <xref:System.ServiceModel.OperationBehaviorAttribute> インスタンスに適用されている場合。</span><span class="sxs-lookup"><span data-stu-id="4be4d-109">A <xref:System.ServiceModel.ReleaseInstanceMode> is applied to an <xref:System.ServiceModel.OperationBehaviorAttribute> instance.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4be4d-110">関連項目</span><span class="sxs-lookup"><span data-stu-id="4be4d-110">See also</span></span>

- <xref:System.ServiceModel.OperationBehaviorAttribute>
