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
ms.openlocfilehash: 39c9752912e88b04455516c0e9bed43610ba8aa0
ms.sourcegitcommit: 0926684d8d34f4c6b5acce58d2193db093cb9cf2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2020
ms.locfileid: "83703816"
---
# <a name="iclriocompletionmanageroncomplete-method"></a><span data-ttu-id="50638-102">ICLRIoCompletionManager::OnComplete メソッド</span><span class="sxs-lookup"><span data-stu-id="50638-102">ICLRIoCompletionManager::OnComplete Method</span></span>
<span data-ttu-id="50638-103">[Ihohooの](ihostiocompletionmanager-bind-method.md)呼び出しを使用して作成された i/o 要求の状態を共通言語ランタイム (CLR) に通知します:: Bind メソッド。</span><span class="sxs-lookup"><span data-stu-id="50638-103">Notifies the common language runtime (CLR) of the status of an I/O request that was made by using a call to the [IHostIoCompletionManager::Bind](ihostiocompletionmanager-bind-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="50638-104">構文</span><span class="sxs-lookup"><span data-stu-id="50638-104">Syntax</span></span>  
  
```cpp  
HRESULT OnComplete (  
    [in] DWORD dwErrorCode,  
    [in] DWORD NumberOfBytesTransferred,  
    [in] void* pvOverlapped  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="50638-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="50638-105">Parameters</span></span>  
 `dwErrorCode`  
 <span data-ttu-id="50638-106">からバインド操作の状態を示す HRESULT 値です。</span><span class="sxs-lookup"><span data-stu-id="50638-106">[in] An HRESULT value that indicates the status of the bind operation.</span></span>  
  
- <span data-ttu-id="50638-107">S_OK は、操作が正常に完了したことを示します。</span><span class="sxs-lookup"><span data-stu-id="50638-107">S_OK indicates that the operation completed successfully.</span></span>  
  
- <span data-ttu-id="50638-108">HOST_E_INTERRUPTED は、呼び出しが完了前に終了したことを示します。</span><span class="sxs-lookup"><span data-stu-id="50638-108">HOST_E_INTERRUPTED indicates that the call terminated before completion.</span></span>  
  
- <span data-ttu-id="50638-109">E_FAIL は、不明で回復不可能な重大なエラーが発生したことを示します。</span><span class="sxs-lookup"><span data-stu-id="50638-109">E_FAIL indicates that an unknown, unrecoverable, catastrophic failure occurred.</span></span>  
  
 `NumberOfBytesTransferred`  
 <span data-ttu-id="50638-110">からI/o 要求の処理中に転送されたバイト数。</span><span class="sxs-lookup"><span data-stu-id="50638-110">[in] The number of bytes transferred during the processing of the I/O request.</span></span>  
  
 `pvOverlapped`  
 <span data-ttu-id="50638-111">から`OVERLAPPED`メソッドの呼び出しに渡された構造体へのポインター `IHostIoCompletionManager::Bind` 。</span><span class="sxs-lookup"><span data-stu-id="50638-111">[in] A pointer to the `OVERLAPPED` structure that was passed to the call to the `IHostIoCompletionManager::Bind` method.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="50638-112">戻り値</span><span class="sxs-lookup"><span data-stu-id="50638-112">Return Value</span></span>  
  
|<span data-ttu-id="50638-113">HRESULT</span><span class="sxs-lookup"><span data-stu-id="50638-113">HRESULT</span></span>|<span data-ttu-id="50638-114">説明</span><span class="sxs-lookup"><span data-stu-id="50638-114">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="50638-115">S_OK</span><span class="sxs-lookup"><span data-stu-id="50638-115">S_OK</span></span>|<span data-ttu-id="50638-116">`OnComplete`正常に返されました。</span><span class="sxs-lookup"><span data-stu-id="50638-116">`OnComplete` returned successfully.</span></span>|  
|<span data-ttu-id="50638-117">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="50638-117">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="50638-118">CLR がプロセスに読み込まれていないか、CLR がマネージドコードを実行できない状態であるか、または呼び出しが正常に処理されていません。</span><span class="sxs-lookup"><span data-stu-id="50638-118">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="50638-119">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="50638-119">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="50638-120">呼び出しがタイムアウトしました。</span><span class="sxs-lookup"><span data-stu-id="50638-120">The call timed out.</span></span>|  
|<span data-ttu-id="50638-121">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="50638-121">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="50638-122">呼び出し元がロックを所有していません。</span><span class="sxs-lookup"><span data-stu-id="50638-122">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="50638-123">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="50638-123">HOST_E_ABANDONED</span></span>|<span data-ttu-id="50638-124">ブロックされたスレッドまたはファイバーが待機しているときに、イベントが取り消されました。</span><span class="sxs-lookup"><span data-stu-id="50638-124">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="50638-125">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="50638-125">E_FAIL</span></span>|<span data-ttu-id="50638-126">原因不明の致命的なエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="50638-126">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="50638-127">メソッドが E_FAIL を返すと、そのプロセス内で CLR が使用できなくなります。</span><span class="sxs-lookup"><span data-stu-id="50638-127">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="50638-128">後続のホストメソッドの呼び出しでは HOST_E_CLRNOTAVAILABLE が返されます。</span><span class="sxs-lookup"><span data-stu-id="50638-128">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="50638-129">解説</span><span class="sxs-lookup"><span data-stu-id="50638-129">Remarks</span></span>  
 <span data-ttu-id="50638-130">ホストで i/o 完了の抽象化が実装されている場合、CLR は[Iho/ocompletion manager](ihostiocompletionmanager-interface.md)のメソッドを使用して、ホストを介して i/o 要求を行います。</span><span class="sxs-lookup"><span data-stu-id="50638-130">If the host implements an I/O completion abstraction, the CLR makes I/O requests through the host by using methods of [IHostIoCompletionManager](ihostiocompletionmanager-interface.md).</span></span> <span data-ttu-id="50638-131">次に、ホストはメソッドを呼び出して、その `OnComplete` ような要求の結果をランタイムに通知します。</span><span class="sxs-lookup"><span data-stu-id="50638-131">The host then calls the `OnComplete` method to notify the runtime of the outcome of such requests.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="50638-132">要件</span><span class="sxs-lookup"><span data-stu-id="50638-132">Requirements</span></span>  
 <span data-ttu-id="50638-133">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="50638-133">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="50638-134">**ヘッダー:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="50638-134">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="50638-135">**ライブラリ:** Mscoree.dll にリソースとして含まれています</span><span class="sxs-lookup"><span data-stu-id="50638-135">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="50638-136">**.NET Framework のバージョン:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="50638-136">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="50638-137">関連項目</span><span class="sxs-lookup"><span data-stu-id="50638-137">See also</span></span>

- [<span data-ttu-id="50638-138">ICLRIoCompletionManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="50638-138">ICLRIoCompletionManager Interface</span></span>](iclriocompletionmanager-interface.md)
- [<span data-ttu-id="50638-139">IHostIoCompletionManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="50638-139">IHostIoCompletionManager Interface</span></span>](ihostiocompletionmanager-interface.md)
- [<span data-ttu-id="50638-140">IHostThreadPoolManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="50638-140">IHostThreadPoolManager Interface</span></span>](ihostthreadpoolmanager-interface.md)
