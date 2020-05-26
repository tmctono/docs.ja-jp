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
ms.openlocfilehash: ba221beaa0edce49e75f75edddaee72e1beb9747
ms.sourcegitcommit: d223616e7e6fe2139079052e6fcbe25413fb9900
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/22/2020
ms.locfileid: "83803503"
---
# <a name="ihostsyncmanagercreateautoevent-method"></a><span data-ttu-id="2ebce-102">IHostSyncManager::CreateAutoEvent メソッド</span><span class="sxs-lookup"><span data-stu-id="2ebce-102">IHostSyncManager::CreateAutoEvent Method</span></span>
<span data-ttu-id="2ebce-103">自動リセットイベントオブジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="2ebce-103">Creates an auto-reset event object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2ebce-104">構文</span><span class="sxs-lookup"><span data-stu-id="2ebce-104">Syntax</span></span>  
  
```cpp  
HRESULT CreateAutoEvent (  
    [out] IHostAutoEvent **ppEvent  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2ebce-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="2ebce-105">Parameters</span></span>  
 `ppEvent`  
 <span data-ttu-id="2ebce-106">入出力ホストによって実装されている[IHostAutoEvent](ihostautoevent-interface.md)インスタンスのアドレスへのポインター。イベントオブジェクトを作成できなかった場合は null。</span><span class="sxs-lookup"><span data-stu-id="2ebce-106">[out] A pointer to the address of an [IHostAutoEvent](ihostautoevent-interface.md) instance implemented by the host, or null if the event object could not be created.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="2ebce-107">戻り値</span><span class="sxs-lookup"><span data-stu-id="2ebce-107">Return Value</span></span>  
  
|<span data-ttu-id="2ebce-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="2ebce-108">HRESULT</span></span>|<span data-ttu-id="2ebce-109">説明</span><span class="sxs-lookup"><span data-stu-id="2ebce-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="2ebce-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="2ebce-110">S_OK</span></span>|<span data-ttu-id="2ebce-111">`CreateAutoEvent`正常に返されました。</span><span class="sxs-lookup"><span data-stu-id="2ebce-111">`CreateAutoEvent` returned successfully.</span></span>|  
|<span data-ttu-id="2ebce-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="2ebce-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="2ebce-113">共通言語ランタイム (CLR) がプロセスに読み込まれていないか、CLR がマネージコードを実行できない状態であるか、または呼び出しが正常に処理されていません。</span><span class="sxs-lookup"><span data-stu-id="2ebce-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="2ebce-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="2ebce-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="2ebce-115">呼び出しがタイムアウトしました。</span><span class="sxs-lookup"><span data-stu-id="2ebce-115">The call timed out.</span></span>|  
|<span data-ttu-id="2ebce-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="2ebce-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="2ebce-117">呼び出し元がロックを所有していません。</span><span class="sxs-lookup"><span data-stu-id="2ebce-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="2ebce-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="2ebce-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="2ebce-119">ブロックされたスレッドまたはファイバーが待機しているときに、イベントが取り消されました。</span><span class="sxs-lookup"><span data-stu-id="2ebce-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="2ebce-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="2ebce-120">E_FAIL</span></span>|<span data-ttu-id="2ebce-121">原因不明の致命的なエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="2ebce-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="2ebce-122">メソッドが E_FAIL を返すと、そのプロセス内で CLR が使用できなくなります。</span><span class="sxs-lookup"><span data-stu-id="2ebce-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="2ebce-123">後続のホストメソッドの呼び出しでは HOST_E_CLRNOTAVAILABLE が返されます。</span><span class="sxs-lookup"><span data-stu-id="2ebce-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="2ebce-124">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="2ebce-124">E_OUTOFMEMORY</span></span>|<span data-ttu-id="2ebce-125">要求されたイベントオブジェクトを作成するのに十分なメモリがありませんでした。</span><span class="sxs-lookup"><span data-stu-id="2ebce-125">Not enough memory was available to create the requested event object.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2ebce-126">解説</span><span class="sxs-lookup"><span data-stu-id="2ebce-126">Remarks</span></span>  
 <span data-ttu-id="2ebce-127">`CreateAutoEvent`待機中のスレッドが解放された後に、状態が自動的に非シグナルに変更される自動イベントオブジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="2ebce-127">`CreateAutoEvent` creates an auto-event object whose state is automatically changed to non-signaled after the waiting thread has been released.</span></span> <span data-ttu-id="2ebce-128">このメソッドは、 `CreateEvent` `false` パラメーターに指定された値を使用して、Win32 関数をミラー化します。 `bManualReset`</span><span class="sxs-lookup"><span data-stu-id="2ebce-128">This method mirrors the Win32 `CreateEvent` function with a value of `false` specified for the `bManualReset` parameter</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2ebce-129">要件</span><span class="sxs-lookup"><span data-stu-id="2ebce-129">Requirements</span></span>  
 <span data-ttu-id="2ebce-130">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2ebce-130">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2ebce-131">**ヘッダー:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="2ebce-131">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="2ebce-132">**ライブラリ:** Mscoree.dll にリソースとして含まれています</span><span class="sxs-lookup"><span data-stu-id="2ebce-132">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="2ebce-133">**.NET Framework のバージョン:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2ebce-133">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2ebce-134">関連項目</span><span class="sxs-lookup"><span data-stu-id="2ebce-134">See also</span></span>

- [<span data-ttu-id="2ebce-135">ICLRSyncManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="2ebce-135">ICLRSyncManager Interface</span></span>](iclrsyncmanager-interface.md)
- [<span data-ttu-id="2ebce-136">IHostAutoEvent インターフェイス</span><span class="sxs-lookup"><span data-stu-id="2ebce-136">IHostAutoEvent Interface</span></span>](ihostautoevent-interface.md)
- [<span data-ttu-id="2ebce-137">IHostControl インターフェイス</span><span class="sxs-lookup"><span data-stu-id="2ebce-137">IHostControl Interface</span></span>](ihostcontrol-interface.md)
- [<span data-ttu-id="2ebce-138">IHostSyncManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="2ebce-138">IHostSyncManager Interface</span></span>](ihostsyncmanager-interface.md)
