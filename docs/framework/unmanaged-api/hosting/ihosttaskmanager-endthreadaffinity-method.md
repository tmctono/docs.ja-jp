---
title: IHostTaskManager::EndThreadAffinity メソッド
ms.date: 03/30/2017
api_name:
- IHostTaskManager.EndThreadAffinity
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostTaskManager::EndThreadAffinity
helpviewer_keywords:
- EndThreadAffinity method [.NET Framework hosting]
- IHostTaskManager::EndThreadAffinity method [.NET Framework hosting]
ms.assetid: 7738a904-0cd7-4fde-a3eb-2323a5533157
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 3f94f365aa8c9221c64e9611deab3597e06ed862
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61789429"
---
# <a name="ihosttaskmanagerendthreadaffinity-method"></a><span data-ttu-id="aca9d-102">IHostTaskManager::EndThreadAffinity メソッド</span><span class="sxs-lookup"><span data-stu-id="aca9d-102">IHostTaskManager::EndThreadAffinity Method</span></span>
<span data-ttu-id="aca9d-103">マネージ コードのホストが終了する、現在のタスクを別のオペレーティング システム スレッドに移動できない期間以前の呼び出しに通知[ihosttaskmanager::beginthreadaffinity](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-beginthreadaffinity-method.md)します。</span><span class="sxs-lookup"><span data-stu-id="aca9d-103">Notifies the host that managed code is exiting the period in which the current task must not be moved to another operating system thread, following an earlier call to [IHostTaskManager::BeginThreadAffinity](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-beginthreadaffinity-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="aca9d-104">構文</span><span class="sxs-lookup"><span data-stu-id="aca9d-104">Syntax</span></span>  
  
```  
HRESULT EndThreadAffinity ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="aca9d-105">戻り値</span><span class="sxs-lookup"><span data-stu-id="aca9d-105">Return Value</span></span>  
  
|<span data-ttu-id="aca9d-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="aca9d-106">HRESULT</span></span>|<span data-ttu-id="aca9d-107">説明</span><span class="sxs-lookup"><span data-stu-id="aca9d-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="aca9d-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="aca9d-108">S_OK</span></span>|<span data-ttu-id="aca9d-109">`EndThreadAffinity` 正常に返されます。</span><span class="sxs-lookup"><span data-stu-id="aca9d-109">`EndThreadAffinity` returned successfully.</span></span>|  
|<span data-ttu-id="aca9d-110">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="aca9d-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="aca9d-111">共通言語ランタイム (CLR) は、プロセスに読み込まれていないか、CLR は状態をマネージ コードを実行または呼び出しを正常に処理ができません。</span><span class="sxs-lookup"><span data-stu-id="aca9d-111">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="aca9d-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="aca9d-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="aca9d-113">呼び出しがタイムアウトになりました。</span><span class="sxs-lookup"><span data-stu-id="aca9d-113">The call timed out.</span></span>|  
|<span data-ttu-id="aca9d-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="aca9d-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="aca9d-115">呼び出し元がロックを所有していません。</span><span class="sxs-lookup"><span data-stu-id="aca9d-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="aca9d-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="aca9d-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="aca9d-117">イベントがキャンセルされましたブロックされたスレッドまたはファイバーが待機しています。</span><span class="sxs-lookup"><span data-stu-id="aca9d-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="aca9d-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="aca9d-118">E_FAIL</span></span>|<span data-ttu-id="aca9d-119">不明な致命的なエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="aca9d-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="aca9d-120">メソッドには、E_FAIL が返される、ときに、CLR は、プロセス内で使用可能ではなくなりました。</span><span class="sxs-lookup"><span data-stu-id="aca9d-120">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="aca9d-121">メソッドをホストする後続の呼び出しには、HOST_E_CLRNOTAVAILABLE が返されます。</span><span class="sxs-lookup"><span data-stu-id="aca9d-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="aca9d-122">E_UNEXPECTED</span><span class="sxs-lookup"><span data-stu-id="aca9d-122">E_UNEXPECTED</span></span>|<span data-ttu-id="aca9d-123">`EndThreadAffinity` 以前に対応する呼び出しなしで呼び出されました`BeginThreadAffinity`します。</span><span class="sxs-lookup"><span data-stu-id="aca9d-123">`EndThreadAffinity` was called without an earlier corresponding call to `BeginThreadAffinity`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="aca9d-124">Remarks</span><span class="sxs-lookup"><span data-stu-id="aca9d-124">Remarks</span></span>  
 <span data-ttu-id="aca9d-125">CLR は、対応する呼び出し`BeginThreadAffinity`呼び出す前に、現在のタスクで`EndThreadAffinity`します。</span><span class="sxs-lookup"><span data-stu-id="aca9d-125">The CLR makes a corresponding call to `BeginThreadAffinity` on the current task before calling `EndThreadAffinity`.</span></span> <span data-ttu-id="aca9d-126">このような対応する呼び出しがない場合、ホストの実装の[IHostTaskManager](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md) E_UNEXPECTED を返し、何も操作する必要があります。</span><span class="sxs-lookup"><span data-stu-id="aca9d-126">In the absence of such a corresponding call, the host's implementation of [IHostTaskManager](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md) should return E_UNEXPECTED, and take no action.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="aca9d-127">必要条件</span><span class="sxs-lookup"><span data-stu-id="aca9d-127">Requirements</span></span>  
 <span data-ttu-id="aca9d-128">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="aca9d-128">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="aca9d-129">**ヘッダー:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="aca9d-129">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="aca9d-130">**ライブラリ:** MSCorEE.dll でリソースとして含まれます</span><span class="sxs-lookup"><span data-stu-id="aca9d-130">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="aca9d-131">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="aca9d-131">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="aca9d-132">関連項目</span><span class="sxs-lookup"><span data-stu-id="aca9d-132">See also</span></span>

- <xref:System.Threading>
- [<span data-ttu-id="aca9d-133">ICLRTask インターフェイス</span><span class="sxs-lookup"><span data-stu-id="aca9d-133">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [<span data-ttu-id="aca9d-134">ICLRTaskManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="aca9d-134">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [<span data-ttu-id="aca9d-135">IHostTask インターフェイス</span><span class="sxs-lookup"><span data-stu-id="aca9d-135">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [<span data-ttu-id="aca9d-136">IHostTaskManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="aca9d-136">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
