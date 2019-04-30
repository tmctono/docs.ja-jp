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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 8cf7978af4081b84a361e0a96a6c9da7180cb217
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61951724"
---
# <a name="ihostiocompletionmanagercreateiocompletionport-method"></a><span data-ttu-id="54843-102">IHostIoCompletionManager::CreateIoCompletionPort メソッド</span><span class="sxs-lookup"><span data-stu-id="54843-102">IHostIoCompletionManager::CreateIoCompletionPort Method</span></span>
<span data-ttu-id="54843-103">ホストが新しい I/O 完了ポートを作成することを要求します。</span><span class="sxs-lookup"><span data-stu-id="54843-103">Requests that the host create a new I/O completion port.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="54843-104">構文</span><span class="sxs-lookup"><span data-stu-id="54843-104">Syntax</span></span>  
  
```  
HRESULT CreateIoCompletionPort (  
    [out] HANDLE *phPort  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="54843-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="54843-105">Parameters</span></span>  
 `phPort`  
 <span data-ttu-id="54843-106">[out]新しく作成された I/O 完了ポート、または 0 (ゼロ)、ポートを作成できませんでしたがへのハンドルへのポインター。</span><span class="sxs-lookup"><span data-stu-id="54843-106">[out] A pointer to a handle to the newly created I/O completion port, or 0 (zero), if the port could not be created.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="54843-107">戻り値</span><span class="sxs-lookup"><span data-stu-id="54843-107">Return Value</span></span>  
  
|<span data-ttu-id="54843-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="54843-108">HRESULT</span></span>|<span data-ttu-id="54843-109">説明</span><span class="sxs-lookup"><span data-stu-id="54843-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="54843-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="54843-110">S_OK</span></span>|<span data-ttu-id="54843-111">`CreateIoCompletionPort` 正常に返されます。</span><span class="sxs-lookup"><span data-stu-id="54843-111">`CreateIoCompletionPort` returned successfully.</span></span>|  
|<span data-ttu-id="54843-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="54843-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="54843-113">共通言語ランタイム (CLR) は、プロセスに読み込まれていないか、CLR は状態をマネージ コードを実行または呼び出しを正常に処理ができません。</span><span class="sxs-lookup"><span data-stu-id="54843-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="54843-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="54843-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="54843-115">呼び出しがタイムアウトになりました。</span><span class="sxs-lookup"><span data-stu-id="54843-115">The call timed out.</span></span>|  
|<span data-ttu-id="54843-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="54843-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="54843-117">呼び出し元がロックを所有していません。</span><span class="sxs-lookup"><span data-stu-id="54843-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="54843-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="54843-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="54843-119">イベントがキャンセルされましたブロックされたスレッドまたはファイバーが待機しています。</span><span class="sxs-lookup"><span data-stu-id="54843-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="54843-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="54843-120">E_FAIL</span></span>|<span data-ttu-id="54843-121">不明な致命的なエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="54843-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="54843-122">メソッドには、E_FAIL が返される、ときに、CLR は、プロセス内で使用可能ではなくなりました。</span><span class="sxs-lookup"><span data-stu-id="54843-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="54843-123">メソッドをホストする後続の呼び出しには、HOST_E_CLRNOTAVAILABLE が返されます。</span><span class="sxs-lookup"><span data-stu-id="54843-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="54843-124">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="54843-124">E_OUTOFMEMORY</span></span>|<span data-ttu-id="54843-125">メモリが不足していますが、要求されたリソースを割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="54843-125">Not enough memory was available to allocate the requested resource.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="54843-126">Remarks</span><span class="sxs-lookup"><span data-stu-id="54843-126">Remarks</span></span>  
 <span data-ttu-id="54843-127">CLR の呼び出し、`CreateIoCompletionPort`メソッドをホストで新しい I/O 完了ポートを作成するよう依頼します。</span><span class="sxs-lookup"><span data-stu-id="54843-127">The CLR calls the `CreateIoCompletionPort` method to request that the host create a new I/O completion port.</span></span> <span data-ttu-id="54843-128">呼び出すことによってこのポートにバインドする I/O 操作、 [ihostiocompletionmanager::bind](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-bind-method.md)メソッド。</span><span class="sxs-lookup"><span data-stu-id="54843-128">It binds I/O operations to this port through a call to the [IHostIoCompletionManager::Bind](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-bind-method.md) method.</span></span> <span data-ttu-id="54843-129">ホストの状態に報告、CLR を呼び出して[iclriocompletionmanager::oncomplete](../../../../docs/framework/unmanaged-api/hosting/iclriocompletionmanager-oncomplete-method.md)します。</span><span class="sxs-lookup"><span data-stu-id="54843-129">The host reports status back to the CLR by calling [ICLRIoCompletionManager::OnComplete](../../../../docs/framework/unmanaged-api/hosting/iclriocompletionmanager-oncomplete-method.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="54843-130">必要条件</span><span class="sxs-lookup"><span data-stu-id="54843-130">Requirements</span></span>  
 <span data-ttu-id="54843-131">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="54843-131">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="54843-132">**ヘッダー:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="54843-132">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="54843-133">**ライブラリ:** MSCorEE.dll でリソースとして含まれます</span><span class="sxs-lookup"><span data-stu-id="54843-133">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="54843-134">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="54843-134">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="54843-135">関連項目</span><span class="sxs-lookup"><span data-stu-id="54843-135">See also</span></span>

- [<span data-ttu-id="54843-136">ICLRIoCompletionManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="54843-136">ICLRIoCompletionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclriocompletionmanager-interface.md)
- [<span data-ttu-id="54843-137">IHostIoCompletionManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="54843-137">IHostIoCompletionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-interface.md)
