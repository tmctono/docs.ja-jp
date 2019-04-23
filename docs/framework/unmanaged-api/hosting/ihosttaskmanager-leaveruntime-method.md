---
title: IHostTaskManager::LeaveRuntime メソッド
ms.date: 03/30/2017
api_name:
- IHostTaskManager.LeaveRuntime
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostTaskManager::LeaveRuntime
helpviewer_keywords:
- IHostTaskManager::LeaveRuntime method [.NET Framework hosting]
- LeaveRuntime method [.NET Framework hosting]
ms.assetid: 43689cc4-e48e-46e5-a22d-bafd768b8759
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 81da8052b79047933b4afc6d5686029465d83eba
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59191498"
---
# <a name="ihosttaskmanagerleaveruntime-method"></a><span data-ttu-id="05c26-102">IHostTaskManager::LeaveRuntime メソッド</span><span class="sxs-lookup"><span data-stu-id="05c26-102">IHostTaskManager::LeaveRuntime Method</span></span>
<span data-ttu-id="05c26-103">現在実行中のタスクが共通言語ランタイム (CLR) のままにし、アンマネージ コードを入力することをホストに通知します。</span><span class="sxs-lookup"><span data-stu-id="05c26-103">Notifies the host that the currently executing task is about to leave the common language runtime (CLR) and enter unmanaged code.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="05c26-104">対応する呼び出し[ihosttaskmanager::enterruntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-enterruntime-method.md)現在実行中のタスクがマネージ コードを再入力するホストに通知します。</span><span class="sxs-lookup"><span data-stu-id="05c26-104">A corresponding call to [IHostTaskManager::EnterRuntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-enterruntime-method.md) notifies the host that the currently executing task is reentering managed code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="05c26-105">構文</span><span class="sxs-lookup"><span data-stu-id="05c26-105">Syntax</span></span>  
  
