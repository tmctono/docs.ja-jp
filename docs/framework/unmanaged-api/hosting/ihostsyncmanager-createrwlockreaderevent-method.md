---
title: IHostSyncManager::CreateRWLockReaderEvent メソッド
ms.date: 03/30/2017
api_name:
- IHostSyncManager.CreateRWLockReaderEvent
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostSyncManager::CreateRWLockReaderEvent
helpviewer_keywords:
- CreateRWLockReaderEvent method [.NET Framework hosting]
- IHostSyncManager::CreateRWLockReaderEvent method [.NET Framework hosting]
ms.assetid: 68c4ea19-c47c-45c6-b420-d3a2ba1c2d50
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c3e4095e0af13149a852ca055aa6a5e1e2d6848a
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67753409"
---
# <a name="ihostsyncmanagercreaterwlockreaderevent-method"></a><span data-ttu-id="b4d3a-102">IHostSyncManager::CreateRWLockReaderEvent メソッド</span><span class="sxs-lookup"><span data-stu-id="b4d3a-102">IHostSyncManager::CreateRWLockReaderEvent Method</span></span>
<span data-ttu-id="b4d3a-103">リーダー ロックの実装のための手動リセット イベント オブジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="b4d3a-103">Creates a manual-reset event object for the implementation of a reader lock.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b4d3a-104">構文</span><span class="sxs-lookup"><span data-stu-id="b4d3a-104">Syntax</span></span>  
  
