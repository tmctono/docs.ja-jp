---
title: IHostTaskManager::CallNeedsHostHook メソッド
ms.date: 03/30/2017
api_name:
- IHostTaskManager.CallNeedsHostHook
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostTaskManager::CallNeedsHostHook
helpviewer_keywords:
- CallNeedsHostHook method [.NET Framework hosting]
- IHostTaskManager::CallNeedsHostHook method [.NET Framework hosting]
ms.assetid: b60f1f59-9825-4b57-961f-d2979518e6a7
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: adc270be51988cba78c6e522b16b480baef725c4
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61943514"
---
# <a name="ihosttaskmanagercallneedshosthook-method"></a><span data-ttu-id="cac6e-102">IHostTaskManager::CallNeedsHostHook メソッド</span><span class="sxs-lookup"><span data-stu-id="cac6e-102">IHostTaskManager::CallNeedsHostHook Method</span></span>
<span data-ttu-id="cac6e-103">共通言語ランタイム (CLR) が指定された非管理対象の関数呼び出しをインラインにできるかどうかを指定するホストを有効にします。</span><span class="sxs-lookup"><span data-stu-id="cac6e-103">Enables the host to specify whether the common language runtime (CLR) can inline the specified call to an unmanaged function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cac6e-104">構文</span><span class="sxs-lookup"><span data-stu-id="cac6e-104">Syntax</span></span>  
  
