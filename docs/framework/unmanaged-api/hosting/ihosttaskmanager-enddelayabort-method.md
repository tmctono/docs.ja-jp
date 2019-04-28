---
title: IHostTaskManager::EndDelayAbort メソッド
ms.date: 03/30/2017
api_name:
- IHostTaskManager.EndDelayAbort
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostTaskManager::EndDelayAbort
helpviewer_keywords:
- EndDelayAbort method [.NET Framework hosting]
- IHostTaskManager::EndDelayAbort method [.NET Framework hosting]
ms.assetid: 6e02facb-2504-4356-9af5-0cee1f8436a7
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 10d12e5cab41f016ddee78089dc1df1f5c942ecd
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61789455"
---
# <a name="ihosttaskmanagerenddelayabort-method"></a><span data-ttu-id="b98e7-102">IHostTaskManager::EndDelayAbort メソッド</span><span class="sxs-lookup"><span data-stu-id="b98e7-102">IHostTaskManager::EndDelayAbort Method</span></span>
<span data-ttu-id="b98e7-103">マネージ コードのホストが終了する期間を現在のタスクを中止する必要がない、事前に呼び出した通知[ihosttaskmanager::begindelayabort](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-begindelayabort-method.md)します。</span><span class="sxs-lookup"><span data-stu-id="b98e7-103">Notifies the host that managed code is exiting the period in which the current task must not be aborted, following an earlier call to [IHostTaskManager::BeginDelayAbort](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-begindelayabort-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b98e7-104">構文</span><span class="sxs-lookup"><span data-stu-id="b98e7-104">Syntax</span></span>  
  
```  
HRESULT EndDelayAbort ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="b98e7-105">戻り値</span><span class="sxs-lookup"><span data-stu-id="b98e7-105">Return Value</span></span>  
  
|<span data-ttu-id="b98e7-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="b98e7-106">HRESULT</span></span>|<span data-ttu-id="b98e7-107">説明</span><span class="sxs-lookup"><span data-stu-id="b98e7-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="b98e7-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="b98e7-108">S_OK</span></span>|<span data-ttu-id="b98e7-109">`EndDelayAbort` 正常に返されます。</span><span class="sxs-lookup"><span data-stu-id="b98e7-109">`EndDelayAbort` returned successfully.</span></span>|  
|<span data-ttu-id="b98e7-110">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="b98e7-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="b98e7-111">共通言語ランタイム (CLR) は、プロセスに読み込まれていないか、CLR は状態をマネージ コードを実行または呼び出しを正常に処理ができません。</span><span class="sxs-lookup"><span data-stu-id="b98e7-111">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="b98e7-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="b98e7-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="b98e7-113">呼び出しがタイムアウトになりました。</span><span class="sxs-lookup"><span data-stu-id="b98e7-113">The call timed out.</span></span>|  
|<span data-ttu-id="b98e7-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="b98e7-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="b98e7-115">呼び出し元がロックを所有していません。</span><span class="sxs-lookup"><span data-stu-id="b98e7-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="b98e7-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="b98e7-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="b98e7-117">イベントがキャンセルされましたブロックされたスレッドまたはファイバーが待機しています。</span><span class="sxs-lookup"><span data-stu-id="b98e7-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="b98e7-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="b98e7-118">E_FAIL</span></span>|<span data-ttu-id="b98e7-119">不明な致命的なエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="b98e7-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="b98e7-120">メソッドには、E_FAIL が返される、ときに、CLR は、プロセス内で使用可能ではなくなりました。</span><span class="sxs-lookup"><span data-stu-id="b98e7-120">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="b98e7-121">メソッドをホストする後続の呼び出しには、HOST_E_CLRNOTAVAILABLE が返されます。</span><span class="sxs-lookup"><span data-stu-id="b98e7-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="b98e7-122">E_UNEXPECTED</span><span class="sxs-lookup"><span data-stu-id="b98e7-122">E_UNEXPECTED</span></span>|<span data-ttu-id="b98e7-123">`EndDelayAbort` 対応する呼び出しなしで呼び出されました`BeginDelayAbort`します。</span><span class="sxs-lookup"><span data-stu-id="b98e7-123">`EndDelayAbort` was called without a corresponding call to `BeginDelayAbort`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b98e7-124">Remarks</span><span class="sxs-lookup"><span data-stu-id="b98e7-124">Remarks</span></span>  
 <span data-ttu-id="b98e7-125">CLR は、対応する呼び出し`BeginDelayAbort`呼び出す前に、現在のタスクで`EndDelayAbort`します。</span><span class="sxs-lookup"><span data-stu-id="b98e7-125">The CLR makes a corresponding call to `BeginDelayAbort` on the current task before calling `EndDelayAbort`.</span></span> <span data-ttu-id="b98e7-126">このような対応する呼び出しがない場合のホストの実装[IHostTaskManager](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)から E_UNEXPECTED が返されます`EndDelayAbort`アクションはならないとします。</span><span class="sxs-lookup"><span data-stu-id="b98e7-126">In the absence of such a corresponding call, the host's implementation of [IHostTaskManager](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md) should return E_UNEXPECTED from `EndDelayAbort`, and should take no action.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b98e7-127">必要条件</span><span class="sxs-lookup"><span data-stu-id="b98e7-127">Requirements</span></span>  
 <span data-ttu-id="b98e7-128">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="b98e7-128">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b98e7-129">**ヘッダー:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="b98e7-129">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="b98e7-130">**ライブラリ:** MSCorEE.dll でリソースとして含まれます</span><span class="sxs-lookup"><span data-stu-id="b98e7-130">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="b98e7-131">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b98e7-131">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b98e7-132">関連項目</span><span class="sxs-lookup"><span data-stu-id="b98e7-132">See also</span></span>

- <xref:System.Threading>
- [<span data-ttu-id="b98e7-133">ICLRTask インターフェイス</span><span class="sxs-lookup"><span data-stu-id="b98e7-133">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [<span data-ttu-id="b98e7-134">ICLRTaskManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="b98e7-134">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [<span data-ttu-id="b98e7-135">IHostTask インターフェイス</span><span class="sxs-lookup"><span data-stu-id="b98e7-135">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [<span data-ttu-id="b98e7-136">IHostTaskManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="b98e7-136">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
