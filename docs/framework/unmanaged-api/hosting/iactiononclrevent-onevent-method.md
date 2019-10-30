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
ms.openlocfilehash: 98807717fc913052dae15f9f3cbd462d4f537ad4
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73126924"
---
# <a name="iactiononclreventonevent-method"></a><span data-ttu-id="a642f-102">IActionOnCLREvent::OnEvent メソッド</span><span class="sxs-lookup"><span data-stu-id="a642f-102">IActionOnCLREvent::OnEvent Method</span></span>
<span data-ttu-id="a642f-103">[ICLROnEventManager:: RegisterActionOnEvent](../../../../docs/framework/unmanaged-api/hosting/iclroneventmanager-registeractiononevent-method.md)メソッドの呼び出しを使用して登録されたイベントに対してコールバックを実行します。</span><span class="sxs-lookup"><span data-stu-id="a642f-103">Performs callbacks on events that have been registered by using a call to the [ICLROnEventManager::RegisterActionOnEvent](../../../../docs/framework/unmanaged-api/hosting/iclroneventmanager-registeractiononevent-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a642f-104">構文</span><span class="sxs-lookup"><span data-stu-id="a642f-104">Syntax</span></span>  
  
```cpp  
HRESULT OnEvent (  
    [in] EClrEvent event,  
    [in] PVOID     data  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a642f-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="a642f-105">Parameters</span></span>  
 `event`  
 <span data-ttu-id="a642f-106">からイベントの種類を示す、 [Eclrevent](../../../../docs/framework/unmanaged-api/hosting/eclrevent-enumeration.md)の値の1つ。</span><span class="sxs-lookup"><span data-stu-id="a642f-106">[in] One of the [EClrEvent](../../../../docs/framework/unmanaged-api/hosting/eclrevent-enumeration.md) values, which indicates the type of event.</span></span>  
  
 `data`  
 <span data-ttu-id="a642f-107">から`event`に関する詳細を格納しているオブジェクトへのポインター。</span><span class="sxs-lookup"><span data-stu-id="a642f-107">[in] A pointer to an object that contains details about `event`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="a642f-108">戻り値</span><span class="sxs-lookup"><span data-stu-id="a642f-108">Return Value</span></span>  
  
|<span data-ttu-id="a642f-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="a642f-109">HRESULT</span></span>|<span data-ttu-id="a642f-110">説明</span><span class="sxs-lookup"><span data-stu-id="a642f-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="a642f-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="a642f-111">S_OK</span></span>|<span data-ttu-id="a642f-112">`OnEvent` が正常に返されました。</span><span class="sxs-lookup"><span data-stu-id="a642f-112">`OnEvent` returned successfully.</span></span>|  
|<span data-ttu-id="a642f-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="a642f-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="a642f-114">共通言語ランタイム (CLR) がプロセスに読み込まれていないか、CLR がマネージコードを実行できない状態であるか、または呼び出しが正常に処理されていません。</span><span class="sxs-lookup"><span data-stu-id="a642f-114">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="a642f-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="a642f-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="a642f-116">呼び出しがタイムアウトしました。</span><span class="sxs-lookup"><span data-stu-id="a642f-116">The call timed out.</span></span>|  
|<span data-ttu-id="a642f-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="a642f-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="a642f-118">呼び出し元がロックを所有していません。</span><span class="sxs-lookup"><span data-stu-id="a642f-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="a642f-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="a642f-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="a642f-120">ブロックされたスレッドまたはファイバーが待機しているときに、イベントが取り消されました。</span><span class="sxs-lookup"><span data-stu-id="a642f-120">An event was cancelled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="a642f-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="a642f-121">E_FAIL</span></span>|<span data-ttu-id="a642f-122">原因不明の致命的なエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="a642f-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="a642f-123">メソッドから E_FAIL が返された場合、そのプロセス内で CLR は使用できなくなります。</span><span class="sxs-lookup"><span data-stu-id="a642f-123">If a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="a642f-124">後続のホストメソッドの呼び出しでは、HOST_E_CLRNOTAVAILABLE が返されます。</span><span class="sxs-lookup"><span data-stu-id="a642f-124">Subsequent calls to any hosting method return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a642f-125">Remarks</span><span class="sxs-lookup"><span data-stu-id="a642f-125">Remarks</span></span>  
 <span data-ttu-id="a642f-126">`data` パラメーターは、指定されていない型のオブジェクトへのポインターです。</span><span class="sxs-lookup"><span data-stu-id="a642f-126">The `data` parameter is a pointer to an object of unspecified type.</span></span> <span data-ttu-id="a642f-127">`event` パラメーターが `Event_DomainUnload`の場合、`data` は、アンロードされた <xref:System.AppDomain> の数値識別子です。</span><span class="sxs-lookup"><span data-stu-id="a642f-127">If the `event` parameter is `Event_DomainUnload`, `data` is the numeric identifier for the <xref:System.AppDomain> that was unloaded.</span></span> <span data-ttu-id="a642f-128">ホストは、この識別子をキーとして使用して適切なアクションを実行できます。</span><span class="sxs-lookup"><span data-stu-id="a642f-128">The host can take appropriate action using this identifier as a key.</span></span>  
  
 <span data-ttu-id="a642f-129">`event` が `Event_MDAFired`場合、`data` は、マネージデバッグアシスタント (MDA) からのメッセージ出力を含む[MDAInfo](../../../../docs/framework/unmanaged-api/hosting/mdainfo-structure.md)インスタンスへのポインターです。</span><span class="sxs-lookup"><span data-stu-id="a642f-129">If `event` is `Event_MDAFired`, `data` is a pointer to an [MDAInfo](../../../../docs/framework/unmanaged-api/hosting/mdainfo-structure.md) instance that contains the message output from a Managed Debugging Assistant (MDA).</span></span> <span data-ttu-id="a642f-130">Mda は、開発者がデバッグを支援する CLR の機能です。これは、特にトラップが困難なイベントに関する XML メッセージを生成することによって行われます。</span><span class="sxs-lookup"><span data-stu-id="a642f-130">MDAs are a feature of the CLR that help developers with debugging, by generating XML messages about events that are otherwise difficult to trap.</span></span> <span data-ttu-id="a642f-131">このようなメッセージは、マネージコードとアンマネージコードの間の遷移をデバッグする場合に特に役立ちます。</span><span class="sxs-lookup"><span data-stu-id="a642f-131">Such messages can be especially useful in debugging transitions between managed and unmanaged code.</span></span> <span data-ttu-id="a642f-132">詳細については、「[マネージデバッグアシスタントによるエラーの診断](../../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a642f-132">For more information, see [Diagnosing Errors with Managed Debugging Assistants](../../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a642f-133">［要件］</span><span class="sxs-lookup"><span data-stu-id="a642f-133">Requirements</span></span>  
 <span data-ttu-id="a642f-134">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a642f-134">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a642f-135">**ヘッダー:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="a642f-135">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="a642f-136">**ライブラリ:** Mscoree.dll にリソースとして含まれています</span><span class="sxs-lookup"><span data-stu-id="a642f-136">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="a642f-137">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a642f-137">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a642f-138">関連項目</span><span class="sxs-lookup"><span data-stu-id="a642f-138">See also</span></span>

- [<span data-ttu-id="a642f-139">マネージド デバッグ アシスタントによるエラーの診断</span><span class="sxs-lookup"><span data-stu-id="a642f-139">Diagnosing Errors with Managed Debugging Assistants</span></span>](../../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)
- [<span data-ttu-id="a642f-140">EClrEvent 列挙型</span><span class="sxs-lookup"><span data-stu-id="a642f-140">EClrEvent Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/eclrevent-enumeration.md)
- [<span data-ttu-id="a642f-141">IActionOnCLREvent インターフェイス</span><span class="sxs-lookup"><span data-stu-id="a642f-141">IActionOnCLREvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iactiononclrevent-interface.md)
- [<span data-ttu-id="a642f-142">ICLRControl インターフェイス</span><span class="sxs-lookup"><span data-stu-id="a642f-142">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)
- [<span data-ttu-id="a642f-143">ICLROnEventManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="a642f-143">ICLROnEventManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclroneventmanager-interface.md)
- [<span data-ttu-id="a642f-144">MDAInfo 構造体</span><span class="sxs-lookup"><span data-stu-id="a642f-144">MDAInfo Structure</span></span>](../../../../docs/framework/unmanaged-api/hosting/mdainfo-structure.md)
