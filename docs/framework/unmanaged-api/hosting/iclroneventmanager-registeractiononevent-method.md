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
ms.openlocfilehash: 4068166438c524ad1c0ed4efe455b1f66b6641d5
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73140825"
---
# <a name="iclroneventmanagerregisteractiononevent-method"></a><span data-ttu-id="277a9-102">ICLROnEventManager::RegisterActionOnEvent メソッド</span><span class="sxs-lookup"><span data-stu-id="277a9-102">ICLROnEventManager::RegisterActionOnEvent Method</span></span>
<span data-ttu-id="277a9-103">指定されたイベントのコールバックポインターを登録します。</span><span class="sxs-lookup"><span data-stu-id="277a9-103">Registers a callback pointer for the specified event.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="277a9-104">構文</span><span class="sxs-lookup"><span data-stu-id="277a9-104">Syntax</span></span>  
  
```cpp  
HRESULT RegisterActionOnEvent (  
    [in] EClrEvent event,  
    [in] IActionOnCLREvent *pAction  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="277a9-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="277a9-105">Parameters</span></span>  
 `event`  
 <span data-ttu-id="277a9-106">から`pAction`によって記述されるコールバックポインターを登録するイベントを示す、 [Eclrevent](../../../../docs/framework/unmanaged-api/hosting/eclrevent-enumeration.md)値の1つ。</span><span class="sxs-lookup"><span data-stu-id="277a9-106">[in] One of the [EClrEvent](../../../../docs/framework/unmanaged-api/hosting/eclrevent-enumeration.md) values, indicating the event for which to register the callback pointer described by `pAction`.</span></span>  
  
 `pAction`  
 <span data-ttu-id="277a9-107">から登録されたイベントが発生したときに呼び出される[Iactiononclrevent](../../../../docs/framework/unmanaged-api/hosting/iactiononclrevent-interface.md)オブジェクトへのポインター。</span><span class="sxs-lookup"><span data-stu-id="277a9-107">[in] A pointer to an [IActionOnCLREvent](../../../../docs/framework/unmanaged-api/hosting/iactiononclrevent-interface.md) object that is called when the registered event fires.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="277a9-108">戻り値</span><span class="sxs-lookup"><span data-stu-id="277a9-108">Return Value</span></span>  
  
|<span data-ttu-id="277a9-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="277a9-109">HRESULT</span></span>|<span data-ttu-id="277a9-110">説明</span><span class="sxs-lookup"><span data-stu-id="277a9-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="277a9-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="277a9-111">S_OK</span></span>|<span data-ttu-id="277a9-112">`RegisterActionOnEvent` が正常に返されました。</span><span class="sxs-lookup"><span data-stu-id="277a9-112">`RegisterActionOnEvent` returned successfully.</span></span>|  
|<span data-ttu-id="277a9-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="277a9-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="277a9-114">共通言語ランタイム (CLR) がプロセスに読み込まれていないか、CLR がマネージコードを実行できない状態であるか、または呼び出しが正常に処理されていません。</span><span class="sxs-lookup"><span data-stu-id="277a9-114">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="277a9-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="277a9-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="277a9-116">呼び出しがタイムアウトしました。</span><span class="sxs-lookup"><span data-stu-id="277a9-116">The call timed out.</span></span>|  
|<span data-ttu-id="277a9-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="277a9-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="277a9-118">呼び出し元がロックを所有していません。</span><span class="sxs-lookup"><span data-stu-id="277a9-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="277a9-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="277a9-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="277a9-120">ブロックされたスレッドまたはファイバーが待機しているときに、イベントが取り消されました。</span><span class="sxs-lookup"><span data-stu-id="277a9-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="277a9-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="277a9-121">E_FAIL</span></span>|<span data-ttu-id="277a9-122">原因不明の致命的なエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="277a9-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="277a9-123">メソッドから E_FAIL が返された後は、そのプロセス内で CLR を使用できなくなります。</span><span class="sxs-lookup"><span data-stu-id="277a9-123">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="277a9-124">後続のホストメソッドの呼び出しでは、HOST_E_CLRNOTAVAILABLE が返されます。</span><span class="sxs-lookup"><span data-stu-id="277a9-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="277a9-125">Remarks</span><span class="sxs-lookup"><span data-stu-id="277a9-125">Remarks</span></span>  
 <span data-ttu-id="277a9-126">ホストは、`EClrEvent`で説明されている2つのイベントの種類のいずれかまたは両方のコールバックを登録できます。</span><span class="sxs-lookup"><span data-stu-id="277a9-126">The host can register callbacks for either or both of the two event types described by `EClrEvent`.</span></span> <span data-ttu-id="277a9-127">ホストは、 [ICLRControl:: GetCLRManager](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-getclrmanager-method.md)メソッドを呼び出すことによって `ICLROnEventManager` インターフェイスを取得します。</span><span class="sxs-lookup"><span data-stu-id="277a9-127">The host gets the `ICLROnEventManager` interface by calling the [ICLRControl::GetCLRManager](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-getclrmanager-method.md) method.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="277a9-128">レジスタを `RegisterActionOnEvent` するイベントを複数回起動したり、さまざまなスレッドから CLR のアンロードまたは無効化を通知したりすることができます。</span><span class="sxs-lookup"><span data-stu-id="277a9-128">The events that `RegisterActionOnEvent` registers can be fired more than once and from different threads to signal an unload or the disabling of the CLR.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="277a9-129">［要件］</span><span class="sxs-lookup"><span data-stu-id="277a9-129">Requirements</span></span>  
 <span data-ttu-id="277a9-130">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="277a9-130">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="277a9-131">**ヘッダー:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="277a9-131">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="277a9-132">**ライブラリ:** Mscoree.dll にリソースとして含まれています</span><span class="sxs-lookup"><span data-stu-id="277a9-132">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="277a9-133">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="277a9-133">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="277a9-134">関連項目</span><span class="sxs-lookup"><span data-stu-id="277a9-134">See also</span></span>

- [<span data-ttu-id="277a9-135">EClrEvent 列挙型</span><span class="sxs-lookup"><span data-stu-id="277a9-135">EClrEvent Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/eclrevent-enumeration.md)
- [<span data-ttu-id="277a9-136">IActionOnCLREvent インターフェイス</span><span class="sxs-lookup"><span data-stu-id="277a9-136">IActionOnCLREvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iactiononclrevent-interface.md)
- [<span data-ttu-id="277a9-137">ICLRControl インターフェイス</span><span class="sxs-lookup"><span data-stu-id="277a9-137">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)
- [<span data-ttu-id="277a9-138">ICLROnEventManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="277a9-138">ICLROnEventManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclroneventmanager-interface.md)
