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
ms.openlocfilehash: 8eba189d6dfca3781c28631a72a9af3c037efeda
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73136793"
---
# <a name="ihostmanualevent-interface"></a><span data-ttu-id="117bd-102">IHostManualEvent インターフェイス</span><span class="sxs-lookup"><span data-stu-id="117bd-102">IHostManualEvent Interface</span></span>
<span data-ttu-id="117bd-103">手動リセットイベントの表現のホストの実装を提供します。</span><span class="sxs-lookup"><span data-stu-id="117bd-103">Provides the host's implementation of a representation of a manual reset event.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="117bd-104">メソッド</span><span class="sxs-lookup"><span data-stu-id="117bd-104">Methods</span></span>  
  
|<span data-ttu-id="117bd-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="117bd-105">Method</span></span>|<span data-ttu-id="117bd-106">説明</span><span class="sxs-lookup"><span data-stu-id="117bd-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="117bd-107">Reset メソッド</span><span class="sxs-lookup"><span data-stu-id="117bd-107">Reset Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-reset-method.md)|<span data-ttu-id="117bd-108">現在の `IHostManualEvent` インスタンスを非シグナル状態にリセットします。</span><span class="sxs-lookup"><span data-stu-id="117bd-108">Resets the current `IHostManualEvent` instance to a non-signaled state.</span></span>|  
|[<span data-ttu-id="117bd-109">Set メソッド</span><span class="sxs-lookup"><span data-stu-id="117bd-109">Set Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-set-method.md)|<span data-ttu-id="117bd-110">現在の `IHostManualEvent` インスタンスをシグナル状態に設定します。</span><span class="sxs-lookup"><span data-stu-id="117bd-110">Sets the current `IHostManualEvent` instance to a signaled state.</span></span>|  
|[<span data-ttu-id="117bd-111">Wait メソッド</span><span class="sxs-lookup"><span data-stu-id="117bd-111">Wait Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-wait-method.md)|<span data-ttu-id="117bd-112">現在の `IHostManualEvent` インスタンスが所有されるか、指定された時間が経過するまで待機するようにします。</span><span class="sxs-lookup"><span data-stu-id="117bd-112">Causes the current `IHostManualEvent` instance to wait until it is owned, or a specified amount of time elapses.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="117bd-113">［要件］</span><span class="sxs-lookup"><span data-stu-id="117bd-113">Requirements</span></span>  
 <span data-ttu-id="117bd-114">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="117bd-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="117bd-115">**ヘッダー:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="117bd-115">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="117bd-116">**ライブラリ:** Mscoree.dll にリソースとして含まれています</span><span class="sxs-lookup"><span data-stu-id="117bd-116">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="117bd-117">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="117bd-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="117bd-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="117bd-118">See also</span></span>

- [<span data-ttu-id="117bd-119">ICLRSyncManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="117bd-119">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)
- [<span data-ttu-id="117bd-120">IHostAutoEvent インターフェイス</span><span class="sxs-lookup"><span data-stu-id="117bd-120">IHostAutoEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostautoevent-interface.md)
- [<span data-ttu-id="117bd-121">IHostSemaphore インターフェイス</span><span class="sxs-lookup"><span data-stu-id="117bd-121">IHostSemaphore Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsemaphore-interface.md)
- [<span data-ttu-id="117bd-122">IHostSyncManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="117bd-122">IHostSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)
- [<span data-ttu-id="117bd-123">ホスト インターフェイス</span><span class="sxs-lookup"><span data-stu-id="117bd-123">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
