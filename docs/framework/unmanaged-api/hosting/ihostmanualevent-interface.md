---
title: IHostManualEvent インターフェイス
ms.date: 03/30/2017
api_name:
- IHostManualEvent
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostManualEvent
helpviewer_keywords:
- IHostManualEvent interface [.NET Framework hosting]
ms.assetid: 300c2661-b7d1-4c39-b080-9ebdef0fd523
topic_type:
- apiref
ms.openlocfilehash: 7c46f00063cdf9281a5f1080594e8d6dbc6c101e
ms.sourcegitcommit: d223616e7e6fe2139079052e6fcbe25413fb9900
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/22/2020
ms.locfileid: "83804593"
---
# <a name="ihostmanualevent-interface"></a><span data-ttu-id="28631-102">IHostManualEvent インターフェイス</span><span class="sxs-lookup"><span data-stu-id="28631-102">IHostManualEvent Interface</span></span>
<span data-ttu-id="28631-103">手動リセットイベントの表現のホストの実装を提供します。</span><span class="sxs-lookup"><span data-stu-id="28631-103">Provides the host's implementation of a representation of a manual reset event.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="28631-104">メソッド</span><span class="sxs-lookup"><span data-stu-id="28631-104">Methods</span></span>  
  
|<span data-ttu-id="28631-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="28631-105">Method</span></span>|<span data-ttu-id="28631-106">説明</span><span class="sxs-lookup"><span data-stu-id="28631-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="28631-107">Reset メソッド</span><span class="sxs-lookup"><span data-stu-id="28631-107">Reset Method</span></span>](ihostmanualevent-reset-method.md)|<span data-ttu-id="28631-108">現在の `IHostManualEvent` インスタンスをシグナル状態以外の状態にリセットします。</span><span class="sxs-lookup"><span data-stu-id="28631-108">Resets the current `IHostManualEvent` instance to a non-signaled state.</span></span>|  
|[<span data-ttu-id="28631-109">Set メソッド</span><span class="sxs-lookup"><span data-stu-id="28631-109">Set Method</span></span>](ihostmanualevent-set-method.md)|<span data-ttu-id="28631-110">現在の `IHostManualEvent` インスタンスをシグナル状態に設定します。</span><span class="sxs-lookup"><span data-stu-id="28631-110">Sets the current `IHostManualEvent` instance to a signaled state.</span></span>|  
|[<span data-ttu-id="28631-111">Wait メソッド</span><span class="sxs-lookup"><span data-stu-id="28631-111">Wait Method</span></span>](ihostmanualevent-wait-method.md)|<span data-ttu-id="28631-112">現在の `IHostManualEvent` インスタンスが所有されるか、指定された時間が経過するまで待機するようにします。</span><span class="sxs-lookup"><span data-stu-id="28631-112">Causes the current `IHostManualEvent` instance to wait until it is owned, or a specified amount of time elapses.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="28631-113">要件</span><span class="sxs-lookup"><span data-stu-id="28631-113">Requirements</span></span>  
 <span data-ttu-id="28631-114">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="28631-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="28631-115">**ヘッダー:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="28631-115">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="28631-116">**ライブラリ:** Mscoree.dll にリソースとして含まれています</span><span class="sxs-lookup"><span data-stu-id="28631-116">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="28631-117">**.NET Framework のバージョン:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="28631-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="28631-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="28631-118">See also</span></span>

- [<span data-ttu-id="28631-119">ICLRSyncManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="28631-119">ICLRSyncManager Interface</span></span>](iclrsyncmanager-interface.md)
- [<span data-ttu-id="28631-120">IHostAutoEvent インターフェイス</span><span class="sxs-lookup"><span data-stu-id="28631-120">IHostAutoEvent Interface</span></span>](ihostautoevent-interface.md)
- [<span data-ttu-id="28631-121">IHostSemaphore インターフェイス</span><span class="sxs-lookup"><span data-stu-id="28631-121">IHostSemaphore Interface</span></span>](ihostsemaphore-interface.md)
- [<span data-ttu-id="28631-122">IHostSyncManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="28631-122">IHostSyncManager Interface</span></span>](ihostsyncmanager-interface.md)
- [<span data-ttu-id="28631-123">ホスト インターフェイス</span><span class="sxs-lookup"><span data-stu-id="28631-123">Hosting Interfaces</span></span>](hosting-interfaces.md)