```  
HRESULT CallNeedsHostHook (  
    [in]  SIZE_T target,   
    [out] BOOL   *pbCallNeedsHostHook  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="cac6e-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="cac6e-105">Parameters</span></span>  
 `target`  
 <span data-ttu-id="cac6e-106">[in]呼び出されるアンマネージ関数のマップされたポータブル実行可能 (PE) ファイル内のアドレス。</span><span class="sxs-lookup"><span data-stu-id="cac6e-106">[in] The address within the mapped portable executable (PE) file of the unmanaged function that is to be called.</span></span>  
  
 `pbCallNeedsHostHook`  
 <span data-ttu-id="cac6e-107">[out]ホストにフックする呼び出しが必要かどうかを示すブール値へのポインター。</span><span class="sxs-lookup"><span data-stu-id="cac6e-107">[out] A pointer to a Boolean value that indicates whether the host requires the call to be hooked.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="cac6e-108">戻り値</span><span class="sxs-lookup"><span data-stu-id="cac6e-108">Return Value</span></span>  
  
|<span data-ttu-id="cac6e-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="cac6e-109">HRESULT</span></span>|<span data-ttu-id="cac6e-110">説明</span><span class="sxs-lookup"><span data-stu-id="cac6e-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="cac6e-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="cac6e-111">S_OK</span></span>|<span data-ttu-id="cac6e-112">`CallNeedsHostHook` 正常に返されます。</span><span class="sxs-lookup"><span data-stu-id="cac6e-112">`CallNeedsHostHook` returned successfully.</span></span>|  
|<span data-ttu-id="cac6e-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="cac6e-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="cac6e-114">プロセスに CLR が読み込まれていないか、CLR は状態をマネージ コードを実行または呼び出しを正常に処理ができません。</span><span class="sxs-lookup"><span data-stu-id="cac6e-114">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="cac6e-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="cac6e-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="cac6e-116">呼び出しがタイムアウトになりました。</span><span class="sxs-lookup"><span data-stu-id="cac6e-116">The call timed out.</span></span>|  
|<span data-ttu-id="cac6e-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="cac6e-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="cac6e-118">呼び出し元がロックを所有していません。</span><span class="sxs-lookup"><span data-stu-id="cac6e-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="cac6e-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="cac6e-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="cac6e-120">イベントがキャンセルされましたブロックされたスレッドまたはファイバーが待機しています。</span><span class="sxs-lookup"><span data-stu-id="cac6e-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="cac6e-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="cac6e-121">E_FAIL</span></span>|<span data-ttu-id="cac6e-122">不明な致命的なエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="cac6e-122">An unknown catastrophic failure has occurred.</span></span> <span data-ttu-id="cac6e-123">メソッドには、E_FAIL が返される、ときに、CLR は、プロセス内で使用可能ではなくなりました。</span><span class="sxs-lookup"><span data-stu-id="cac6e-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="cac6e-124">メソッドをホストする後続の呼び出しには、HOST_E_CLRNOTAVAILABLE が返されます。</span><span class="sxs-lookup"><span data-stu-id="cac6e-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="cac6e-125">Remarks</span><span class="sxs-lookup"><span data-stu-id="cac6e-125">Remarks</span></span>  
 <span data-ttu-id="cac6e-126">各プラットフォームの分析を実行している CLR コードの実行を最適化するため、呼び出しがインライン化できるかどうかを判断するコンパイル中に呼び出しを起動します。</span><span class="sxs-lookup"><span data-stu-id="cac6e-126">To help optimize code execution, the CLR performs an analysis of each platform invoke call during compilation to determine whether the call can be inlined.</span></span> <span data-ttu-id="cac6e-127">`CallNeedsHostHook` 非管理対象の関数の呼び出しのフックを要求することで決定をオーバーライドするホストを有効にします。</span><span class="sxs-lookup"><span data-stu-id="cac6e-127">`CallNeedsHostHook` enables the host to override that decision by requiring that a call to an unmanaged function be hooked.</span></span> <span data-ttu-id="cac6e-128">フックをホストには、ランタイムは、呼び出しをインライン展開にしません。</span><span class="sxs-lookup"><span data-stu-id="cac6e-128">If the host requires a hook, the runtime does not inline the call.</span></span>  
  
 <span data-ttu-id="cac6e-129">通常、ホストは要求フックを浮動小数点の状態を調整する必要がありますが、または呼び出しが、ホストがランタイムのメモリまたは取得されたロックの要求を追跡できない状態を入力することの通知を受信するとします。</span><span class="sxs-lookup"><span data-stu-id="cac6e-129">The host typically would require a hook where it must adjust a floating-point state, or upon receiving notification that a call is entering a state where the host cannot track the runtime's requests for memory or any locks taken.</span></span> <span data-ttu-id="cac6e-130">ホストは、呼び出しをフックする必要がある場合、ランタイムを呼び出しを使用してとマネージ コードの間の遷移のホストに通知[EnterRuntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-enterruntime-method.md)、 [LeaveRuntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-leaveruntime-method.md)、 [ReverseEnterRuntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-reverseenterruntime-method.md)、および[ReverseLeaveRuntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-reverseleaveruntime-method.md)します。</span><span class="sxs-lookup"><span data-stu-id="cac6e-130">When the host requires that the call be hooked, the runtime notifies the host of transitions to and from managed code by using calls to [EnterRuntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-enterruntime-method.md), [LeaveRuntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-leaveruntime-method.md), [ReverseEnterRuntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-reverseenterruntime-method.md), and [ReverseLeaveRuntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-reverseleaveruntime-method.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cac6e-131">必要条件</span><span class="sxs-lookup"><span data-stu-id="cac6e-131">Requirements</span></span>  
 <span data-ttu-id="cac6e-132">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="cac6e-132">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cac6e-133">**ヘッダー:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="cac6e-133">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="cac6e-134">**ライブラリ:** MSCorEE.dll でリソースとして含まれます</span><span class="sxs-lookup"><span data-stu-id="cac6e-134">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="cac6e-135">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cac6e-135">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cac6e-136">関連項目</span><span class="sxs-lookup"><span data-stu-id="cac6e-136">See also</span></span>

- [<span data-ttu-id="cac6e-137">ICLRTask インターフェイス</span><span class="sxs-lookup"><span data-stu-id="cac6e-137">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [<span data-ttu-id="cac6e-138">ICLRTaskManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="cac6e-138">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [<span data-ttu-id="cac6e-139">IHostTask インターフェイス</span><span class="sxs-lookup"><span data-stu-id="cac6e-139">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [<span data-ttu-id="cac6e-140">IHostTaskManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="cac6e-140">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
