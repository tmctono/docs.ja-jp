---
title: IHostTaskManager::EnterRuntime メソッド
ms.date: 03/30/2017
api_name:
- IHostTaskManager.EnterRuntime
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostTaskManager::EnterRuntime
helpviewer_keywords:
- IHostTaskManager::EnterRuntime method [.NET Framework hosting]
- EnterRuntime method [.NET Framework hosting]
ms.assetid: 1aa7a4b1-636a-4f5e-b834-b406d72f7120
topic_type:
- apiref
ms.openlocfilehash: 94ad0073678e88e15d4b083793dca1423130f7e9
ms.sourcegitcommit: 44a7cd8687f227fc6db3211ccf4783dc20235e51
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/26/2020
ms.locfileid: "77628087"
---
# <a name="ihosttaskmanagerenterruntime-method"></a><span data-ttu-id="e0b65-102">IHostTaskManager::EnterRuntime メソッド</span><span class="sxs-lookup"><span data-stu-id="e0b65-102">IHostTaskManager::EnterRuntime Method</span></span>
<span data-ttu-id="e0b65-103">プラットフォーム呼び出しメソッドなどのアンマネージメソッドへの呼び出しが実行制御を共通言語ランタイム (CLR) に返すことをホストに通知します。</span><span class="sxs-lookup"><span data-stu-id="e0b65-103">Notifies the host that a call to an unmanaged method, such as a platform invoke method, is returning execution control to the common language runtime (CLR).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e0b65-104">構文</span><span class="sxs-lookup"><span data-stu-id="e0b65-104">Syntax</span></span>  
  
```cpp  
HRESULT EnterRuntime ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="e0b65-105">戻り値</span><span class="sxs-lookup"><span data-stu-id="e0b65-105">Return Value</span></span>  
  
|<span data-ttu-id="e0b65-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="e0b65-106">HRESULT</span></span>|<span data-ttu-id="e0b65-107">説明</span><span class="sxs-lookup"><span data-stu-id="e0b65-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="e0b65-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="e0b65-108">S_OK</span></span>|<span data-ttu-id="e0b65-109">`EnterRuntime` が正常に返されました。</span><span class="sxs-lookup"><span data-stu-id="e0b65-109">`EnterRuntime` returned successfully.</span></span>|  
|<span data-ttu-id="e0b65-110">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="e0b65-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="e0b65-111">CLR がプロセスに読み込まれていないか、CLR がマネージドコードを実行できない状態であるか、または呼び出しが正常に処理されていません。</span><span class="sxs-lookup"><span data-stu-id="e0b65-111">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="e0b65-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="e0b65-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="e0b65-113">呼び出しがタイムアウトしました。</span><span class="sxs-lookup"><span data-stu-id="e0b65-113">The call timed out.</span></span>|  
|<span data-ttu-id="e0b65-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="e0b65-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="e0b65-115">呼び出し元がロックを所有していません。</span><span class="sxs-lookup"><span data-stu-id="e0b65-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="e0b65-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="e0b65-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="e0b65-117">ブロックされたスレッドまたはファイバーが待機しているときに、イベントが取り消されました。</span><span class="sxs-lookup"><span data-stu-id="e0b65-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="e0b65-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="e0b65-118">E_FAIL</span></span>|<span data-ttu-id="e0b65-119">原因不明の致命的なエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="e0b65-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="e0b65-120">メソッドが E_FAIL を返すと、そのプロセス内で CLR が使用できなくなります。</span><span class="sxs-lookup"><span data-stu-id="e0b65-120">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="e0b65-121">後続のホストメソッドの呼び出しでは HOST_E_CLRNOTAVAILABLE が返されます。</span><span class="sxs-lookup"><span data-stu-id="e0b65-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="e0b65-122">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="e0b65-122">E_OUTOFMEMORY</span></span>|<span data-ttu-id="e0b65-123">要求された割り当てを完了するのに十分なメモリがありませんでした。</span><span class="sxs-lookup"><span data-stu-id="e0b65-123">Not enough memory was available to complete the requested allocation.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e0b65-124">コメント</span><span class="sxs-lookup"><span data-stu-id="e0b65-124">Remarks</span></span>  
 <span data-ttu-id="e0b65-125">`EnterRuntime` が呼び出され、アンマネージ関数が実行を[終了し、](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-leaveruntime-method.md)実行が完了し、実行制御がランタイムに返されるアンマネージ関数がホストに通知されます。</span><span class="sxs-lookup"><span data-stu-id="e0b65-125">`EnterRuntime` is called to notify the host that an unmanaged function, for which an earlier call to the [LeaveRuntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-leaveruntime-method.md) method was made, has finished executing, and is returning execution control to the runtime.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="e0b65-126">[ReverseEnterRuntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-reverseenterruntime-method.md)を呼び出すと、以前に `LeaveRuntime` を呼び出したアンマネージ関数がマネージコードを呼び出していることがホストに通知されます。</span><span class="sxs-lookup"><span data-stu-id="e0b65-126">[ReverseEnterRuntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-reverseenterruntime-method.md) is called to notify the host that an unmanaged function, for which an earlier call to `LeaveRuntime` was made, is making a call into managed code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e0b65-127">要件</span><span class="sxs-lookup"><span data-stu-id="e0b65-127">Requirements</span></span>  
 <span data-ttu-id="e0b65-128">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e0b65-128">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e0b65-129">**ヘッダー:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="e0b65-129">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="e0b65-130">**ライブラリ:** Mscoree.dll にリソースとして含まれています</span><span class="sxs-lookup"><span data-stu-id="e0b65-130">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="e0b65-131">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e0b65-131">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e0b65-132">参照</span><span class="sxs-lookup"><span data-stu-id="e0b65-132">See also</span></span>

- <span data-ttu-id="e0b65-133">[高度な COM 相互運用性](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bd9cdfyx(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="e0b65-133">[Advanced COM Interoperability](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bd9cdfyx(v=vs.100))</span></span>
- [<span data-ttu-id="e0b65-134">方法: PInvoke を使用してマネージド コードからネイティブ DLL を呼び出す</span><span class="sxs-lookup"><span data-stu-id="e0b65-134">How to: Call Native DLLs from Managed Code Using PInvoke</span></span>](/cpp/dotnet/how-to-call-native-dlls-from-managed-code-using-pinvoke)
- [<span data-ttu-id="e0b65-135">ICLRTask インターフェイス</span><span class="sxs-lookup"><span data-stu-id="e0b65-135">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [<span data-ttu-id="e0b65-136">ICLRTaskManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="e0b65-136">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [<span data-ttu-id="e0b65-137">IHostTask インターフェイス</span><span class="sxs-lookup"><span data-stu-id="e0b65-137">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [<span data-ttu-id="e0b65-138">IHostTaskManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="e0b65-138">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
- [<span data-ttu-id="e0b65-139">LeaveRuntime メソッド</span><span class="sxs-lookup"><span data-stu-id="e0b65-139">LeaveRuntime Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-leaveruntime-method.md)
