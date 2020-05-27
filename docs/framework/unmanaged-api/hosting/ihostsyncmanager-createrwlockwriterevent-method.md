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
ms.openlocfilehash: f00d166541f7955516e9d5c1dce2a4342c08ad0a
ms.sourcegitcommit: d223616e7e6fe2139079052e6fcbe25413fb9900
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/22/2020
ms.locfileid: "83803144"
---
# <a name="ihostsyncmanagercreaterwlockwriterevent-method"></a><span data-ttu-id="ffe7e-102">IHostSyncManager::CreateRWLockWriterEvent メソッド</span><span class="sxs-lookup"><span data-stu-id="ffe7e-102">IHostSyncManager::CreateRWLockWriterEvent Method</span></span>
<span data-ttu-id="ffe7e-103">ライターロックの実装用の自動リセットイベントオブジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="ffe7e-103">Creates an auto-reset event object for the implementation of a writer lock.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ffe7e-104">構文</span><span class="sxs-lookup"><span data-stu-id="ffe7e-104">Syntax</span></span>  
  
```cpp  
HRESULT CreateRWLockWriterEvent (  
    [in]  SIZE_T cookie,  
    [out] IHostAutoEvent **ppEvent  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ffe7e-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="ffe7e-105">Parameters</span></span>  
 `cookie`  
 <span data-ttu-id="ffe7e-106">から自動リセットイベントに関連付けるクッキー。</span><span class="sxs-lookup"><span data-stu-id="ffe7e-106">[in] A cookie to associate with the auto-reset event.</span></span>  
  
 `ppEvent`  
 <span data-ttu-id="ffe7e-107">入出力[IHostAutoEvent](ihostautoevent-interface.md)インスタンスのアドレスへのポインター。イベントオブジェクトを作成できなかった場合は null。</span><span class="sxs-lookup"><span data-stu-id="ffe7e-107">[out] A pointer to the address of an [IHostAutoEvent](ihostautoevent-interface.md) instance, or null if the event object could not be created.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="ffe7e-108">戻り値</span><span class="sxs-lookup"><span data-stu-id="ffe7e-108">Return Value</span></span>  
  
|<span data-ttu-id="ffe7e-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="ffe7e-109">HRESULT</span></span>|<span data-ttu-id="ffe7e-110">説明</span><span class="sxs-lookup"><span data-stu-id="ffe7e-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="ffe7e-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="ffe7e-111">S_OK</span></span>|<span data-ttu-id="ffe7e-112">`CreateRWLockWriterEvent`正常に返されました。</span><span class="sxs-lookup"><span data-stu-id="ffe7e-112">`CreateRWLockWriterEvent` returned successfully.</span></span>|  
|<span data-ttu-id="ffe7e-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="ffe7e-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="ffe7e-114">共通言語ランタイム (CLR) がプロセスに読み込まれていないか、CLR がマネージコードを実行できない状態であるか、または呼び出しが正常に処理されていません。</span><span class="sxs-lookup"><span data-stu-id="ffe7e-114">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="ffe7e-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="ffe7e-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="ffe7e-116">呼び出しがタイムアウトしました。</span><span class="sxs-lookup"><span data-stu-id="ffe7e-116">The call timed out.</span></span>|  
|<span data-ttu-id="ffe7e-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="ffe7e-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="ffe7e-118">呼び出し元がロックを所有していません。</span><span class="sxs-lookup"><span data-stu-id="ffe7e-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="ffe7e-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="ffe7e-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="ffe7e-120">ブロックされたスレッドまたはファイバーが待機しているときに、イベントが取り消されました。</span><span class="sxs-lookup"><span data-stu-id="ffe7e-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="ffe7e-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="ffe7e-121">E_FAIL</span></span>|<span data-ttu-id="ffe7e-122">原因不明の致命的なエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="ffe7e-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="ffe7e-123">メソッドが E_FAIL を返すと、そのプロセス内で CLR が使用できなくなります。</span><span class="sxs-lookup"><span data-stu-id="ffe7e-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="ffe7e-124">後続のホストメソッドの呼び出しでは HOST_E_CLRNOTAVAILABLE が返されます。</span><span class="sxs-lookup"><span data-stu-id="ffe7e-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="ffe7e-125">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="ffe7e-125">E_OUTOFMEMORY</span></span>|<span data-ttu-id="ffe7e-126">要求されたイベントオブジェクトを作成するのに十分なメモリがありませんでした。</span><span class="sxs-lookup"><span data-stu-id="ffe7e-126">Not enough memory was available to create the requested event object.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ffe7e-127">解説</span><span class="sxs-lookup"><span data-stu-id="ffe7e-127">Remarks</span></span>  
 <span data-ttu-id="ffe7e-128">CLR は、メソッドを呼び出して、 `CreateRWLockWriterEvent` `IHostAutoEvent` ライターロックの実装で使用するインスタンスへの参照を取得します。</span><span class="sxs-lookup"><span data-stu-id="ffe7e-128">The CLR calls the `CreateRWLockWriterEvent` method to get a reference to an `IHostAutoEvent` instance to use in its implementation of a writer lock.</span></span> <span data-ttu-id="ffe7e-129">ホストは、指定された cookie を使用して、 [ICLRSyncManager](iclrsyncmanager-interface.md)インターフェイスの反復メソッドを呼び出すことによって、ロックを待機しているタスクを判別できます。</span><span class="sxs-lookup"><span data-stu-id="ffe7e-129">The host can use the specified cookie to determine which tasks are waiting on the lock by calling the iteration methods of the [ICLRSyncManager](iclrsyncmanager-interface.md) interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ffe7e-130">要件</span><span class="sxs-lookup"><span data-stu-id="ffe7e-130">Requirements</span></span>  
 <span data-ttu-id="ffe7e-131">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ffe7e-131">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ffe7e-132">**ヘッダー:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="ffe7e-132">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="ffe7e-133">**ライブラリ:** Mscoree.dll にリソースとして含まれています</span><span class="sxs-lookup"><span data-stu-id="ffe7e-133">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="ffe7e-134">**.NET Framework のバージョン:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ffe7e-134">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ffe7e-135">関連項目</span><span class="sxs-lookup"><span data-stu-id="ffe7e-135">See also</span></span>

- [<span data-ttu-id="ffe7e-136">ICLRSyncManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="ffe7e-136">ICLRSyncManager Interface</span></span>](iclrsyncmanager-interface.md)
- [<span data-ttu-id="ffe7e-137">IHostAutoEvent インターフェイス</span><span class="sxs-lookup"><span data-stu-id="ffe7e-137">IHostAutoEvent Interface</span></span>](ihostautoevent-interface.md)
- [<span data-ttu-id="ffe7e-138">IHostManualEvent インターフェイス</span><span class="sxs-lookup"><span data-stu-id="ffe7e-138">IHostManualEvent Interface</span></span>](ihostmanualevent-interface.md)
- [<span data-ttu-id="ffe7e-139">IHostSyncManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="ffe7e-139">IHostSyncManager Interface</span></span>](ihostsyncmanager-interface.md)
