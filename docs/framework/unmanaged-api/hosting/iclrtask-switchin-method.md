---
title: ICLRTask::SwitchIn メソッド
ms.date: 03/30/2017
api_name:
- ICLRTask.SwitchIn
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRTask::SwitchIn
helpviewer_keywords:
- ICLRTask::SwitchIn method [.NET Framework hosting]
- SwitchIn method [.NET Framework hosting]
ms.assetid: 3d37ce20-aa65-4043-8f13-7c728b5d8a52
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f408dd5e4d383040d9e3c03cd5bba8ebd320610f
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2019
ms.locfileid: "69938366"
---
# <a name="iclrtaskswitchin-method"></a><span data-ttu-id="7d109-102">ICLRTask::SwitchIn メソッド</span><span class="sxs-lookup"><span data-stu-id="7d109-102">ICLRTask::SwitchIn Method</span></span>
<span data-ttu-id="7d109-103">現在の[ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)インスタンスが表すタスクが操作可能な状態であることを、共通言語ランタイム (CLR) に通知します。</span><span class="sxs-lookup"><span data-stu-id="7d109-103">Notifies the common language runtime (CLR) that the task that the current [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) instance represents is now in an operable state.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7d109-104">構文</span><span class="sxs-lookup"><span data-stu-id="7d109-104">Syntax</span></span>  
  
```cpp  
HRESULT SwitchIn (  
    [in] HANDLE threadHandle  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7d109-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="7d109-105">Parameters</span></span>  
 `threadHandle`  
 <span data-ttu-id="7d109-106">から現在`ICLRTask`のインスタンスによって表されるタスクが実行されている物理スレッドへのハンドル。</span><span class="sxs-lookup"><span data-stu-id="7d109-106">[in] A handle to the physical thread on which the task represented by the current `ICLRTask` instance is executing.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="7d109-107">戻り値</span><span class="sxs-lookup"><span data-stu-id="7d109-107">Return Value</span></span>  
  
|<span data-ttu-id="7d109-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="7d109-108">HRESULT</span></span>|<span data-ttu-id="7d109-109">説明</span><span class="sxs-lookup"><span data-stu-id="7d109-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="7d109-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="7d109-110">S_OK</span></span>|<span data-ttu-id="7d109-111">`SwitchIn`正常に返されました。</span><span class="sxs-lookup"><span data-stu-id="7d109-111">`SwitchIn` returned successfully.</span></span>|  
|<span data-ttu-id="7d109-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="7d109-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="7d109-113">CLR がプロセスに読み込まれていないか、CLR がマネージドコードを実行できない状態であるか、または呼び出しが正常に処理されていません。</span><span class="sxs-lookup"><span data-stu-id="7d109-113">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="7d109-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="7d109-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="7d109-115">呼び出しがタイムアウトしました。</span><span class="sxs-lookup"><span data-stu-id="7d109-115">The call timed out.</span></span>|  
|<span data-ttu-id="7d109-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="7d109-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="7d109-117">呼び出し元がロックを所有していません。</span><span class="sxs-lookup"><span data-stu-id="7d109-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="7d109-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="7d109-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="7d109-119">ブロックされたスレッドまたはファイバーが待機しているときに、イベントが取り消されました。</span><span class="sxs-lookup"><span data-stu-id="7d109-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="7d109-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="7d109-120">E_FAIL</span></span>|<span data-ttu-id="7d109-121">原因不明の致命的なエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="7d109-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="7d109-122">メソッドから E_FAIL が返された場合、そのプロセス内で CLR は使用できなくなります。</span><span class="sxs-lookup"><span data-stu-id="7d109-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="7d109-123">後続のホストメソッドの呼び出しでは、HOST_E_CLRNOTAVAILABLE が返されます。</span><span class="sxs-lookup"><span data-stu-id="7d109-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="7d109-124">HOST_E_INVALIDOPERATION</span><span class="sxs-lookup"><span data-stu-id="7d109-124">HOST_E_INVALIDOPERATION</span></span>|<span data-ttu-id="7d109-125">`SwitchIn`は、以前の[Switchout メソッド](../../../../docs/framework/unmanaged-api/hosting/iclrtask-switchout-method.md)の呼び出しなしで呼び出されました。</span><span class="sxs-lookup"><span data-stu-id="7d109-125">`SwitchIn` was called without an earlier call to [SwitchOut Method](../../../../docs/framework/unmanaged-api/hosting/iclrtask-switchout-method.md).</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7d109-126">Remarks</span><span class="sxs-lookup"><span data-stu-id="7d109-126">Remarks</span></span>  
 <span data-ttu-id="7d109-127">パラメーター `threadHandle`は、現在`ICLRTask`のインスタンスによって表されるタスクがスケジュールされているオペレーティングシステムスレッドへのハンドルを表します。</span><span class="sxs-lookup"><span data-stu-id="7d109-127">The `threadHandle` parameter represents a handle to the operating system thread on which the task represented by the current `ICLRTask` instance has been scheduled.</span></span> <span data-ttu-id="7d109-128">このスレッドで偽装が発生した場合は、タスクを切り替える前に[IHostSecurityManager:: RevertToSelf](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-reverttoself-method.md)を呼び出す必要があります。</span><span class="sxs-lookup"><span data-stu-id="7d109-128">If impersonation has occurred on this thread, you must call [IHostSecurityManager::RevertToSelf](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-reverttoself-method.md) before switching in the task.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="7d109-129">`SwitchIn` を`SwitchOut`呼び出していないを呼び出すと、が HRESULT 値 HOST_E_INVALIDOPERATION で失敗します。</span><span class="sxs-lookup"><span data-stu-id="7d109-129">A call to `SwitchIn` without an earlier call to `SwitchOut` fails with an HRESULT value of HOST_E_INVALIDOPERATION.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7d109-130">必要条件</span><span class="sxs-lookup"><span data-stu-id="7d109-130">Requirements</span></span>  
 <span data-ttu-id="7d109-131">**・** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="7d109-131">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7d109-132">**ヘッダー:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="7d109-132">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="7d109-133">**ライブラリ**Mscoree.dll にリソースとして含まれています</span><span class="sxs-lookup"><span data-stu-id="7d109-133">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="7d109-134">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7d109-134">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7d109-135">関連項目</span><span class="sxs-lookup"><span data-stu-id="7d109-135">See also</span></span>

- [<span data-ttu-id="7d109-136">ICLRTask インターフェイス</span><span class="sxs-lookup"><span data-stu-id="7d109-136">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [<span data-ttu-id="7d109-137">ICLRTaskManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="7d109-137">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [<span data-ttu-id="7d109-138">IHostTask インターフェイス</span><span class="sxs-lookup"><span data-stu-id="7d109-138">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [<span data-ttu-id="7d109-139">IHostTaskManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="7d109-139">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
