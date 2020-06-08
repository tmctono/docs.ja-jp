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
ms.openlocfilehash: 240712296254e02f4d268a00e1c15ef34f4519f1
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/08/2020
ms.locfileid: "84501548"
---
# <a name="ihostiocompletionmanagercreateiocompletionport-method"></a><span data-ttu-id="82e0d-102">IHostIoCompletionManager::CreateIoCompletionPort メソッド</span><span class="sxs-lookup"><span data-stu-id="82e0d-102">IHostIoCompletionManager::CreateIoCompletionPort Method</span></span>
<span data-ttu-id="82e0d-103">ホストが新しい i/o 完了ポートを作成することを要求します。</span><span class="sxs-lookup"><span data-stu-id="82e0d-103">Requests that the host create a new I/O completion port.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="82e0d-104">構文</span><span class="sxs-lookup"><span data-stu-id="82e0d-104">Syntax</span></span>  
  
```cpp  
HRESULT CreateIoCompletionPort (  
    [out] HANDLE *phPort  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="82e0d-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="82e0d-105">Parameters</span></span>  
 `phPort`  
 <span data-ttu-id="82e0d-106">入出力新しく作成された i/o 完了ポートのハンドルへのポインター。ポートを作成できなかった場合は 0 (ゼロ)。</span><span class="sxs-lookup"><span data-stu-id="82e0d-106">[out] A pointer to a handle to the newly created I/O completion port, or 0 (zero), if the port could not be created.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="82e0d-107">戻り値</span><span class="sxs-lookup"><span data-stu-id="82e0d-107">Return Value</span></span>  
  
|<span data-ttu-id="82e0d-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="82e0d-108">HRESULT</span></span>|<span data-ttu-id="82e0d-109">説明</span><span class="sxs-lookup"><span data-stu-id="82e0d-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="82e0d-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="82e0d-110">S_OK</span></span>|<span data-ttu-id="82e0d-111">`CreateIoCompletionPort`正常に返されました。</span><span class="sxs-lookup"><span data-stu-id="82e0d-111">`CreateIoCompletionPort` returned successfully.</span></span>|  
|<span data-ttu-id="82e0d-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="82e0d-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="82e0d-113">共通言語ランタイム (CLR) がプロセスに読み込まれていないか、CLR がマネージコードを実行できない状態であるか、または呼び出しが正常に処理されていません。</span><span class="sxs-lookup"><span data-stu-id="82e0d-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="82e0d-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="82e0d-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="82e0d-115">呼び出しがタイムアウトしました。</span><span class="sxs-lookup"><span data-stu-id="82e0d-115">The call timed out.</span></span>|  
|<span data-ttu-id="82e0d-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="82e0d-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="82e0d-117">呼び出し元がロックを所有していません。</span><span class="sxs-lookup"><span data-stu-id="82e0d-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="82e0d-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="82e0d-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="82e0d-119">ブロックされたスレッドまたはファイバーが待機しているときに、イベントが取り消されました。</span><span class="sxs-lookup"><span data-stu-id="82e0d-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="82e0d-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="82e0d-120">E_FAIL</span></span>|<span data-ttu-id="82e0d-121">原因不明の致命的なエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="82e0d-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="82e0d-122">メソッドが E_FAIL を返すと、そのプロセス内で CLR が使用できなくなります。</span><span class="sxs-lookup"><span data-stu-id="82e0d-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="82e0d-123">後続のホストメソッドの呼び出しでは HOST_E_CLRNOTAVAILABLE が返されます。</span><span class="sxs-lookup"><span data-stu-id="82e0d-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="82e0d-124">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="82e0d-124">E_OUTOFMEMORY</span></span>|<span data-ttu-id="82e0d-125">要求されたリソースを割り当てるのに十分なメモリがありませんでした。</span><span class="sxs-lookup"><span data-stu-id="82e0d-125">Not enough memory was available to allocate the requested resource.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="82e0d-126">解説</span><span class="sxs-lookup"><span data-stu-id="82e0d-126">Remarks</span></span>  
 <span data-ttu-id="82e0d-127">CLR は、メソッドを呼び出して、 `CreateIoCompletionPort` ホストが新しい i/o 完了ポートを作成するように要求します。</span><span class="sxs-lookup"><span data-stu-id="82e0d-127">The CLR calls the `CreateIoCompletionPort` method to request that the host create a new I/O completion port.</span></span> <span data-ttu-id="82e0d-128">このポートは、 [Ihoを](ihostiocompletionmanager-bind-method.md)呼び出して、このポートに i/o 操作をバインドします。</span><span class="sxs-lookup"><span data-stu-id="82e0d-128">It binds I/O operations to this port through a call to the [IHostIoCompletionManager::Bind](ihostiocompletionmanager-bind-method.md) method.</span></span> <span data-ttu-id="82e0d-129">ホストは、 [Iclriocomplete manager:: OnComplete](iclriocompletionmanager-oncomplete-method.md)を呼び出すことによって、状態を CLR に報告します。</span><span class="sxs-lookup"><span data-stu-id="82e0d-129">The host reports status back to the CLR by calling [ICLRIoCompletionManager::OnComplete](iclriocompletionmanager-oncomplete-method.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="82e0d-130">要件</span><span class="sxs-lookup"><span data-stu-id="82e0d-130">Requirements</span></span>  
 <span data-ttu-id="82e0d-131">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="82e0d-131">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="82e0d-132">**ヘッダー:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="82e0d-132">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="82e0d-133">**ライブラリ:** Mscoree.dll にリソースとして含まれています</span><span class="sxs-lookup"><span data-stu-id="82e0d-133">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="82e0d-134">**.NET Framework のバージョン:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="82e0d-134">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="82e0d-135">関連項目</span><span class="sxs-lookup"><span data-stu-id="82e0d-135">See also</span></span>

- [<span data-ttu-id="82e0d-136">ICLRIoCompletionManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="82e0d-136">ICLRIoCompletionManager Interface</span></span>](iclriocompletionmanager-interface.md)
- [<span data-ttu-id="82e0d-137">IHostIoCompletionManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="82e0d-137">IHostIoCompletionManager Interface</span></span>](ihostiocompletionmanager-interface.md)
