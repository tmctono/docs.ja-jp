---
title: IHostSyncManager::CreateRWLockWriterEvent メソッド
ms.date: 03/30/2017
api_name:
- IHostSyncManager.CreateRWLockWriterEvent
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostSyncManager::CreateRWLockWriterEvent
helpviewer_keywords:
- CreateRWLockWriterEvent method [.NET Framework hosting]
- IHostSyncManager::CreateRWLockWriterEvent method [.NET Framework hosting]
ms.assetid: 70e488c2-cf53-4dc0-ba52-74372d215c41
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 533f7244dc47bc26b59cb9de6289ce011387bf68
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67753393"
---
# <a name="ihostsyncmanagercreaterwlockwriterevent-method"></a><span data-ttu-id="d42fb-102">IHostSyncManager::CreateRWLockWriterEvent メソッド</span><span class="sxs-lookup"><span data-stu-id="d42fb-102">IHostSyncManager::CreateRWLockWriterEvent Method</span></span>
<span data-ttu-id="d42fb-103">ライター ロックの実装の自動リセット イベント オブジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="d42fb-103">Creates an auto-reset event object for the implementation of a writer lock.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d42fb-104">構文</span><span class="sxs-lookup"><span data-stu-id="d42fb-104">Syntax</span></span>  
  
```cpp  
HRESULT CreateRWLockWriterEvent (  
    [in]  SIZE_T cookie,  
    [out] IHostAutoEvent **ppEvent  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d42fb-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="d42fb-105">Parameters</span></span>  
 `cookie`  
 <span data-ttu-id="d42fb-106">[in]自動リセット イベントに関連付けるクッキー。</span><span class="sxs-lookup"><span data-stu-id="d42fb-106">[in] A cookie to associate with the auto-reset event.</span></span>  
  
 `ppEvent`  
 <span data-ttu-id="d42fb-107">[out]アドレスへのポインター、 [IHostAutoEvent](../../../../docs/framework/unmanaged-api/hosting/ihostautoevent-interface.md)インスタンス、または null の場合は、イベント オブジェクトを作成できませんでした。</span><span class="sxs-lookup"><span data-stu-id="d42fb-107">[out] A pointer to the address of an [IHostAutoEvent](../../../../docs/framework/unmanaged-api/hosting/ihostautoevent-interface.md) instance, or null if the event object could not be created.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="d42fb-108">戻り値</span><span class="sxs-lookup"><span data-stu-id="d42fb-108">Return Value</span></span>  
  
|<span data-ttu-id="d42fb-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="d42fb-109">HRESULT</span></span>|<span data-ttu-id="d42fb-110">説明</span><span class="sxs-lookup"><span data-stu-id="d42fb-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="d42fb-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="d42fb-111">S_OK</span></span>|<span data-ttu-id="d42fb-112">`CreateRWLockWriterEvent` 正常に返されます。</span><span class="sxs-lookup"><span data-stu-id="d42fb-112">`CreateRWLockWriterEvent` returned successfully.</span></span>|  
|<span data-ttu-id="d42fb-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="d42fb-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="d42fb-114">共通言語ランタイム (CLR) は、プロセスに読み込まれていないか、CLR は状態をマネージ コードを実行または呼び出しを正常に処理ができません。</span><span class="sxs-lookup"><span data-stu-id="d42fb-114">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="d42fb-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="d42fb-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="d42fb-116">呼び出しがタイムアウトになりました。</span><span class="sxs-lookup"><span data-stu-id="d42fb-116">The call timed out.</span></span>|  
|<span data-ttu-id="d42fb-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="d42fb-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="d42fb-118">呼び出し元がロックを所有していません。</span><span class="sxs-lookup"><span data-stu-id="d42fb-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="d42fb-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="d42fb-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="d42fb-120">イベントがキャンセルされましたブロックされたスレッドまたはファイバーが待機しています。</span><span class="sxs-lookup"><span data-stu-id="d42fb-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="d42fb-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="d42fb-121">E_FAIL</span></span>|<span data-ttu-id="d42fb-122">不明な致命的なエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="d42fb-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="d42fb-123">メソッドには、E_FAIL が返される、ときに、CLR は、プロセス内で使用可能ではなくなりました。</span><span class="sxs-lookup"><span data-stu-id="d42fb-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="d42fb-124">メソッドをホストする後続の呼び出しには、HOST_E_CLRNOTAVAILABLE が返されます。</span><span class="sxs-lookup"><span data-stu-id="d42fb-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="d42fb-125">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="d42fb-125">E_OUTOFMEMORY</span></span>|<span data-ttu-id="d42fb-126">メモリ不足は、要求されたイベント オブジェクトを作成できませんでした。</span><span class="sxs-lookup"><span data-stu-id="d42fb-126">Not enough memory was available to create the requested event object.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d42fb-127">Remarks</span><span class="sxs-lookup"><span data-stu-id="d42fb-127">Remarks</span></span>  
 <span data-ttu-id="d42fb-128">CLR の呼び出し、`CreateRWLockWriterEvent`への参照を取得するメソッド、`IHostAutoEvent`ライター ロックの実装で使用するインスタンス。</span><span class="sxs-lookup"><span data-stu-id="d42fb-128">The CLR calls the `CreateRWLockWriterEvent` method to get a reference to an `IHostAutoEvent` instance to use in its implementation of a writer lock.</span></span> <span data-ttu-id="d42fb-129">ホストは、指定したクッキーを使用して、イテレーション メソッドを呼び出して、ロックを待機しているタスクを決定する、 [ICLRSyncManager](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)インターフェイス。</span><span class="sxs-lookup"><span data-stu-id="d42fb-129">The host can use the specified cookie to determine which tasks are waiting on the lock by calling the iteration methods of the [ICLRSyncManager](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md) interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d42fb-130">必要条件</span><span class="sxs-lookup"><span data-stu-id="d42fb-130">Requirements</span></span>  
 <span data-ttu-id="d42fb-131">**プラットフォーム:** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="d42fb-131">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d42fb-132">**ヘッダー:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="d42fb-132">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="d42fb-133">**ライブラリ:** MSCorEE.dll でリソースとして含まれます</span><span class="sxs-lookup"><span data-stu-id="d42fb-133">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="d42fb-134">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d42fb-134">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d42fb-135">関連項目</span><span class="sxs-lookup"><span data-stu-id="d42fb-135">See also</span></span>

- [<span data-ttu-id="d42fb-136">ICLRSyncManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="d42fb-136">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)
- [<span data-ttu-id="d42fb-137">IHostAutoEvent インターフェイス</span><span class="sxs-lookup"><span data-stu-id="d42fb-137">IHostAutoEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostautoevent-interface.md)
- [<span data-ttu-id="d42fb-138">IHostManualEvent インターフェイス</span><span class="sxs-lookup"><span data-stu-id="d42fb-138">IHostManualEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-interface.md)
- [<span data-ttu-id="d42fb-139">IHostSyncManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="d42fb-139">IHostSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)
