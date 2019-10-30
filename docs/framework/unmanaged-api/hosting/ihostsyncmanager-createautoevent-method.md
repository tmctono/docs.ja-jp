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
ms.openlocfilehash: b3778e12dd96d4f4653633252e13469601c4879d
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73139440"
---
# <a name="ihostsyncmanagercreateautoevent-method"></a><span data-ttu-id="3598a-102">IHostSyncManager::CreateAutoEvent メソッド</span><span class="sxs-lookup"><span data-stu-id="3598a-102">IHostSyncManager::CreateAutoEvent Method</span></span>
<span data-ttu-id="3598a-103">自動リセットイベントオブジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="3598a-103">Creates an auto-reset event object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3598a-104">構文</span><span class="sxs-lookup"><span data-stu-id="3598a-104">Syntax</span></span>  
  
```cpp  
HRESULT CreateAutoEvent (  
    [out] IHostAutoEvent **ppEvent  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3598a-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="3598a-105">Parameters</span></span>  
 `ppEvent`  
 <span data-ttu-id="3598a-106">入出力ホストによって実装されている[IHostAutoEvent](../../../../docs/framework/unmanaged-api/hosting/ihostautoevent-interface.md)インスタンスのアドレスへのポインター。イベントオブジェクトを作成できなかった場合は null。</span><span class="sxs-lookup"><span data-stu-id="3598a-106">[out] A pointer to the address of an [IHostAutoEvent](../../../../docs/framework/unmanaged-api/hosting/ihostautoevent-interface.md) instance implemented by the host, or null if the event object could not be created.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="3598a-107">戻り値</span><span class="sxs-lookup"><span data-stu-id="3598a-107">Return Value</span></span>  
  
|<span data-ttu-id="3598a-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="3598a-108">HRESULT</span></span>|<span data-ttu-id="3598a-109">説明</span><span class="sxs-lookup"><span data-stu-id="3598a-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="3598a-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="3598a-110">S_OK</span></span>|<span data-ttu-id="3598a-111">`CreateAutoEvent` が正常に返されました。</span><span class="sxs-lookup"><span data-stu-id="3598a-111">`CreateAutoEvent` returned successfully.</span></span>|  
|<span data-ttu-id="3598a-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="3598a-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="3598a-113">共通言語ランタイム (CLR) がプロセスに読み込まれていないか、CLR がマネージコードを実行できない状態であるか、または呼び出しが正常に処理されていません。</span><span class="sxs-lookup"><span data-stu-id="3598a-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="3598a-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="3598a-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="3598a-115">呼び出しがタイムアウトしました。</span><span class="sxs-lookup"><span data-stu-id="3598a-115">The call timed out.</span></span>|  
|<span data-ttu-id="3598a-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="3598a-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="3598a-117">呼び出し元がロックを所有していません。</span><span class="sxs-lookup"><span data-stu-id="3598a-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="3598a-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="3598a-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="3598a-119">ブロックされたスレッドまたはファイバーが待機しているときに、イベントが取り消されました。</span><span class="sxs-lookup"><span data-stu-id="3598a-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="3598a-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="3598a-120">E_FAIL</span></span>|<span data-ttu-id="3598a-121">原因不明の致命的なエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="3598a-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="3598a-122">メソッドから E_FAIL が返された場合、そのプロセス内で CLR は使用できなくなります。</span><span class="sxs-lookup"><span data-stu-id="3598a-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="3598a-123">後続のホストメソッドの呼び出しでは、HOST_E_CLRNOTAVAILABLE が返されます。</span><span class="sxs-lookup"><span data-stu-id="3598a-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="3598a-124">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="3598a-124">E_OUTOFMEMORY</span></span>|<span data-ttu-id="3598a-125">要求されたイベントオブジェクトを作成するのに十分なメモリがありませんでした。</span><span class="sxs-lookup"><span data-stu-id="3598a-125">Not enough memory was available to create the requested event object.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3598a-126">Remarks</span><span class="sxs-lookup"><span data-stu-id="3598a-126">Remarks</span></span>  
 <span data-ttu-id="3598a-127">`CreateAutoEvent` は、待機中のスレッドが解放された後に、状態が自動的に非シグナルに変更される自動イベントオブジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="3598a-127">`CreateAutoEvent` creates an auto-event object whose state is automatically changed to non-signaled after the waiting thread has been released.</span></span> <span data-ttu-id="3598a-128">このメソッドは、`bManualReset` パラメーターに指定された `false` の値を持つ Win32 `CreateEvent` 関数をミラー化します。</span><span class="sxs-lookup"><span data-stu-id="3598a-128">This method mirrors the Win32 `CreateEvent` function with a value of `false` specified for the `bManualReset` parameter</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3598a-129">［要件］</span><span class="sxs-lookup"><span data-stu-id="3598a-129">Requirements</span></span>  
 <span data-ttu-id="3598a-130">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3598a-130">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3598a-131">**ヘッダー:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="3598a-131">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="3598a-132">**ライブラリ:** Mscoree.dll にリソースとして含まれています</span><span class="sxs-lookup"><span data-stu-id="3598a-132">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="3598a-133">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3598a-133">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3598a-134">関連項目</span><span class="sxs-lookup"><span data-stu-id="3598a-134">See also</span></span>

- [<span data-ttu-id="3598a-135">ICLRSyncManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="3598a-135">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)
- [<span data-ttu-id="3598a-136">IHostAutoEvent インターフェイス</span><span class="sxs-lookup"><span data-stu-id="3598a-136">IHostAutoEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostautoevent-interface.md)
- [<span data-ttu-id="3598a-137">IHostControl インターフェイス</span><span class="sxs-lookup"><span data-stu-id="3598a-137">IHostControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostcontrol-interface.md)
- [<span data-ttu-id="3598a-138">IHostSyncManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="3598a-138">IHostSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)
