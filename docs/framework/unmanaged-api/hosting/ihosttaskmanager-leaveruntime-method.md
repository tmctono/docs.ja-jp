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
ms.openlocfilehash: 8ac1c18d094deca50d461ef9ff0933a4f87176e0
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73132994"
---
# <a name="ihosttaskmanagerleaveruntime-method"></a><span data-ttu-id="73a92-102">IHostTaskManager::LeaveRuntime メソッド</span><span class="sxs-lookup"><span data-stu-id="73a92-102">IHostTaskManager::LeaveRuntime Method</span></span>
<span data-ttu-id="73a92-103">現在実行中のタスクが共通言語ランタイム (CLR) を終了しようとしていることをホストに通知し、アンマネージコードを入力します。</span><span class="sxs-lookup"><span data-stu-id="73a92-103">Notifies the host that the currently executing task is about to leave the common language runtime (CLR) and enter unmanaged code.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="73a92-104">[IHostTaskManager:: EnterRuntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-enterruntime-method.md)への対応する呼び出しは、現在実行中のタスクがマネージコードを再要求していることをホストに通知します。</span><span class="sxs-lookup"><span data-stu-id="73a92-104">A corresponding call to [IHostTaskManager::EnterRuntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-enterruntime-method.md) notifies the host that the currently executing task is reentering managed code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="73a92-105">構文</span><span class="sxs-lookup"><span data-stu-id="73a92-105">Syntax</span></span>  
  
