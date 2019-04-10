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
ms.openlocfilehash: 527607d5c39e7f698ab44baf4af0e7600ae2f473
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2019
ms.locfileid: "59222823"
---
# <a name="ihostgcmanagersuspensionending-method"></a><span data-ttu-id="0083a-102">IHostGCManager::SuspensionEnding メソッド</span><span class="sxs-lookup"><span data-stu-id="0083a-102">IHostGCManager::SuspensionEnding Method</span></span>
<span data-ttu-id="0083a-103">共通言語ランタイム (CLR) がガベージ コレクションの中断されていたスレッド上のタスクの実行を再開することをホストに通知します。</span><span class="sxs-lookup"><span data-stu-id="0083a-103">Notifies the host that the common language runtime (CLR) is resuming execution of tasks on threads that had been suspended for a garbage collection.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0083a-104">構文</span><span class="sxs-lookup"><span data-stu-id="0083a-104">Syntax</span></span>  
  
```  
HRESULT SuspensionEnding (  
    [in] DWORD generation  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0083a-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="0083a-105">Parameters</span></span>  
 `generation`  
 <span data-ttu-id="0083a-106">[in]だけを完了しているガベージ コレクション ジェネレーション元のスレッドを再開しています。</span><span class="sxs-lookup"><span data-stu-id="0083a-106">[in] The garbage collection generation that is just finishing, from which the thread is resuming.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="0083a-107">戻り値</span><span class="sxs-lookup"><span data-stu-id="0083a-107">Return Value</span></span>  
  
|<span data-ttu-id="0083a-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="0083a-108">HRESULT</span></span>|<span data-ttu-id="0083a-109">説明</span><span class="sxs-lookup"><span data-stu-id="0083a-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="0083a-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="0083a-110">S_OK</span></span>|`SuspensionEnding` <span data-ttu-id="0083a-111">正常に返されます。</span><span class="sxs-lookup"><span data-stu-id="0083a-111">returned successfully.</span></span>|  
|<span data-ttu-id="0083a-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="0083a-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="0083a-113">プロセスに CLR が読み込まれていないか、CLR は状態をマネージ コードを実行または呼び出しを正常に処理ができません。</span><span class="sxs-lookup"><span data-stu-id="0083a-113">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="0083a-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="0083a-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="0083a-115">呼び出しがタイムアウトになりました。</span><span class="sxs-lookup"><span data-stu-id="0083a-115">The call timed out.</span></span>|  
|<span data-ttu-id="0083a-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="0083a-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="0083a-117">呼び出し元がロックを所有していません。</span><span class="sxs-lookup"><span data-stu-id="0083a-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="0083a-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="0083a-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="0083a-119">イベントがキャンセルされましたブロックされたスレッドまたはファイバーが待機しています。</span><span class="sxs-lookup"><span data-stu-id="0083a-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="0083a-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="0083a-120">E_FAIL</span></span>|<span data-ttu-id="0083a-121">不明な致命的なエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="0083a-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="0083a-122">メソッドには、E_FAIL が返される、ときに、CLR は、プロセス内で使用可能ではなくなりました。</span><span class="sxs-lookup"><span data-stu-id="0083a-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="0083a-123">メソッドをホストする後続の呼び出しには、HOST_E_CLRNOTAVAILABLE が返されます。</span><span class="sxs-lookup"><span data-stu-id="0083a-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0083a-124">Remarks</span><span class="sxs-lookup"><span data-stu-id="0083a-124">Remarks</span></span>  
 <span data-ttu-id="0083a-125">CLR 呼び出し`SuspensionEnding`後、スレッドが実行を再開することをホストに通知するために、ガベージ コレクションを実行します。</span><span class="sxs-lookup"><span data-stu-id="0083a-125">The CLR calls `SuspensionEnding` after it performs a garbage collection, to inform the host that the thread is resuming execution.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="0083a-126">メソッドの呼び出しが行われたスレッドのスケジュールを変更できません。</span><span class="sxs-lookup"><span data-stu-id="0083a-126">Do not reschedule the thread the method call was made from.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0083a-127">必要条件</span><span class="sxs-lookup"><span data-stu-id="0083a-127">Requirements</span></span>  
 <span data-ttu-id="0083a-128">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="0083a-128">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0083a-129">**ヘッダー:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="0083a-129">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="0083a-130">**ライブラリ:** MSCorEE.dll でリソースとして含まれます</span><span class="sxs-lookup"><span data-stu-id="0083a-130">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="0083a-131">.NET Framework のバージョン: </span><span class="sxs-lookup"><span data-stu-id="0083a-131">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="0083a-132">関連項目</span><span class="sxs-lookup"><span data-stu-id="0083a-132">See also</span></span>

- [<span data-ttu-id="0083a-133">ICLRTask インターフェイス</span><span class="sxs-lookup"><span data-stu-id="0083a-133">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [<span data-ttu-id="0083a-134">ICLRTaskManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="0083a-134">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [<span data-ttu-id="0083a-135">IHostTask インターフェイス</span><span class="sxs-lookup"><span data-stu-id="0083a-135">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [<span data-ttu-id="0083a-136">IHostTaskManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="0083a-136">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
- [<span data-ttu-id="0083a-137">IHostGCManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="0083a-137">IHostGCManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostgcmanager-interface.md)
