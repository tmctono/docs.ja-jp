---
title: ICLROnEventManager::RegisterActionOnEvent メソッド
ms.date: 03/30/2017
api_name:
- ICLROnEventManager.RegisterActionOnEvent
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLROnEventManager::RegisterActionOnEvent
helpviewer_keywords:
- ICLROnEventManager::RegisterActionOnEvent method [.NET Framework hosting]
- RegisterActionOnEvent method [.NET Framework hosting]
ms.assetid: b944cf49-918d-4c4e-993b-77d097a52550
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f86468d96d5ffbb5029562f69edb9e8579985470
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/06/2019
ms.locfileid: "57466675"
---
# <a name="iclroneventmanagerregisteractiononevent-method"></a><span data-ttu-id="59f83-102">ICLROnEventManager::RegisterActionOnEvent メソッド</span><span class="sxs-lookup"><span data-stu-id="59f83-102">ICLROnEventManager::RegisterActionOnEvent Method</span></span>
<span data-ttu-id="59f83-103">指定したイベントのコールバック ポインターを登録します。</span><span class="sxs-lookup"><span data-stu-id="59f83-103">Registers a callback pointer for the specified event.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="59f83-104">構文</span><span class="sxs-lookup"><span data-stu-id="59f83-104">Syntax</span></span>  
  
```  
HRESULT RegisterActionOnEvent (  
    [in] EClrEvent event,  
    [in] IActionOnCLREvent *pAction  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="59f83-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="59f83-105">Parameters</span></span>  
 `event`  
 <span data-ttu-id="59f83-106">[in]1 つ、 [EClrEvent](../../../../docs/framework/unmanaged-api/hosting/eclrevent-enumeration.md)で説明されているコールバック ポインターを登録するイベントを示す値`pAction`します。</span><span class="sxs-lookup"><span data-stu-id="59f83-106">[in] One of the [EClrEvent](../../../../docs/framework/unmanaged-api/hosting/eclrevent-enumeration.md) values, indicating the event for which to register the callback pointer described by `pAction`.</span></span>  
  
 `pAction`  
 <span data-ttu-id="59f83-107">[in]ポインター、 [IActionOnCLREvent](../../../../docs/framework/unmanaged-api/hosting/iactiononclrevent-interface.md)登録済みのイベントが発生したときに呼び出されるオブジェクト。</span><span class="sxs-lookup"><span data-stu-id="59f83-107">[in] A pointer to an [IActionOnCLREvent](../../../../docs/framework/unmanaged-api/hosting/iactiononclrevent-interface.md) object that is called when the registered event fires.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="59f83-108">戻り値</span><span class="sxs-lookup"><span data-stu-id="59f83-108">Return Value</span></span>  
  
|<span data-ttu-id="59f83-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="59f83-109">HRESULT</span></span>|<span data-ttu-id="59f83-110">説明</span><span class="sxs-lookup"><span data-stu-id="59f83-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="59f83-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="59f83-111">S_OK</span></span>|<span data-ttu-id="59f83-112">`RegisterActionOnEvent` 正常に返されます。</span><span class="sxs-lookup"><span data-stu-id="59f83-112">`RegisterActionOnEvent` returned successfully.</span></span>|  
|<span data-ttu-id="59f83-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="59f83-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="59f83-114">共通言語ランタイム (CLR) は、プロセスに読み込まれていないか、CLR は状態をマネージ コードを実行または呼び出しを正常に処理ができません。</span><span class="sxs-lookup"><span data-stu-id="59f83-114">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="59f83-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="59f83-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="59f83-116">呼び出しがタイムアウトになりました。</span><span class="sxs-lookup"><span data-stu-id="59f83-116">The call timed out.</span></span>|  
|<span data-ttu-id="59f83-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="59f83-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="59f83-118">呼び出し元がロックを所有していません。</span><span class="sxs-lookup"><span data-stu-id="59f83-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="59f83-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="59f83-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="59f83-120">イベントがキャンセルされましたブロックされたスレッドまたはファイバーが待機しています。</span><span class="sxs-lookup"><span data-stu-id="59f83-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="59f83-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="59f83-121">E_FAIL</span></span>|<span data-ttu-id="59f83-122">不明な致命的なエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="59f83-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="59f83-123">メソッドには、E_FAIL が返された、後に、CLR は、プロセス内で使用可能ではなくなりました。</span><span class="sxs-lookup"><span data-stu-id="59f83-123">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="59f83-124">メソッドをホストする後続の呼び出しには、HOST_E_CLRNOTAVAILABLE が返されます。</span><span class="sxs-lookup"><span data-stu-id="59f83-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="59f83-125">Remarks</span><span class="sxs-lookup"><span data-stu-id="59f83-125">Remarks</span></span>  
 <span data-ttu-id="59f83-126">ホストは、どちらか一方または両方で説明されている 2 つのイベントの種類のコールバックを登録できる`EClrEvent`します。</span><span class="sxs-lookup"><span data-stu-id="59f83-126">The host can register callbacks for either or both of the two event types described by `EClrEvent`.</span></span> <span data-ttu-id="59f83-127">ホストの取得、`ICLROnEventManager`インターフェイスを呼び出すことによって、 [iclrcontrol::getclrmanager](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-getclrmanager-method.md)メソッド。</span><span class="sxs-lookup"><span data-stu-id="59f83-127">The host gets the `ICLROnEventManager` interface by calling the [ICLRControl::GetCLRManager](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-getclrmanager-method.md) method.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="59f83-128">イベントを`RegisterActionOnEvent`レジスタは 2 回以上、アンロード、または CLR の無効化を通知する別のスレッドから発生することができます。</span><span class="sxs-lookup"><span data-stu-id="59f83-128">The events that `RegisterActionOnEvent` registers can be fired more than once and from different threads to signal an unload or the disabling of the CLR.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="59f83-129">必要条件</span><span class="sxs-lookup"><span data-stu-id="59f83-129">Requirements</span></span>  
 <span data-ttu-id="59f83-130">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="59f83-130">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="59f83-131">**ヘッダー:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="59f83-131">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="59f83-132">**ライブラリ:** MSCorEE.dll でリソースとして含まれます</span><span class="sxs-lookup"><span data-stu-id="59f83-132">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="59f83-133">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="59f83-133">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="59f83-134">関連項目</span><span class="sxs-lookup"><span data-stu-id="59f83-134">See also</span></span>
- [<span data-ttu-id="59f83-135">EClrEvent 列挙型</span><span class="sxs-lookup"><span data-stu-id="59f83-135">EClrEvent Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/eclrevent-enumeration.md)
- [<span data-ttu-id="59f83-136">IActionOnCLREvent インターフェイス</span><span class="sxs-lookup"><span data-stu-id="59f83-136">IActionOnCLREvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iactiononclrevent-interface.md)
- [<span data-ttu-id="59f83-137">ICLRControl インターフェイス</span><span class="sxs-lookup"><span data-stu-id="59f83-137">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)
- [<span data-ttu-id="59f83-138">ICLROnEventManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="59f83-138">ICLROnEventManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclroneventmanager-interface.md)
