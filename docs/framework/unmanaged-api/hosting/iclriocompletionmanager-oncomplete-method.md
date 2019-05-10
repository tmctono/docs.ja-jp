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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 4f2df623f9d191899390456a20e84a88f06f0b49
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/28/2019
ms.locfileid: "64592852"
---
# <a name="iclriocompletionmanageroncomplete-method"></a><span data-ttu-id="c546f-102">ICLRIoCompletionManager::OnComplete メソッド</span><span class="sxs-lookup"><span data-stu-id="c546f-102">ICLRIoCompletionManager::OnComplete Method</span></span>
<span data-ttu-id="c546f-103">共通言語ランタイム (CLR) の通知への呼び出しを使用して作成された I/O 要求の状態、 [ihostiocompletionmanager::bind](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-bind-method.md)メソッド。</span><span class="sxs-lookup"><span data-stu-id="c546f-103">Notifies the common language runtime (CLR) of the status of an I/O request that was made by using a call to the [IHostIoCompletionManager::Bind](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-bind-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c546f-104">構文</span><span class="sxs-lookup"><span data-stu-id="c546f-104">Syntax</span></span>  
  
```  
HRESULT OnComplete (  
    [in] DWORD dwErrorCode,  
    [in] DWORD NumberOfBytesTransferred,  
    [in] void* pvOverlapped  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c546f-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="c546f-105">Parameters</span></span>  
 `dwErrorCode`  
 <span data-ttu-id="c546f-106">[in]バインド操作の状態を示す HRESULT 値。</span><span class="sxs-lookup"><span data-stu-id="c546f-106">[in] An HRESULT value that indicates the status of the bind operation.</span></span>  
  
- <span data-ttu-id="c546f-107">S_OK では、操作が正常に完了したことを示します。</span><span class="sxs-lookup"><span data-stu-id="c546f-107">S_OK indicates that the operation completed successfully.</span></span>  
  
- <span data-ttu-id="c546f-108">HOST_E_INTERRUPTED では、呼び出しが完了する前に終了したことを示します。</span><span class="sxs-lookup"><span data-stu-id="c546f-108">HOST_E_INTERRUPTED indicates that the call terminated before completion.</span></span>  
  
- <span data-ttu-id="c546f-109">E_FAIL では、未知の回復不能な壊滅的なエラーが発生したことを示します。</span><span class="sxs-lookup"><span data-stu-id="c546f-109">E_FAIL indicates that an unknown, unrecoverable, catastrophic failure occurred.</span></span>  
  
 `NumberOfBytesTransferred`  
 <span data-ttu-id="c546f-110">[in]I/O 要求の処理中に転送されたバイト数。</span><span class="sxs-lookup"><span data-stu-id="c546f-110">[in] The number of bytes transferred during the processing of the I/O request.</span></span>  
  
 `pvOverlapped`  
 <span data-ttu-id="c546f-111">[in]ポインター、`OVERLAPPED`への呼び出しに渡された構造体、`IHostIoCompletionManager::Bind`メソッド。</span><span class="sxs-lookup"><span data-stu-id="c546f-111">[in] A pointer to the `OVERLAPPED` structure that was passed to the call to the `IHostIoCompletionManager::Bind` method.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="c546f-112">戻り値</span><span class="sxs-lookup"><span data-stu-id="c546f-112">Return Value</span></span>  
  
|<span data-ttu-id="c546f-113">HRESULT</span><span class="sxs-lookup"><span data-stu-id="c546f-113">HRESULT</span></span>|<span data-ttu-id="c546f-114">説明</span><span class="sxs-lookup"><span data-stu-id="c546f-114">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="c546f-115">S_OK</span><span class="sxs-lookup"><span data-stu-id="c546f-115">S_OK</span></span>|<span data-ttu-id="c546f-116">`OnComplete` 正常に返されます。</span><span class="sxs-lookup"><span data-stu-id="c546f-116">`OnComplete` returned successfully.</span></span>|  
|<span data-ttu-id="c546f-117">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="c546f-117">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="c546f-118">プロセスに CLR が読み込まれていないか、CLR は状態をマネージ コードを実行または呼び出しを正常に処理ができません。</span><span class="sxs-lookup"><span data-stu-id="c546f-118">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="c546f-119">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="c546f-119">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="c546f-120">呼び出しがタイムアウトになりました。</span><span class="sxs-lookup"><span data-stu-id="c546f-120">The call timed out.</span></span>|  
|<span data-ttu-id="c546f-121">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="c546f-121">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="c546f-122">呼び出し元がロックを所有していません。</span><span class="sxs-lookup"><span data-stu-id="c546f-122">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="c546f-123">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="c546f-123">HOST_E_ABANDONED</span></span>|<span data-ttu-id="c546f-124">イベントがキャンセルされましたブロックされたスレッドまたはファイバーが待機しています。</span><span class="sxs-lookup"><span data-stu-id="c546f-124">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="c546f-125">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="c546f-125">E_FAIL</span></span>|<span data-ttu-id="c546f-126">不明な致命的なエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="c546f-126">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="c546f-127">メソッドには、E_FAIL が返された、後に、CLR は、プロセス内で使用可能ではなくなりました。</span><span class="sxs-lookup"><span data-stu-id="c546f-127">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="c546f-128">メソッドをホストする後続の呼び出しには、HOST_E_CLRNOTAVAILABLE が返されます。</span><span class="sxs-lookup"><span data-stu-id="c546f-128">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c546f-129">Remarks</span><span class="sxs-lookup"><span data-stu-id="c546f-129">Remarks</span></span>  
 <span data-ttu-id="c546f-130">ホストは、I/O 完了の抽象化を実装する場合、CLR がのメソッドを使用してホスト経由で I/O 要求は[IHostIoCompletionManager](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-interface.md)します。</span><span class="sxs-lookup"><span data-stu-id="c546f-130">If the host implements an I/O completion abstraction, the CLR makes I/O requests through the host by using methods of [IHostIoCompletionManager](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-interface.md).</span></span> <span data-ttu-id="c546f-131">ホストを呼び出して、`OnComplete`このような要求の結果をランタイムに通知するメソッド。</span><span class="sxs-lookup"><span data-stu-id="c546f-131">The host then calls the `OnComplete` method to notify the runtime of the outcome of such requests.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c546f-132">必要条件</span><span class="sxs-lookup"><span data-stu-id="c546f-132">Requirements</span></span>  
 <span data-ttu-id="c546f-133">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="c546f-133">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c546f-134">**ヘッダー:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="c546f-134">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="c546f-135">**ライブラリ:** MSCorEE.dll でリソースとして含まれます</span><span class="sxs-lookup"><span data-stu-id="c546f-135">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="c546f-136">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c546f-136">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c546f-137">関連項目</span><span class="sxs-lookup"><span data-stu-id="c546f-137">See also</span></span>

- [<span data-ttu-id="c546f-138">ICLRIoCompletionManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="c546f-138">ICLRIoCompletionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclriocompletionmanager-interface.md)
- [<span data-ttu-id="c546f-139">IHostIoCompletionManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="c546f-139">IHostIoCompletionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-interface.md)
- [<span data-ttu-id="c546f-140">IHostThreadPoolManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="c546f-140">IHostThreadPoolManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-interface.md)