```cpp  
HRESULT CreateRWLockReaderEvent (  
    [in]  BOOL bInitialState,  
    [in]  SIZE_T cookie,  
    [out] IHostManualEvent **ppEvent  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b4d3a-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="b4d3a-105">Parameters</span></span>  
 `bInitialState`  
 <span data-ttu-id="b4d3a-106">[in]`true`場合は、`ppEvent`シグナル。 それ以外にする必要があります`false`します。</span><span class="sxs-lookup"><span data-stu-id="b4d3a-106">[in] `true`, if `ppEvent` should be signaled; otherwise, `false`.</span></span>  
  
 `cookie`  
 <span data-ttu-id="b4d3a-107">[in]リーダー ロックと関連付けるクッキー。</span><span class="sxs-lookup"><span data-stu-id="b4d3a-107">[in] A cookie to associate with the reader lock.</span></span>  
  
 `ppEvent`  
 <span data-ttu-id="b4d3a-108">[out]アドレスへのポインター、 [IHostManualEvent](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-interface.md)インスタンス、または null の場合は、イベント オブジェクトを作成できませんでした。</span><span class="sxs-lookup"><span data-stu-id="b4d3a-108">[out] A pointer to the address of an [IHostManualEvent](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-interface.md) instance, or null if the event object could not be created.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="b4d3a-109">戻り値</span><span class="sxs-lookup"><span data-stu-id="b4d3a-109">Return Value</span></span>  
  
|<span data-ttu-id="b4d3a-110">HRESULT</span><span class="sxs-lookup"><span data-stu-id="b4d3a-110">HRESULT</span></span>|<span data-ttu-id="b4d3a-111">説明</span><span class="sxs-lookup"><span data-stu-id="b4d3a-111">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="b4d3a-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="b4d3a-112">S_OK</span></span>|<span data-ttu-id="b4d3a-113">`CreateRWLockReaderEvent` 正常に返されます。</span><span class="sxs-lookup"><span data-stu-id="b4d3a-113">`CreateRWLockReaderEvent` returned successfully.</span></span>|  
|<span data-ttu-id="b4d3a-114">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="b4d3a-114">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="b4d3a-115">共通言語ランタイム (CLR) は、プロセスに読み込まれていないか、CLR は状態をマネージ コードを実行または呼び出しを正常に処理ができません。</span><span class="sxs-lookup"><span data-stu-id="b4d3a-115">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="b4d3a-116">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="b4d3a-116">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="b4d3a-117">呼び出しがタイムアウトになりました。</span><span class="sxs-lookup"><span data-stu-id="b4d3a-117">The call timed out.</span></span>|  
|<span data-ttu-id="b4d3a-118">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="b4d3a-118">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="b4d3a-119">呼び出し元がロックを所有していません。</span><span class="sxs-lookup"><span data-stu-id="b4d3a-119">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="b4d3a-120">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="b4d3a-120">HOST_E_ABANDONED</span></span>|<span data-ttu-id="b4d3a-121">イベントがキャンセルされましたブロックされたスレッドまたはファイバーが待機しています。</span><span class="sxs-lookup"><span data-stu-id="b4d3a-121">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="b4d3a-122">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="b4d3a-122">E_FAIL</span></span>|<span data-ttu-id="b4d3a-123">不明な致命的なエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="b4d3a-123">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="b4d3a-124">メソッドには、E_FAIL が返される、ときに、CLR は、プロセス内で使用可能ではなくなりました。</span><span class="sxs-lookup"><span data-stu-id="b4d3a-124">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="b4d3a-125">メソッドをホストする後続の呼び出しには、HOST_E_CLRNOTAVAILABLE が返されます。</span><span class="sxs-lookup"><span data-stu-id="b4d3a-125">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="b4d3a-126">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="b4d3a-126">E_OUTOFMEMORY</span></span>|<span data-ttu-id="b4d3a-127">メモリ不足は、要求されたイベント オブジェクトを作成できませんでした。</span><span class="sxs-lookup"><span data-stu-id="b4d3a-127">Not enough memory was available to create the requested event object.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b4d3a-128">Remarks</span><span class="sxs-lookup"><span data-stu-id="b4d3a-128">Remarks</span></span>  
 <span data-ttu-id="b4d3a-129">CLR 呼び出し`CreateRWLockReaderEvent`への参照を取得する、`IHostManualEvent`リーダー ロックの実装で使用するインスタンス。</span><span class="sxs-lookup"><span data-stu-id="b4d3a-129">The CLR calls `CreateRWLockReaderEvent` to get a reference to an `IHostManualEvent` instance to use in its implementation of a reader lock.</span></span> <span data-ttu-id="b4d3a-130">ホストは、cookie を使用してクエリを実行して、リーダー ロックを待機しているタスクを決定する、 [ICLRSyncManager](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)インターフェイス。</span><span class="sxs-lookup"><span data-stu-id="b4d3a-130">The host can use the cookie to determine which tasks are waiting on the reader lock by querying the [ICLRSyncManager](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md) interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b4d3a-131">必要条件</span><span class="sxs-lookup"><span data-stu-id="b4d3a-131">Requirements</span></span>  
 <span data-ttu-id="b4d3a-132">**プラットフォーム:** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="b4d3a-132">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b4d3a-133">**ヘッダー:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="b4d3a-133">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="b4d3a-134">**ライブラリ:** MSCorEE.dll でリソースとして含まれます</span><span class="sxs-lookup"><span data-stu-id="b4d3a-134">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="b4d3a-135">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b4d3a-135">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b4d3a-136">関連項目</span><span class="sxs-lookup"><span data-stu-id="b4d3a-136">See also</span></span>

- [<span data-ttu-id="b4d3a-137">ICLRSyncManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="b4d3a-137">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)
- [<span data-ttu-id="b4d3a-138">IHostAutoEvent インターフェイス</span><span class="sxs-lookup"><span data-stu-id="b4d3a-138">IHostAutoEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostautoevent-interface.md)
- [<span data-ttu-id="b4d3a-139">IHostManualEvent インターフェイス</span><span class="sxs-lookup"><span data-stu-id="b4d3a-139">IHostManualEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-interface.md)
- [<span data-ttu-id="b4d3a-140">IHostSyncManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="b4d3a-140">IHostSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)
