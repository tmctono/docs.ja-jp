---
title: IHostTaskManager::Sleep メソッド
ms.date: 03/30/2017
api_name:
- IHostTaskManager.Sleep
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostTaskManager::Sleep
helpviewer_keywords:
- IHostTaskManager::Sleep method [.NET Framework hosting]
- Sleep method, IHostTaskManager interface [.NET Framework hosting]
ms.assetid: f67d25f3-9199-4c5f-b1e8-1c819243cfd5
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 4618f7ea08aa304ff5e77800cf3c0a90dd88fdbd
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59110918"
---
# <a name="ihosttaskmanagersleep-method"></a><span data-ttu-id="e0795-102">IHostTaskManager::Sleep メソッド</span><span class="sxs-lookup"><span data-stu-id="e0795-102">IHostTaskManager::Sleep Method</span></span>
<span data-ttu-id="e0795-103">現在のタスクがスリープ状態になることをホストに通知します。</span><span class="sxs-lookup"><span data-stu-id="e0795-103">Notifies the host that the current task is going to sleep.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e0795-104">構文</span><span class="sxs-lookup"><span data-stu-id="e0795-104">Syntax</span></span>  
  
```  
HRESULT Sleep (  
    [in] DWORD dwMilliseconds,  
    [in] DWORD option  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e0795-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="e0795-105">Parameters</span></span>  
 `dwMilliseconds`  
 <span data-ttu-id="e0795-106">[in]スレッドがスリープ状態をミリ秒単位で時間間隔。</span><span class="sxs-lookup"><span data-stu-id="e0795-106">[in] The time interval, in milliseconds, that the thread will sleep.</span></span>  
  
 `option`  
 <span data-ttu-id="e0795-107">[in]1 つ、 [WAIT_OPTION](../../../../docs/framework/unmanaged-api/hosting/wait-option-enumeration.md)ホストが実行する場合は、このアクションを示す列挙値は、アクション ブロックします。</span><span class="sxs-lookup"><span data-stu-id="e0795-107">[in] One of the [WAIT_OPTION](../../../../docs/framework/unmanaged-api/hosting/wait-option-enumeration.md) enumeration values, indicating what action the host should take if this action blocks.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="e0795-108">戻り値</span><span class="sxs-lookup"><span data-stu-id="e0795-108">Return Value</span></span>  
  
|<span data-ttu-id="e0795-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="e0795-109">HRESULT</span></span>|<span data-ttu-id="e0795-110">説明</span><span class="sxs-lookup"><span data-stu-id="e0795-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="e0795-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="e0795-111">S_OK</span></span>|<span data-ttu-id="e0795-112">`Sleep` 正常に返されます。</span><span class="sxs-lookup"><span data-stu-id="e0795-112">`Sleep` returned successfully.</span></span>|  
|<span data-ttu-id="e0795-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="e0795-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="e0795-114">共通言語ランタイム (CLR) は、プロセスに読み込まれていないか、CLR は状態をマネージ コードを実行または呼び出しを正常に処理ができません。</span><span class="sxs-lookup"><span data-stu-id="e0795-114">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="e0795-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="e0795-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="e0795-116">呼び出しがタイムアウトになりました。</span><span class="sxs-lookup"><span data-stu-id="e0795-116">The call timed out.</span></span>|  
|<span data-ttu-id="e0795-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="e0795-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="e0795-118">呼び出し元がロックを所有していません。</span><span class="sxs-lookup"><span data-stu-id="e0795-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="e0795-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="e0795-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="e0795-120">イベントがキャンセルされましたブロックされたスレッドまたはファイバーが待機しています。</span><span class="sxs-lookup"><span data-stu-id="e0795-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="e0795-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="e0795-121">E_FAIL</span></span>|<span data-ttu-id="e0795-122">不明な致命的なエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="e0795-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="e0795-123">メソッドには、E_FAIL が返される、ときに、CLR は、プロセス内で使用可能ではなくなりました。</span><span class="sxs-lookup"><span data-stu-id="e0795-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="e0795-124">メソッドをホストする後続の呼び出しには、HOST_E_CLRNOTAVAILABLE が返されます。</span><span class="sxs-lookup"><span data-stu-id="e0795-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e0795-125">Remarks</span><span class="sxs-lookup"><span data-stu-id="e0795-125">Remarks</span></span>  
 <span data-ttu-id="e0795-126">CLR は通常、呼び出し`IHostTaskManager::Sleep`とき<xref:System.Threading.Thread.Sleep%2A?displayProperty=nameWithType>ユーザー コードから呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="e0795-126">The CLR typically calls `IHostTaskManager::Sleep` when <xref:System.Threading.Thread.Sleep%2A?displayProperty=nameWithType> is called from user code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e0795-127">必要条件</span><span class="sxs-lookup"><span data-stu-id="e0795-127">Requirements</span></span>  
 <span data-ttu-id="e0795-128">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="e0795-128">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e0795-129">**ヘッダー:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="e0795-129">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="e0795-130">**ライブラリ:** MSCorEE.dll でリソースとして含まれます</span><span class="sxs-lookup"><span data-stu-id="e0795-130">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="e0795-131">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e0795-131">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e0795-132">関連項目</span><span class="sxs-lookup"><span data-stu-id="e0795-132">See also</span></span>

- [<span data-ttu-id="e0795-133">ICLRTask インターフェイス</span><span class="sxs-lookup"><span data-stu-id="e0795-133">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [<span data-ttu-id="e0795-134">ICLRTaskManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="e0795-134">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [<span data-ttu-id="e0795-135">IHostTask インターフェイス</span><span class="sxs-lookup"><span data-stu-id="e0795-135">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [<span data-ttu-id="e0795-136">IHostTaskManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="e0795-136">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
