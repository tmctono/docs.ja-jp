---
title: IHostIoCompletionManager::SetCLRIoCompletionManager メソッド
ms.date: 03/30/2017
api_name:
- IHostIoCompletionManager.SetCLRIoCompletionManager
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostIoCompletionManager::SetCLRIoCompletionManager
helpviewer_keywords:
- IHostIoCompletionManager::SetCLRIoCompletionManager method [.NET Framework hosting]
- SetCLRIoCompletionManager method [.NET Framework hosting]
ms.assetid: 4254bb01-3a14-4f34-a3be-60ff1f5072b5
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 97d4561c34c03eefc7487f5f96b7a490a480ac19
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67780757"
---
# <a name="ihostiocompletionmanagersetclriocompletionmanager-method"></a><span data-ttu-id="488b7-102">IHostIoCompletionManager::SetCLRIoCompletionManager メソッド</span><span class="sxs-lookup"><span data-stu-id="488b7-102">IHostIoCompletionManager::SetCLRIoCompletionManager Method</span></span>
<span data-ttu-id="488b7-103">により、ホストへのインターフェイス ポインターで、 [ICLRIoCompletionManager](../../../../docs/framework/unmanaged-api/hosting/iclriocompletionmanager-interface.md)共通言語ランタイム (CLR) によって実装されるインスタンス。</span><span class="sxs-lookup"><span data-stu-id="488b7-103">Provides the host with an interface pointer to the [ICLRIoCompletionManager](../../../../docs/framework/unmanaged-api/hosting/iclriocompletionmanager-interface.md) instance implemented by the common language runtime (CLR).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="488b7-104">構文</span><span class="sxs-lookup"><span data-stu-id="488b7-104">Syntax</span></span>  
  
```cpp  
HRESULT SetCLRIoCompletionManager (  
    [in] ICLRIoCompletionManager *pManager  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="488b7-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="488b7-105">Parameters</span></span>  
 `pManager`  
 <span data-ttu-id="488b7-106">[in]インターフェイス ポインターを`ICLRIoCompletionManager`CLR によって指定されたインスタンス。</span><span class="sxs-lookup"><span data-stu-id="488b7-106">[in] An interface pointer to an `ICLRIoCompletionManager` instance provided by the CLR.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="488b7-107">戻り値</span><span class="sxs-lookup"><span data-stu-id="488b7-107">Return Value</span></span>  
  
|<span data-ttu-id="488b7-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="488b7-108">HRESULT</span></span>|<span data-ttu-id="488b7-109">説明</span><span class="sxs-lookup"><span data-stu-id="488b7-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="488b7-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="488b7-110">S_OK</span></span>|<span data-ttu-id="488b7-111">`SetCLRIoCompletionManager` 正常に返されます。</span><span class="sxs-lookup"><span data-stu-id="488b7-111">`SetCLRIoCompletionManager` returned successfully.</span></span>|  
|<span data-ttu-id="488b7-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="488b7-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="488b7-113">プロセスに CLR が読み込まれていないか、CLR は状態をマネージ コードを実行または呼び出しを正常に処理ができません。</span><span class="sxs-lookup"><span data-stu-id="488b7-113">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="488b7-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="488b7-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="488b7-115">呼び出しがタイムアウトになりました。</span><span class="sxs-lookup"><span data-stu-id="488b7-115">The call timed out.</span></span>|  
|<span data-ttu-id="488b7-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="488b7-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="488b7-117">呼び出し元がロックを所有していません。</span><span class="sxs-lookup"><span data-stu-id="488b7-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="488b7-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="488b7-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="488b7-119">イベントがキャンセルされましたブロックされたスレッドまたはファイバーが待機しています。</span><span class="sxs-lookup"><span data-stu-id="488b7-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="488b7-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="488b7-120">E_FAIL</span></span>|<span data-ttu-id="488b7-121">不明な致命的なエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="488b7-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="488b7-122">メソッドには、E_FAIL が返される、ときに、CLR は、プロセス内で使用可能ではなくなりました。</span><span class="sxs-lookup"><span data-stu-id="488b7-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="488b7-123">メソッドをホストする後続の呼び出しには、HOST_E_CLRNOTAVAILABLE が返されます。</span><span class="sxs-lookup"><span data-stu-id="488b7-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="488b7-124">Remarks</span><span class="sxs-lookup"><span data-stu-id="488b7-124">Remarks</span></span>  
 <span data-ttu-id="488b7-125">CLR が呼び出された後`SetCLRIoCompletionManager`、ホストが呼び出す必要があります[iclriocompletionmanager::oncomplete](../../../../docs/framework/unmanaged-api/hosting/iclriocompletionmanager-oncomplete-method.md)が I/O 要求が完了したときに CLR に通知します。</span><span class="sxs-lookup"><span data-stu-id="488b7-125">After the CLR has called `SetCLRIoCompletionManager`, the host must call [ICLRIoCompletionManager::OnComplete](../../../../docs/framework/unmanaged-api/hosting/iclriocompletionmanager-oncomplete-method.md) to notify the CLR when an I/O request has been completed.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="488b7-126">必要条件</span><span class="sxs-lookup"><span data-stu-id="488b7-126">Requirements</span></span>  
 <span data-ttu-id="488b7-127">**プラットフォーム:** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="488b7-127">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="488b7-128">**ヘッダー:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="488b7-128">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="488b7-129">**ライブラリ:** MSCorEE.dll でリソースとして含まれます</span><span class="sxs-lookup"><span data-stu-id="488b7-129">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="488b7-130">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="488b7-130">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="488b7-131">関連項目</span><span class="sxs-lookup"><span data-stu-id="488b7-131">See also</span></span>

- [<span data-ttu-id="488b7-132">ICLRIoCompletionManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="488b7-132">ICLRIoCompletionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclriocompletionmanager-interface.md)
- [<span data-ttu-id="488b7-133">IHostIoCompletionManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="488b7-133">IHostIoCompletionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-interface.md)
