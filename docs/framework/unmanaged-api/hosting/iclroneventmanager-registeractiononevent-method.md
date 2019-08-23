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
ms.openlocfilehash: 36d4b0692b112a66fea3dd878c7054a083fb68ff
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2019
ms.locfileid: "69951147"
---
# <a name="iclroneventmanagerregisteractiononevent-method"></a><span data-ttu-id="5d340-102">ICLROnEventManager::RegisterActionOnEvent メソッド</span><span class="sxs-lookup"><span data-stu-id="5d340-102">ICLROnEventManager::RegisterActionOnEvent Method</span></span>
<span data-ttu-id="5d340-103">指定されたイベントのコールバックポインターを登録します。</span><span class="sxs-lookup"><span data-stu-id="5d340-103">Registers a callback pointer for the specified event.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5d340-104">構文</span><span class="sxs-lookup"><span data-stu-id="5d340-104">Syntax</span></span>  
  
```cpp  
HRESULT RegisterActionOnEvent (  
    [in] EClrEvent event,  
    [in] IActionOnCLREvent *pAction  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5d340-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="5d340-105">Parameters</span></span>  
 `event`  
 <span data-ttu-id="5d340-106">から[Eclrevent](../../../../docs/framework/unmanaged-api/hosting/eclrevent-enumeration.md)値の1つ。によって`pAction`記述されるコールバックポインターを登録するイベントを示します。</span><span class="sxs-lookup"><span data-stu-id="5d340-106">[in] One of the [EClrEvent](../../../../docs/framework/unmanaged-api/hosting/eclrevent-enumeration.md) values, indicating the event for which to register the callback pointer described by `pAction`.</span></span>  
  
 `pAction`  
 <span data-ttu-id="5d340-107">から登録されたイベントが発生したときに呼び出される[Iactiononclrevent](../../../../docs/framework/unmanaged-api/hosting/iactiononclrevent-interface.md)オブジェクトへのポインター。</span><span class="sxs-lookup"><span data-stu-id="5d340-107">[in] A pointer to an [IActionOnCLREvent](../../../../docs/framework/unmanaged-api/hosting/iactiononclrevent-interface.md) object that is called when the registered event fires.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="5d340-108">戻り値</span><span class="sxs-lookup"><span data-stu-id="5d340-108">Return Value</span></span>  
  
|<span data-ttu-id="5d340-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="5d340-109">HRESULT</span></span>|<span data-ttu-id="5d340-110">説明</span><span class="sxs-lookup"><span data-stu-id="5d340-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="5d340-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="5d340-111">S_OK</span></span>|<span data-ttu-id="5d340-112">`RegisterActionOnEvent`正常に返されました。</span><span class="sxs-lookup"><span data-stu-id="5d340-112">`RegisterActionOnEvent` returned successfully.</span></span>|  
|<span data-ttu-id="5d340-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="5d340-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="5d340-114">共通言語ランタイム (CLR) がプロセスに読み込まれていないか、CLR がマネージコードを実行できない状態であるか、または呼び出しが正常に処理されていません。</span><span class="sxs-lookup"><span data-stu-id="5d340-114">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="5d340-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="5d340-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="5d340-116">呼び出しがタイムアウトしました。</span><span class="sxs-lookup"><span data-stu-id="5d340-116">The call timed out.</span></span>|  
|<span data-ttu-id="5d340-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="5d340-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="5d340-118">呼び出し元がロックを所有していません。</span><span class="sxs-lookup"><span data-stu-id="5d340-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="5d340-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="5d340-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="5d340-120">ブロックされたスレッドまたはファイバーが待機しているときに、イベントが取り消されました。</span><span class="sxs-lookup"><span data-stu-id="5d340-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="5d340-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="5d340-121">E_FAIL</span></span>|<span data-ttu-id="5d340-122">原因不明の致命的なエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="5d340-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="5d340-123">メソッドから E_FAIL が返された後は、そのプロセス内で CLR を使用できなくなります。</span><span class="sxs-lookup"><span data-stu-id="5d340-123">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="5d340-124">後続のホストメソッドの呼び出しでは、HOST_E_CLRNOTAVAILABLE が返されます。</span><span class="sxs-lookup"><span data-stu-id="5d340-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5d340-125">Remarks</span><span class="sxs-lookup"><span data-stu-id="5d340-125">Remarks</span></span>  
 <span data-ttu-id="5d340-126">ホストは、で説明されて`EClrEvent`いる2つのイベントの種類のいずれかまたは両方のコールバックを登録できます。</span><span class="sxs-lookup"><span data-stu-id="5d340-126">The host can register callbacks for either or both of the two event types described by `EClrEvent`.</span></span> <span data-ttu-id="5d340-127">ホストは、 `ICLROnEventManager` [ICLRControl:: getclrmanager](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-getclrmanager-method.md)メソッドを呼び出すことによって、インターフェイスを取得します。</span><span class="sxs-lookup"><span data-stu-id="5d340-127">The host gets the `ICLROnEventManager` interface by calling the [ICLRControl::GetCLRManager](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-getclrmanager-method.md) method.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="5d340-128">登録する`RegisterActionOnEvent`イベントは、複数の異なるスレッドから起動して、CLR のアンロードまたは無効化を通知することができます。</span><span class="sxs-lookup"><span data-stu-id="5d340-128">The events that `RegisterActionOnEvent` registers can be fired more than once and from different threads to signal an unload or the disabling of the CLR.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5d340-129">必要条件</span><span class="sxs-lookup"><span data-stu-id="5d340-129">Requirements</span></span>  
 <span data-ttu-id="5d340-130">**・** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="5d340-130">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5d340-131">**ヘッダー:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="5d340-131">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="5d340-132">**ライブラリ**Mscoree.dll にリソースとして含まれています</span><span class="sxs-lookup"><span data-stu-id="5d340-132">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="5d340-133">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5d340-133">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5d340-134">関連項目</span><span class="sxs-lookup"><span data-stu-id="5d340-134">See also</span></span>

- [<span data-ttu-id="5d340-135">EClrEvent 列挙型</span><span class="sxs-lookup"><span data-stu-id="5d340-135">EClrEvent Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/eclrevent-enumeration.md)
- [<span data-ttu-id="5d340-136">IActionOnCLREvent インターフェイス</span><span class="sxs-lookup"><span data-stu-id="5d340-136">IActionOnCLREvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iactiononclrevent-interface.md)
- [<span data-ttu-id="5d340-137">ICLRControl インターフェイス</span><span class="sxs-lookup"><span data-stu-id="5d340-137">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)
- [<span data-ttu-id="5d340-138">ICLROnEventManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="5d340-138">ICLROnEventManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclroneventmanager-interface.md)
