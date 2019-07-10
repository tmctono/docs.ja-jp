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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2a01779e6203ddfea32e72838b7e02996fd868c2
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67749618"
---
# <a name="ihosttaskmanagerenterruntime-method"></a><span data-ttu-id="1e813-102">IHostTaskManager::EnterRuntime メソッド</span><span class="sxs-lookup"><span data-stu-id="1e813-102">IHostTaskManager::EnterRuntime Method</span></span>
<span data-ttu-id="1e813-103">非管理対象のメソッドの呼び出しなど、プラットフォーム呼び出しメソッド、制御を返す実行共通言語ランタイム (CLR) をホストに通知します。</span><span class="sxs-lookup"><span data-stu-id="1e813-103">Notifies the host that a call to an unmanaged method, such as a platform invoke method, is returning execution control to the common language runtime (CLR).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1e813-104">構文</span><span class="sxs-lookup"><span data-stu-id="1e813-104">Syntax</span></span>  
  
```cpp  
HRESULT EnterRuntime ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="1e813-105">戻り値</span><span class="sxs-lookup"><span data-stu-id="1e813-105">Return Value</span></span>  
  
|<span data-ttu-id="1e813-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="1e813-106">HRESULT</span></span>|<span data-ttu-id="1e813-107">説明</span><span class="sxs-lookup"><span data-stu-id="1e813-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="1e813-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="1e813-108">S_OK</span></span>|<span data-ttu-id="1e813-109">`EnterRuntime` 正常に返されます。</span><span class="sxs-lookup"><span data-stu-id="1e813-109">`EnterRuntime` returned successfully.</span></span>|  
|<span data-ttu-id="1e813-110">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="1e813-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="1e813-111">プロセスに CLR が読み込まれていないか、CLR は状態をマネージ コードを実行または呼び出しを正常に処理ができません。</span><span class="sxs-lookup"><span data-stu-id="1e813-111">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="1e813-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="1e813-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="1e813-113">呼び出しがタイムアウトになりました。</span><span class="sxs-lookup"><span data-stu-id="1e813-113">The call timed out.</span></span>|  
|<span data-ttu-id="1e813-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="1e813-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="1e813-115">呼び出し元がロックを所有していません。</span><span class="sxs-lookup"><span data-stu-id="1e813-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="1e813-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="1e813-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="1e813-117">イベントがキャンセルされましたブロックされたスレッドまたはファイバーが待機しています。</span><span class="sxs-lookup"><span data-stu-id="1e813-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="1e813-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="1e813-118">E_FAIL</span></span>|<span data-ttu-id="1e813-119">不明な致命的なエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="1e813-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="1e813-120">メソッドには、E_FAIL が返される、ときに、CLR は、プロセス内で使用可能ではなくなりました。</span><span class="sxs-lookup"><span data-stu-id="1e813-120">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="1e813-121">メソッドをホストする後続の呼び出しには、HOST_E_CLRNOTAVAILABLE が返されます。</span><span class="sxs-lookup"><span data-stu-id="1e813-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="1e813-122">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="1e813-122">E_OUTOFMEMORY</span></span>|<span data-ttu-id="1e813-123">メモリ不足は、要求された割り当てを完了できませんでした。</span><span class="sxs-lookup"><span data-stu-id="1e813-123">Not enough memory was available to complete the requested allocation.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1e813-124">Remarks</span><span class="sxs-lookup"><span data-stu-id="1e813-124">Remarks</span></span>  
 <span data-ttu-id="1e813-125">`EnterRuntime` ホストに通知するために呼び出されるをアンマネージ関数を事前に呼び出した、 [LeaveRuntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-leaveruntime-method.md)メソッドが行われた、実行が完了および実行制御をランタイムに返します。</span><span class="sxs-lookup"><span data-stu-id="1e813-125">`EnterRuntime` is called to notify the host that an unmanaged function, for which an earlier call to the [LeaveRuntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-leaveruntime-method.md) method was made, has finished executing, and is returning execution control to the runtime.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="1e813-126">[ReverseEnterRuntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-reverseenterruntime-method.md)が呼び出され、ホストに通知するをアンマネージ関数を事前に呼び出した`LeaveRuntime`が行われた、マネージ コードに呼び出しを行います。</span><span class="sxs-lookup"><span data-stu-id="1e813-126">[ReverseEnterRuntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-reverseenterruntime-method.md) is called to notify the host that an unmanaged function, for which an earlier call to `LeaveRuntime` was made, is making a call into managed code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1e813-127">必要条件</span><span class="sxs-lookup"><span data-stu-id="1e813-127">Requirements</span></span>  
 <span data-ttu-id="1e813-128">**プラットフォーム:** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="1e813-128">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1e813-129">**ヘッダー:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="1e813-129">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="1e813-130">**ライブラリ:** MSCorEE.dll でリソースとして含まれます</span><span class="sxs-lookup"><span data-stu-id="1e813-130">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="1e813-131">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1e813-131">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1e813-132">関連項目</span><span class="sxs-lookup"><span data-stu-id="1e813-132">See also</span></span>

- [<span data-ttu-id="1e813-133">高度な COM 相互運用性</span><span class="sxs-lookup"><span data-stu-id="1e813-133">Advanced COM Interoperability</span></span>](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bd9cdfyx)
- [<span data-ttu-id="1e813-134">方法: PInvoke を使用してマネージド コードからネイティブ DLL を呼び出す</span><span class="sxs-lookup"><span data-stu-id="1e813-134">How to: Call Native DLLs from Managed Code Using PInvoke</span></span>](/cpp/dotnet/how-to-call-native-dlls-from-managed-code-using-pinvoke)
- [<span data-ttu-id="1e813-135">ICLRTask インターフェイス</span><span class="sxs-lookup"><span data-stu-id="1e813-135">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [<span data-ttu-id="1e813-136">ICLRTaskManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="1e813-136">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [<span data-ttu-id="1e813-137">IHostTask インターフェイス</span><span class="sxs-lookup"><span data-stu-id="1e813-137">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [<span data-ttu-id="1e813-138">IHostTaskManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="1e813-138">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
- [<span data-ttu-id="1e813-139">LeaveRuntime メソッド</span><span class="sxs-lookup"><span data-stu-id="1e813-139">LeaveRuntime Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-leaveruntime-method.md)
