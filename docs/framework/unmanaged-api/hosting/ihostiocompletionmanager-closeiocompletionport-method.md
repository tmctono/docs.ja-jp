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
ms.openlocfilehash: 5e2e49b4c993e127a31b54d40f721e0714198780
ms.sourcegitcommit: d223616e7e6fe2139079052e6fcbe25413fb9900
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/22/2020
ms.locfileid: "83804776"
---
# <a name="ihostiocompletionmanagercloseiocompletionport-method"></a><span data-ttu-id="2d271-102">IHostIoCompletionManager::CloseIoCompletionPort メソッド</span><span class="sxs-lookup"><span data-stu-id="2d271-102">IHostIoCompletionManager::CloseIoCompletionPort Method</span></span>
<span data-ttu-id="2d271-103">[CreateIoCompletionPort](ihostiocompletionmanager-createiocompletionport-method.md)の以前の呼び出しで開かれたポートをホストが閉じることを要求します。</span><span class="sxs-lookup"><span data-stu-id="2d271-103">Requests that the host close a port that was opened through an earlier call to [CreateIoCompletionPort](ihostiocompletionmanager-createiocompletionport-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2d271-104">構文</span><span class="sxs-lookup"><span data-stu-id="2d271-104">Syntax</span></span>  
  
```cpp  
HRESULT CloseIoCompletionPort (  
    [in] HANDLE hPort  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2d271-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="2d271-105">Parameters</span></span>  
 `hPort`  
 <span data-ttu-id="2d271-106">から閉じるポートのハンドル。</span><span class="sxs-lookup"><span data-stu-id="2d271-106">[in] The handle of the port to close.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="2d271-107">戻り値</span><span class="sxs-lookup"><span data-stu-id="2d271-107">Return Value</span></span>  
  
|<span data-ttu-id="2d271-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="2d271-108">HRESULT</span></span>|<span data-ttu-id="2d271-109">説明</span><span class="sxs-lookup"><span data-stu-id="2d271-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="2d271-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="2d271-110">S_OK</span></span>|<span data-ttu-id="2d271-111">`CloseIoCompletionPort`正常に返されました。</span><span class="sxs-lookup"><span data-stu-id="2d271-111">`CloseIoCompletionPort` returned successfully.</span></span>|  
|<span data-ttu-id="2d271-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="2d271-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="2d271-113">共通言語ランタイム (CLR) がプロセスに読み込まれていないか、CLR がマネージコードを実行できない状態であるか、または呼び出しが正常に処理されていません。</span><span class="sxs-lookup"><span data-stu-id="2d271-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="2d271-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="2d271-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="2d271-115">呼び出しがタイムアウトしました。</span><span class="sxs-lookup"><span data-stu-id="2d271-115">The call timed out.</span></span>|  
|<span data-ttu-id="2d271-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="2d271-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="2d271-117">呼び出し元がロックを所有していません。</span><span class="sxs-lookup"><span data-stu-id="2d271-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="2d271-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="2d271-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="2d271-119">ブロックされたスレッドまたはファイバーが待機しているときに、イベントが取り消されました。</span><span class="sxs-lookup"><span data-stu-id="2d271-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="2d271-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="2d271-120">E_FAIL</span></span>|<span data-ttu-id="2d271-121">原因不明の致命的なエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="2d271-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="2d271-122">メソッドが E_FAIL を返すと、そのプロセス内で CLR が使用できなくなります。</span><span class="sxs-lookup"><span data-stu-id="2d271-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="2d271-123">後続のホストメソッドの呼び出しでは HOST_E_CLRNOTAVAILABLE が返されます。</span><span class="sxs-lookup"><span data-stu-id="2d271-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="2d271-124">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="2d271-124">E_INVALIDARG</span></span>|<span data-ttu-id="2d271-125">無効なポートハンドルが渡されました。</span><span class="sxs-lookup"><span data-stu-id="2d271-125">An invalid port handle was passed.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2d271-126">解説</span><span class="sxs-lookup"><span data-stu-id="2d271-126">Remarks</span></span>  
 <span data-ttu-id="2d271-127">`hPort`は、の以前の呼び出しによって作成されたポートへのハンドルである必要があり `CreateIoCompletionPort` ます。</span><span class="sxs-lookup"><span data-stu-id="2d271-127">`hPort` must be a handle to a port that was created by an earlier call to `CreateIoCompletionPort`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2d271-128">要件</span><span class="sxs-lookup"><span data-stu-id="2d271-128">Requirements</span></span>  
 <span data-ttu-id="2d271-129">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2d271-129">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2d271-130">**ヘッダー:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="2d271-130">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="2d271-131">**ライブラリ:** Mscoree.dll にリソースとして含まれています</span><span class="sxs-lookup"><span data-stu-id="2d271-131">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="2d271-132">**.NET Framework のバージョン:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2d271-132">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2d271-133">関連項目</span><span class="sxs-lookup"><span data-stu-id="2d271-133">See also</span></span>

- [<span data-ttu-id="2d271-134">ICLRIoCompletionManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="2d271-134">ICLRIoCompletionManager Interface</span></span>](iclriocompletionmanager-interface.md)
- [<span data-ttu-id="2d271-135">IHostIoCompletionManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="2d271-135">IHostIoCompletionManager Interface</span></span>](ihostiocompletionmanager-interface.md)
