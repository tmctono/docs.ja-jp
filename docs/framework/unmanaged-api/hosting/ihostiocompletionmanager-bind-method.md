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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: de39de96cd7c7ba0be2dc1bea78f79cfe996575c
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2019
ms.locfileid: "69937569"
---
# <a name="ihostiocompletionmanagerbind-method"></a><span data-ttu-id="ee7c0-102">IHostIoCompletionManager::Bind メソッド</span><span class="sxs-lookup"><span data-stu-id="ee7c0-102">IHostIoCompletionManager::Bind Method</span></span>
<span data-ttu-id="ee7c0-103">以前に[CreateIoCompletionPort](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-createiocompletionport-method.md)を呼び出したときに作成された i/o 完了ポートに、指定されたハンドルをバインドします。</span><span class="sxs-lookup"><span data-stu-id="ee7c0-103">Binds the specified handle to an I/O completion port that has been created by an earlier call to [CreateIoCompletionPort](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-createiocompletionport-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ee7c0-104">構文</span><span class="sxs-lookup"><span data-stu-id="ee7c0-104">Syntax</span></span>  
  
```cpp  
HRESULT Bind (  
    [in] HANDLE hPort,  
    [in] HANDLE hHandle  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ee7c0-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="ee7c0-105">Parameters</span></span>  
 `hPort`  
 <span data-ttu-id="ee7c0-106">からバインド`hHandle`先の i/o 完了ポート。</span><span class="sxs-lookup"><span data-stu-id="ee7c0-106">[in] The I/O completion port to which to bind `hHandle`.</span></span> <span data-ttu-id="ee7c0-107">の値が null `hPort`の場合、 `hHandle`は既定の i/o 完了ポートにバインドされます。</span><span class="sxs-lookup"><span data-stu-id="ee7c0-107">If the value of `hPort` is null, `hHandle` is bound to the default I/O completion port.</span></span>  
  
 `hHandle`  
 <span data-ttu-id="ee7c0-108">からバインド先のオペレーティングシステムハンドル`hPort`。</span><span class="sxs-lookup"><span data-stu-id="ee7c0-108">[in] The operating system handle to bind to `hPort`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="ee7c0-109">戻り値</span><span class="sxs-lookup"><span data-stu-id="ee7c0-109">Return Value</span></span>  
  
|<span data-ttu-id="ee7c0-110">HRESULT</span><span class="sxs-lookup"><span data-stu-id="ee7c0-110">HRESULT</span></span>|<span data-ttu-id="ee7c0-111">説明</span><span class="sxs-lookup"><span data-stu-id="ee7c0-111">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="ee7c0-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="ee7c0-112">S_OK</span></span>|<span data-ttu-id="ee7c0-113">`Bind`正常に返されました。</span><span class="sxs-lookup"><span data-stu-id="ee7c0-113">`Bind` returned successfully.</span></span>|  
|<span data-ttu-id="ee7c0-114">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="ee7c0-114">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="ee7c0-115">共通言語ランタイム (CLR) がプロセスに読み込まれていないか、CLR がマネージコードを実行できない状態であるか、または呼び出しが正常に処理されていません。</span><span class="sxs-lookup"><span data-stu-id="ee7c0-115">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="ee7c0-116">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="ee7c0-116">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="ee7c0-117">呼び出しがタイムアウトしました。</span><span class="sxs-lookup"><span data-stu-id="ee7c0-117">The call timed out.</span></span>|  
|<span data-ttu-id="ee7c0-118">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="ee7c0-118">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="ee7c0-119">呼び出し元がロックを所有していません。</span><span class="sxs-lookup"><span data-stu-id="ee7c0-119">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="ee7c0-120">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="ee7c0-120">HOST_E_ABANDONED</span></span>|<span data-ttu-id="ee7c0-121">ブロックされたスレッドまたはファイバーが待機しているときに、イベントが取り消されました。</span><span class="sxs-lookup"><span data-stu-id="ee7c0-121">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="ee7c0-122">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="ee7c0-122">E_FAIL</span></span>|<span data-ttu-id="ee7c0-123">原因不明の致命的なエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="ee7c0-123">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="ee7c0-124">メソッドから E_FAIL が返された場合、そのプロセス内で CLR は使用できなくなります。</span><span class="sxs-lookup"><span data-stu-id="ee7c0-124">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="ee7c0-125">後続のホストメソッドの呼び出しでは、HOST_E_CLRNOTAVAILABLE が返されます。</span><span class="sxs-lookup"><span data-stu-id="ee7c0-125">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ee7c0-126">Remarks</span><span class="sxs-lookup"><span data-stu-id="ee7c0-126">Remarks</span></span>  
 <span data-ttu-id="ee7c0-127">I/o 完了ポートは、の呼び出し`CreateIoCompletionPort`を使用して作成されます。</span><span class="sxs-lookup"><span data-stu-id="ee7c0-127">An I/O completion port is created by using a call to `CreateIoCompletionPort`.</span></span> <span data-ttu-id="ee7c0-128">CLR はを`Bind`呼び出して、そのポートにハンドルをバインドします。</span><span class="sxs-lookup"><span data-stu-id="ee7c0-128">The CLR calls `Bind` to bind a handle to that port.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="ee7c0-129">I/o 要求が完了すると、ホストは[Iclriocomplete manager:: OnComplete](../../../../docs/framework/unmanaged-api/hosting/iclriocompletionmanager-oncomplete-method.md)メソッドを呼び出す必要があります。</span><span class="sxs-lookup"><span data-stu-id="ee7c0-129">When an I/O request completes, the host must call the [ICLRIoCompletionManager::OnComplete](../../../../docs/framework/unmanaged-api/hosting/iclriocompletionmanager-oncomplete-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ee7c0-130">必要条件</span><span class="sxs-lookup"><span data-stu-id="ee7c0-130">Requirements</span></span>  
 <span data-ttu-id="ee7c0-131">**・** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="ee7c0-131">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ee7c0-132">**ヘッダー:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="ee7c0-132">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="ee7c0-133">**ライブラリ**Mscoree.dll にリソースとして含まれています</span><span class="sxs-lookup"><span data-stu-id="ee7c0-133">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="ee7c0-134">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ee7c0-134">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ee7c0-135">関連項目</span><span class="sxs-lookup"><span data-stu-id="ee7c0-135">See also</span></span>

- [<span data-ttu-id="ee7c0-136">ICLRIoCompletionManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="ee7c0-136">ICLRIoCompletionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclriocompletionmanager-interface.md)
