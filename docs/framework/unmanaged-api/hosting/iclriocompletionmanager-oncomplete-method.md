---
title: ICLRIoCompletionManager::OnComplete メソッド
ms.date: 03/30/2017
api_name:
- ICLRIoCompletionManager.OnComplete
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRIoCompletionManager::OnComplete
helpviewer_keywords:
- OnComplete method [.NET Framework hosting]
- ICLRIoCompletionManager::OnComplete method [.NET Framework hosting]
ms.assetid: 003f6974-9727-4322-bed5-e330d1224d0b
topic_type:
- apiref
ms.openlocfilehash: b44a71137e39130bb0fe4c303fdff62c76d38cbd
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73141014"
---
# <a name="iclriocompletionmanageroncomplete-method"></a><span data-ttu-id="12862-102">ICLRIoCompletionManager::OnComplete メソッド</span><span class="sxs-lookup"><span data-stu-id="12862-102">ICLRIoCompletionManager::OnComplete Method</span></span>
<span data-ttu-id="12862-103">[Ihohooの](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-bind-method.md)呼び出しを使用して作成された i/o 要求の状態を共通言語ランタイム (CLR) に通知します:: Bind メソッド。</span><span class="sxs-lookup"><span data-stu-id="12862-103">Notifies the common language runtime (CLR) of the status of an I/O request that was made by using a call to the [IHostIoCompletionManager::Bind](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-bind-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="12862-104">構文</span><span class="sxs-lookup"><span data-stu-id="12862-104">Syntax</span></span>  
  
```cpp  
HRESULT OnComplete (  
    [in] DWORD dwErrorCode,  
    [in] DWORD NumberOfBytesTransferred,  
    [in] void* pvOverlapped  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="12862-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="12862-105">Parameters</span></span>  
 `dwErrorCode`  
 <span data-ttu-id="12862-106">からバインド操作の状態を示す HRESULT 値です。</span><span class="sxs-lookup"><span data-stu-id="12862-106">[in] An HRESULT value that indicates the status of the bind operation.</span></span>  
  
- <span data-ttu-id="12862-107">S_OK は、操作が正常に完了したことを示します。</span><span class="sxs-lookup"><span data-stu-id="12862-107">S_OK indicates that the operation completed successfully.</span></span>  
  
- <span data-ttu-id="12862-108">HOST_E_INTERRUPTED は、呼び出しが完了前に終了したことを示します。</span><span class="sxs-lookup"><span data-stu-id="12862-108">HOST_E_INTERRUPTED indicates that the call terminated before completion.</span></span>  
  
- <span data-ttu-id="12862-109">E_FAIL は、不明な、回復不可能な重大なエラーが発生したことを示します。</span><span class="sxs-lookup"><span data-stu-id="12862-109">E_FAIL indicates that an unknown, unrecoverable, catastrophic failure occurred.</span></span>  
  
 `NumberOfBytesTransferred`  
 <span data-ttu-id="12862-110">からI/o 要求の処理中に転送されたバイト数。</span><span class="sxs-lookup"><span data-stu-id="12862-110">[in] The number of bytes transferred during the processing of the I/O request.</span></span>  
  
 `pvOverlapped`  
 <span data-ttu-id="12862-111">から`IHostIoCompletionManager::Bind` メソッドの呼び出しに渡された `OVERLAPPED` 構造体へのポインター。</span><span class="sxs-lookup"><span data-stu-id="12862-111">[in] A pointer to the `OVERLAPPED` structure that was passed to the call to the `IHostIoCompletionManager::Bind` method.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="12862-112">戻り値</span><span class="sxs-lookup"><span data-stu-id="12862-112">Return Value</span></span>  
  
|<span data-ttu-id="12862-113">HRESULT</span><span class="sxs-lookup"><span data-stu-id="12862-113">HRESULT</span></span>|<span data-ttu-id="12862-114">説明</span><span class="sxs-lookup"><span data-stu-id="12862-114">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="12862-115">S_OK</span><span class="sxs-lookup"><span data-stu-id="12862-115">S_OK</span></span>|<span data-ttu-id="12862-116">`OnComplete` が正常に返されました。</span><span class="sxs-lookup"><span data-stu-id="12862-116">`OnComplete` returned successfully.</span></span>|  
|<span data-ttu-id="12862-117">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="12862-117">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="12862-118">CLR がプロセスに読み込まれていないか、CLR がマネージドコードを実行できない状態であるか、または呼び出しが正常に処理されていません。</span><span class="sxs-lookup"><span data-stu-id="12862-118">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="12862-119">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="12862-119">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="12862-120">呼び出しがタイムアウトしました。</span><span class="sxs-lookup"><span data-stu-id="12862-120">The call timed out.</span></span>|  
|<span data-ttu-id="12862-121">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="12862-121">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="12862-122">呼び出し元がロックを所有していません。</span><span class="sxs-lookup"><span data-stu-id="12862-122">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="12862-123">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="12862-123">HOST_E_ABANDONED</span></span>|<span data-ttu-id="12862-124">ブロックされたスレッドまたはファイバーが待機しているときに、イベントが取り消されました。</span><span class="sxs-lookup"><span data-stu-id="12862-124">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="12862-125">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="12862-125">E_FAIL</span></span>|<span data-ttu-id="12862-126">原因不明の致命的なエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="12862-126">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="12862-127">メソッドから E_FAIL が返された後は、そのプロセス内で CLR を使用できなくなります。</span><span class="sxs-lookup"><span data-stu-id="12862-127">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="12862-128">後続のホストメソッドの呼び出しでは、HOST_E_CLRNOTAVAILABLE が返されます。</span><span class="sxs-lookup"><span data-stu-id="12862-128">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="12862-129">Remarks</span><span class="sxs-lookup"><span data-stu-id="12862-129">Remarks</span></span>  
 <span data-ttu-id="12862-130">ホストで i/o 完了の抽象化が実装されている場合、CLR は[Iho/ocompletion manager](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-interface.md)のメソッドを使用して、ホストを介して i/o 要求を行います。</span><span class="sxs-lookup"><span data-stu-id="12862-130">If the host implements an I/O completion abstraction, the CLR makes I/O requests through the host by using methods of [IHostIoCompletionManager](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-interface.md).</span></span> <span data-ttu-id="12862-131">次に、ホストは `OnComplete` メソッドを呼び出して、そのような要求の結果をランタイムに通知します。</span><span class="sxs-lookup"><span data-stu-id="12862-131">The host then calls the `OnComplete` method to notify the runtime of the outcome of such requests.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="12862-132">［要件］</span><span class="sxs-lookup"><span data-stu-id="12862-132">Requirements</span></span>  
 <span data-ttu-id="12862-133">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="12862-133">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="12862-134">**ヘッダー:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="12862-134">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="12862-135">**ライブラリ:** Mscoree.dll にリソースとして含まれています</span><span class="sxs-lookup"><span data-stu-id="12862-135">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="12862-136">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="12862-136">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="12862-137">関連項目</span><span class="sxs-lookup"><span data-stu-id="12862-137">See also</span></span>

- [<span data-ttu-id="12862-138">ICLRIoCompletionManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="12862-138">ICLRIoCompletionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclriocompletionmanager-interface.md)
- [<span data-ttu-id="12862-139">IHostIoCompletionManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="12862-139">IHostIoCompletionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-interface.md)
- [<span data-ttu-id="12862-140">IHostThreadPoolManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="12862-140">IHostThreadPoolManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-interface.md)
