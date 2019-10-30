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
ms.openlocfilehash: a58fcb6c1fa2aad96cdd29194a21eaf590536cdd
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73129389"
---
# <a name="iclrdebugmanagerisdebuggerattached-method"></a><span data-ttu-id="7c92e-102">ICLRDebugManager::IsDebuggerAttached メソッド</span><span class="sxs-lookup"><span data-stu-id="7c92e-102">ICLRDebugManager::IsDebuggerAttached Method</span></span>
<span data-ttu-id="7c92e-103">デバッガーがプロセスにアタッチされているかどうかを示す値を取得します。</span><span class="sxs-lookup"><span data-stu-id="7c92e-103">Gets a value that indicates whether a debugger is attached to the process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7c92e-104">構文</span><span class="sxs-lookup"><span data-stu-id="7c92e-104">Syntax</span></span>  
  
```cpp  
HRESULT IsDebuggerAttached (  
    [out] BOOL *pbAttached  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7c92e-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="7c92e-105">Parameters</span></span>  
 `pbAttached`  
 <span data-ttu-id="7c92e-106">[out] デバッガーがプロセスにアタッチされている場合は `true`。それ以外の場合は、`false`ます。</span><span class="sxs-lookup"><span data-stu-id="7c92e-106">[out] `true` if a debugger is attached to the process; otherwise, `false`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="7c92e-107">戻り値</span><span class="sxs-lookup"><span data-stu-id="7c92e-107">Return Value</span></span>  
  
|<span data-ttu-id="7c92e-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="7c92e-108">HRESULT</span></span>|<span data-ttu-id="7c92e-109">説明</span><span class="sxs-lookup"><span data-stu-id="7c92e-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="7c92e-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="7c92e-110">S_OK</span></span>|<span data-ttu-id="7c92e-111">`IsDebuggerAttached` が正常に返されました。</span><span class="sxs-lookup"><span data-stu-id="7c92e-111">`IsDebuggerAttached` returned successfully.</span></span>|  
|<span data-ttu-id="7c92e-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="7c92e-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="7c92e-113">共通言語ランタイム (CLR) がプロセスに読み込まれていないか、CLR がマネージコードを実行できない状態であるか、または呼び出しが正常に処理されていません。</span><span class="sxs-lookup"><span data-stu-id="7c92e-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="7c92e-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="7c92e-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="7c92e-115">呼び出しがタイムアウトしました。</span><span class="sxs-lookup"><span data-stu-id="7c92e-115">The call timed out.</span></span>|  
|<span data-ttu-id="7c92e-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="7c92e-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="7c92e-117">呼び出し元がロックを所有していません。</span><span class="sxs-lookup"><span data-stu-id="7c92e-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="7c92e-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="7c92e-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="7c92e-119">ブロックされたスレッドまたはファイバーが待機しているときに、イベントが取り消されました。</span><span class="sxs-lookup"><span data-stu-id="7c92e-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="7c92e-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="7c92e-120">E_FAIL</span></span>|<span data-ttu-id="7c92e-121">原因不明の致命的なエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="7c92e-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="7c92e-122">メソッドから E_FAIL が返された後は、そのプロセス内で CLR を使用できなくなります。</span><span class="sxs-lookup"><span data-stu-id="7c92e-122">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="7c92e-123">後続のホストメソッドの呼び出しでは、HOST_E_CLRNOTAVAILABLE が返されます。</span><span class="sxs-lookup"><span data-stu-id="7c92e-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7c92e-124">Remarks</span><span class="sxs-lookup"><span data-stu-id="7c92e-124">Remarks</span></span>  
 <span data-ttu-id="7c92e-125">`IsDebuggerAttached` を使用すると、ホストは CLR に対してクエリを実行し、デバッガーがプロセスにアタッチされているかどうかを判断できます。</span><span class="sxs-lookup"><span data-stu-id="7c92e-125">`IsDebuggerAttached` allows the host to query the CLR to determine whether a debugger is attached to the process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7c92e-126">［要件］</span><span class="sxs-lookup"><span data-stu-id="7c92e-126">Requirements</span></span>  
 <span data-ttu-id="7c92e-127">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7c92e-127">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7c92e-128">**ヘッダー:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="7c92e-128">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="7c92e-129">**ライブラリ:** Mscoree.dll にリソースとして含まれています</span><span class="sxs-lookup"><span data-stu-id="7c92e-129">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="7c92e-130">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7c92e-130">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7c92e-131">関連項目</span><span class="sxs-lookup"><span data-stu-id="7c92e-131">See also</span></span>

- [<span data-ttu-id="7c92e-132">ICLRControl インターフェイス</span><span class="sxs-lookup"><span data-stu-id="7c92e-132">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)
- [<span data-ttu-id="7c92e-133">ICLRDebugManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="7c92e-133">ICLRDebugManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-interface.md)
- [<span data-ttu-id="7c92e-134">IHostControl インターフェイス</span><span class="sxs-lookup"><span data-stu-id="7c92e-134">IHostControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostcontrol-interface.md)
