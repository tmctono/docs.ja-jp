---
title: IHostTaskManager::BeginThreadAffinity メソッド
ms.date: 03/30/2017
api_name:
- IHostTaskManager.BeginThreadAffinity
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostTaskManager::BeginThreadAffinity
helpviewer_keywords:
- IHostTaskManager::BeginThreadAffinity method [.NET Framework hosting]
- BeginThreadAffinity method [.NET Framework hosting]
ms.assetid: fea3ab88-ce41-4c5a-847b-bb78cd748da6
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 59af484710dc0848d7712017021adc5f3dcb7bce
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67749774"
---
# <a name="ihosttaskmanagerbeginthreadaffinity-method"></a><span data-ttu-id="97c3e-102">IHostTaskManager::BeginThreadAffinity メソッド</span><span class="sxs-lookup"><span data-stu-id="97c3e-102">IHostTaskManager::BeginThreadAffinity Method</span></span>
<span data-ttu-id="97c3e-103">マネージ コードのホストが、現在のタスクを別のオペレーティング システム スレッドに移動できない期間を入力することを通知します。</span><span class="sxs-lookup"><span data-stu-id="97c3e-103">Notifies the host that managed code is entering a period in which the current task must not be moved to another operating system thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="97c3e-104">構文</span><span class="sxs-lookup"><span data-stu-id="97c3e-104">Syntax</span></span>  
  
```cpp  
HRESULT BeginThreadAffinity ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="97c3e-105">戻り値</span><span class="sxs-lookup"><span data-stu-id="97c3e-105">Return Value</span></span>  
  
|<span data-ttu-id="97c3e-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="97c3e-106">HRESULT</span></span>|<span data-ttu-id="97c3e-107">説明</span><span class="sxs-lookup"><span data-stu-id="97c3e-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="97c3e-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="97c3e-108">S_OK</span></span>|<span data-ttu-id="97c3e-109">`BeginThreadAffinity` 正常に返されます。</span><span class="sxs-lookup"><span data-stu-id="97c3e-109">`BeginThreadAffinity` returned successfully.</span></span>|  
|<span data-ttu-id="97c3e-110">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="97c3e-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="97c3e-111">共通言語ランタイム (CLR) は、プロセスに読み込まれていないか、CLR は状態をマネージ コードを実行または呼び出しを正常に処理ができません。</span><span class="sxs-lookup"><span data-stu-id="97c3e-111">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="97c3e-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="97c3e-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="97c3e-113">呼び出しがタイムアウトになりました。</span><span class="sxs-lookup"><span data-stu-id="97c3e-113">The call timed out.</span></span>|  
|<span data-ttu-id="97c3e-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="97c3e-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="97c3e-115">呼び出し元がロックを所有していません。</span><span class="sxs-lookup"><span data-stu-id="97c3e-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="97c3e-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="97c3e-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="97c3e-117">イベントがキャンセルされましたブロックされたスレッドまたはファイバーが待機しています。</span><span class="sxs-lookup"><span data-stu-id="97c3e-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="97c3e-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="97c3e-118">E_FAIL</span></span>|<span data-ttu-id="97c3e-119">不明な致命的なエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="97c3e-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="97c3e-120">メソッドには、E_FAIL が返される、ときに、CLR は、プロセス内で使用可能ではなくなりました。</span><span class="sxs-lookup"><span data-stu-id="97c3e-120">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="97c3e-121">メソッドをホストする後続の呼び出しには、HOST_E_CLRNOTAVAILABLE が返されます。</span><span class="sxs-lookup"><span data-stu-id="97c3e-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="97c3e-122">Remarks</span><span class="sxs-lookup"><span data-stu-id="97c3e-122">Remarks</span></span>  
 <span data-ttu-id="97c3e-123">CLR は通常、呼び出し`IHostTaskManager::BeginThreadAffinity`への呼び出しのコンテキストで<xref:System.Threading.Thread.BeginThreadAffinity%2A?displayProperty=nameWithType>します。</span><span class="sxs-lookup"><span data-stu-id="97c3e-123">The CLR typically calls `IHostTaskManager::BeginThreadAffinity` in the context of a call to <xref:System.Threading.Thread.BeginThreadAffinity%2A?displayProperty=nameWithType>.</span></span> <span data-ttu-id="97c3e-124">対応する呼び出しが行われるまで、現在のタスクをスケジュールしない必要があります[ihosttaskmanager::endthreadaffinity](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-endthreadaffinity-method.md)します。</span><span class="sxs-lookup"><span data-stu-id="97c3e-124">The current task must not be rescheduled until a corresponding call is made to [IHostTaskManager::EndThreadAffinity](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-endthreadaffinity-method.md).</span></span> <span data-ttu-id="97c3e-125">タスクをスイッチ アウトします、に戻りが切り替わった、ときに、同じスイッチ アウト元となるオペレーティング システム スレッドに割り当てる必要があります。呼び出しを入れ子になった`BeginThreadAffinity`がある影響しない、呼び出しが、現在のタスクを参照しているためです。</span><span class="sxs-lookup"><span data-stu-id="97c3e-125">Tasks can be switched out, but when they are switched back in, they must be assigned to the same operating system thread from which they were switched out. Nested calls to `BeginThreadAffinity` have no effect, because the call refers to the current task.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="97c3e-126">必要条件</span><span class="sxs-lookup"><span data-stu-id="97c3e-126">Requirements</span></span>  
 <span data-ttu-id="97c3e-127">**プラットフォーム:** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="97c3e-127">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="97c3e-128">**ヘッダー:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="97c3e-128">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="97c3e-129">**ライブラリ:** MSCorEE.dll でリソースとして含まれます</span><span class="sxs-lookup"><span data-stu-id="97c3e-129">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="97c3e-130">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="97c3e-130">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="97c3e-131">関連項目</span><span class="sxs-lookup"><span data-stu-id="97c3e-131">See also</span></span>

- [<span data-ttu-id="97c3e-132">ICLRTask インターフェイス</span><span class="sxs-lookup"><span data-stu-id="97c3e-132">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [<span data-ttu-id="97c3e-133">ICLRTaskManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="97c3e-133">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [<span data-ttu-id="97c3e-134">IHostTask インターフェイス</span><span class="sxs-lookup"><span data-stu-id="97c3e-134">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [<span data-ttu-id="97c3e-135">IHostTaskManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="97c3e-135">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
