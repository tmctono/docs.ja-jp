---
title: IHostSyncManager::CreateManualEvent メソッド
ms.date: 03/30/2017
api_name:
- IHostSyncManager.CreateManualEvent
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostSyncManager::CreateManualEvent
helpviewer_keywords:
- CreateManualEvent method [.NET Framework hosting]
- IHostSyncManager::CreateManualEvent method [.NET Framework hosting]
ms.assetid: 68661fbd-09cf-46dc-890b-e694f8a3880a
topic_type:
- apiref
ms.openlocfilehash: 13679b4d40e660dfdd18e6fbafe19226b2ffda37
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73195868"
---
# <a name="ihostsyncmanagercreatemanualevent-method"></a><span data-ttu-id="944ca-102">IHostSyncManager::CreateManualEvent メソッド</span><span class="sxs-lookup"><span data-stu-id="944ca-102">IHostSyncManager::CreateManualEvent Method</span></span>
<span data-ttu-id="944ca-103">手動リセットイベントオブジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="944ca-103">Creates a manual-reset event object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="944ca-104">構文</span><span class="sxs-lookup"><span data-stu-id="944ca-104">Syntax</span></span>  
  
```cpp  
HRESULT CreateManualEvent (  
    [in]  BOOL bInitialState,  
    [out] IHostManualEvent **ppEvent  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="944ca-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="944ca-105">Parameters</span></span>  
 `bInitialState`  
 <span data-ttu-id="944ca-106">[in] オブジェクトがシグナル状態である場合は `true`。それ以外の場合は、`false`ます。</span><span class="sxs-lookup"><span data-stu-id="944ca-106">[in] `true`, if the object is signaled; otherwise, `false`.</span></span>  
  
 `ppEvent`  
 <span data-ttu-id="944ca-107">入出力[IHostManualEvent](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-interface.md)インスタンスのアドレスへのポインター。イベントを作成できなかった場合は null。</span><span class="sxs-lookup"><span data-stu-id="944ca-107">[out] A pointer to the address of an [IHostManualEvent](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-interface.md) instance, or null if the event could not be created.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="944ca-108">戻り値</span><span class="sxs-lookup"><span data-stu-id="944ca-108">Return Value</span></span>  
  
|<span data-ttu-id="944ca-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="944ca-109">HRESULT</span></span>|<span data-ttu-id="944ca-110">説明</span><span class="sxs-lookup"><span data-stu-id="944ca-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="944ca-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="944ca-111">S_OK</span></span>|<span data-ttu-id="944ca-112">`CreateManualEvent` が正常に返されました。</span><span class="sxs-lookup"><span data-stu-id="944ca-112">`CreateManualEvent` returned successfully.</span></span>|  
|<span data-ttu-id="944ca-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="944ca-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="944ca-114">共通言語ランタイム (CLR) がプロセスに読み込まれていないか、CLR がマネージコードを実行できない状態であるか、または呼び出しが正常に処理されていません。</span><span class="sxs-lookup"><span data-stu-id="944ca-114">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="944ca-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="944ca-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="944ca-116">呼び出しがタイムアウトしました。</span><span class="sxs-lookup"><span data-stu-id="944ca-116">The call timed out.</span></span>|  
|<span data-ttu-id="944ca-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="944ca-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="944ca-118">呼び出し元がロックを所有していません。</span><span class="sxs-lookup"><span data-stu-id="944ca-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="944ca-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="944ca-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="944ca-120">ブロックされたスレッドまたはファイバーが待機しているときに、イベントが取り消されました。</span><span class="sxs-lookup"><span data-stu-id="944ca-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="944ca-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="944ca-121">E_FAIL</span></span>|<span data-ttu-id="944ca-122">原因不明の致命的なエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="944ca-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="944ca-123">メソッドから E_FAIL が返された場合、そのプロセス内で CLR は使用できなくなります。</span><span class="sxs-lookup"><span data-stu-id="944ca-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="944ca-124">後続のホストメソッドの呼び出しでは、HOST_E_CLRNOTAVAILABLE が返されます。</span><span class="sxs-lookup"><span data-stu-id="944ca-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="944ca-125">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="944ca-125">E_OUTOFMEMORY</span></span>|<span data-ttu-id="944ca-126">要求されたイベントオブジェクトを作成するのに十分なメモリがありませんでした。</span><span class="sxs-lookup"><span data-stu-id="944ca-126">Not enough memory was available to create the requested event object.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="944ca-127">Remarks</span><span class="sxs-lookup"><span data-stu-id="944ca-127">Remarks</span></span>  
 <span data-ttu-id="944ca-128">`CreateManualEvent` は、シグナル状態以外の状態に設定するために[IHostManualEvent:: reset](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-reset-method.md)メソッドの呼び出しを必要とする手動リセットイベントオブジェクトである `IHostManualEvent`を作成します。</span><span class="sxs-lookup"><span data-stu-id="944ca-128">`CreateManualEvent` creates an `IHostManualEvent`, a manual-reset event object that requires a call to the [IHostManualEvent::Reset](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-reset-method.md) method to set it to a non-signaled state.</span></span> <span data-ttu-id="944ca-129">`CreateManualEvent` は、`bManualReset` パラメーターに指定された `true` の値を持つ Win32 `CreateEvent` 関数をミラー化します。</span><span class="sxs-lookup"><span data-stu-id="944ca-129">`CreateManualEvent` mirrors the Win32 `CreateEvent` function with a value of `true` specified for the `bManualReset` parameter.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="944ca-130">［要件］</span><span class="sxs-lookup"><span data-stu-id="944ca-130">Requirements</span></span>  
 <span data-ttu-id="944ca-131">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="944ca-131">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="944ca-132">**ヘッダー:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="944ca-132">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="944ca-133">**ライブラリ:** Mscoree.dll にリソースとして含まれています</span><span class="sxs-lookup"><span data-stu-id="944ca-133">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="944ca-134">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="944ca-134">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="944ca-135">関連項目</span><span class="sxs-lookup"><span data-stu-id="944ca-135">See also</span></span>

- [<span data-ttu-id="944ca-136">ICLRSyncManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="944ca-136">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)
- [<span data-ttu-id="944ca-137">IHostManualEvent インターフェイス</span><span class="sxs-lookup"><span data-stu-id="944ca-137">IHostManualEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-interface.md)
- [<span data-ttu-id="944ca-138">IHostSyncManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="944ca-138">IHostSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)
