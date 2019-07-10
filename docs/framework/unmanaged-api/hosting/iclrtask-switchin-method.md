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
ms.openlocfilehash: ccc08ae210dd02bc71a1d83bc81525a7308c20e1
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67770390"
---
# <a name="iclrtaskswitchin-method"></a><span data-ttu-id="3b751-102">ICLRTask::SwitchIn メソッド</span><span class="sxs-lookup"><span data-stu-id="3b751-102">ICLRTask::SwitchIn Method</span></span>
<span data-ttu-id="3b751-103">共通言語ランタイム (CLR) に通知するタスクを現在[ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)インスタンスを表しますが、可能な状態でします。</span><span class="sxs-lookup"><span data-stu-id="3b751-103">Notifies the common language runtime (CLR) that the task that the current [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) instance represents is now in an operable state.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3b751-104">構文</span><span class="sxs-lookup"><span data-stu-id="3b751-104">Syntax</span></span>  
  
```cpp  
HRESULT SwitchIn (  
    [in] HANDLE threadHandle  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3b751-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="3b751-105">Parameters</span></span>  
 `threadHandle`  
 <span data-ttu-id="3b751-106">[in]タスクが現在によって表される物理スレッドを識別するハンドル`ICLRTask`インスタンスを実行します。</span><span class="sxs-lookup"><span data-stu-id="3b751-106">[in] A handle to the physical thread on which the task represented by the current `ICLRTask` instance is executing.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="3b751-107">戻り値</span><span class="sxs-lookup"><span data-stu-id="3b751-107">Return Value</span></span>  
  
|<span data-ttu-id="3b751-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="3b751-108">HRESULT</span></span>|<span data-ttu-id="3b751-109">説明</span><span class="sxs-lookup"><span data-stu-id="3b751-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="3b751-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="3b751-110">S_OK</span></span>|<span data-ttu-id="3b751-111">`SwitchIn` 正常に返されます。</span><span class="sxs-lookup"><span data-stu-id="3b751-111">`SwitchIn` returned successfully.</span></span>|  
|<span data-ttu-id="3b751-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="3b751-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="3b751-113">プロセスに CLR が読み込まれていないか、CLR は状態をマネージ コードを実行または呼び出しを正常に処理ができません。</span><span class="sxs-lookup"><span data-stu-id="3b751-113">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="3b751-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="3b751-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="3b751-115">呼び出しがタイムアウトになりました。</span><span class="sxs-lookup"><span data-stu-id="3b751-115">The call timed out.</span></span>|  
|<span data-ttu-id="3b751-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="3b751-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="3b751-117">呼び出し元がロックを所有していません。</span><span class="sxs-lookup"><span data-stu-id="3b751-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="3b751-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="3b751-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="3b751-119">イベントがキャンセルされましたブロックされたスレッドまたはファイバーが待機しています。</span><span class="sxs-lookup"><span data-stu-id="3b751-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="3b751-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="3b751-120">E_FAIL</span></span>|<span data-ttu-id="3b751-121">不明な致命的なエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="3b751-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="3b751-122">メソッドには、E_FAIL が返される、ときに、CLR は、プロセス内で使用可能ではなくなりました。</span><span class="sxs-lookup"><span data-stu-id="3b751-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="3b751-123">メソッドをホストする後続の呼び出しには、HOST_E_CLRNOTAVAILABLE が返されます。</span><span class="sxs-lookup"><span data-stu-id="3b751-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="3b751-124">HOST_E_INVALIDOPERATION</span><span class="sxs-lookup"><span data-stu-id="3b751-124">HOST_E_INVALIDOPERATION</span></span>|<span data-ttu-id="3b751-125">`SwitchIn` 事前に呼び出したなしで呼び出されました[SwitchOut メソッド](../../../../docs/framework/unmanaged-api/hosting/iclrtask-switchout-method.md)します。</span><span class="sxs-lookup"><span data-stu-id="3b751-125">`SwitchIn` was called without an earlier call to [SwitchOut Method](../../../../docs/framework/unmanaged-api/hosting/iclrtask-switchout-method.md).</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3b751-126">Remarks</span><span class="sxs-lookup"><span data-stu-id="3b751-126">Remarks</span></span>  
 <span data-ttu-id="3b751-127">`threadHandle`パラメーターには、タスクが現在によって表されるオペレーティング システム スレッド ハンドルを表します`ICLRTask`インスタンスがスケジュールされています。</span><span class="sxs-lookup"><span data-stu-id="3b751-127">The `threadHandle` parameter represents a handle to the operating system thread on which the task represented by the current `ICLRTask` instance has been scheduled.</span></span> <span data-ttu-id="3b751-128">呼び出す必要がある場合、このスレッドでは、権限借用が発生しました、 [ihostsecuritymanager::reverttoself](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-reverttoself-method.md)タスクに切り替える前にします。</span><span class="sxs-lookup"><span data-stu-id="3b751-128">If impersonation has occurred on this thread, you must call [IHostSecurityManager::RevertToSelf](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-reverttoself-method.md) before switching in the task.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="3b751-129">呼び出し`SwitchIn`を以前の呼び出しがない`SwitchOut`HOST_E_INVALIDOPERATION の HRESULT 値で失敗します。</span><span class="sxs-lookup"><span data-stu-id="3b751-129">A call to `SwitchIn` without an earlier call to `SwitchOut` fails with an HRESULT value of HOST_E_INVALIDOPERATION.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3b751-130">必要条件</span><span class="sxs-lookup"><span data-stu-id="3b751-130">Requirements</span></span>  
 <span data-ttu-id="3b751-131">**プラットフォーム:** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="3b751-131">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3b751-132">**ヘッダー:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="3b751-132">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="3b751-133">**ライブラリ:** MSCorEE.dll でリソースとして含まれます</span><span class="sxs-lookup"><span data-stu-id="3b751-133">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="3b751-134">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3b751-134">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3b751-135">関連項目</span><span class="sxs-lookup"><span data-stu-id="3b751-135">See also</span></span>

- [<span data-ttu-id="3b751-136">ICLRTask インターフェイス</span><span class="sxs-lookup"><span data-stu-id="3b751-136">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [<span data-ttu-id="3b751-137">ICLRTaskManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="3b751-137">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [<span data-ttu-id="3b751-138">IHostTask インターフェイス</span><span class="sxs-lookup"><span data-stu-id="3b751-138">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [<span data-ttu-id="3b751-139">IHostTaskManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="3b751-139">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
