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
ms.openlocfilehash: 8b8b8521a09fa54a105e8263a471ab0467fb6ccc
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176293"
---
# <a name="ihosttaskmanagercallneedshosthook-method"></a><span data-ttu-id="29aac-102">IHostTaskManager::CallNeedsHostHook メソッド</span><span class="sxs-lookup"><span data-stu-id="29aac-102">IHostTaskManager::CallNeedsHostHook Method</span></span>
<span data-ttu-id="29aac-103">ホストが、指定されたアンマネージ関数の呼び出しをインライン処理できるかどうかを指定できます。</span><span class="sxs-lookup"><span data-stu-id="29aac-103">Enables the host to specify whether the common language runtime (CLR) can inline the specified call to an unmanaged function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="29aac-104">構文</span><span class="sxs-lookup"><span data-stu-id="29aac-104">Syntax</span></span>  
  
```cpp  
HRESULT CallNeedsHostHook (  
    [in]  SIZE_T target,
    [out] BOOL   *pbCallNeedsHostHook  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="29aac-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="29aac-105">Parameters</span></span>  
 `target`  
 <span data-ttu-id="29aac-106">[in]呼び出されるアンマネージ関数の、マップされたポータブル実行可能 (PE) ファイル内のアドレス。</span><span class="sxs-lookup"><span data-stu-id="29aac-106">[in] The address within the mapped portable executable (PE) file of the unmanaged function that is to be called.</span></span>  
  
 `pbCallNeedsHostHook`  
 <span data-ttu-id="29aac-107">[アウト]ホストが呼び出しをフックする必要があるかどうかを示すブール値へのポインター。</span><span class="sxs-lookup"><span data-stu-id="29aac-107">[out] A pointer to a Boolean value that indicates whether the host requires the call to be hooked.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="29aac-108">戻り値</span><span class="sxs-lookup"><span data-stu-id="29aac-108">Return Value</span></span>  
  
|<span data-ttu-id="29aac-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="29aac-109">HRESULT</span></span>|<span data-ttu-id="29aac-110">説明</span><span class="sxs-lookup"><span data-stu-id="29aac-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="29aac-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="29aac-111">S_OK</span></span>|<span data-ttu-id="29aac-112">`CallNeedsHostHook`正常に返されました。</span><span class="sxs-lookup"><span data-stu-id="29aac-112">`CallNeedsHostHook` returned successfully.</span></span>|  
|<span data-ttu-id="29aac-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="29aac-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="29aac-114">CLR がプロセスに読み込まれていないか、CLR がマネージ コードを実行できない状態または呼び出しを正常に処理できない状態にあります。</span><span class="sxs-lookup"><span data-stu-id="29aac-114">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="29aac-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="29aac-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="29aac-116">通話がタイムアウトしました。</span><span class="sxs-lookup"><span data-stu-id="29aac-116">The call timed out.</span></span>|  
|<span data-ttu-id="29aac-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="29aac-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="29aac-118">呼び出し元がロックを所有していません。</span><span class="sxs-lookup"><span data-stu-id="29aac-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="29aac-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="29aac-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="29aac-120">ブロックされたスレッドまたはファイバが待機しているときにイベントがキャンセルされました。</span><span class="sxs-lookup"><span data-stu-id="29aac-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="29aac-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="29aac-121">E_FAIL</span></span>|<span data-ttu-id="29aac-122">不明な致命的な障害が発生しました。</span><span class="sxs-lookup"><span data-stu-id="29aac-122">An unknown catastrophic failure has occurred.</span></span> <span data-ttu-id="29aac-123">メソッドがE_FAILを返すと、CLR はプロセス内で使用できなくなります。</span><span class="sxs-lookup"><span data-stu-id="29aac-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="29aac-124">ホスト メソッドへの後続の呼び出しは、HOST_E_CLRNOTAVAILABLEを返します。</span><span class="sxs-lookup"><span data-stu-id="29aac-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="29aac-125">解説</span><span class="sxs-lookup"><span data-stu-id="29aac-125">Remarks</span></span>  
 <span data-ttu-id="29aac-126">コードの実行を最適化するために、CLR はコンパイル中に各プラットフォーム呼び出しの分析を実行し、呼び出しをインライン展開できるかどうかを判断します。</span><span class="sxs-lookup"><span data-stu-id="29aac-126">To help optimize code execution, the CLR performs an analysis of each platform invoke call during compilation to determine whether the call can be inlined.</span></span> <span data-ttu-id="29aac-127">`CallNeedsHostHook`を使用すると、ホストはアンマネージ関数の呼び出しをフックするように要求することによって、その決定をオーバーライドできます。</span><span class="sxs-lookup"><span data-stu-id="29aac-127">`CallNeedsHostHook` enables the host to override that decision by requiring that a call to an unmanaged function be hooked.</span></span> <span data-ttu-id="29aac-128">ホストがフックを必要とする場合、ランタイムは呼び出しをインライン行いません。</span><span class="sxs-lookup"><span data-stu-id="29aac-128">If the host requires a hook, the runtime does not inline the call.</span></span>  
  
 <span data-ttu-id="29aac-129">ホストは通常、浮動小数点の状態を調整する必要があるフックを必要とするか、または呼び出しがランタイムのメモリ要求またはロックを追跡できない状態に入っているという通知を受け取ったときに必要になります。</span><span class="sxs-lookup"><span data-stu-id="29aac-129">The host typically would require a hook where it must adjust a floating-point state, or upon receiving notification that a call is entering a state where the host cannot track the runtime's requests for memory or any locks taken.</span></span> <span data-ttu-id="29aac-130">ホストが呼び出しをフックする必要がある場合、ランタイムは[、EnterRuntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-enterruntime-method.md) [、LeaveRuntime、](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-leaveruntime-method.md)[リバースエンターランタイム](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-reverseenterruntime-method.md)、および[リバースリーブランタイム](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-reverseleaveruntime-method.md)の呼び出しを使用して、マネージ コードとの間の遷移のホストに通知します。</span><span class="sxs-lookup"><span data-stu-id="29aac-130">When the host requires that the call be hooked, the runtime notifies the host of transitions to and from managed code by using calls to [EnterRuntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-enterruntime-method.md), [LeaveRuntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-leaveruntime-method.md), [ReverseEnterRuntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-reverseenterruntime-method.md), and [ReverseLeaveRuntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-reverseleaveruntime-method.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="29aac-131">必要条件</span><span class="sxs-lookup"><span data-stu-id="29aac-131">Requirements</span></span>  
 <span data-ttu-id="29aac-132">**:**「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="29aac-132">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="29aac-133">**ヘッダー:** msCorEE.h</span><span class="sxs-lookup"><span data-stu-id="29aac-133">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="29aac-134">**ライブラリ:** MSCorEE.dll にリソースとして含まれる</span><span class="sxs-lookup"><span data-stu-id="29aac-134">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="29aac-135">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="29aac-135">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="29aac-136">関連項目</span><span class="sxs-lookup"><span data-stu-id="29aac-136">See also</span></span>

- [<span data-ttu-id="29aac-137">ICLRTask インターフェイス</span><span class="sxs-lookup"><span data-stu-id="29aac-137">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [<span data-ttu-id="29aac-138">ICLRTaskManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="29aac-138">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [<span data-ttu-id="29aac-139">IHostTask インターフェイス</span><span class="sxs-lookup"><span data-stu-id="29aac-139">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [<span data-ttu-id="29aac-140">IHostTaskManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="29aac-140">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
