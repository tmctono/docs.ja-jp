---
title: IHostTaskManager::SetCLRTaskManager メソッド
ms.date: 03/30/2017
api_name:
- IHostTaskManager.SetCLRTaskManager
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostTaskManager::SetCLRTaskManager
helpviewer_keywords:
- IHostTaskManager::SetCLRTaskManager method [.NET Framework hosting]
- SetCLRTaskManager method [.NET Framework hosting]
ms.assetid: ec90ee83-bd4b-408b-9274-62a923ab86a1
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 4a93efc0701248f8e4ef930261b31b3ce948647a
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/06/2019
ms.locfileid: "57484928"
---
# <a name="ihosttaskmanagersetclrtaskmanager-method"></a><span data-ttu-id="9ee4b-102">IHostTaskManager::SetCLRTaskManager メソッド</span><span class="sxs-lookup"><span data-stu-id="9ee4b-102">IHostTaskManager::SetCLRTaskManager Method</span></span>
<span data-ttu-id="9ee4b-103">により、ホストへのインターフェイス ポインターで、 [ICLRTaskManager](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)共通言語ランタイム (CLR) によって実装されるインスタンス。</span><span class="sxs-lookup"><span data-stu-id="9ee4b-103">Provides the host with an interface pointer to an [ICLRTaskManager](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md) instance implemented by the common language runtime (CLR).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9ee4b-104">構文</span><span class="sxs-lookup"><span data-stu-id="9ee4b-104">Syntax</span></span>  
  
```  
HRESULT SetCLRTaskManager (  
    [in] ICLRTaskManager *pManager  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9ee4b-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="9ee4b-105">Parameters</span></span>  
 `pManager`  
 <span data-ttu-id="9ee4b-106">[in]ポインター、`ICLRTaskManager`共通言語ランタイムによって実装されているインスタンス。</span><span class="sxs-lookup"><span data-stu-id="9ee4b-106">[in] A pointer to an `ICLRTaskManager` instance implemented by the common language runtime.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="9ee4b-107">戻り値</span><span class="sxs-lookup"><span data-stu-id="9ee4b-107">Return Value</span></span>  
  
|<span data-ttu-id="9ee4b-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="9ee4b-108">HRESULT</span></span>|<span data-ttu-id="9ee4b-109">説明</span><span class="sxs-lookup"><span data-stu-id="9ee4b-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="9ee4b-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="9ee4b-110">S_OK</span></span>|<span data-ttu-id="9ee4b-111">`SetCLRTaskManager` 正常に返されます。</span><span class="sxs-lookup"><span data-stu-id="9ee4b-111">`SetCLRTaskManager` returned successfully.</span></span>|  
|<span data-ttu-id="9ee4b-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="9ee4b-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="9ee4b-113">プロセスに CLR が読み込まれていないか、CLR は状態をマネージ コードを実行または呼び出しを正常に処理ができません。</span><span class="sxs-lookup"><span data-stu-id="9ee4b-113">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="9ee4b-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="9ee4b-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="9ee4b-115">呼び出しがタイムアウトになりました。</span><span class="sxs-lookup"><span data-stu-id="9ee4b-115">The call timed out.</span></span>|  
|<span data-ttu-id="9ee4b-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="9ee4b-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="9ee4b-117">呼び出し元がロックを所有していません。</span><span class="sxs-lookup"><span data-stu-id="9ee4b-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="9ee4b-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="9ee4b-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="9ee4b-119">イベントがキャンセルされましたブロックされたスレッドまたはファイバーが待機しています。</span><span class="sxs-lookup"><span data-stu-id="9ee4b-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="9ee4b-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="9ee4b-120">E_FAIL</span></span>|<span data-ttu-id="9ee4b-121">不明な致命的なエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="9ee4b-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="9ee4b-122">メソッドには、E_FAIL が返される、ときに、CLR は、プロセス内で使用可能ではなくなりました。</span><span class="sxs-lookup"><span data-stu-id="9ee4b-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="9ee4b-123">メソッドをホストする後続の呼び出しには、HOST_E_CLRNOTAVAILABLE が返されます。</span><span class="sxs-lookup"><span data-stu-id="9ee4b-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9ee4b-124">Remarks</span><span class="sxs-lookup"><span data-stu-id="9ee4b-124">Remarks</span></span>  
 <span data-ttu-id="9ee4b-125">ランタイム呼び出し`SetCLRTaskManager`にインターフェイス ポインターを使用して、ホストを提供する、`ICLRTaskManager`インスタンス。</span><span class="sxs-lookup"><span data-stu-id="9ee4b-125">The runtime calls `SetCLRTaskManager` to provide the host with an interface pointer to an `ICLRTaskManager` instance.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9ee4b-126">必要条件</span><span class="sxs-lookup"><span data-stu-id="9ee4b-126">Requirements</span></span>  
 <span data-ttu-id="9ee4b-127">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="9ee4b-127">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9ee4b-128">**ヘッダー:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="9ee4b-128">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="9ee4b-129">**ライブラリ:** MSCorEE.dll でリソースとして含まれます</span><span class="sxs-lookup"><span data-stu-id="9ee4b-129">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="9ee4b-130">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9ee4b-130">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9ee4b-131">関連項目</span><span class="sxs-lookup"><span data-stu-id="9ee4b-131">See also</span></span>
- [<span data-ttu-id="9ee4b-132">ICLRTask インターフェイス</span><span class="sxs-lookup"><span data-stu-id="9ee4b-132">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [<span data-ttu-id="9ee4b-133">ICLRTaskManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="9ee4b-133">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [<span data-ttu-id="9ee4b-134">IHostTask インターフェイス</span><span class="sxs-lookup"><span data-stu-id="9ee4b-134">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [<span data-ttu-id="9ee4b-135">IHostTaskManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="9ee4b-135">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
