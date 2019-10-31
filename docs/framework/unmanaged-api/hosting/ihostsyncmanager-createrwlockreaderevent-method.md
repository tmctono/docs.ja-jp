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
ms.openlocfilehash: 64cf6c80ab1cf4b3ca52c60d6e72b54c438f9f4a
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73195835"
---
# <a name="ihostsyncmanagercreaterwlockreaderevent-method"></a><span data-ttu-id="96afe-102">IHostSyncManager::CreateRWLockReaderEvent メソッド</span><span class="sxs-lookup"><span data-stu-id="96afe-102">IHostSyncManager::CreateRWLockReaderEvent Method</span></span>
<span data-ttu-id="96afe-103">リーダーロックの実装のための手動リセットイベントオブジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="96afe-103">Creates a manual-reset event object for the implementation of a reader lock.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="96afe-104">構文</span><span class="sxs-lookup"><span data-stu-id="96afe-104">Syntax</span></span>  
  
```cpp  
HRESULT CreateRWLockReaderEvent (  
    [in]  BOOL bInitialState,  
    [in]  SIZE_T cookie,  
    [out] IHostManualEvent **ppEvent  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="96afe-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="96afe-105">Parameters</span></span>  
 `bInitialState`  
 <span data-ttu-id="96afe-106">[in] `true`、`ppEvent` を通知する必要がある場合はです。それ以外の場合は、`false`ます。</span><span class="sxs-lookup"><span data-stu-id="96afe-106">[in] `true`, if `ppEvent` should be signaled; otherwise, `false`.</span></span>  
  
 `cookie`  
 <span data-ttu-id="96afe-107">からリーダーロックに関連付けるクッキー。</span><span class="sxs-lookup"><span data-stu-id="96afe-107">[in] A cookie to associate with the reader lock.</span></span>  
  
 `ppEvent`  
 <span data-ttu-id="96afe-108">入出力[IHostManualEvent](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-interface.md)インスタンスのアドレスへのポインター。イベントオブジェクトを作成できなかった場合は null。</span><span class="sxs-lookup"><span data-stu-id="96afe-108">[out] A pointer to the address of an [IHostManualEvent](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-interface.md) instance, or null if the event object could not be created.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="96afe-109">戻り値</span><span class="sxs-lookup"><span data-stu-id="96afe-109">Return Value</span></span>  
  
|<span data-ttu-id="96afe-110">HRESULT</span><span class="sxs-lookup"><span data-stu-id="96afe-110">HRESULT</span></span>|<span data-ttu-id="96afe-111">説明</span><span class="sxs-lookup"><span data-stu-id="96afe-111">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="96afe-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="96afe-112">S_OK</span></span>|<span data-ttu-id="96afe-113">`CreateRWLockReaderEvent` が正常に返されました。</span><span class="sxs-lookup"><span data-stu-id="96afe-113">`CreateRWLockReaderEvent` returned successfully.</span></span>|  
|<span data-ttu-id="96afe-114">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="96afe-114">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="96afe-115">共通言語ランタイム (CLR) がプロセスに読み込まれていないか、CLR がマネージコードを実行できない状態であるか、または呼び出しが正常に処理されていません。</span><span class="sxs-lookup"><span data-stu-id="96afe-115">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="96afe-116">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="96afe-116">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="96afe-117">呼び出しがタイムアウトしました。</span><span class="sxs-lookup"><span data-stu-id="96afe-117">The call timed out.</span></span>|  
|<span data-ttu-id="96afe-118">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="96afe-118">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="96afe-119">呼び出し元がロックを所有していません。</span><span class="sxs-lookup"><span data-stu-id="96afe-119">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="96afe-120">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="96afe-120">HOST_E_ABANDONED</span></span>|<span data-ttu-id="96afe-121">ブロックされたスレッドまたはファイバーが待機しているときに、イベントが取り消されました。</span><span class="sxs-lookup"><span data-stu-id="96afe-121">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="96afe-122">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="96afe-122">E_FAIL</span></span>|<span data-ttu-id="96afe-123">原因不明の致命的なエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="96afe-123">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="96afe-124">メソッドから E_FAIL が返された場合、そのプロセス内で CLR は使用できなくなります。</span><span class="sxs-lookup"><span data-stu-id="96afe-124">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="96afe-125">後続のホストメソッドの呼び出しでは、HOST_E_CLRNOTAVAILABLE が返されます。</span><span class="sxs-lookup"><span data-stu-id="96afe-125">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="96afe-126">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="96afe-126">E_OUTOFMEMORY</span></span>|<span data-ttu-id="96afe-127">要求されたイベントオブジェクトを作成するのに十分なメモリがありませんでした。</span><span class="sxs-lookup"><span data-stu-id="96afe-127">Not enough memory was available to create the requested event object.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="96afe-128">Remarks</span><span class="sxs-lookup"><span data-stu-id="96afe-128">Remarks</span></span>  
 <span data-ttu-id="96afe-129">CLR は `CreateRWLockReaderEvent` を呼び出して、リーダーロックの実装で使用する `IHostManualEvent` インスタンスへの参照を取得します。</span><span class="sxs-lookup"><span data-stu-id="96afe-129">The CLR calls `CreateRWLockReaderEvent` to get a reference to an `IHostManualEvent` instance to use in its implementation of a reader lock.</span></span> <span data-ttu-id="96afe-130">ホストは cookie を使用して、 [ICLRSyncManager](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)インターフェイスを照会することによって、リーダーロックを待機しているタスクを特定できます。</span><span class="sxs-lookup"><span data-stu-id="96afe-130">The host can use the cookie to determine which tasks are waiting on the reader lock by querying the [ICLRSyncManager](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md) interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="96afe-131">［要件］</span><span class="sxs-lookup"><span data-stu-id="96afe-131">Requirements</span></span>  
 <span data-ttu-id="96afe-132">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="96afe-132">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="96afe-133">**ヘッダー:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="96afe-133">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="96afe-134">**ライブラリ:** Mscoree.dll にリソースとして含まれています</span><span class="sxs-lookup"><span data-stu-id="96afe-134">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="96afe-135">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="96afe-135">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="96afe-136">関連項目</span><span class="sxs-lookup"><span data-stu-id="96afe-136">See also</span></span>

- [<span data-ttu-id="96afe-137">ICLRSyncManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="96afe-137">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)
- [<span data-ttu-id="96afe-138">IHostAutoEvent インターフェイス</span><span class="sxs-lookup"><span data-stu-id="96afe-138">IHostAutoEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostautoevent-interface.md)
- [<span data-ttu-id="96afe-139">IHostManualEvent インターフェイス</span><span class="sxs-lookup"><span data-stu-id="96afe-139">IHostManualEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-interface.md)
- [<span data-ttu-id="96afe-140">IHostSyncManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="96afe-140">IHostSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)
