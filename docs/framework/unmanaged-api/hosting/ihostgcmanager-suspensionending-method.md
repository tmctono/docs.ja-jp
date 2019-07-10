---
title: IHostGCManager::SuspensionEnding メソッド
ms.date: 03/30/2017
api_name:
- IHostGCManager.SuspensionEnding
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostGCManager::SuspensionEnding
helpviewer_keywords:
- SuspensionEnding method, IHostGCManager interface [.NET Framework hosting]
- IHostGCManager::SuspensionEnding method [.NET Framework hosting]
ms.assetid: 8849a1db-17f0-44b7-880a-bd36d431eb91
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 9a815d1a5e8b40aee84ca2b9971ae4be7fb2c725
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67763731"
---
# <a name="ihostgcmanagersuspensionending-method"></a><span data-ttu-id="10959-102">IHostGCManager::SuspensionEnding メソッド</span><span class="sxs-lookup"><span data-stu-id="10959-102">IHostGCManager::SuspensionEnding Method</span></span>
<span data-ttu-id="10959-103">共通言語ランタイム (CLR) がガベージ コレクションの中断されていたスレッド上のタスクの実行を再開することをホストに通知します。</span><span class="sxs-lookup"><span data-stu-id="10959-103">Notifies the host that the common language runtime (CLR) is resuming execution of tasks on threads that had been suspended for a garbage collection.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="10959-104">構文</span><span class="sxs-lookup"><span data-stu-id="10959-104">Syntax</span></span>  
  
```cpp  
HRESULT SuspensionEnding (  
    [in] DWORD generation  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="10959-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="10959-105">Parameters</span></span>  
 `generation`  
 <span data-ttu-id="10959-106">[in]だけを完了しているガベージ コレクション ジェネレーション元のスレッドを再開しています。</span><span class="sxs-lookup"><span data-stu-id="10959-106">[in] The garbage collection generation that is just finishing, from which the thread is resuming.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="10959-107">戻り値</span><span class="sxs-lookup"><span data-stu-id="10959-107">Return Value</span></span>  
  
|<span data-ttu-id="10959-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="10959-108">HRESULT</span></span>|<span data-ttu-id="10959-109">説明</span><span class="sxs-lookup"><span data-stu-id="10959-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="10959-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="10959-110">S_OK</span></span>|<span data-ttu-id="10959-111">`SuspensionEnding` 正常に返されます。</span><span class="sxs-lookup"><span data-stu-id="10959-111">`SuspensionEnding` returned successfully.</span></span>|  
|<span data-ttu-id="10959-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="10959-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="10959-113">プロセスに CLR が読み込まれていないか、CLR は状態をマネージ コードを実行または呼び出しを正常に処理ができません。</span><span class="sxs-lookup"><span data-stu-id="10959-113">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="10959-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="10959-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="10959-115">呼び出しがタイムアウトになりました。</span><span class="sxs-lookup"><span data-stu-id="10959-115">The call timed out.</span></span>|  
|<span data-ttu-id="10959-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="10959-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="10959-117">呼び出し元がロックを所有していません。</span><span class="sxs-lookup"><span data-stu-id="10959-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="10959-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="10959-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="10959-119">イベントがキャンセルされましたブロックされたスレッドまたはファイバーが待機しています。</span><span class="sxs-lookup"><span data-stu-id="10959-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="10959-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="10959-120">E_FAIL</span></span>|<span data-ttu-id="10959-121">不明な致命的なエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="10959-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="10959-122">メソッドには、E_FAIL が返される、ときに、CLR は、プロセス内で使用可能ではなくなりました。</span><span class="sxs-lookup"><span data-stu-id="10959-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="10959-123">メソッドをホストする後続の呼び出しには、HOST_E_CLRNOTAVAILABLE が返されます。</span><span class="sxs-lookup"><span data-stu-id="10959-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="10959-124">Remarks</span><span class="sxs-lookup"><span data-stu-id="10959-124">Remarks</span></span>  
 <span data-ttu-id="10959-125">CLR 呼び出し`SuspensionEnding`後、スレッドが実行を再開することをホストに通知するために、ガベージ コレクションを実行します。</span><span class="sxs-lookup"><span data-stu-id="10959-125">The CLR calls `SuspensionEnding` after it performs a garbage collection, to inform the host that the thread is resuming execution.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="10959-126">メソッドの呼び出しが行われたスレッドのスケジュールを変更できません。</span><span class="sxs-lookup"><span data-stu-id="10959-126">Do not reschedule the thread the method call was made from.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="10959-127">必要条件</span><span class="sxs-lookup"><span data-stu-id="10959-127">Requirements</span></span>  
 <span data-ttu-id="10959-128">**プラットフォーム:** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="10959-128">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="10959-129">**ヘッダー:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="10959-129">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="10959-130">**ライブラリ:** MSCorEE.dll でリソースとして含まれます</span><span class="sxs-lookup"><span data-stu-id="10959-130">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="10959-131">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="10959-131">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="10959-132">関連項目</span><span class="sxs-lookup"><span data-stu-id="10959-132">See also</span></span>

- [<span data-ttu-id="10959-133">ICLRTask インターフェイス</span><span class="sxs-lookup"><span data-stu-id="10959-133">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [<span data-ttu-id="10959-134">ICLRTaskManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="10959-134">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [<span data-ttu-id="10959-135">IHostTask インターフェイス</span><span class="sxs-lookup"><span data-stu-id="10959-135">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [<span data-ttu-id="10959-136">IHostTaskManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="10959-136">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
- [<span data-ttu-id="10959-137">IHostGCManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="10959-137">IHostGCManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostgcmanager-interface.md)
