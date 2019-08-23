---
title: IHostGCManager::SuspensionStarting メソッド
ms.date: 03/30/2017
api_name:
- IHostGCManager.SuspensionStarting
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostGCManager::SuspensionStarting
helpviewer_keywords:
- SuspensionStarting method, IHostGCManager interface [.NET Framework hosting]
- IHostGCManager::SuspensionStarting method [.NET Framework hosting]
ms.assetid: c381f524-94cf-4fa2-9298-50f847a03431
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e3e808c7ed03d7b4cc9dfe77389df6b2eff491f7
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2019
ms.locfileid: "69937721"
---
# <a name="ihostgcmanagersuspensionstarting-method"></a><span data-ttu-id="9cab0-102">IHostGCManager::SuspensionStarting メソッド</span><span class="sxs-lookup"><span data-stu-id="9cab0-102">IHostGCManager::SuspensionStarting Method</span></span>
<span data-ttu-id="9cab0-103">ガベージコレクションを実行するために、共通言語ランタイム (CLR) がタスクの実行を中断していることをホストに通知します。</span><span class="sxs-lookup"><span data-stu-id="9cab0-103">Notifies the host that the common language runtime (CLR) is suspending execution of tasks, to perform a garbage collection.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9cab0-104">構文</span><span class="sxs-lookup"><span data-stu-id="9cab0-104">Syntax</span></span>  
  
```cpp  
HRESULT SuspensionStarting ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="9cab0-105">戻り値</span><span class="sxs-lookup"><span data-stu-id="9cab0-105">Return Value</span></span>  
  
|<span data-ttu-id="9cab0-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="9cab0-106">HRESULT</span></span>|<span data-ttu-id="9cab0-107">説明</span><span class="sxs-lookup"><span data-stu-id="9cab0-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="9cab0-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="9cab0-108">S_OK</span></span>|<span data-ttu-id="9cab0-109">`SuspensionStarting`正常に返されました。</span><span class="sxs-lookup"><span data-stu-id="9cab0-109">`SuspensionStarting` returned successfully.</span></span>|  
|<span data-ttu-id="9cab0-110">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="9cab0-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="9cab0-111">CLR がプロセスに読み込まれていないか、CLR がマネージドコードを実行できない状態であるか、または呼び出しが正常に処理されていません。</span><span class="sxs-lookup"><span data-stu-id="9cab0-111">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="9cab0-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="9cab0-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="9cab0-113">呼び出しがタイムアウトしました。</span><span class="sxs-lookup"><span data-stu-id="9cab0-113">The call timed out.</span></span>|  
|<span data-ttu-id="9cab0-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="9cab0-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="9cab0-115">呼び出し元がロックを所有していません。</span><span class="sxs-lookup"><span data-stu-id="9cab0-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="9cab0-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="9cab0-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="9cab0-117">ブロックされたスレッドまたはファイバーが待機しているときに、イベントが取り消されました。</span><span class="sxs-lookup"><span data-stu-id="9cab0-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="9cab0-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="9cab0-118">E_FAIL</span></span>|<span data-ttu-id="9cab0-119">原因不明の致命的なエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="9cab0-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="9cab0-120">メソッドから E_FAIL が返された場合、そのプロセス内で CLR は使用できなくなります。</span><span class="sxs-lookup"><span data-stu-id="9cab0-120">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="9cab0-121">後続のホストメソッドの呼び出しでは、HOST_E_CLRNOTAVAILABLE が返されます。</span><span class="sxs-lookup"><span data-stu-id="9cab0-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9cab0-122">Remarks</span><span class="sxs-lookup"><span data-stu-id="9cab0-122">Remarks</span></span>  
 <span data-ttu-id="9cab0-123">CLR はを`SuspensionStarting`呼び出して、ガベージコレクションが発生していることをホストに通知します。</span><span class="sxs-lookup"><span data-stu-id="9cab0-123">The CLR calls `SuspensionStarting` to inform the host that garbage collection is occurring.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="9cab0-124">このタスクを再スケジュールしないでください。</span><span class="sxs-lookup"><span data-stu-id="9cab0-124">Do not reschedule this task.</span></span> <span data-ttu-id="9cab0-125">[ThreadIsBlockingForSuspension](../../../../docs/framework/unmanaged-api/hosting/ihostgcmanager-threadisblockingforsuspension-method.md)が呼び出されたときに、ホストはタスクを再スケジュールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="9cab0-125">The host must reschedule a task when [ThreadIsBlockingForSuspension](../../../../docs/framework/unmanaged-api/hosting/ihostgcmanager-threadisblockingforsuspension-method.md) is called.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9cab0-126">必要条件</span><span class="sxs-lookup"><span data-stu-id="9cab0-126">Requirements</span></span>  
 <span data-ttu-id="9cab0-127">**・** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="9cab0-127">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9cab0-128">**ヘッダー:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="9cab0-128">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="9cab0-129">**ライブラリ**Mscoree.dll にリソースとして含まれています</span><span class="sxs-lookup"><span data-stu-id="9cab0-129">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="9cab0-130">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9cab0-130">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9cab0-131">関連項目</span><span class="sxs-lookup"><span data-stu-id="9cab0-131">See also</span></span>

- [<span data-ttu-id="9cab0-132">ICLRTask インターフェイス</span><span class="sxs-lookup"><span data-stu-id="9cab0-132">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [<span data-ttu-id="9cab0-133">ICLRTaskManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="9cab0-133">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [<span data-ttu-id="9cab0-134">IHostTask インターフェイス</span><span class="sxs-lookup"><span data-stu-id="9cab0-134">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [<span data-ttu-id="9cab0-135">IHostTaskManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="9cab0-135">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
- [<span data-ttu-id="9cab0-136">IHostGCManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="9cab0-136">IHostGCManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostgcmanager-interface.md)
