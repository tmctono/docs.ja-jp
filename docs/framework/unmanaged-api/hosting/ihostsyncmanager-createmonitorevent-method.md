---
title: IHostSyncManager::CreateMonitorEvent メソッド
ms.date: 03/30/2017
api_name:
- IHostSyncManager.CreateMonitorEvent
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostSyncManager::CreateMonitorEvent
helpviewer_keywords:
- CreateMonitorEvent method [.NET Framework hosting]
- IHostSyncManager::CreateMonitorEvent method [.NET Framework hosting]
ms.assetid: 524c7fd3-9b5c-46e7-99ba-555fd2fe33f0
topic_type:
- apiref
ms.openlocfilehash: f7426585045c7ae81377ec9bfca9d397d6f734cb
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73192014"
---
# <a name="ihostsyncmanagercreatemonitorevent-method"></a><span data-ttu-id="5f291-102">IHostSyncManager::CreateMonitorEvent メソッド</span><span class="sxs-lookup"><span data-stu-id="5f291-102">IHostSyncManager::CreateMonitorEvent Method</span></span>
<span data-ttu-id="5f291-103">監視対象の自動リセットイベントオブジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="5f291-103">Creates a monitored auto-reset event object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5f291-104">構文</span><span class="sxs-lookup"><span data-stu-id="5f291-104">Syntax</span></span>  
  
```cpp  
HRESULT CreateMonitorEvent (  
    [in]  SIZE_T cookie,  
    [out] IHostAutoEvent **ppEvent  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5f291-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="5f291-105">Parameters</span></span>  
 `cookie`  
 <span data-ttu-id="5f291-106">からイベントオブジェクトに関連付けるクッキー。</span><span class="sxs-lookup"><span data-stu-id="5f291-106">[in] A cookie to associate with the event object.</span></span>  
  
 `ppEvent`  
 <span data-ttu-id="5f291-107">入出力[IHostAutoEvent](../../../../docs/framework/unmanaged-api/hosting/ihostautoevent-interface.md)インスタンスのアドレスへのポインター。イベントオブジェクトを作成できなかった場合は null。</span><span class="sxs-lookup"><span data-stu-id="5f291-107">[out] A pointer to the address of an [IHostAutoEvent](../../../../docs/framework/unmanaged-api/hosting/ihostautoevent-interface.md) instance, or null if the event object could not be created.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="5f291-108">戻り値</span><span class="sxs-lookup"><span data-stu-id="5f291-108">Return Value</span></span>  
  
|<span data-ttu-id="5f291-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="5f291-109">HRESULT</span></span>|<span data-ttu-id="5f291-110">説明</span><span class="sxs-lookup"><span data-stu-id="5f291-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="5f291-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="5f291-111">S_OK</span></span>|<span data-ttu-id="5f291-112">`CreateMonitorEvent` が正常に返されました。</span><span class="sxs-lookup"><span data-stu-id="5f291-112">`CreateMonitorEvent` returned successfully.</span></span>|  
|<span data-ttu-id="5f291-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="5f291-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="5f291-114">共通言語ランタイム (CLR) がプロセスに読み込まれていないか、CLR がマネージコードを実行できない状態であるか、または呼び出しが正常に処理されていません。</span><span class="sxs-lookup"><span data-stu-id="5f291-114">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="5f291-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="5f291-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="5f291-116">呼び出しがタイムアウトしました。</span><span class="sxs-lookup"><span data-stu-id="5f291-116">The call timed out.</span></span>|  
|<span data-ttu-id="5f291-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="5f291-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="5f291-118">呼び出し元がロックを所有していません。</span><span class="sxs-lookup"><span data-stu-id="5f291-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="5f291-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="5f291-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="5f291-120">ブロックされたスレッドまたはファイバーが待機しているときに、イベントが取り消されました。</span><span class="sxs-lookup"><span data-stu-id="5f291-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="5f291-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="5f291-121">E_FAIL</span></span>|<span data-ttu-id="5f291-122">原因不明の致命的なエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="5f291-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="5f291-123">メソッドから E_FAIL が返された場合、そのプロセス内で CLR は使用できなくなります。</span><span class="sxs-lookup"><span data-stu-id="5f291-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="5f291-124">後続のホストメソッドの呼び出しでは、HOST_E_CLRNOTAVAILABLE が返されます。</span><span class="sxs-lookup"><span data-stu-id="5f291-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="5f291-125">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="5f291-125">E_OUTOFMEMORY</span></span>|<span data-ttu-id="5f291-126">要求されたイベントオブジェクトを作成するのに十分なメモリがありませんでした。</span><span class="sxs-lookup"><span data-stu-id="5f291-126">Not enough memory was available to create the requested event object.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5f291-127">Remarks</span><span class="sxs-lookup"><span data-stu-id="5f291-127">Remarks</span></span>  
 <span data-ttu-id="5f291-128">`CreateMonitorEvent` は、CLR がマネージ <xref:System.Threading.Monitor?displayProperty=nameWithType> 型の実装で使用する `IHostAutoEvent` を返します。</span><span class="sxs-lookup"><span data-stu-id="5f291-128">`CreateMonitorEvent` returns an `IHostAutoEvent` that the CLR uses in its implementation of the managed <xref:System.Threading.Monitor?displayProperty=nameWithType> type.</span></span> <span data-ttu-id="5f291-129">このメソッドは、`bManualReset` パラメーターに指定された `false` の値を使用して、Win32 `CreateEvent` 関数をミラー化します。</span><span class="sxs-lookup"><span data-stu-id="5f291-129">This method mirrors the Win32 `CreateEvent` function, with a value of `false` specified for the `bManualReset` parameter.</span></span>  
  
 <span data-ttu-id="5f291-130">ホストは cookie を使用して、 [ICLRSyncManager:: GetMonitorOwner](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-getmonitorowner-method.md)メソッドを呼び出すことによって、どのタスクがモニターで待機しているかを判断できます。</span><span class="sxs-lookup"><span data-stu-id="5f291-130">The host can use the cookie to determine which task is waiting on the monitor by calling the [ICLRSyncManager::GetMonitorOwner](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-getmonitorowner-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5f291-131">［要件］</span><span class="sxs-lookup"><span data-stu-id="5f291-131">Requirements</span></span>  
 <span data-ttu-id="5f291-132">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5f291-132">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5f291-133">**ヘッダー:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="5f291-133">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="5f291-134">**ライブラリ:** Mscoree.dll にリソースとして含まれています</span><span class="sxs-lookup"><span data-stu-id="5f291-134">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="5f291-135">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5f291-135">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5f291-136">関連項目</span><span class="sxs-lookup"><span data-stu-id="5f291-136">See also</span></span>

- [<span data-ttu-id="5f291-137">ICLRSyncManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="5f291-137">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)
- [<span data-ttu-id="5f291-138">IHostAutoEvent インターフェイス</span><span class="sxs-lookup"><span data-stu-id="5f291-138">IHostAutoEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostautoevent-interface.md)
- [<span data-ttu-id="5f291-139">IHostSyncManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="5f291-139">IHostSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)
- <xref:System.Threading.Monitor>
