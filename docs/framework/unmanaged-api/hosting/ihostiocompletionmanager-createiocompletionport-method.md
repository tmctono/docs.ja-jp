---
title: IHostIoCompletionManager::CreateIoCompletionPort メソッド
ms.date: 03/30/2017
api_name:
- IHostIoCompletionManager.CreateIoCompletionPort
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostIoCompletionManager::CreateIoCompletionPort
helpviewer_keywords:
- IHostIoCompletionManager::CreateIoCompletionPort method [.NET Framework hosting]
- CreateIoCompletionPort method [.NET Framework hosting]
ms.assetid: 907a2b43-68db-44a7-acac-89e792e7bb3c
topic_type:
- apiref
ms.openlocfilehash: 2b679a9ea427d53d67474a196b5b3ae2c698ea5e
ms.sourcegitcommit: d223616e7e6fe2139079052e6fcbe25413fb9900
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/22/2020
ms.locfileid: "83804790"
---
# <a name="ihostiocompletionmanagercreateiocompletionport-method"></a><span data-ttu-id="9e09c-102">IHostIoCompletionManager::CreateIoCompletionPort メソッド</span><span class="sxs-lookup"><span data-stu-id="9e09c-102">IHostIoCompletionManager::CreateIoCompletionPort Method</span></span>
<span data-ttu-id="9e09c-103">ホストが新しい i/o 完了ポートを作成することを要求します。</span><span class="sxs-lookup"><span data-stu-id="9e09c-103">Requests that the host create a new I/O completion port.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9e09c-104">構文</span><span class="sxs-lookup"><span data-stu-id="9e09c-104">Syntax</span></span>  
  
```cpp  
HRESULT CreateIoCompletionPort (  
    [out] HANDLE *phPort  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9e09c-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="9e09c-105">Parameters</span></span>  
 `phPort`  
 <span data-ttu-id="9e09c-106">入出力新しく作成された i/o 完了ポートのハンドルへのポインター。ポートを作成できなかった場合は 0 (ゼロ)。</span><span class="sxs-lookup"><span data-stu-id="9e09c-106">[out] A pointer to a handle to the newly created I/O completion port, or 0 (zero), if the port could not be created.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="9e09c-107">戻り値</span><span class="sxs-lookup"><span data-stu-id="9e09c-107">Return Value</span></span>  
  
|<span data-ttu-id="9e09c-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="9e09c-108">HRESULT</span></span>|<span data-ttu-id="9e09c-109">説明</span><span class="sxs-lookup"><span data-stu-id="9e09c-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="9e09c-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="9e09c-110">S_OK</span></span>|<span data-ttu-id="9e09c-111">`CreateIoCompletionPort`正常に返されました。</span><span class="sxs-lookup"><span data-stu-id="9e09c-111">`CreateIoCompletionPort` returned successfully.</span></span>|  
|<span data-ttu-id="9e09c-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="9e09c-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="9e09c-113">共通言語ランタイム (CLR) がプロセスに読み込まれていないか、CLR がマネージコードを実行できない状態であるか、または呼び出しが正常に処理されていません。</span><span class="sxs-lookup"><span data-stu-id="9e09c-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="9e09c-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="9e09c-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="9e09c-115">呼び出しがタイムアウトしました。</span><span class="sxs-lookup"><span data-stu-id="9e09c-115">The call timed out.</span></span>|  
|<span data-ttu-id="9e09c-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="9e09c-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="9e09c-117">呼び出し元がロックを所有していません。</span><span class="sxs-lookup"><span data-stu-id="9e09c-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="9e09c-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="9e09c-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="9e09c-119">ブロックされたスレッドまたはファイバーが待機しているときに、イベントが取り消されました。</span><span class="sxs-lookup"><span data-stu-id="9e09c-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="9e09c-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="9e09c-120">E_FAIL</span></span>|<span data-ttu-id="9e09c-121">原因不明の致命的なエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="9e09c-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="9e09c-122">メソッドが E_FAIL を返すと、そのプロセス内で CLR が使用できなくなります。</span><span class="sxs-lookup"><span data-stu-id="9e09c-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="9e09c-123">後続のホストメソッドの呼び出しでは HOST_E_CLRNOTAVAILABLE が返されます。</span><span class="sxs-lookup"><span data-stu-id="9e09c-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="9e09c-124">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="9e09c-124">E_OUTOFMEMORY</span></span>|<span data-ttu-id="9e09c-125">要求されたリソースを割り当てるのに十分なメモリがありませんでした。</span><span class="sxs-lookup"><span data-stu-id="9e09c-125">Not enough memory was available to allocate the requested resource.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9e09c-126">解説</span><span class="sxs-lookup"><span data-stu-id="9e09c-126">Remarks</span></span>  
 <span data-ttu-id="9e09c-127">CLR は、メソッドを呼び出して、 `CreateIoCompletionPort` ホストが新しい i/o 完了ポートを作成するように要求します。</span><span class="sxs-lookup"><span data-stu-id="9e09c-127">The CLR calls the `CreateIoCompletionPort` method to request that the host create a new I/O completion port.</span></span> <span data-ttu-id="9e09c-128">このポートは、 [Ihoを](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-bind-method.md)呼び出して、このポートに i/o 操作をバインドします。</span><span class="sxs-lookup"><span data-stu-id="9e09c-128">It binds I/O operations to this port through a call to the [IHostIoCompletionManager::Bind](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-bind-method.md) method.</span></span> <span data-ttu-id="9e09c-129">ホストは、 [Iclriocomplete manager:: OnComplete](iclriocompletionmanager-oncomplete-method.md)を呼び出すことによって、状態を CLR に報告します。</span><span class="sxs-lookup"><span data-stu-id="9e09c-129">The host reports status back to the CLR by calling [ICLRIoCompletionManager::OnComplete](iclriocompletionmanager-oncomplete-method.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9e09c-130">要件</span><span class="sxs-lookup"><span data-stu-id="9e09c-130">Requirements</span></span>  
 <span data-ttu-id="9e09c-131">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9e09c-131">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9e09c-132">**ヘッダー:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="9e09c-132">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="9e09c-133">**ライブラリ:** Mscoree.dll にリソースとして含まれています</span><span class="sxs-lookup"><span data-stu-id="9e09c-133">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="9e09c-134">**.NET Framework のバージョン:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9e09c-134">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9e09c-135">関連項目</span><span class="sxs-lookup"><span data-stu-id="9e09c-135">See also</span></span>

- [<span data-ttu-id="9e09c-136">ICLRIoCompletionManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="9e09c-136">ICLRIoCompletionManager Interface</span></span>](iclriocompletionmanager-interface.md)
- [<span data-ttu-id="9e09c-137">IHostIoCompletionManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="9e09c-137">IHostIoCompletionManager Interface</span></span>](ihostiocompletionmanager-interface.md)
