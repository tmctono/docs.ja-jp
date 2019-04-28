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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 12b0e32ab46b3e8ba5120da4b16a10db85f105a6
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61696302"
---
# <a name="ihostsyncmanagercreatemonitorevent-method"></a><span data-ttu-id="fc5c0-102">IHostSyncManager::CreateMonitorEvent メソッド</span><span class="sxs-lookup"><span data-stu-id="fc5c0-102">IHostSyncManager::CreateMonitorEvent Method</span></span>
<span data-ttu-id="fc5c0-103">監視対象の自動リセット イベント オブジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="fc5c0-103">Creates a monitored auto-reset event object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fc5c0-104">構文</span><span class="sxs-lookup"><span data-stu-id="fc5c0-104">Syntax</span></span>  
  
```  
HRESULT CreateMonitorEvent (  
    [in]  SIZE_T cookie,  
    [out] IHostAutoEvent **ppEvent  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="fc5c0-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="fc5c0-105">Parameters</span></span>  
 `cookie`  
 <span data-ttu-id="fc5c0-106">[in]イベント オブジェクトに関連付けるクッキー。</span><span class="sxs-lookup"><span data-stu-id="fc5c0-106">[in] A cookie to associate with the event object.</span></span>  
  
 `ppEvent`  
 <span data-ttu-id="fc5c0-107">[out]アドレスへのポインター、 [IHostAutoEvent](../../../../docs/framework/unmanaged-api/hosting/ihostautoevent-interface.md)インスタンス、または null の場合は、イベント オブジェクトを作成できませんでした。</span><span class="sxs-lookup"><span data-stu-id="fc5c0-107">[out] A pointer to the address of an [IHostAutoEvent](../../../../docs/framework/unmanaged-api/hosting/ihostautoevent-interface.md) instance, or null if the event object could not be created.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="fc5c0-108">戻り値</span><span class="sxs-lookup"><span data-stu-id="fc5c0-108">Return Value</span></span>  
  
|<span data-ttu-id="fc5c0-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="fc5c0-109">HRESULT</span></span>|<span data-ttu-id="fc5c0-110">説明</span><span class="sxs-lookup"><span data-stu-id="fc5c0-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="fc5c0-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="fc5c0-111">S_OK</span></span>|<span data-ttu-id="fc5c0-112">`CreateMonitorEvent` 正常に返されます。</span><span class="sxs-lookup"><span data-stu-id="fc5c0-112">`CreateMonitorEvent` returned successfully.</span></span>|  
|<span data-ttu-id="fc5c0-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="fc5c0-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="fc5c0-114">共通言語ランタイム (CLR) は、プロセスに読み込まれていないか、CLR は状態をマネージ コードを実行または呼び出しを正常に処理ができません。</span><span class="sxs-lookup"><span data-stu-id="fc5c0-114">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="fc5c0-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="fc5c0-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="fc5c0-116">呼び出しがタイムアウトになりました。</span><span class="sxs-lookup"><span data-stu-id="fc5c0-116">The call timed out.</span></span>|  
|<span data-ttu-id="fc5c0-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="fc5c0-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="fc5c0-118">呼び出し元がロックを所有していません。</span><span class="sxs-lookup"><span data-stu-id="fc5c0-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="fc5c0-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="fc5c0-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="fc5c0-120">イベントがキャンセルされましたブロックされたスレッドまたはファイバーが待機しています。</span><span class="sxs-lookup"><span data-stu-id="fc5c0-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="fc5c0-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="fc5c0-121">E_FAIL</span></span>|<span data-ttu-id="fc5c0-122">不明な致命的なエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="fc5c0-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="fc5c0-123">メソッドには、E_FAIL が返される、ときに、CLR は、プロセス内で使用可能ではなくなりました。</span><span class="sxs-lookup"><span data-stu-id="fc5c0-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="fc5c0-124">メソッドをホストする後続の呼び出しには、HOST_E_CLRNOTAVAILABLE が返されます。</span><span class="sxs-lookup"><span data-stu-id="fc5c0-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="fc5c0-125">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="fc5c0-125">E_OUTOFMEMORY</span></span>|<span data-ttu-id="fc5c0-126">メモリ不足は、要求されたイベント オブジェクトを作成できませんでした。</span><span class="sxs-lookup"><span data-stu-id="fc5c0-126">Not enough memory was available to create the requested event object.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="fc5c0-127">Remarks</span><span class="sxs-lookup"><span data-stu-id="fc5c0-127">Remarks</span></span>  
 <span data-ttu-id="fc5c0-128">`CreateMonitorEvent` 返します、 `IHostAutoEvent` CLR が、管理対象の実装で使用する<xref:System.Threading.Monitor?displayProperty=nameWithType>型。</span><span class="sxs-lookup"><span data-stu-id="fc5c0-128">`CreateMonitorEvent` returns an `IHostAutoEvent` that the CLR uses in its implementation of the managed <xref:System.Threading.Monitor?displayProperty=nameWithType> type.</span></span> <span data-ttu-id="fc5c0-129">このメソッドは、Win32 をミラー化`CreateEvent`関数の値を持つ`false`の指定、`bManualReset`パラメーター。</span><span class="sxs-lookup"><span data-stu-id="fc5c0-129">This method mirrors the Win32 `CreateEvent` function, with a value of `false` specified for the `bManualReset` parameter.</span></span>  
  
 <span data-ttu-id="fc5c0-130">ホストは、cookie を使用して、どのタスクが呼び出すことで、モニターの待機しているかを判断する、 [iclrsyncmanager::getmonitorowner](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-getmonitorowner-method.md)メソッド。</span><span class="sxs-lookup"><span data-stu-id="fc5c0-130">The host can use the cookie to determine which task is waiting on the monitor by calling the [ICLRSyncManager::GetMonitorOwner](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-getmonitorowner-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fc5c0-131">必要条件</span><span class="sxs-lookup"><span data-stu-id="fc5c0-131">Requirements</span></span>  
 <span data-ttu-id="fc5c0-132">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="fc5c0-132">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fc5c0-133">**ヘッダー:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="fc5c0-133">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="fc5c0-134">**ライブラリ:** MSCorEE.dll でリソースとして含まれます</span><span class="sxs-lookup"><span data-stu-id="fc5c0-134">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="fc5c0-135">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fc5c0-135">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fc5c0-136">関連項目</span><span class="sxs-lookup"><span data-stu-id="fc5c0-136">See also</span></span>

- [<span data-ttu-id="fc5c0-137">ICLRSyncManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="fc5c0-137">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)
- [<span data-ttu-id="fc5c0-138">IHostAutoEvent インターフェイス</span><span class="sxs-lookup"><span data-stu-id="fc5c0-138">IHostAutoEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostautoevent-interface.md)
- [<span data-ttu-id="fc5c0-139">IHostSyncManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="fc5c0-139">IHostSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)
- <xref:System.Threading.Monitor>
