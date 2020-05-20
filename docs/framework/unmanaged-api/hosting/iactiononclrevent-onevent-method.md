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
ms.openlocfilehash: a216a2925382016adeb100554bdceefdf3ee902b
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/19/2020
ms.locfileid: "83616061"
---
# <a name="iactiononclreventonevent-method"></a><span data-ttu-id="da42d-102">IActionOnCLREvent::OnEvent メソッド</span><span class="sxs-lookup"><span data-stu-id="da42d-102">IActionOnCLREvent::OnEvent Method</span></span>
<span data-ttu-id="da42d-103">[ICLROnEventManager:: RegisterActionOnEvent](iclroneventmanager-registeractiononevent-method.md)メソッドの呼び出しを使用して登録されたイベントに対してコールバックを実行します。</span><span class="sxs-lookup"><span data-stu-id="da42d-103">Performs callbacks on events that have been registered by using a call to the [ICLROnEventManager::RegisterActionOnEvent](iclroneventmanager-registeractiononevent-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="da42d-104">構文</span><span class="sxs-lookup"><span data-stu-id="da42d-104">Syntax</span></span>  
  
```cpp  
HRESULT OnEvent (  
    [in] EClrEvent event,  
    [in] PVOID     data  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="da42d-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="da42d-105">Parameters</span></span>  
 `event`  
 <span data-ttu-id="da42d-106">からイベントの種類を示す、 [Eclrevent](eclrevent-enumeration.md)の値の1つ。</span><span class="sxs-lookup"><span data-stu-id="da42d-106">[in] One of the [EClrEvent](eclrevent-enumeration.md) values, which indicates the type of event.</span></span>  
  
 `data`  
 <span data-ttu-id="da42d-107">からの詳細を格納しているオブジェクトへのポインター `event` 。</span><span class="sxs-lookup"><span data-stu-id="da42d-107">[in] A pointer to an object that contains details about `event`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="da42d-108">戻り値</span><span class="sxs-lookup"><span data-stu-id="da42d-108">Return Value</span></span>  
  
|<span data-ttu-id="da42d-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="da42d-109">HRESULT</span></span>|<span data-ttu-id="da42d-110">説明</span><span class="sxs-lookup"><span data-stu-id="da42d-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="da42d-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="da42d-111">S_OK</span></span>|<span data-ttu-id="da42d-112">`OnEvent`正常に返されました。</span><span class="sxs-lookup"><span data-stu-id="da42d-112">`OnEvent` returned successfully.</span></span>|  
|<span data-ttu-id="da42d-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="da42d-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="da42d-114">共通言語ランタイム (CLR) がプロセスに読み込まれていないか、CLR がマネージコードを実行できない状態であるか、または呼び出しが正常に処理されていません。</span><span class="sxs-lookup"><span data-stu-id="da42d-114">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="da42d-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="da42d-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="da42d-116">呼び出しがタイムアウトしました。</span><span class="sxs-lookup"><span data-stu-id="da42d-116">The call timed out.</span></span>|  
|<span data-ttu-id="da42d-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="da42d-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="da42d-118">呼び出し元がロックを所有していません。</span><span class="sxs-lookup"><span data-stu-id="da42d-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="da42d-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="da42d-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="da42d-120">ブロックされたスレッドまたはファイバーが待機しているときに、イベントが取り消されました。</span><span class="sxs-lookup"><span data-stu-id="da42d-120">An event was cancelled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="da42d-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="da42d-121">E_FAIL</span></span>|<span data-ttu-id="da42d-122">原因不明の致命的なエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="da42d-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="da42d-123">メソッドが E_FAIL を返す場合、そのプロセス内で CLR は使用できなくなります。</span><span class="sxs-lookup"><span data-stu-id="da42d-123">If a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="da42d-124">後続のホストメソッドを呼び出すと HOST_E_CLRNOTAVAILABLE が返されます。</span><span class="sxs-lookup"><span data-stu-id="da42d-124">Subsequent calls to any hosting method return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="da42d-125">解説</span><span class="sxs-lookup"><span data-stu-id="da42d-125">Remarks</span></span>  
 <span data-ttu-id="da42d-126">`data`パラメーターが、指定されていない型のオブジェクトへのポインターです。</span><span class="sxs-lookup"><span data-stu-id="da42d-126">The `data` parameter is a pointer to an object of unspecified type.</span></span> <span data-ttu-id="da42d-127">`event`パラメーターがの場合 `Event_DomainUnload` 、 `data` は、 <xref:System.AppDomain> アンロードされたの数値識別子です。</span><span class="sxs-lookup"><span data-stu-id="da42d-127">If the `event` parameter is `Event_DomainUnload`, `data` is the numeric identifier for the <xref:System.AppDomain> that was unloaded.</span></span> <span data-ttu-id="da42d-128">ホストは、この識別子をキーとして使用して適切なアクションを実行できます。</span><span class="sxs-lookup"><span data-stu-id="da42d-128">The host can take appropriate action using this identifier as a key.</span></span>  
  
 <span data-ttu-id="da42d-129">がの場合 `event` `Event_MDAFired` 、 `data` はマネージデバッグアシスタント (MDA) からのメッセージ出力を格納する[MDAInfo](../../../../docs/framework/unmanaged-api/hosting/mdainfo-structure.md)インスタンスへのポインターです。</span><span class="sxs-lookup"><span data-stu-id="da42d-129">If `event` is `Event_MDAFired`, `data` is a pointer to an [MDAInfo](../../../../docs/framework/unmanaged-api/hosting/mdainfo-structure.md) instance that contains the message output from a Managed Debugging Assistant (MDA).</span></span> <span data-ttu-id="da42d-130">Mda は、開発者がデバッグを支援する CLR の機能です。これは、特にトラップが困難なイベントに関する XML メッセージを生成することによって行われます。</span><span class="sxs-lookup"><span data-stu-id="da42d-130">MDAs are a feature of the CLR that help developers with debugging, by generating XML messages about events that are otherwise difficult to trap.</span></span> <span data-ttu-id="da42d-131">このようなメッセージは、マネージコードとアンマネージコードの間の遷移をデバッグする場合に特に役立ちます。</span><span class="sxs-lookup"><span data-stu-id="da42d-131">Such messages can be especially useful in debugging transitions between managed and unmanaged code.</span></span> <span data-ttu-id="da42d-132">詳細については、「[マネージデバッグアシスタントによるエラーの診断](../../debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="da42d-132">For more information, see [Diagnosing Errors with Managed Debugging Assistants](../../debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="da42d-133">要件</span><span class="sxs-lookup"><span data-stu-id="da42d-133">Requirements</span></span>  
 <span data-ttu-id="da42d-134">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="da42d-134">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="da42d-135">**ヘッダー:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="da42d-135">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="da42d-136">**ライブラリ:** Mscoree.dll にリソースとして含まれています</span><span class="sxs-lookup"><span data-stu-id="da42d-136">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="da42d-137">**.NET Framework のバージョン:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="da42d-137">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="da42d-138">関連項目</span><span class="sxs-lookup"><span data-stu-id="da42d-138">See also</span></span>

- [<span data-ttu-id="da42d-139">マネージド デバッグ アシスタントによるエラーの診断</span><span class="sxs-lookup"><span data-stu-id="da42d-139">Diagnosing Errors with Managed Debugging Assistants</span></span>](../../debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)
- [<span data-ttu-id="da42d-140">EClrEvent 列挙型</span><span class="sxs-lookup"><span data-stu-id="da42d-140">EClrEvent Enumeration</span></span>](eclrevent-enumeration.md)
- [<span data-ttu-id="da42d-141">IActionOnCLREvent インターフェイス</span><span class="sxs-lookup"><span data-stu-id="da42d-141">IActionOnCLREvent Interface</span></span>](iactiononclrevent-interface.md)
- [<span data-ttu-id="da42d-142">ICLRControl インターフェイス</span><span class="sxs-lookup"><span data-stu-id="da42d-142">ICLRControl Interface</span></span>](iclrcontrol-interface.md)
- [<span data-ttu-id="da42d-143">ICLROnEventManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="da42d-143">ICLROnEventManager Interface</span></span>](iclroneventmanager-interface.md)
- [<span data-ttu-id="da42d-144">MDAInfo 構造体</span><span class="sxs-lookup"><span data-stu-id="da42d-144">MDAInfo Structure</span></span>](mdainfo-structure.md)
