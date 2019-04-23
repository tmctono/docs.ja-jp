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
ms.openlocfilehash: 5f36a963417aba082667bb9fb609e0d1dcad7b09
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59187679"
---
# <a name="iclrtaskswitchin-method"></a><span data-ttu-id="78a34-102">ICLRTask::SwitchIn メソッド</span><span class="sxs-lookup"><span data-stu-id="78a34-102">ICLRTask::SwitchIn Method</span></span>
<span data-ttu-id="78a34-103">共通言語ランタイム (CLR) に通知するタスクを現在[ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)インスタンスを表しますが、可能な状態でします。</span><span class="sxs-lookup"><span data-stu-id="78a34-103">Notifies the common language runtime (CLR) that the task that the current [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) instance represents is now in an operable state.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="78a34-104">構文</span><span class="sxs-lookup"><span data-stu-id="78a34-104">Syntax</span></span>  
  
```  
HRESULT SwitchIn (  
    [in] HANDLE threadHandle  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="78a34-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="78a34-105">Parameters</span></span>  
 `threadHandle`  
 <span data-ttu-id="78a34-106">[in]タスクが現在によって表される物理スレッドを識別するハンドル`ICLRTask`インスタンスを実行します。</span><span class="sxs-lookup"><span data-stu-id="78a34-106">[in] A handle to the physical thread on which the task represented by the current `ICLRTask` instance is executing.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="78a34-107">戻り値</span><span class="sxs-lookup"><span data-stu-id="78a34-107">Return Value</span></span>  
  
|<span data-ttu-id="78a34-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="78a34-108">HRESULT</span></span>|<span data-ttu-id="78a34-109">説明</span><span class="sxs-lookup"><span data-stu-id="78a34-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="78a34-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="78a34-110">S_OK</span></span>|<span data-ttu-id="78a34-111">`SwitchIn` 正常に返されます。</span><span class="sxs-lookup"><span data-stu-id="78a34-111">`SwitchIn` returned successfully.</span></span>|  
|<span data-ttu-id="78a34-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="78a34-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="78a34-113">プロセスに CLR が読み込まれていないか、CLR は状態をマネージ コードを実行または呼び出しを正常に処理ができません。</span><span class="sxs-lookup"><span data-stu-id="78a34-113">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="78a34-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="78a34-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="78a34-115">呼び出しがタイムアウトになりました。</span><span class="sxs-lookup"><span data-stu-id="78a34-115">The call timed out.</span></span>|  
|<span data-ttu-id="78a34-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="78a34-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="78a34-117">呼び出し元がロックを所有していません。</span><span class="sxs-lookup"><span data-stu-id="78a34-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="78a34-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="78a34-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="78a34-119">イベントがキャンセルされましたブロックされたスレッドまたはファイバーが待機しています。</span><span class="sxs-lookup"><span data-stu-id="78a34-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="78a34-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="78a34-120">E_FAIL</span></span>|<span data-ttu-id="78a34-121">不明な致命的なエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="78a34-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="78a34-122">メソッドには、E_FAIL が返される、ときに、CLR は、プロセス内で使用可能ではなくなりました。</span><span class="sxs-lookup"><span data-stu-id="78a34-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="78a34-123">メソッドをホストする後続の呼び出しには、HOST_E_CLRNOTAVAILABLE が返されます。</span><span class="sxs-lookup"><span data-stu-id="78a34-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="78a34-124">HOST_E_INVALIDOPERATION</span><span class="sxs-lookup"><span data-stu-id="78a34-124">HOST_E_INVALIDOPERATION</span></span>|<span data-ttu-id="78a34-125">`SwitchIn` 事前に呼び出したなしで呼び出されました[SwitchOut メソッド](../../../../docs/framework/unmanaged-api/hosting/iclrtask-switchout-method.md)します。</span><span class="sxs-lookup"><span data-stu-id="78a34-125">`SwitchIn` was called without an earlier call to [SwitchOut Method](../../../../docs/framework/unmanaged-api/hosting/iclrtask-switchout-method.md).</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="78a34-126">Remarks</span><span class="sxs-lookup"><span data-stu-id="78a34-126">Remarks</span></span>  
 <span data-ttu-id="78a34-127">`threadHandle`パラメーターには、タスクが現在によって表されるオペレーティング システム スレッド ハンドルを表します`ICLRTask`インスタンスがスケジュールされています。</span><span class="sxs-lookup"><span data-stu-id="78a34-127">The `threadHandle` parameter represents a handle to the operating system thread on which the task represented by the current `ICLRTask` instance has been scheduled.</span></span> <span data-ttu-id="78a34-128">呼び出す必要がある場合、このスレッドでは、権限借用が発生しました、 [ihostsecuritymanager::reverttoself](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-reverttoself-method.md)タスクに切り替える前にします。</span><span class="sxs-lookup"><span data-stu-id="78a34-128">If impersonation has occurred on this thread, you must call [IHostSecurityManager::RevertToSelf](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-reverttoself-method.md) before switching in the task.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="78a34-129">呼び出し`SwitchIn`を以前の呼び出しがない`SwitchOut`HOST_E_INVALIDOPERATION の HRESULT 値で失敗します。</span><span class="sxs-lookup"><span data-stu-id="78a34-129">A call to `SwitchIn` without an earlier call to `SwitchOut` fails with an HRESULT value of HOST_E_INVALIDOPERATION.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="78a34-130">必要条件</span><span class="sxs-lookup"><span data-stu-id="78a34-130">Requirements</span></span>  
 <span data-ttu-id="78a34-131">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="78a34-131">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="78a34-132">**ヘッダー:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="78a34-132">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="78a34-133">**ライブラリ:** MSCorEE.dll でリソースとして含まれます</span><span class="sxs-lookup"><span data-stu-id="78a34-133">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="78a34-134">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="78a34-134">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="78a34-135">関連項目</span><span class="sxs-lookup"><span data-stu-id="78a34-135">See also</span></span>

- [<span data-ttu-id="78a34-136">ICLRTask インターフェイス</span><span class="sxs-lookup"><span data-stu-id="78a34-136">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [<span data-ttu-id="78a34-137">ICLRTaskManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="78a34-137">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [<span data-ttu-id="78a34-138">IHostTask インターフェイス</span><span class="sxs-lookup"><span data-stu-id="78a34-138">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [<span data-ttu-id="78a34-139">IHostTaskManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="78a34-139">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
