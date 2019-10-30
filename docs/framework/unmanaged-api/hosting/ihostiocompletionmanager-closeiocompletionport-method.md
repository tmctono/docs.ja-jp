---
title: IHostIoCompletionManager::CloseIoCompletionPort メソッド
ms.date: 03/30/2017
api_name:
- IHostIoCompletionManager.CloseIoCompletionPort
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostIoCompletionManager::CloseIoCompletionPort
helpviewer_keywords:
- IHostIoCompletionManager::CloseIoCompletionPort method [.NET Framework hosting]
- CloseIoCompletionPort method [.NET Framework hosting]
ms.assetid: e86ad7be-3758-498a-a972-5522d69dfbb3
topic_type:
- apiref
ms.openlocfilehash: 254254af705f93793b030882e0ac79d0372ca55f
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73133887"
---
# <a name="ihostiocompletionmanagercloseiocompletionport-method"></a><span data-ttu-id="3c5b8-102">IHostIoCompletionManager::CloseIoCompletionPort メソッド</span><span class="sxs-lookup"><span data-stu-id="3c5b8-102">IHostIoCompletionManager::CloseIoCompletionPort Method</span></span>
<span data-ttu-id="3c5b8-103">[CreateIoCompletionPort](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-createiocompletionport-method.md)の以前の呼び出しで開かれたポートをホストが閉じることを要求します。</span><span class="sxs-lookup"><span data-stu-id="3c5b8-103">Requests that the host close a port that was opened through an earlier call to [CreateIoCompletionPort](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-createiocompletionport-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3c5b8-104">構文</span><span class="sxs-lookup"><span data-stu-id="3c5b8-104">Syntax</span></span>  
  
```cpp  
HRESULT CloseIoCompletionPort (  
    [in] HANDLE hPort  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3c5b8-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="3c5b8-105">Parameters</span></span>  
 `hPort`  
 <span data-ttu-id="3c5b8-106">から閉じるポートのハンドル。</span><span class="sxs-lookup"><span data-stu-id="3c5b8-106">[in] The handle of the port to close.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="3c5b8-107">戻り値</span><span class="sxs-lookup"><span data-stu-id="3c5b8-107">Return Value</span></span>  
  
|<span data-ttu-id="3c5b8-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="3c5b8-108">HRESULT</span></span>|<span data-ttu-id="3c5b8-109">説明</span><span class="sxs-lookup"><span data-stu-id="3c5b8-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="3c5b8-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="3c5b8-110">S_OK</span></span>|<span data-ttu-id="3c5b8-111">`CloseIoCompletionPort` が正常に返されました。</span><span class="sxs-lookup"><span data-stu-id="3c5b8-111">`CloseIoCompletionPort` returned successfully.</span></span>|  
|<span data-ttu-id="3c5b8-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="3c5b8-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="3c5b8-113">共通言語ランタイム (CLR) がプロセスに読み込まれていないか、CLR がマネージコードを実行できない状態であるか、または呼び出しが正常に処理されていません。</span><span class="sxs-lookup"><span data-stu-id="3c5b8-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="3c5b8-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="3c5b8-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="3c5b8-115">呼び出しがタイムアウトしました。</span><span class="sxs-lookup"><span data-stu-id="3c5b8-115">The call timed out.</span></span>|  
|<span data-ttu-id="3c5b8-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="3c5b8-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="3c5b8-117">呼び出し元がロックを所有していません。</span><span class="sxs-lookup"><span data-stu-id="3c5b8-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="3c5b8-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="3c5b8-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="3c5b8-119">ブロックされたスレッドまたはファイバーが待機しているときに、イベントが取り消されました。</span><span class="sxs-lookup"><span data-stu-id="3c5b8-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="3c5b8-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="3c5b8-120">E_FAIL</span></span>|<span data-ttu-id="3c5b8-121">原因不明の致命的なエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="3c5b8-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="3c5b8-122">メソッドから E_FAIL が返された場合、そのプロセス内で CLR は使用できなくなります。</span><span class="sxs-lookup"><span data-stu-id="3c5b8-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="3c5b8-123">後続のホストメソッドの呼び出しでは、HOST_E_CLRNOTAVAILABLE が返されます。</span><span class="sxs-lookup"><span data-stu-id="3c5b8-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="3c5b8-124">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="3c5b8-124">E_INVALIDARG</span></span>|<span data-ttu-id="3c5b8-125">無効なポートハンドルが渡されました。</span><span class="sxs-lookup"><span data-stu-id="3c5b8-125">An invalid port handle was passed.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3c5b8-126">Remarks</span><span class="sxs-lookup"><span data-stu-id="3c5b8-126">Remarks</span></span>  
 <span data-ttu-id="3c5b8-127">`hPort` は、`CreateIoCompletionPort`の以前の呼び出しで作成されたポートを示すハンドルである必要があります。</span><span class="sxs-lookup"><span data-stu-id="3c5b8-127">`hPort` must be a handle to a port that was created by an earlier call to `CreateIoCompletionPort`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3c5b8-128">［要件］</span><span class="sxs-lookup"><span data-stu-id="3c5b8-128">Requirements</span></span>  
 <span data-ttu-id="3c5b8-129">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3c5b8-129">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3c5b8-130">**ヘッダー:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="3c5b8-130">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="3c5b8-131">**ライブラリ:** Mscoree.dll にリソースとして含まれています</span><span class="sxs-lookup"><span data-stu-id="3c5b8-131">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="3c5b8-132">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3c5b8-132">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3c5b8-133">関連項目</span><span class="sxs-lookup"><span data-stu-id="3c5b8-133">See also</span></span>

- [<span data-ttu-id="3c5b8-134">ICLRIoCompletionManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="3c5b8-134">ICLRIoCompletionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclriocompletionmanager-interface.md)
- [<span data-ttu-id="3c5b8-135">IHostIoCompletionManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="3c5b8-135">IHostIoCompletionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-interface.md)
