---
title: ICLRDebugManager::IsDebuggerAttached メソッド
ms.date: 03/30/2017
api_name:
- ICLRDebugManager.IsDebuggerAttached
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRDebugManager::IsDebuggerAttached
helpviewer_keywords:
- IsDebuggerAttached method, ICLRDebugManager interface [.NET Framework hosting]
- ICLRDebugManager::IsDebuggerAttached method [.NET Framework hosting]
ms.assetid: 2f105fe0-f52d-49c5-bda5-583fb27e3aa6
topic_type:
- apiref
ms.openlocfilehash: a21391f52a27e7f7a3abe533499c6b2581ec4a73
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/19/2020
ms.locfileid: "83615751"
---
# <a name="iclrdebugmanagerisdebuggerattached-method"></a><span data-ttu-id="29b95-102">ICLRDebugManager::IsDebuggerAttached メソッド</span><span class="sxs-lookup"><span data-stu-id="29b95-102">ICLRDebugManager::IsDebuggerAttached Method</span></span>
<span data-ttu-id="29b95-103">デバッガーがプロセスにアタッチされているかどうかを示す値を取得します。</span><span class="sxs-lookup"><span data-stu-id="29b95-103">Gets a value that indicates whether a debugger is attached to the process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="29b95-104">構文</span><span class="sxs-lookup"><span data-stu-id="29b95-104">Syntax</span></span>  
  
```cpp  
HRESULT IsDebuggerAttached (  
    [out] BOOL *pbAttached  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="29b95-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="29b95-105">Parameters</span></span>  
 `pbAttached`  
 <span data-ttu-id="29b95-106">[出力] `true`デバッガーがプロセスにアタッチされている場合は、それ以外の場合は `false` 。</span><span class="sxs-lookup"><span data-stu-id="29b95-106">[out] `true` if a debugger is attached to the process; otherwise, `false`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="29b95-107">戻り値</span><span class="sxs-lookup"><span data-stu-id="29b95-107">Return Value</span></span>  
  
|<span data-ttu-id="29b95-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="29b95-108">HRESULT</span></span>|<span data-ttu-id="29b95-109">説明</span><span class="sxs-lookup"><span data-stu-id="29b95-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="29b95-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="29b95-110">S_OK</span></span>|<span data-ttu-id="29b95-111">`IsDebuggerAttached`正常に返されました。</span><span class="sxs-lookup"><span data-stu-id="29b95-111">`IsDebuggerAttached` returned successfully.</span></span>|  
|<span data-ttu-id="29b95-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="29b95-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="29b95-113">共通言語ランタイム (CLR) がプロセスに読み込まれていないか、CLR がマネージコードを実行できない状態であるか、または呼び出しが正常に処理されていません。</span><span class="sxs-lookup"><span data-stu-id="29b95-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="29b95-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="29b95-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="29b95-115">呼び出しがタイムアウトしました。</span><span class="sxs-lookup"><span data-stu-id="29b95-115">The call timed out.</span></span>|  
|<span data-ttu-id="29b95-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="29b95-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="29b95-117">呼び出し元がロックを所有していません。</span><span class="sxs-lookup"><span data-stu-id="29b95-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="29b95-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="29b95-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="29b95-119">ブロックされたスレッドまたはファイバーが待機しているときに、イベントが取り消されました。</span><span class="sxs-lookup"><span data-stu-id="29b95-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="29b95-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="29b95-120">E_FAIL</span></span>|<span data-ttu-id="29b95-121">原因不明の致命的なエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="29b95-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="29b95-122">メソッドが E_FAIL を返すと、そのプロセス内で CLR が使用できなくなります。</span><span class="sxs-lookup"><span data-stu-id="29b95-122">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="29b95-123">後続のホストメソッドの呼び出しでは HOST_E_CLRNOTAVAILABLE が返されます。</span><span class="sxs-lookup"><span data-stu-id="29b95-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="29b95-124">解説</span><span class="sxs-lookup"><span data-stu-id="29b95-124">Remarks</span></span>  
 <span data-ttu-id="29b95-125">`IsDebuggerAttached`デバッガーがプロセスにアタッチされているかどうかを判断するために、ホストが CLR を照会できるようにします。</span><span class="sxs-lookup"><span data-stu-id="29b95-125">`IsDebuggerAttached` allows the host to query the CLR to determine whether a debugger is attached to the process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="29b95-126">要件</span><span class="sxs-lookup"><span data-stu-id="29b95-126">Requirements</span></span>  
 <span data-ttu-id="29b95-127">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="29b95-127">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="29b95-128">**ヘッダー:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="29b95-128">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="29b95-129">**ライブラリ:** Mscoree.dll にリソースとして含まれています</span><span class="sxs-lookup"><span data-stu-id="29b95-129">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="29b95-130">**.NET Framework のバージョン:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="29b95-130">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="29b95-131">関連項目</span><span class="sxs-lookup"><span data-stu-id="29b95-131">See also</span></span>

- [<span data-ttu-id="29b95-132">ICLRControl インターフェイス</span><span class="sxs-lookup"><span data-stu-id="29b95-132">ICLRControl Interface</span></span>](iclrcontrol-interface.md)
- [<span data-ttu-id="29b95-133">ICLRDebugManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="29b95-133">ICLRDebugManager Interface</span></span>](iclrdebugmanager-interface.md)
- [<span data-ttu-id="29b95-134">IHostControl インターフェイス</span><span class="sxs-lookup"><span data-stu-id="29b95-134">IHostControl Interface</span></span>](ihostcontrol-interface.md)
