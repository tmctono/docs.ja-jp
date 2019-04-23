---
title: IHostSyncManager インターフェイス
ms.date: 03/30/2017
api_name:
- IHostSyncManager
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostSyncManager
helpviewer_keywords:
- IHostSyncManager interface [.NET Framework hosting]
ms.assetid: 2e081a37-6a28-4c93-b7ab-1c96a464637c
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 200da8b87b52a29c2b075d1e06929031d3f588b7
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59174227"
---
# <a name="ihostsyncmanager-interface"></a><span data-ttu-id="5c529-102">IHostSyncManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="5c529-102">IHostSyncManager Interface</span></span>
<span data-ttu-id="5c529-103">共通言語ランタイム (CLR) に同期の Win32 関数を使用する代わりに、ホストを呼び出すことによって同期プリミティブを作成できるようにするメソッドを提供します。</span><span class="sxs-lookup"><span data-stu-id="5c529-103">Provides methods that allow the common language runtime (CLR) to create synchronization primitives by calling the host instead of using the Win32 synchronization functions.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="5c529-104">メソッド</span><span class="sxs-lookup"><span data-stu-id="5c529-104">Methods</span></span>  
  
|<span data-ttu-id="5c529-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="5c529-105">Method</span></span>|<span data-ttu-id="5c529-106">説明</span><span class="sxs-lookup"><span data-stu-id="5c529-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="5c529-107">CreateAutoEvent メソッド</span><span class="sxs-lookup"><span data-stu-id="5c529-107">CreateAutoEvent Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-createautoevent-method.md)|<span data-ttu-id="5c529-108">自動リセット イベント オブジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="5c529-108">Creates an auto-reset event object.</span></span>|  
|[<span data-ttu-id="5c529-109">CreateCrst メソッド</span><span class="sxs-lookup"><span data-stu-id="5c529-109">CreateCrst Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-createcrst-method.md)|<span data-ttu-id="5c529-110">同期のためのクリティカル セクション オブジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="5c529-110">Creates a critical section object for synchronization.</span></span>|  
|[<span data-ttu-id="5c529-111">CreateCrstWithSpinCount メソッド</span><span class="sxs-lookup"><span data-stu-id="5c529-111">CreateCrstWithSpinCount Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-createcrstwithspincount-method.md)|<span data-ttu-id="5c529-112">同期のためのスピン カウントとクリティカル セクション オブジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="5c529-112">Creates a critical section object with spin count for synchronization.</span></span>|  
|[<span data-ttu-id="5c529-113">CreateManualEvent メソッド</span><span class="sxs-lookup"><span data-stu-id="5c529-113">CreateManualEvent Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-createmanualevent-method.md)|<span data-ttu-id="5c529-114">手動リセット イベント オブジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="5c529-114">Creates a manual-reset event object.</span></span>|  
|[<span data-ttu-id="5c529-115">CreateMonitorEvent メソッド</span><span class="sxs-lookup"><span data-stu-id="5c529-115">CreateMonitorEvent Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-createmonitorevent-method.md)|<span data-ttu-id="5c529-116">監視対象の自動リセット イベント オブジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="5c529-116">Creates a monitored auto-reset event object.</span></span>|  
|[<span data-ttu-id="5c529-117">CreateRWLockReaderEvent メソッド</span><span class="sxs-lookup"><span data-stu-id="5c529-117">CreateRWLockReaderEvent Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-createrwlockreaderevent-method.md)|<span data-ttu-id="5c529-118">リーダー ロックの実装のための手動リセット イベント オブジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="5c529-118">Creates a manual-reset event object for the implementation of a reader lock.</span></span>|  
|[<span data-ttu-id="5c529-119">CreateRWLockWriterEvent メソッド</span><span class="sxs-lookup"><span data-stu-id="5c529-119">CreateRWLockWriterEvent Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-createrwlockwriterevent-method.md)|<span data-ttu-id="5c529-120">ライター ロックの実装の自動リセット イベント オブジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="5c529-120">Creates an auto-reset event object for the implementation of a writer lock.</span></span>|  
|[<span data-ttu-id="5c529-121">CreateSemaphore メソッド</span><span class="sxs-lookup"><span data-stu-id="5c529-121">CreateSemaphore Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-createsemaphore-method.md)|<span data-ttu-id="5c529-122">作成、 [IHostSemaphore](../../../../docs/framework/unmanaged-api/hosting/ihostsemaphore-interface.md)待機イベントのセマフォとして使用する clr オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="5c529-122">Creates an [IHostSemaphore](../../../../docs/framework/unmanaged-api/hosting/ihostsemaphore-interface.md) object for the CLR to use as a semaphore for wait events.</span></span>|  
|[<span data-ttu-id="5c529-123">SetCLRSyncManager メソッド</span><span class="sxs-lookup"><span data-stu-id="5c529-123">SetCLRSyncManager Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-setclrsyncmanager-method.md)|<span data-ttu-id="5c529-124">セット、 [ICLRSyncManager](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)インスタンスに現在関連付ける`IHostSyncManager`インスタンス。</span><span class="sxs-lookup"><span data-stu-id="5c529-124">Sets the [ICLRSyncManager](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md) instance to associate with the current `IHostSyncManager` instance.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5c529-125">Remarks</span><span class="sxs-lookup"><span data-stu-id="5c529-125">Remarks</span></span>  
 <span data-ttu-id="5c529-126">CLR のホストの実装を検出する`IHostSyncManager`呼び出すことによって、 [ihostcontrol::gethostmanager](../../../../docs/framework/unmanaged-api/hosting/ihostcontrol-gethostmanager-method.md)メソッドを`IID`IID_IHostSyncManager の。</span><span class="sxs-lookup"><span data-stu-id="5c529-126">The CLR discovers the host's implementation of `IHostSyncManager` by calling the [IHostControl::GetHostManager](../../../../docs/framework/unmanaged-api/hosting/ihostcontrol-gethostmanager-method.md) method with an `IID` of IID_IHostSyncManager.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5c529-127">必要条件</span><span class="sxs-lookup"><span data-stu-id="5c529-127">Requirements</span></span>  
 <span data-ttu-id="5c529-128">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="5c529-128">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5c529-129">**ヘッダー:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="5c529-129">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="5c529-130">**ライブラリ:** MSCorEE.dll でリソースとして含まれます</span><span class="sxs-lookup"><span data-stu-id="5c529-130">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="5c529-131">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5c529-131">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5c529-132">関連項目</span><span class="sxs-lookup"><span data-stu-id="5c529-132">See also</span></span>

- [<span data-ttu-id="5c529-133">ICLRSyncManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="5c529-133">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)
- [<span data-ttu-id="5c529-134">ホスト インターフェイス</span><span class="sxs-lookup"><span data-stu-id="5c529-134">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
