---
title: IHostSyncManager::CreateAutoEvent メソッド
ms.date: 03/30/2017
api_name:
- IHostSyncManager.CreateAutoEvent
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostSyncManager::CreateAutoEvent
helpviewer_keywords:
- IHostSyncManager::CreateAutoEvent method [.NET Framework hosting]
- CreateAutoEvent method [.NET Framework hosting]
ms.assetid: 3153643e-cf5c-4b44-8e0e-c2b22cb08208
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f60d0d8480dcbe697b9ae76abd210120fc6b6955
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/06/2019
ms.locfileid: "57485513"
---
# <a name="ihostsyncmanagercreateautoevent-method"></a><span data-ttu-id="d27ae-102">IHostSyncManager::CreateAutoEvent メソッド</span><span class="sxs-lookup"><span data-stu-id="d27ae-102">IHostSyncManager::CreateAutoEvent Method</span></span>
<span data-ttu-id="d27ae-103">自動リセット イベント オブジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="d27ae-103">Creates an auto-reset event object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d27ae-104">構文</span><span class="sxs-lookup"><span data-stu-id="d27ae-104">Syntax</span></span>  
  
```  
HRESULT CreateAutoEvent (  
    [out] IHostAutoEvent **ppEvent  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d27ae-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="d27ae-105">Parameters</span></span>  
 `ppEvent`  
 <span data-ttu-id="d27ae-106">[out]アドレスへのポインター、 [IHostAutoEvent](../../../../docs/framework/unmanaged-api/hosting/ihostautoevent-interface.md)インスタンスのホストによって実装される、または null の場合は、イベント オブジェクトを作成できませんでした。</span><span class="sxs-lookup"><span data-stu-id="d27ae-106">[out] A pointer to the address of an [IHostAutoEvent](../../../../docs/framework/unmanaged-api/hosting/ihostautoevent-interface.md) instance implemented by the host, or null if the event object could not be created.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="d27ae-107">戻り値</span><span class="sxs-lookup"><span data-stu-id="d27ae-107">Return Value</span></span>  
  
|<span data-ttu-id="d27ae-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="d27ae-108">HRESULT</span></span>|<span data-ttu-id="d27ae-109">説明</span><span class="sxs-lookup"><span data-stu-id="d27ae-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="d27ae-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="d27ae-110">S_OK</span></span>|<span data-ttu-id="d27ae-111">`CreateAutoEvent` 正常に返されます。</span><span class="sxs-lookup"><span data-stu-id="d27ae-111">`CreateAutoEvent` returned successfully.</span></span>|  
|<span data-ttu-id="d27ae-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="d27ae-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="d27ae-113">共通言語ランタイム (CLR) は、プロセスに読み込まれていないか、CLR は状態をマネージ コードを実行または呼び出しを正常に処理ができません。</span><span class="sxs-lookup"><span data-stu-id="d27ae-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="d27ae-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="d27ae-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="d27ae-115">呼び出しがタイムアウトになりました。</span><span class="sxs-lookup"><span data-stu-id="d27ae-115">The call timed out.</span></span>|  
|<span data-ttu-id="d27ae-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="d27ae-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="d27ae-117">呼び出し元がロックを所有していません。</span><span class="sxs-lookup"><span data-stu-id="d27ae-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="d27ae-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="d27ae-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="d27ae-119">イベントがキャンセルされましたブロックされたスレッドまたはファイバーが待機しています。</span><span class="sxs-lookup"><span data-stu-id="d27ae-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="d27ae-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="d27ae-120">E_FAIL</span></span>|<span data-ttu-id="d27ae-121">不明な致命的なエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="d27ae-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="d27ae-122">メソッドには、E_FAIL が返される、ときに、CLR は、プロセス内で使用可能ではなくなりました。</span><span class="sxs-lookup"><span data-stu-id="d27ae-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="d27ae-123">メソッドをホストする後続の呼び出しには、HOST_E_CLRNOTAVAILABLE が返されます。</span><span class="sxs-lookup"><span data-stu-id="d27ae-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="d27ae-124">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="d27ae-124">E_OUTOFMEMORY</span></span>|<span data-ttu-id="d27ae-125">メモリ不足は、要求されたイベント オブジェクトを作成できませんでした。</span><span class="sxs-lookup"><span data-stu-id="d27ae-125">Not enough memory was available to create the requested event object.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d27ae-126">Remarks</span><span class="sxs-lookup"><span data-stu-id="d27ae-126">Remarks</span></span>  
 <span data-ttu-id="d27ae-127">`CreateAutoEvent` 非シグナル待機中のスレッドが解放された後に状態が変更は自動的に自動イベント オブジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="d27ae-127">`CreateAutoEvent` creates an auto-event object whose state is automatically changed to non-signaled after the waiting thread has been released.</span></span> <span data-ttu-id="d27ae-128">このメソッドは、Win32 をミラー化`CreateEvent`の値を持つ関数`false`の指定、`bManualReset`パラメーター</span><span class="sxs-lookup"><span data-stu-id="d27ae-128">This method mirrors the Win32 `CreateEvent` function with a value of `false` specified for the `bManualReset` parameter</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d27ae-129">必要条件</span><span class="sxs-lookup"><span data-stu-id="d27ae-129">Requirements</span></span>  
 <span data-ttu-id="d27ae-130">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="d27ae-130">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d27ae-131">**ヘッダー:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="d27ae-131">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="d27ae-132">**ライブラリ:** MSCorEE.dll でリソースとして含まれます</span><span class="sxs-lookup"><span data-stu-id="d27ae-132">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="d27ae-133">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d27ae-133">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d27ae-134">関連項目</span><span class="sxs-lookup"><span data-stu-id="d27ae-134">See also</span></span>
- [<span data-ttu-id="d27ae-135">ICLRSyncManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="d27ae-135">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)
- [<span data-ttu-id="d27ae-136">IHostAutoEvent インターフェイス</span><span class="sxs-lookup"><span data-stu-id="d27ae-136">IHostAutoEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostautoevent-interface.md)
- [<span data-ttu-id="d27ae-137">IHostControl インターフェイス</span><span class="sxs-lookup"><span data-stu-id="d27ae-137">IHostControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostcontrol-interface.md)
- [<span data-ttu-id="d27ae-138">IHostSyncManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="d27ae-138">IHostSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)
