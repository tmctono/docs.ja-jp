---
title: IHostSemaphore インターフェイス
ms.date: 03/30/2017
api_name:
- IHostSemaphore
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostSemaphore
helpviewer_keywords:
- IHostSemaphore interface [.NET Framework hosting]
ms.assetid: c0765321-656c-441e-bab5-58176292be1e
topic_type:
- apiref
ms.openlocfilehash: 2cf490bcd167b7a498ae21f479f616694ccb5521
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73139484"
---
# <a name="ihostsemaphore-interface"></a><span data-ttu-id="0ef43-102">IHostSemaphore インターフェイス</span><span class="sxs-lookup"><span data-stu-id="0ef43-102">IHostSemaphore Interface</span></span>
<span data-ttu-id="0ef43-103">スレッド処理のためのセマフォのホストの実装を表します。</span><span class="sxs-lookup"><span data-stu-id="0ef43-103">Represents the host's implementation of a semaphore for threading.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="0ef43-104">メソッド</span><span class="sxs-lookup"><span data-stu-id="0ef43-104">Methods</span></span>  
  
|<span data-ttu-id="0ef43-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="0ef43-105">Method</span></span>|<span data-ttu-id="0ef43-106">説明</span><span class="sxs-lookup"><span data-stu-id="0ef43-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="0ef43-107">ReleaseSemaphore メソッド</span><span class="sxs-lookup"><span data-stu-id="0ef43-107">ReleaseSemaphore Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsemaphore-releasesemaphore-method.md)|<span data-ttu-id="0ef43-108">現在の `IHostSemaphore` インスタンスのカウントを、指定した量だけ増やします。</span><span class="sxs-lookup"><span data-stu-id="0ef43-108">Increases the count of the current `IHostSemaphore` instance by the specified amount.</span></span>|  
|[<span data-ttu-id="0ef43-109">Wait メソッド</span><span class="sxs-lookup"><span data-stu-id="0ef43-109">Wait Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsemaphore-wait-method.md)|<span data-ttu-id="0ef43-110">現在の `IHostSemaphore` インスタンスが所有されるか、指定された時間が経過するまで待機するようにします。</span><span class="sxs-lookup"><span data-stu-id="0ef43-110">Causes the current `IHostSemaphore` instance to wait until it is owned or the specified amount of time elapses.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="0ef43-111">［要件］</span><span class="sxs-lookup"><span data-stu-id="0ef43-111">Requirements</span></span>  
 <span data-ttu-id="0ef43-112">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0ef43-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0ef43-113">**ヘッダー:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="0ef43-113">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="0ef43-114">**ライブラリ:** Mscoree.dll にリソースとして含まれています</span><span class="sxs-lookup"><span data-stu-id="0ef43-114">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="0ef43-115">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0ef43-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0ef43-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="0ef43-116">See also</span></span>

- [<span data-ttu-id="0ef43-117">ICLRSyncManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="0ef43-117">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)
- [<span data-ttu-id="0ef43-118">IHostAutoEvent インターフェイス</span><span class="sxs-lookup"><span data-stu-id="0ef43-118">IHostAutoEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostautoevent-interface.md)
- [<span data-ttu-id="0ef43-119">IHostManualEvent インターフェイス</span><span class="sxs-lookup"><span data-stu-id="0ef43-119">IHostManualEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-interface.md)
- [<span data-ttu-id="0ef43-120">IHostSyncManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="0ef43-120">IHostSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)
- [<span data-ttu-id="0ef43-121">ホスト インターフェイス</span><span class="sxs-lookup"><span data-stu-id="0ef43-121">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
