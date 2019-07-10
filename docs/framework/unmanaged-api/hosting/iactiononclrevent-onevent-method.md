---
title: IActionOnCLREvent::OnEvent メソッド
ms.date: 03/30/2017
api_name:
- IActionOnCLREvent.OnEvent
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IActionOnCLREvent::OnEvent
helpviewer_keywords:
- OnEvent method [.NET Framework hosting]
- IActionOnCLREvent::OnEvent method [.NET Framework hosting]
ms.assetid: 0970f10c-4304-4c12-91c0-83e51455afb4
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 777cf1084f77587b83ff63a02ba84d474be0f87c
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67757838"
---
# <a name="iactiononclreventonevent-method"></a><span data-ttu-id="e0da2-102">IActionOnCLREvent::OnEvent メソッド</span><span class="sxs-lookup"><span data-stu-id="e0da2-102">IActionOnCLREvent::OnEvent Method</span></span>
<span data-ttu-id="e0da2-103">呼び出しを使用して登録されているイベントのコールバックを実行、 [iclroneventmanager::registeractiononevent](../../../../docs/framework/unmanaged-api/hosting/iclroneventmanager-registeractiononevent-method.md)メソッド。</span><span class="sxs-lookup"><span data-stu-id="e0da2-103">Performs callbacks on events that have been registered by using a call to the [ICLROnEventManager::RegisterActionOnEvent](../../../../docs/framework/unmanaged-api/hosting/iclroneventmanager-registeractiononevent-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e0da2-104">構文</span><span class="sxs-lookup"><span data-stu-id="e0da2-104">Syntax</span></span>  
  
```cpp  
HRESULT OnEvent (  
    [in] EClrEvent event,  
    [in] PVOID     data  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e0da2-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="e0da2-105">Parameters</span></span>  
 `event`  
 <span data-ttu-id="e0da2-106">[in]1 つ、 [EClrEvent](../../../../docs/framework/unmanaged-api/hosting/eclrevent-enumeration.md)値で、イベントの種類を示します。</span><span class="sxs-lookup"><span data-stu-id="e0da2-106">[in] One of the [EClrEvent](../../../../docs/framework/unmanaged-api/hosting/eclrevent-enumeration.md) values, which indicates the type of event.</span></span>  
  
 `data`  
 <span data-ttu-id="e0da2-107">[in]についての詳細を格納しているオブジェクトへのポインター`event`します。</span><span class="sxs-lookup"><span data-stu-id="e0da2-107">[in] A pointer to an object that contains details about `event`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="e0da2-108">戻り値</span><span class="sxs-lookup"><span data-stu-id="e0da2-108">Return Value</span></span>  
  
|<span data-ttu-id="e0da2-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="e0da2-109">HRESULT</span></span>|<span data-ttu-id="e0da2-110">説明</span><span class="sxs-lookup"><span data-stu-id="e0da2-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="e0da2-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="e0da2-111">S_OK</span></span>|<span data-ttu-id="e0da2-112">`OnEvent` 正常に返されます。</span><span class="sxs-lookup"><span data-stu-id="e0da2-112">`OnEvent` returned successfully.</span></span>|  
|<span data-ttu-id="e0da2-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="e0da2-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="e0da2-114">共通言語ランタイム (CLR) は、プロセスに読み込まれていないか、CLR は状態をマネージ コードを実行または呼び出しを正常に処理ができません。</span><span class="sxs-lookup"><span data-stu-id="e0da2-114">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="e0da2-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="e0da2-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="e0da2-116">呼び出しがタイムアウトになりました。</span><span class="sxs-lookup"><span data-stu-id="e0da2-116">The call timed out.</span></span>|  
|<span data-ttu-id="e0da2-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="e0da2-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="e0da2-118">呼び出し元がロックを所有していません。</span><span class="sxs-lookup"><span data-stu-id="e0da2-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="e0da2-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="e0da2-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="e0da2-120">イベントがキャンセルされましたブロックされたスレッドまたはファイバーが待機しています。</span><span class="sxs-lookup"><span data-stu-id="e0da2-120">An event was cancelled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="e0da2-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="e0da2-121">E_FAIL</span></span>|<span data-ttu-id="e0da2-122">不明な致命的なエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="e0da2-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="e0da2-123">メソッドから E_FAIL が返された場合、CLR は、プロセス内で使用可能ではなくなりました。</span><span class="sxs-lookup"><span data-stu-id="e0da2-123">If a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="e0da2-124">ホスティングのメッソドに後続の呼び出しには、HOST_E_CLRNOTAVAILABLE が返されます。</span><span class="sxs-lookup"><span data-stu-id="e0da2-124">Subsequent calls to any hosting method return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e0da2-125">Remarks</span><span class="sxs-lookup"><span data-stu-id="e0da2-125">Remarks</span></span>  
 <span data-ttu-id="e0da2-126">`data`パラメーターが指定されていない型のオブジェクトへのポインター。</span><span class="sxs-lookup"><span data-stu-id="e0da2-126">The `data` parameter is a pointer to an object of unspecified type.</span></span> <span data-ttu-id="e0da2-127">場合、`event`パラメーターが`Event_DomainUnload`、`data`の数値識別子、<xref:System.AppDomain>アンロードされました。</span><span class="sxs-lookup"><span data-stu-id="e0da2-127">If the `event` parameter is `Event_DomainUnload`, `data` is the numeric identifier for the <xref:System.AppDomain> that was unloaded.</span></span> <span data-ttu-id="e0da2-128">ホストは、キーとしてこの識別子を使用して適切なアクションを実行できます。</span><span class="sxs-lookup"><span data-stu-id="e0da2-128">The host can take appropriate action using this identifier as a key.</span></span>  
  
 <span data-ttu-id="e0da2-129">場合`event`は`Event_MDAFired`、`data`へのポインター、 [MDAInfo](../../../../docs/framework/unmanaged-api/hosting/mdainfo-structure.md)メッセージ出力から、マネージ デバッグ アシスタント (MDA) が含まれているインスタンス。</span><span class="sxs-lookup"><span data-stu-id="e0da2-129">If `event` is `Event_MDAFired`, `data` is a pointer to an [MDAInfo](../../../../docs/framework/unmanaged-api/hosting/mdainfo-structure.md) instance that contains the message output from a Managed Debugging Assistant (MDA).</span></span> <span data-ttu-id="e0da2-130">Mda は、トラップが困難な場合はイベントに関する XML メッセージを生成することによって、デバッグを支援する CLR の機能です。</span><span class="sxs-lookup"><span data-stu-id="e0da2-130">MDAs are a feature of the CLR that help developers with debugging, by generating XML messages about events that are otherwise difficult to trap.</span></span> <span data-ttu-id="e0da2-131">このようなメッセージは、マネージ コードとアンマネージ コード間の遷移のデバッグに特に便利です。</span><span class="sxs-lookup"><span data-stu-id="e0da2-131">Such messages can be especially useful in debugging transitions between managed and unmanaged code.</span></span> <span data-ttu-id="e0da2-132">詳細については、次を参照してください。[マネージ デバッグ アシスタントによるエラーの診断](../../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)します。</span><span class="sxs-lookup"><span data-stu-id="e0da2-132">For more information, see [Diagnosing Errors with Managed Debugging Assistants](../../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e0da2-133">必要条件</span><span class="sxs-lookup"><span data-stu-id="e0da2-133">Requirements</span></span>  
 <span data-ttu-id="e0da2-134">**プラットフォーム:** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="e0da2-134">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e0da2-135">**ヘッダー:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="e0da2-135">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="e0da2-136">**ライブラリ:** MSCorEE.dll でリソースとして含まれます</span><span class="sxs-lookup"><span data-stu-id="e0da2-136">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="e0da2-137">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e0da2-137">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e0da2-138">関連項目</span><span class="sxs-lookup"><span data-stu-id="e0da2-138">See also</span></span>

- [<span data-ttu-id="e0da2-139">マネージド デバッグ アシスタントによるエラーの診断</span><span class="sxs-lookup"><span data-stu-id="e0da2-139">Diagnosing Errors with Managed Debugging Assistants</span></span>](../../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)
- [<span data-ttu-id="e0da2-140">EClrEvent 列挙型</span><span class="sxs-lookup"><span data-stu-id="e0da2-140">EClrEvent Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/eclrevent-enumeration.md)
- [<span data-ttu-id="e0da2-141">IActionOnCLREvent インターフェイス</span><span class="sxs-lookup"><span data-stu-id="e0da2-141">IActionOnCLREvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iactiononclrevent-interface.md)
- [<span data-ttu-id="e0da2-142">ICLRControl インターフェイス</span><span class="sxs-lookup"><span data-stu-id="e0da2-142">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)
- [<span data-ttu-id="e0da2-143">ICLROnEventManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="e0da2-143">ICLROnEventManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclroneventmanager-interface.md)
- [<span data-ttu-id="e0da2-144">MDAInfo 構造体</span><span class="sxs-lookup"><span data-stu-id="e0da2-144">MDAInfo Structure</span></span>](../../../../docs/framework/unmanaged-api/hosting/mdainfo-structure.md)