```cpp  
HRESULT LeaveRuntime (  
    [in] SIZE_T target  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="73a92-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="73a92-106">Parameters</span></span>  
 `target`  
 <span data-ttu-id="73a92-107">から呼び出されるアンマネージ関数の、マップされた移植可能な実行可能ファイル内のアドレス。</span><span class="sxs-lookup"><span data-stu-id="73a92-107">[in] The address within the mapped portable executable file of the unmanaged function to be called.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="73a92-108">戻り値</span><span class="sxs-lookup"><span data-stu-id="73a92-108">Return Value</span></span>  
  
|<span data-ttu-id="73a92-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="73a92-109">HRESULT</span></span>|<span data-ttu-id="73a92-110">説明</span><span class="sxs-lookup"><span data-stu-id="73a92-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="73a92-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="73a92-111">S_OK</span></span>|<span data-ttu-id="73a92-112">`LeaveRuntime` が正常に返されました。</span><span class="sxs-lookup"><span data-stu-id="73a92-112">`LeaveRuntime` returned successfully.</span></span>|  
|<span data-ttu-id="73a92-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="73a92-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="73a92-114">CLR がプロセスに読み込まれていないか、CLR がマネージドコードを実行できない状態であるか、または呼び出しが正常に処理されていません。</span><span class="sxs-lookup"><span data-stu-id="73a92-114">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="73a92-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="73a92-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="73a92-116">呼び出しがタイムアウトしました。</span><span class="sxs-lookup"><span data-stu-id="73a92-116">The call timed out.</span></span>|  
|<span data-ttu-id="73a92-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="73a92-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="73a92-118">呼び出し元がロックを所有していません。</span><span class="sxs-lookup"><span data-stu-id="73a92-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="73a92-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="73a92-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="73a92-120">ブロックされたスレッドまたはファイバーが待機しているときに、イベントが取り消されました。</span><span class="sxs-lookup"><span data-stu-id="73a92-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="73a92-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="73a92-121">E_FAIL</span></span>|<span data-ttu-id="73a92-122">原因不明の致命的なエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="73a92-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="73a92-123">メソッドから E_FAIL が返された場合、そのプロセス内で CLR は使用できなくなります。</span><span class="sxs-lookup"><span data-stu-id="73a92-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="73a92-124">後続のホストメソッドの呼び出しでは、HOST_E_CLRNOTAVAILABLE が返されます。</span><span class="sxs-lookup"><span data-stu-id="73a92-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="73a92-125">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="73a92-125">E_OUTOFMEMORY</span></span>|<span data-ttu-id="73a92-126">要求された割り当てを完了するために必要なメモリが不足しています。</span><span class="sxs-lookup"><span data-stu-id="73a92-126">Not enough memory is available to complete the requested allocation.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="73a92-127">Remarks</span><span class="sxs-lookup"><span data-stu-id="73a92-127">Remarks</span></span>  
 <span data-ttu-id="73a92-128">アンマネージコードとの間の呼び出しシーケンスは入れ子にすることができます。</span><span class="sxs-lookup"><span data-stu-id="73a92-128">Call sequences to and from unmanaged code can be nested.</span></span> <span data-ttu-id="73a92-129">たとえば、次の一覧では、`LeaveRuntime`、 [IHostTaskManager:: ReverseEnterRuntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-reverseenterruntime-method.md)、 [IHostTaskManager:: ReverseLeaveRuntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-reverseleaveruntime-method.md)、および `IHostTaskManager::EnterRuntime` の呼び出しのシーケンスによって、ホストが入れ子になったレイヤー。</span><span class="sxs-lookup"><span data-stu-id="73a92-129">For example, the list below describes a hypothetical situation in which the sequence of calls to `LeaveRuntime`, [IHostTaskManager::ReverseEnterRuntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-reverseenterruntime-method.md), [IHostTaskManager::ReverseLeaveRuntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-reverseleaveruntime-method.md), and `IHostTaskManager::EnterRuntime` allows the host to identify the nested layers.</span></span>  
  
|<span data-ttu-id="73a92-130">操作</span><span class="sxs-lookup"><span data-stu-id="73a92-130">Action</span></span>|<span data-ttu-id="73a92-131">対応するメソッド呼び出し</span><span class="sxs-lookup"><span data-stu-id="73a92-131">Corresponding Method Call</span></span>|  
|------------|-------------------------------|  
|<span data-ttu-id="73a92-132">マネージ Visual Basic 実行可能ファイルは、プラットフォーム呼び出しを使用して C で記述されたアンマネージ関数を呼び出します。</span><span class="sxs-lookup"><span data-stu-id="73a92-132">A managed Visual Basic executable calls an unmanaged function written in C by using platform invoke.</span></span>|`IHostTaskManager::LeaveRuntime`|  
|<span data-ttu-id="73a92-133">アンマネージ C 関数は、でC#記述されたマネージ DLL 内のメソッドを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="73a92-133">The unmanaged C function calls a method in a managed DLL written in C#.</span></span>|`IHostTaskManager::ReverseEnterRuntime`|  
|<span data-ttu-id="73a92-134">マネージC#関数は、C で記述された別のアンマネージ関数を呼び出します。これは、プラットフォーム呼び出しを使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="73a92-134">The managed C# function calls another unmanaged function written in C, also using platform invoke.</span></span>|`IHostTaskManager::LeaveRuntime`|  
|<span data-ttu-id="73a92-135">2番目のアンマネージ関数はC# 、関数に実行を返します。</span><span class="sxs-lookup"><span data-stu-id="73a92-135">The second unmanaged function returns execution to the C# function.</span></span>|`IHostTaskManager::EnterRuntime`|  
|<span data-ttu-id="73a92-136">関数C#は、最初のアンマネージ関数に実行を返します。</span><span class="sxs-lookup"><span data-stu-id="73a92-136">The C# function returns execution to the first unmanaged function.</span></span>|`IHostTaskManager::ReverseLeaveRuntime`|  
|<span data-ttu-id="73a92-137">最初のアンマネージ関数は、実行を Visual Basic プログラムに返します。</span><span class="sxs-lookup"><span data-stu-id="73a92-137">The first unmanaged function returns execution to the Visual Basic program.</span></span>|`IHostTaskManager::EnterRuntime`|  
  
## <a name="requirements"></a><span data-ttu-id="73a92-138">［要件］</span><span class="sxs-lookup"><span data-stu-id="73a92-138">Requirements</span></span>  
 <span data-ttu-id="73a92-139">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="73a92-139">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="73a92-140">**ヘッダー:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="73a92-140">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="73a92-141">**ライブラリ:** Mscoree.dll にリソースとして含まれています</span><span class="sxs-lookup"><span data-stu-id="73a92-141">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="73a92-142">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="73a92-142">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="73a92-143">関連項目</span><span class="sxs-lookup"><span data-stu-id="73a92-143">See also</span></span>

- [<span data-ttu-id="73a92-144">ICLRTask インターフェイス</span><span class="sxs-lookup"><span data-stu-id="73a92-144">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [<span data-ttu-id="73a92-145">ICLRTaskManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="73a92-145">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [<span data-ttu-id="73a92-146">IHostTask インターフェイス</span><span class="sxs-lookup"><span data-stu-id="73a92-146">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [<span data-ttu-id="73a92-147">IHostTaskManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="73a92-147">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
