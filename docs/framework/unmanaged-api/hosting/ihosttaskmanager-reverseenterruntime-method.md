---
title: IHostTaskManager::ReverseEnterRuntime メソッド
ms.date: 03/30/2017
api_name:
- IHostTaskManager.ReverseEnterRuntime
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostTaskManager::ReverseEnterRuntime
helpviewer_keywords:
- IHostTaskManager::ReverseEnterRuntime method [.NET Framework hosting]
- ReverseEnterRuntime method [.NET Framework hosting]
ms.assetid: b1e26bff-d3ea-436e-9867-29720df999f4
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 6eefdaf5dee423b0a9ae054446224a3ea97e3c9b
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61796683"
---
# <a name="ihosttaskmanagerreverseenterruntime-method"></a><span data-ttu-id="da07e-102">IHostTaskManager::ReverseEnterRuntime メソッド</span><span class="sxs-lookup"><span data-stu-id="da07e-102">IHostTaskManager::ReverseEnterRuntime Method</span></span>
<span data-ttu-id="da07e-103">アンマネージ コードから共通言語ランタイム (CLR) に呼び出しがされているホストに通知します。</span><span class="sxs-lookup"><span data-stu-id="da07e-103">Notifies the host that a call is being made into the common language runtime (CLR) from unmanaged code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="da07e-104">構文</span><span class="sxs-lookup"><span data-stu-id="da07e-104">Syntax</span></span>  
  
```  
HRESULT ReverseEnterRuntime ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="da07e-105">戻り値</span><span class="sxs-lookup"><span data-stu-id="da07e-105">Return Value</span></span>  
  
|<span data-ttu-id="da07e-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="da07e-106">HRESULT</span></span>|<span data-ttu-id="da07e-107">説明</span><span class="sxs-lookup"><span data-stu-id="da07e-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="da07e-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="da07e-108">S_OK</span></span>|<span data-ttu-id="da07e-109">`ReverseEnterRuntime` 正常に返されます。</span><span class="sxs-lookup"><span data-stu-id="da07e-109">`ReverseEnterRuntime` returned successfully.</span></span>|  
|<span data-ttu-id="da07e-110">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="da07e-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="da07e-111">プロセスに CLR が読み込まれていないか、CLR は状態をマネージ コードを実行または呼び出しを正常に処理ができません。</span><span class="sxs-lookup"><span data-stu-id="da07e-111">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="da07e-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="da07e-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="da07e-113">呼び出しがタイムアウトになりました。</span><span class="sxs-lookup"><span data-stu-id="da07e-113">The call timed out.</span></span>|  
|<span data-ttu-id="da07e-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="da07e-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="da07e-115">呼び出し元がロックを所有していません。</span><span class="sxs-lookup"><span data-stu-id="da07e-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="da07e-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="da07e-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="da07e-117">イベントがキャンセルされましたブロックされたスレッドまたはファイバーが待機しています。</span><span class="sxs-lookup"><span data-stu-id="da07e-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="da07e-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="da07e-118">E_FAIL</span></span>|<span data-ttu-id="da07e-119">不明な致命的なエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="da07e-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="da07e-120">メソッドには、E_FAIL が返される、ときに、CLR は、プロセス内で使用可能ではなくなりました。</span><span class="sxs-lookup"><span data-stu-id="da07e-120">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="da07e-121">メソッドをホストする後続の呼び出しには、HOST_E_CLRNOTAVAILABLE が返されます。</span><span class="sxs-lookup"><span data-stu-id="da07e-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="da07e-122">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="da07e-122">E_OUTOFMEMORY</span></span>|<span data-ttu-id="da07e-123">十分なメモリが要求されたリソースの割り当てを完了します。</span><span class="sxs-lookup"><span data-stu-id="da07e-123">Not enough memory is available to complete the requested resource allocation.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="da07e-124">Remarks</span><span class="sxs-lookup"><span data-stu-id="da07e-124">Remarks</span></span>  
 <span data-ttu-id="da07e-125">各呼び出しで発生したシーケンスからマネージ コードで CLR への呼び出しが行われた場合`ReverseEnterRuntime`への呼び出しに対応して[ReverseLeaveRuntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-reverseleaveruntime-method.md)します。</span><span class="sxs-lookup"><span data-stu-id="da07e-125">If the call into the CLR is made from a sequence that originated in managed code, each call to `ReverseEnterRuntime` corresponds to a call to [ReverseLeaveRuntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-reverseleaveruntime-method.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="da07e-126">呼び出しは、入れ子にせず、アンマネージ コードから取得できます。</span><span class="sxs-lookup"><span data-stu-id="da07e-126">Calls can originate from unmanaged code without being nested.</span></span> <span data-ttu-id="da07e-127">この場合への呼び出しはありません[EnterRuntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-enterruntime-method.md)、 [LeaveRuntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-leaveruntime-method.md)、または`ReverseLeaveRuntime`、に対する呼び出しの数と`ReverseEnterRuntime`への呼び出しの数と等しくない`ReverseLeaveRuntime`します。</span><span class="sxs-lookup"><span data-stu-id="da07e-127">In this case, there is no call to [EnterRuntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-enterruntime-method.md), [LeaveRuntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-leaveruntime-method.md), or `ReverseLeaveRuntime`, and the number of calls to `ReverseEnterRuntime` does not equal the number of calls to `ReverseLeaveRuntime`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="da07e-128">必要条件</span><span class="sxs-lookup"><span data-stu-id="da07e-128">Requirements</span></span>  
 <span data-ttu-id="da07e-129">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="da07e-129">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="da07e-130">**ヘッダー:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="da07e-130">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="da07e-131">**ライブラリ:** MSCorEE.dll でリソースとして含まれます</span><span class="sxs-lookup"><span data-stu-id="da07e-131">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="da07e-132">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="da07e-132">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="da07e-133">関連項目</span><span class="sxs-lookup"><span data-stu-id="da07e-133">See also</span></span>

- [<span data-ttu-id="da07e-134">ICLRTask インターフェイス</span><span class="sxs-lookup"><span data-stu-id="da07e-134">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [<span data-ttu-id="da07e-135">ICLRTaskManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="da07e-135">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [<span data-ttu-id="da07e-136">IHostTask インターフェイス</span><span class="sxs-lookup"><span data-stu-id="da07e-136">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [<span data-ttu-id="da07e-137">IHostTaskManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="da07e-137">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