```  
HRESULT LeaveRuntime (  
    [in] SIZE_T target  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="05c26-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="05c26-106">Parameters</span></span>  
 `target`  
 <span data-ttu-id="05c26-107">[in]呼び出されるアンマネージ関数のマップされたポータブル実行可能ファイル内のアドレス。</span><span class="sxs-lookup"><span data-stu-id="05c26-107">[in] The address within the mapped portable executable file of the unmanaged function to be called.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="05c26-108">戻り値</span><span class="sxs-lookup"><span data-stu-id="05c26-108">Return Value</span></span>  
  
|<span data-ttu-id="05c26-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="05c26-109">HRESULT</span></span>|<span data-ttu-id="05c26-110">説明</span><span class="sxs-lookup"><span data-stu-id="05c26-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="05c26-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="05c26-111">S_OK</span></span>|<span data-ttu-id="05c26-112">`LeaveRuntime` 正常に返されます。</span><span class="sxs-lookup"><span data-stu-id="05c26-112">`LeaveRuntime` returned successfully.</span></span>|  
|<span data-ttu-id="05c26-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="05c26-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="05c26-114">プロセスに CLR が読み込まれていないか、CLR は状態をマネージ コードを実行または呼び出しを正常に処理ができません。</span><span class="sxs-lookup"><span data-stu-id="05c26-114">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="05c26-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="05c26-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="05c26-116">呼び出しがタイムアウトになりました。</span><span class="sxs-lookup"><span data-stu-id="05c26-116">The call timed out.</span></span>|  
|<span data-ttu-id="05c26-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="05c26-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="05c26-118">呼び出し元がロックを所有していません。</span><span class="sxs-lookup"><span data-stu-id="05c26-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="05c26-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="05c26-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="05c26-120">イベントがキャンセルされましたブロックされたスレッドまたはファイバーが待機しています。</span><span class="sxs-lookup"><span data-stu-id="05c26-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="05c26-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="05c26-121">E_FAIL</span></span>|<span data-ttu-id="05c26-122">不明な致命的なエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="05c26-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="05c26-123">メソッドには、E_FAIL が返される、ときに、CLR は、プロセス内で使用可能ではなくなりました。</span><span class="sxs-lookup"><span data-stu-id="05c26-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="05c26-124">メソッドをホストする後続の呼び出しには、HOST_E_CLRNOTAVAILABLE が返されます。</span><span class="sxs-lookup"><span data-stu-id="05c26-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="05c26-125">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="05c26-125">E_OUTOFMEMORY</span></span>|<span data-ttu-id="05c26-126">十分なメモリが要求された割り当てを完了します。</span><span class="sxs-lookup"><span data-stu-id="05c26-126">Not enough memory is available to complete the requested allocation.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="05c26-127">Remarks</span><span class="sxs-lookup"><span data-stu-id="05c26-127">Remarks</span></span>  
 <span data-ttu-id="05c26-128">アンマネージ コードとの間の呼び出しシーケンスを入れ子にすることができます。</span><span class="sxs-lookup"><span data-stu-id="05c26-128">Call sequences to and from unmanaged code can be nested.</span></span> <span data-ttu-id="05c26-129">たとえば、以下の一覧は、仮定の状況を記述しますへの呼び出しのシーケンス`LeaveRuntime`、 [ihosttaskmanager::reverseenterruntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-reverseenterruntime-method.md)、 [ihosttaskmanager::reverseleaveruntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-reverseleaveruntime-method.md)。、および`IHostTaskManager::EnterRuntime`入れ子になったレイヤーを識別するためにホストできるようにします。</span><span class="sxs-lookup"><span data-stu-id="05c26-129">For example, the list below describes a hypothetical situation in which the sequence of calls to `LeaveRuntime`, [IHostTaskManager::ReverseEnterRuntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-reverseenterruntime-method.md), [IHostTaskManager::ReverseLeaveRuntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-reverseleaveruntime-method.md), and `IHostTaskManager::EnterRuntime` allows the host to identify the nested layers.</span></span>  
  
|<span data-ttu-id="05c26-130">アクション</span><span class="sxs-lookup"><span data-stu-id="05c26-130">Action</span></span>|<span data-ttu-id="05c26-131">対応するメソッドの呼び出し</span><span class="sxs-lookup"><span data-stu-id="05c26-131">Corresponding Method Call</span></span>|  
|------------|-------------------------------|  
|<span data-ttu-id="05c26-132">マネージ Visual Basic 実行可能なプラットフォームを使用して C# で記述されたアンマネージ関数を呼び出します。</span><span class="sxs-lookup"><span data-stu-id="05c26-132">A managed Visual Basic executable calls an unmanaged function written in C by using platform invoke.</span></span>|`IHostTaskManager::LeaveRuntime`|  
|<span data-ttu-id="05c26-133">アンマネージ C 関数で記述されたマネージ DLL のメソッドを呼び出すC#します。</span><span class="sxs-lookup"><span data-stu-id="05c26-133">The unmanaged C function calls a method in a managed DLL written in C#.</span></span>|`IHostTaskManager::ReverseEnterRuntime`|  
|<span data-ttu-id="05c26-134">マネージC#関数が C で記述された別のアンマネージ関数を呼び出し、呼び出しもプラットフォームを使用します。</span><span class="sxs-lookup"><span data-stu-id="05c26-134">The managed C# function calls another unmanaged function written in C, also using platform invoke.</span></span>|`IHostTaskManager::LeaveRuntime`|  
|<span data-ttu-id="05c26-135">2 番目のアンマネージ関数が実行を返す、C#関数。</span><span class="sxs-lookup"><span data-stu-id="05c26-135">The second unmanaged function returns execution to the C# function.</span></span>|`IHostTaskManager::EnterRuntime`|  
|<span data-ttu-id="05c26-136">C#関数は、最初にアンマネージ関数に実行を戻します。</span><span class="sxs-lookup"><span data-stu-id="05c26-136">The C# function returns execution to the first unmanaged function.</span></span>|`IHostTaskManager::ReverseLeaveRuntime`|  
|<span data-ttu-id="05c26-137">最初のアンマネージ関数では、Visual Basic プログラムを実行を返します。</span><span class="sxs-lookup"><span data-stu-id="05c26-137">The first unmanaged function returns execution to the Visual Basic program.</span></span>|`IHostTaskManager::EnterRuntime`|  
  
## <a name="requirements"></a><span data-ttu-id="05c26-138">必要条件</span><span class="sxs-lookup"><span data-stu-id="05c26-138">Requirements</span></span>  
 <span data-ttu-id="05c26-139">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="05c26-139">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="05c26-140">**ヘッダー:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="05c26-140">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="05c26-141">**ライブラリ:** MSCorEE.dll でリソースとして含まれます</span><span class="sxs-lookup"><span data-stu-id="05c26-141">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="05c26-142">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="05c26-142">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="05c26-143">関連項目</span><span class="sxs-lookup"><span data-stu-id="05c26-143">See also</span></span>

- [<span data-ttu-id="05c26-144">ICLRTask インターフェイス</span><span class="sxs-lookup"><span data-stu-id="05c26-144">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [<span data-ttu-id="05c26-145">ICLRTaskManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="05c26-145">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [<span data-ttu-id="05c26-146">IHostTask インターフェイス</span><span class="sxs-lookup"><span data-stu-id="05c26-146">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [<span data-ttu-id="05c26-147">IHostTaskManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="05c26-147">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
