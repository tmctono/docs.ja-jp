---
title: IHostIoCompletionManager::Bind メソッド
ms.date: 03/30/2017
api_name:
- IHostIoCompletionManager.Bind
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostIoCompletionManager::Bind
helpviewer_keywords:
- IHostIoCompletionManager::Bind method [.NET Framework hosting]
- Bind method [.NET Framework hosting]
ms.assetid: acd74cb5-7e22-4a07-83c3-82288e1abd9f
topic_type:
- apiref
ms.openlocfilehash: 84fc99f6a5feb7ec73ee16942ba2794fc082dc89
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73133902"
---
# <a name="ihostiocompletionmanagerbind-method"></a><span data-ttu-id="f2a43-102">IHostIoCompletionManager::Bind メソッド</span><span class="sxs-lookup"><span data-stu-id="f2a43-102">IHostIoCompletionManager::Bind Method</span></span>
<span data-ttu-id="f2a43-103">以前に[CreateIoCompletionPort](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-createiocompletionport-method.md)を呼び出したときに作成された i/o 完了ポートに、指定されたハンドルをバインドします。</span><span class="sxs-lookup"><span data-stu-id="f2a43-103">Binds the specified handle to an I/O completion port that has been created by an earlier call to [CreateIoCompletionPort](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-createiocompletionport-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f2a43-104">構文</span><span class="sxs-lookup"><span data-stu-id="f2a43-104">Syntax</span></span>  
  
```cpp  
HRESULT Bind (  
    [in] HANDLE hPort,  
    [in] HANDLE hHandle  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f2a43-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="f2a43-105">Parameters</span></span>  
 `hPort`  
 <span data-ttu-id="f2a43-106">から`hHandle`バインド先の i/o 完了ポート。</span><span class="sxs-lookup"><span data-stu-id="f2a43-106">[in] The I/O completion port to which to bind `hHandle`.</span></span> <span data-ttu-id="f2a43-107">`hPort` の値が null の場合、`hHandle` は既定の i/o 完了ポートにバインドされます。</span><span class="sxs-lookup"><span data-stu-id="f2a43-107">If the value of `hPort` is null, `hHandle` is bound to the default I/O completion port.</span></span>  
  
 `hHandle`  
 <span data-ttu-id="f2a43-108">から`hPort`にバインドするオペレーティングシステムハンドル。</span><span class="sxs-lookup"><span data-stu-id="f2a43-108">[in] The operating system handle to bind to `hPort`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="f2a43-109">戻り値</span><span class="sxs-lookup"><span data-stu-id="f2a43-109">Return Value</span></span>  
  
|<span data-ttu-id="f2a43-110">HRESULT</span><span class="sxs-lookup"><span data-stu-id="f2a43-110">HRESULT</span></span>|<span data-ttu-id="f2a43-111">説明</span><span class="sxs-lookup"><span data-stu-id="f2a43-111">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="f2a43-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="f2a43-112">S_OK</span></span>|<span data-ttu-id="f2a43-113">`Bind` が正常に返されました。</span><span class="sxs-lookup"><span data-stu-id="f2a43-113">`Bind` returned successfully.</span></span>|  
|<span data-ttu-id="f2a43-114">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="f2a43-114">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="f2a43-115">共通言語ランタイム (CLR) がプロセスに読み込まれていないか、CLR がマネージコードを実行できない状態であるか、または呼び出しが正常に処理されていません。</span><span class="sxs-lookup"><span data-stu-id="f2a43-115">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="f2a43-116">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="f2a43-116">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="f2a43-117">呼び出しがタイムアウトしました。</span><span class="sxs-lookup"><span data-stu-id="f2a43-117">The call timed out.</span></span>|  
|<span data-ttu-id="f2a43-118">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="f2a43-118">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="f2a43-119">呼び出し元がロックを所有していません。</span><span class="sxs-lookup"><span data-stu-id="f2a43-119">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="f2a43-120">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="f2a43-120">HOST_E_ABANDONED</span></span>|<span data-ttu-id="f2a43-121">ブロックされたスレッドまたはファイバーが待機しているときに、イベントが取り消されました。</span><span class="sxs-lookup"><span data-stu-id="f2a43-121">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="f2a43-122">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="f2a43-122">E_FAIL</span></span>|<span data-ttu-id="f2a43-123">原因不明の致命的なエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="f2a43-123">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="f2a43-124">メソッドから E_FAIL が返された場合、そのプロセス内で CLR は使用できなくなります。</span><span class="sxs-lookup"><span data-stu-id="f2a43-124">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="f2a43-125">後続のホストメソッドの呼び出しでは、HOST_E_CLRNOTAVAILABLE が返されます。</span><span class="sxs-lookup"><span data-stu-id="f2a43-125">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f2a43-126">Remarks</span><span class="sxs-lookup"><span data-stu-id="f2a43-126">Remarks</span></span>  
 <span data-ttu-id="f2a43-127">I/o 完了ポートは、`CreateIoCompletionPort`の呼び出しを使用して作成されます。</span><span class="sxs-lookup"><span data-stu-id="f2a43-127">An I/O completion port is created by using a call to `CreateIoCompletionPort`.</span></span> <span data-ttu-id="f2a43-128">CLR は `Bind` を呼び出して、ハンドルをそのポートにバインドします。</span><span class="sxs-lookup"><span data-stu-id="f2a43-128">The CLR calls `Bind` to bind a handle to that port.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="f2a43-129">I/o 要求が完了すると、ホストは[Iclriocomplete manager:: OnComplete](../../../../docs/framework/unmanaged-api/hosting/iclriocompletionmanager-oncomplete-method.md)メソッドを呼び出す必要があります。</span><span class="sxs-lookup"><span data-stu-id="f2a43-129">When an I/O request completes, the host must call the [ICLRIoCompletionManager::OnComplete](../../../../docs/framework/unmanaged-api/hosting/iclriocompletionmanager-oncomplete-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f2a43-130">［要件］</span><span class="sxs-lookup"><span data-stu-id="f2a43-130">Requirements</span></span>  
 <span data-ttu-id="f2a43-131">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f2a43-131">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f2a43-132">**ヘッダー:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="f2a43-132">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="f2a43-133">**ライブラリ:** Mscoree.dll にリソースとして含まれています</span><span class="sxs-lookup"><span data-stu-id="f2a43-133">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="f2a43-134">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f2a43-134">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f2a43-135">関連項目</span><span class="sxs-lookup"><span data-stu-id="f2a43-135">See also</span></span>

- [<span data-ttu-id="f2a43-136">ICLRIoCompletionManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="f2a43-136">ICLRIoCompletionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclriocompletionmanager-interface.md)
