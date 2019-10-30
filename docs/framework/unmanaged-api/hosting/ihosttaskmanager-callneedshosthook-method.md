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
ms.openlocfilehash: f5a595651baa48553997c2cba138f4f61bd530f0
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73133103"
---
# <a name="ihosttaskmanagercallneedshosthook-method"></a><span data-ttu-id="fbff8-102">IHostTaskManager::CallNeedsHostHook メソッド</span><span class="sxs-lookup"><span data-stu-id="fbff8-102">IHostTaskManager::CallNeedsHostHook Method</span></span>
<span data-ttu-id="fbff8-103">共通言語ランタイム (CLR) が、指定された呼び出しをアンマネージ関数にインライン化できるかどうかをホストが指定できるようにします。</span><span class="sxs-lookup"><span data-stu-id="fbff8-103">Enables the host to specify whether the common language runtime (CLR) can inline the specified call to an unmanaged function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fbff8-104">構文</span><span class="sxs-lookup"><span data-stu-id="fbff8-104">Syntax</span></span>  
  
```cpp  
HRESULT CallNeedsHostHook (  
    [in]  SIZE_T target,   
    [out] BOOL   *pbCallNeedsHostHook  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="fbff8-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="fbff8-105">Parameters</span></span>  
 `target`  
 <span data-ttu-id="fbff8-106">から呼び出されるアンマネージ関数の、マップされたポータブル実行可能 (PE) ファイル内のアドレス。</span><span class="sxs-lookup"><span data-stu-id="fbff8-106">[in] The address within the mapped portable executable (PE) file of the unmanaged function that is to be called.</span></span>  
  
 `pbCallNeedsHostHook`  
 <span data-ttu-id="fbff8-107">入出力ホストがフックの呼び出しを必要とするかどうかを示すブール値へのポインター。</span><span class="sxs-lookup"><span data-stu-id="fbff8-107">[out] A pointer to a Boolean value that indicates whether the host requires the call to be hooked.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="fbff8-108">戻り値</span><span class="sxs-lookup"><span data-stu-id="fbff8-108">Return Value</span></span>  
  
|<span data-ttu-id="fbff8-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="fbff8-109">HRESULT</span></span>|<span data-ttu-id="fbff8-110">説明</span><span class="sxs-lookup"><span data-stu-id="fbff8-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="fbff8-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="fbff8-111">S_OK</span></span>|<span data-ttu-id="fbff8-112">`CallNeedsHostHook` が正常に返されました。</span><span class="sxs-lookup"><span data-stu-id="fbff8-112">`CallNeedsHostHook` returned successfully.</span></span>|  
|<span data-ttu-id="fbff8-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="fbff8-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="fbff8-114">CLR がプロセスに読み込まれていないか、CLR がマネージドコードを実行できない状態であるか、または呼び出しが正常に処理されていません。</span><span class="sxs-lookup"><span data-stu-id="fbff8-114">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="fbff8-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="fbff8-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="fbff8-116">呼び出しがタイムアウトしました。</span><span class="sxs-lookup"><span data-stu-id="fbff8-116">The call timed out.</span></span>|  
|<span data-ttu-id="fbff8-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="fbff8-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="fbff8-118">呼び出し元がロックを所有していません。</span><span class="sxs-lookup"><span data-stu-id="fbff8-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="fbff8-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="fbff8-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="fbff8-120">ブロックされたスレッドまたはファイバーが待機しているときに、イベントが取り消されました。</span><span class="sxs-lookup"><span data-stu-id="fbff8-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="fbff8-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="fbff8-121">E_FAIL</span></span>|<span data-ttu-id="fbff8-122">原因不明の致命的なエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="fbff8-122">An unknown catastrophic failure has occurred.</span></span> <span data-ttu-id="fbff8-123">メソッドから E_FAIL が返された場合、そのプロセス内で CLR は使用できなくなります。</span><span class="sxs-lookup"><span data-stu-id="fbff8-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="fbff8-124">後続のホストメソッドの呼び出しでは、HOST_E_CLRNOTAVAILABLE が返されます。</span><span class="sxs-lookup"><span data-stu-id="fbff8-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="fbff8-125">Remarks</span><span class="sxs-lookup"><span data-stu-id="fbff8-125">Remarks</span></span>  
 <span data-ttu-id="fbff8-126">コードの実行を最適化するために、CLR はコンパイル中に各プラットフォーム呼び出しの分析を実行し、呼び出しをインライン化できるかどうかを判断します。</span><span class="sxs-lookup"><span data-stu-id="fbff8-126">To help optimize code execution, the CLR performs an analysis of each platform invoke call during compilation to determine whether the call can be inlined.</span></span> <span data-ttu-id="fbff8-127">`CallNeedsHostHook` により、ホストはアンマネージ関数の呼び出しをフックするように要求することによって、その決定をオーバーライドできます。</span><span class="sxs-lookup"><span data-stu-id="fbff8-127">`CallNeedsHostHook` enables the host to override that decision by requiring that a call to an unmanaged function be hooked.</span></span> <span data-ttu-id="fbff8-128">ホストにフックが必要な場合、ランタイムは呼び出しをインライン化しません。</span><span class="sxs-lookup"><span data-stu-id="fbff8-128">If the host requires a hook, the runtime does not inline the call.</span></span>  
  
 <span data-ttu-id="fbff8-129">通常、このホストでは、浮動小数点の状態を調整する必要があるフックが必要になります。または、呼び出しによって実行されるメモリまたはロックのランタイム要求を追跡できない状態になるという通知を受信します。</span><span class="sxs-lookup"><span data-stu-id="fbff8-129">The host typically would require a hook where it must adjust a floating-point state, or upon receiving notification that a call is entering a state where the host cannot track the runtime's requests for memory or any locks taken.</span></span> <span data-ttu-id="fbff8-130">ホストが呼び出しをフックする必要がある場合、ランタイムは、 [Enterruntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-enterruntime-method.md)、all [veruntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-leaveruntime-method.md)、 [ReverseEnterRuntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-reverseenterruntime-method.md)、および[ReverseLeaveRuntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-reverseleaveruntime-method.md)の呼び出しを使用して、マネージコードとの間の遷移をホストに通知します。</span><span class="sxs-lookup"><span data-stu-id="fbff8-130">When the host requires that the call be hooked, the runtime notifies the host of transitions to and from managed code by using calls to [EnterRuntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-enterruntime-method.md), [LeaveRuntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-leaveruntime-method.md), [ReverseEnterRuntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-reverseenterruntime-method.md), and [ReverseLeaveRuntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-reverseleaveruntime-method.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fbff8-131">［要件］</span><span class="sxs-lookup"><span data-stu-id="fbff8-131">Requirements</span></span>  
 <span data-ttu-id="fbff8-132">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fbff8-132">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fbff8-133">**ヘッダー:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="fbff8-133">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="fbff8-134">**ライブラリ:** Mscoree.dll にリソースとして含まれています</span><span class="sxs-lookup"><span data-stu-id="fbff8-134">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="fbff8-135">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fbff8-135">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fbff8-136">関連項目</span><span class="sxs-lookup"><span data-stu-id="fbff8-136">See also</span></span>

- [<span data-ttu-id="fbff8-137">ICLRTask インターフェイス</span><span class="sxs-lookup"><span data-stu-id="fbff8-137">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [<span data-ttu-id="fbff8-138">ICLRTaskManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="fbff8-138">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [<span data-ttu-id="fbff8-139">IHostTask インターフェイス</span><span class="sxs-lookup"><span data-stu-id="fbff8-139">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [<span data-ttu-id="fbff8-140">IHostTaskManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="fbff8-140">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
