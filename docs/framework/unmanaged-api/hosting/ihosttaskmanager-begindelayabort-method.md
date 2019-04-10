---
title: IHostTaskManager::BeginDelayAbort メソッド
ms.date: 03/30/2017
api_name:
- IHostTaskManager.BeginDelayAbort
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostTaskManager::BeginDelayAbort
helpviewer_keywords:
- BeginDelayAbort method [.NET Framework hosting]
- IHostTaskManager::BeginDelayAbort method [.NET Framework hosting]
ms.assetid: 75f42a8b-ed68-4718-a030-a179cfba7d72
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 328462343669b3ea6bed2d86514ea348f6ae2b1e
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2019
ms.locfileid: "59197972"
---
# <a name="ihosttaskmanagerbegindelayabort-method"></a><span data-ttu-id="327de-102">IHostTaskManager::BeginDelayAbort メソッド</span><span class="sxs-lookup"><span data-stu-id="327de-102">IHostTaskManager::BeginDelayAbort Method</span></span>
<span data-ttu-id="327de-103">マネージ コードのホストが、現在のタスクを中止しない期間を入力することを通知します。</span><span class="sxs-lookup"><span data-stu-id="327de-103">Notifies the host that managed code is entering a period in which the current task must not be aborted.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="327de-104">構文</span><span class="sxs-lookup"><span data-stu-id="327de-104">Syntax</span></span>  
  
```  
HRESULT BeginDelayAbort ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="327de-105">戻り値</span><span class="sxs-lookup"><span data-stu-id="327de-105">Return Value</span></span>  
  
|<span data-ttu-id="327de-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="327de-106">HRESULT</span></span>|<span data-ttu-id="327de-107">説明</span><span class="sxs-lookup"><span data-stu-id="327de-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="327de-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="327de-108">S_OK</span></span>|`BeginDelayAbort` <span data-ttu-id="327de-109">正常に返されます。</span><span class="sxs-lookup"><span data-stu-id="327de-109">returned successfully.</span></span>|  
|<span data-ttu-id="327de-110">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="327de-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="327de-111">共通言語ランタイム (CLR) は、プロセスに読み込まれていないか、CLR は状態をマネージ コードを実行または呼び出しを正常に処理ができません。</span><span class="sxs-lookup"><span data-stu-id="327de-111">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="327de-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="327de-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="327de-113">呼び出しがタイムアウトになりました。</span><span class="sxs-lookup"><span data-stu-id="327de-113">The call timed out.</span></span>|  
|<span data-ttu-id="327de-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="327de-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="327de-115">呼び出し元がロックを所有していません。</span><span class="sxs-lookup"><span data-stu-id="327de-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="327de-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="327de-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="327de-117">イベントがキャンセルされましたブロックされたスレッドまたはファイバーが待機しています。</span><span class="sxs-lookup"><span data-stu-id="327de-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="327de-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="327de-118">E_FAIL</span></span>|<span data-ttu-id="327de-119">不明な致命的なエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="327de-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="327de-120">メソッドには、E_FAIL が返される、ときに、CLR は、プロセス内で使用可能ではなくなりました。</span><span class="sxs-lookup"><span data-stu-id="327de-120">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="327de-121">メソッドをホストする後続の呼び出しには、HOST_E_CLRNOTAVAILABLE が返されます。</span><span class="sxs-lookup"><span data-stu-id="327de-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="327de-122">E_UNEXPECTED</span><span class="sxs-lookup"><span data-stu-id="327de-122">E_UNEXPECTED</span></span>|`BeginDelayAbort` <span data-ttu-id="327de-123">対応する呼び出しが、既に呼び出されて[EndDelayAbort](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-enddelayabort-method.md)が受信されていません。</span><span class="sxs-lookup"><span data-stu-id="327de-123">has already been called, but the corresponding call to [EndDelayAbort](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-enddelayabort-method.md) has not yet been received.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="327de-124">Remarks</span><span class="sxs-lookup"><span data-stu-id="327de-124">Remarks</span></span>  
 <span data-ttu-id="327de-125">ホストは、まで、現在のタスクを中止する必要があります`EndDelayAbort`が呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="327de-125">The host must not abort the current task until `EndDelayAbort` is called.</span></span> <span data-ttu-id="327de-126">別の呼び出しの場合`BeginDelayAbort`を呼び出さなくてもされる`EndDelayAbort`、ホストから E_UNEXPECTED を返す必要があります`BeginDelayAbort`とは何も操作。</span><span class="sxs-lookup"><span data-stu-id="327de-126">If another call to `BeginDelayAbort` is made without an intervening call to `EndDelayAbort`, the host should return E_UNEXPECTED from `BeginDelayAbort`, and should take no action.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="327de-127">必要条件</span><span class="sxs-lookup"><span data-stu-id="327de-127">Requirements</span></span>  
 <span data-ttu-id="327de-128">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="327de-128">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="327de-129">**ヘッダー:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="327de-129">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="327de-130">**ライブラリ:** MSCorEE.dll でリソースとして含まれます</span><span class="sxs-lookup"><span data-stu-id="327de-130">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="327de-131">.NET Framework のバージョン: </span><span class="sxs-lookup"><span data-stu-id="327de-131">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="327de-132">関連項目</span><span class="sxs-lookup"><span data-stu-id="327de-132">See also</span></span>

- [<span data-ttu-id="327de-133">ICLRTask インターフェイス</span><span class="sxs-lookup"><span data-stu-id="327de-133">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [<span data-ttu-id="327de-134">ICLRTaskManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="327de-134">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [<span data-ttu-id="327de-135">IHostTaskManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="327de-135">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
