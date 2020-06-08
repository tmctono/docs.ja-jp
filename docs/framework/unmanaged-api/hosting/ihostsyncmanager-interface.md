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
ms.openlocfilehash: fd3c941d89fbd93f30fc1af235f6310b23758973
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/08/2020
ms.locfileid: "84501457"
---
# <a name="ihostsyncmanager-interface"></a><span data-ttu-id="db342-102">IHostSyncManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="db342-102">IHostSyncManager Interface</span></span>
<span data-ttu-id="db342-103">Win32 同期関数を使用する代わりに、共通言語ランタイム (CLR) がホストを呼び出して同期プリミティブを作成できるようにするメソッドを提供します。</span><span class="sxs-lookup"><span data-stu-id="db342-103">Provides methods that allow the common language runtime (CLR) to create synchronization primitives by calling the host instead of using the Win32 synchronization functions.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="db342-104">メソッド</span><span class="sxs-lookup"><span data-stu-id="db342-104">Methods</span></span>  
  
|<span data-ttu-id="db342-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="db342-105">Method</span></span>|<span data-ttu-id="db342-106">説明</span><span class="sxs-lookup"><span data-stu-id="db342-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="db342-107">CreateAutoEvent メソッド</span><span class="sxs-lookup"><span data-stu-id="db342-107">CreateAutoEvent Method</span></span>](ihostsyncmanager-createautoevent-method.md)|<span data-ttu-id="db342-108">自動リセットイベントオブジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="db342-108">Creates an auto-reset event object.</span></span>|  
|[<span data-ttu-id="db342-109">CreateCrst メソッド</span><span class="sxs-lookup"><span data-stu-id="db342-109">CreateCrst Method</span></span>](ihostsyncmanager-createcrst-method.md)|<span data-ttu-id="db342-110">同期のための重要なセクションオブジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="db342-110">Creates a critical section object for synchronization.</span></span>|  
|[<span data-ttu-id="db342-111">CreateCrstWithSpinCount メソッド</span><span class="sxs-lookup"><span data-stu-id="db342-111">CreateCrstWithSpinCount Method</span></span>](ihostsyncmanager-createcrstwithspincount-method.md)|<span data-ttu-id="db342-112">同期のためにスピンカウントを持つクリティカルセクションオブジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="db342-112">Creates a critical section object with spin count for synchronization.</span></span>|  
|[<span data-ttu-id="db342-113">CreateManualEvent メソッド</span><span class="sxs-lookup"><span data-stu-id="db342-113">CreateManualEvent Method</span></span>](ihostsyncmanager-createmanualevent-method.md)|<span data-ttu-id="db342-114">手動リセットイベントオブジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="db342-114">Creates a manual-reset event object.</span></span>|  
|[<span data-ttu-id="db342-115">CreateMonitorEvent メソッド</span><span class="sxs-lookup"><span data-stu-id="db342-115">CreateMonitorEvent Method</span></span>](ihostsyncmanager-createmonitorevent-method.md)|<span data-ttu-id="db342-116">監視対象の自動リセットイベントオブジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="db342-116">Creates a monitored auto-reset event object.</span></span>|  
|[<span data-ttu-id="db342-117">CreateRWLockReaderEvent メソッド</span><span class="sxs-lookup"><span data-stu-id="db342-117">CreateRWLockReaderEvent Method</span></span>](ihostsyncmanager-createrwlockreaderevent-method.md)|<span data-ttu-id="db342-118">リーダーロックの実装のための手動リセットイベントオブジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="db342-118">Creates a manual-reset event object for the implementation of a reader lock.</span></span>|  
|[<span data-ttu-id="db342-119">CreateRWLockWriterEvent メソッド</span><span class="sxs-lookup"><span data-stu-id="db342-119">CreateRWLockWriterEvent Method</span></span>](ihostsyncmanager-createrwlockwriterevent-method.md)|<span data-ttu-id="db342-120">ライターロックの実装用の自動リセットイベントオブジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="db342-120">Creates an auto-reset event object for the implementation of a writer lock.</span></span>|  
|[<span data-ttu-id="db342-121">CreateSemaphore メソッド</span><span class="sxs-lookup"><span data-stu-id="db342-121">CreateSemaphore Method</span></span>](ihostsyncmanager-createsemaphore-method.md)|<span data-ttu-id="db342-122">CLR が待機イベントのセマフォとして使用する[IHostSemaphore](ihostsemaphore-interface.md)オブジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="db342-122">Creates an [IHostSemaphore](ihostsemaphore-interface.md) object for the CLR to use as a semaphore for wait events.</span></span>|  
|[<span data-ttu-id="db342-123">SetCLRSyncManager メソッド</span><span class="sxs-lookup"><span data-stu-id="db342-123">SetCLRSyncManager Method</span></span>](ihostsyncmanager-setclrsyncmanager-method.md)|<span data-ttu-id="db342-124">現在のインスタンスに関連付ける[ICLRSyncManager](iclrsyncmanager-interface.md)インスタンスを設定 `IHostSyncManager` します。</span><span class="sxs-lookup"><span data-stu-id="db342-124">Sets the [ICLRSyncManager](iclrsyncmanager-interface.md) instance to associate with the current `IHostSyncManager` instance.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="db342-125">解説</span><span class="sxs-lookup"><span data-stu-id="db342-125">Remarks</span></span>  
 <span data-ttu-id="db342-126">CLR は、 `IHostSyncManager` IID_IHostSyncManager のを使用して[IHostControl:: GetHostManager](ihostcontrol-gethostmanager-method.md)メソッドを呼び出すことで、ホストのの実装を検出し `IID` ます。</span><span class="sxs-lookup"><span data-stu-id="db342-126">The CLR discovers the host's implementation of `IHostSyncManager` by calling the [IHostControl::GetHostManager](ihostcontrol-gethostmanager-method.md) method with an `IID` of IID_IHostSyncManager.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="db342-127">要件</span><span class="sxs-lookup"><span data-stu-id="db342-127">Requirements</span></span>  
 <span data-ttu-id="db342-128">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="db342-128">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="db342-129">**ヘッダー:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="db342-129">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="db342-130">**ライブラリ:** Mscoree.dll にリソースとして含まれています</span><span class="sxs-lookup"><span data-stu-id="db342-130">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="db342-131">**.NET Framework のバージョン:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="db342-131">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="db342-132">関連項目</span><span class="sxs-lookup"><span data-stu-id="db342-132">See also</span></span>

- [<span data-ttu-id="db342-133">ICLRSyncManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="db342-133">ICLRSyncManager Interface</span></span>](iclrsyncmanager-interface.md)
- [<span data-ttu-id="db342-134">ホスト インターフェイス</span><span class="sxs-lookup"><span data-stu-id="db342-134">Hosting Interfaces</span></span>](hosting-interfaces.md)
