---
title: ICLRRuntimeHost::SetHostControl メソッド
ms.date: 03/30/2017
api_name:
- ICLRRuntimeHost.SetHostControl
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRRuntimeHost::SetHostControl
helpviewer_keywords:
- SetHostControl method [.NET Framework hosting]
- ICLRRuntimeHost::SetHostControl method [.NET Framework hosting]
ms.assetid: 6136be87-e631-4756-81ed-74b66581bad4
topic_type:
- apiref
ms.openlocfilehash: 644b31ae8e8f0c51c08bcad57220a028406cfd3a
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/08/2020
ms.locfileid: "84504076"
---
# <a name="iclrruntimehostsethostcontrol-method"></a><span data-ttu-id="b470a-102">ICLRRuntimeHost::SetHostControl メソッド</span><span class="sxs-lookup"><span data-stu-id="b470a-102">ICLRRuntimeHost::SetHostControl Method</span></span>
<span data-ttu-id="b470a-103">[IHostControl インターフェイス](ihostcontrol-interface.md)のホストの実装を取得するために共通言語ランタイム (CLR) が使用できるインターフェイスポインターを設定します。</span><span class="sxs-lookup"><span data-stu-id="b470a-103">Sets the interface pointer that the common language runtime (CLR) can use to get the host's implementation of [IHostControl Interface](ihostcontrol-interface.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b470a-104">構文</span><span class="sxs-lookup"><span data-stu-id="b470a-104">Syntax</span></span>  
  
```cpp  
HRESULT SetHostControl(  
    [in] IHostControl* pHostControl  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b470a-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="b470a-105">Parameters</span></span>  
 `pHostControl`  
 <span data-ttu-id="b470a-106">から[IHostControl インターフェイス](ihostcontrol-interface.md)のホストの実装へのインターフェイスポインター。</span><span class="sxs-lookup"><span data-stu-id="b470a-106">[in] An interface pointer to the host's implementation of [IHostControl Interface](ihostcontrol-interface.md).</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="b470a-107">戻り値</span><span class="sxs-lookup"><span data-stu-id="b470a-107">Return Value</span></span>  
  
|<span data-ttu-id="b470a-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="b470a-108">HRESULT</span></span>|<span data-ttu-id="b470a-109">説明</span><span class="sxs-lookup"><span data-stu-id="b470a-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="b470a-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="b470a-110">S_OK</span></span>|<span data-ttu-id="b470a-111">`SetHostControl`正常に返されました。</span><span class="sxs-lookup"><span data-stu-id="b470a-111">`SetHostControl` returned successfully.</span></span>|  
|<span data-ttu-id="b470a-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="b470a-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="b470a-113">CLR がプロセスに読み込まれていないか、CLR がマネージドコードを実行できない状態であるか、または呼び出しが正常に処理されていません。</span><span class="sxs-lookup"><span data-stu-id="b470a-113">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="b470a-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="b470a-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="b470a-115">呼び出しがタイムアウトしました。</span><span class="sxs-lookup"><span data-stu-id="b470a-115">The call timed out.</span></span>|  
|<span data-ttu-id="b470a-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="b470a-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="b470a-117">呼び出し元がロックを所有していません。</span><span class="sxs-lookup"><span data-stu-id="b470a-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="b470a-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="b470a-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="b470a-119">ブロックされたスレッドまたはファイバーが待機しているときに、イベントが取り消されました。</span><span class="sxs-lookup"><span data-stu-id="b470a-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="b470a-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="b470a-120">E_FAIL</span></span>|<span data-ttu-id="b470a-121">原因不明の致命的なエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="b470a-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="b470a-122">メソッドが E_FAIL を返す場合、そのプロセス内で CLR は使用できなくなります。</span><span class="sxs-lookup"><span data-stu-id="b470a-122">If a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="b470a-123">後続のホストメソッドの呼び出しでは HOST_E_CLRNOTAVAILABLE が返されます。</span><span class="sxs-lookup"><span data-stu-id="b470a-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="b470a-124">E_CLR_ALREADY_STARTED</span><span class="sxs-lookup"><span data-stu-id="b470a-124">E_CLR_ALREADY_STARTED</span></span>|<span data-ttu-id="b470a-125">CLR は既に初期化されています。</span><span class="sxs-lookup"><span data-stu-id="b470a-125">The CLR has already been initialized.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b470a-126">解説</span><span class="sxs-lookup"><span data-stu-id="b470a-126">Remarks</span></span>  
 <span data-ttu-id="b470a-127">CLR が初期化される前にを呼び出す必要があり `SetHostControl` ます。つまり、 [Start メソッド](iclrruntimehost-start-method.md)を呼び出すか、任意の[メタデータインターフェイス](../metadata/metadata-interfaces.md)を使用します。</span><span class="sxs-lookup"><span data-stu-id="b470a-127">You must call `SetHostControl` before the CLR is initialized, that is, before you call [Start Method](iclrruntimehost-start-method.md) or use any of the [Metadata Interfaces](../metadata/metadata-interfaces.md).</span></span> <span data-ttu-id="b470a-128">`SetHostControl` [Corbindtoの entruntime 関数](corbindtocurrentruntime-function.md)または[Corbindtocurrentruntime 関数](corbindtoruntimeex-function.md)を呼び出した直後にを呼び出すことをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="b470a-128">It is recommended that you call `SetHostControl` immediately after calling [CorBindToCurrentRuntime Function](corbindtocurrentruntime-function.md) or [CorBindToRuntimeEx Function](corbindtoruntimeex-function.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b470a-129">要件</span><span class="sxs-lookup"><span data-stu-id="b470a-129">Requirements</span></span>  
 <span data-ttu-id="b470a-130">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b470a-130">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b470a-131">**ヘッダー:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="b470a-131">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="b470a-132">**ライブラリ:** Mscoree.dll にリソースとして含まれています</span><span class="sxs-lookup"><span data-stu-id="b470a-132">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="b470a-133">**.NET Framework のバージョン:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b470a-133">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b470a-134">関連項目</span><span class="sxs-lookup"><span data-stu-id="b470a-134">See also</span></span>

- [<span data-ttu-id="b470a-135">ICLRRuntimeHost インターフェイス</span><span class="sxs-lookup"><span data-stu-id="b470a-135">ICLRRuntimeHost Interface</span></span>](iclrruntimehost-interface.md)
- [<span data-ttu-id="b470a-136">IHostControl インターフェイス</span><span class="sxs-lookup"><span data-stu-id="b470a-136">IHostControl Interface</span></span>](ihostcontrol-interface.md)
