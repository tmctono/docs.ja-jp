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
ms.openlocfilehash: d73b8b635be78472374668bbcc36541616705651
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67736550"
---
# <a name="ihostiocompletionmanagerbind-method"></a><span data-ttu-id="d7011-102">IHostIoCompletionManager::Bind メソッド</span><span class="sxs-lookup"><span data-stu-id="d7011-102">IHostIoCompletionManager::Bind Method</span></span>
<span data-ttu-id="d7011-103">指定したハンドルを以前の呼び出しによって作成された I/O 完了ポートにバインド[CreateIoCompletionPort](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-createiocompletionport-method.md)します。</span><span class="sxs-lookup"><span data-stu-id="d7011-103">Binds the specified handle to an I/O completion port that has been created by an earlier call to [CreateIoCompletionPort](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-createiocompletionport-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d7011-104">構文</span><span class="sxs-lookup"><span data-stu-id="d7011-104">Syntax</span></span>  
  
```cpp  
HRESULT Bind (  
    [in] HANDLE hPort,  
    [in] HANDLE hHandle  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d7011-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="d7011-105">Parameters</span></span>  
 `hPort`  
 <span data-ttu-id="d7011-106">[in]I/O 完了ポートにバインドする`hHandle`します。</span><span class="sxs-lookup"><span data-stu-id="d7011-106">[in] The I/O completion port to which to bind `hHandle`.</span></span> <span data-ttu-id="d7011-107">場合の値`hPort`が null、`hHandle`既定の I/O 完了ポートにバインドされます。</span><span class="sxs-lookup"><span data-stu-id="d7011-107">If the value of `hPort` is null, `hHandle` is bound to the default I/O completion port.</span></span>  
  
 `hHandle`  
 <span data-ttu-id="d7011-108">[in]オペレーティング システム ハンドルにバインドする`hPort`します。</span><span class="sxs-lookup"><span data-stu-id="d7011-108">[in] The operating system handle to bind to `hPort`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="d7011-109">戻り値</span><span class="sxs-lookup"><span data-stu-id="d7011-109">Return Value</span></span>  
  
|<span data-ttu-id="d7011-110">HRESULT</span><span class="sxs-lookup"><span data-stu-id="d7011-110">HRESULT</span></span>|<span data-ttu-id="d7011-111">説明</span><span class="sxs-lookup"><span data-stu-id="d7011-111">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="d7011-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="d7011-112">S_OK</span></span>|<span data-ttu-id="d7011-113">`Bind` 正常に返されます。</span><span class="sxs-lookup"><span data-stu-id="d7011-113">`Bind` returned successfully.</span></span>|  
|<span data-ttu-id="d7011-114">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="d7011-114">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="d7011-115">共通言語ランタイム (CLR) は、プロセスに読み込まれていないか、CLR は状態をマネージ コードを実行または呼び出しを正常に処理ができません。</span><span class="sxs-lookup"><span data-stu-id="d7011-115">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="d7011-116">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="d7011-116">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="d7011-117">呼び出しがタイムアウトになりました。</span><span class="sxs-lookup"><span data-stu-id="d7011-117">The call timed out.</span></span>|  
|<span data-ttu-id="d7011-118">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="d7011-118">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="d7011-119">呼び出し元がロックを所有していません。</span><span class="sxs-lookup"><span data-stu-id="d7011-119">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="d7011-120">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="d7011-120">HOST_E_ABANDONED</span></span>|<span data-ttu-id="d7011-121">イベントがキャンセルされましたブロックされたスレッドまたはファイバーが待機しています。</span><span class="sxs-lookup"><span data-stu-id="d7011-121">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="d7011-122">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="d7011-122">E_FAIL</span></span>|<span data-ttu-id="d7011-123">不明な致命的なエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="d7011-123">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="d7011-124">メソッドには、E_FAIL が返される、ときに、CLR は、プロセス内で使用可能ではなくなりました。</span><span class="sxs-lookup"><span data-stu-id="d7011-124">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="d7011-125">メソッドをホストする後続の呼び出しには、HOST_E_CLRNOTAVAILABLE が返されます。</span><span class="sxs-lookup"><span data-stu-id="d7011-125">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d7011-126">Remarks</span><span class="sxs-lookup"><span data-stu-id="d7011-126">Remarks</span></span>  
 <span data-ttu-id="d7011-127">呼び出しを使用して、I/O 完了ポートが作成された`CreateIoCompletionPort`します。</span><span class="sxs-lookup"><span data-stu-id="d7011-127">An I/O completion port is created by using a call to `CreateIoCompletionPort`.</span></span> <span data-ttu-id="d7011-128">CLR 呼び出し`Bind`そのポートへのハンドルにバインドします。</span><span class="sxs-lookup"><span data-stu-id="d7011-128">The CLR calls `Bind` to bind a handle to that port.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d7011-129">I/O 要求を完了すると、ホストで呼び出す必要があります、 [iclriocompletionmanager::oncomplete](../../../../docs/framework/unmanaged-api/hosting/iclriocompletionmanager-oncomplete-method.md)メソッド。</span><span class="sxs-lookup"><span data-stu-id="d7011-129">When an I/O request completes, the host must call the [ICLRIoCompletionManager::OnComplete](../../../../docs/framework/unmanaged-api/hosting/iclriocompletionmanager-oncomplete-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d7011-130">必要条件</span><span class="sxs-lookup"><span data-stu-id="d7011-130">Requirements</span></span>  
 <span data-ttu-id="d7011-131">**プラットフォーム:** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="d7011-131">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d7011-132">**ヘッダー:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="d7011-132">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="d7011-133">**ライブラリ:** MSCorEE.dll でリソースとして含まれます</span><span class="sxs-lookup"><span data-stu-id="d7011-133">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="d7011-134">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d7011-134">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d7011-135">関連項目</span><span class="sxs-lookup"><span data-stu-id="d7011-135">See also</span></span>

- [<span data-ttu-id="d7011-136">ICLRIoCompletionManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="d7011-136">ICLRIoCompletionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclriocompletionmanager-interface.md)
