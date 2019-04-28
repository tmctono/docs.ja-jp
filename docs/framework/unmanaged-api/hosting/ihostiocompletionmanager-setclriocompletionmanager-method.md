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
ms.openlocfilehash: cd48664c78e3f5772cdfa655ebbc7cfa716f4950
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61796845"
---
# <a name="ihostiocompletionmanagersetclriocompletionmanager-method"></a><span data-ttu-id="9f795-102">IHostIoCompletionManager::SetCLRIoCompletionManager メソッド</span><span class="sxs-lookup"><span data-stu-id="9f795-102">IHostIoCompletionManager::SetCLRIoCompletionManager Method</span></span>
<span data-ttu-id="9f795-103">により、ホストへのインターフェイス ポインターで、 [ICLRIoCompletionManager](../../../../docs/framework/unmanaged-api/hosting/iclriocompletionmanager-interface.md)共通言語ランタイム (CLR) によって実装されるインスタンス。</span><span class="sxs-lookup"><span data-stu-id="9f795-103">Provides the host with an interface pointer to the [ICLRIoCompletionManager](../../../../docs/framework/unmanaged-api/hosting/iclriocompletionmanager-interface.md) instance implemented by the common language runtime (CLR).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9f795-104">構文</span><span class="sxs-lookup"><span data-stu-id="9f795-104">Syntax</span></span>  
  
```  
HRESULT SetCLRIoCompletionManager (  
    [in] ICLRIoCompletionManager *pManager  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9f795-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="9f795-105">Parameters</span></span>  
 `pManager`  
 <span data-ttu-id="9f795-106">[in]インターフェイス ポインターを`ICLRIoCompletionManager`CLR によって指定されたインスタンス。</span><span class="sxs-lookup"><span data-stu-id="9f795-106">[in] An interface pointer to an `ICLRIoCompletionManager` instance provided by the CLR.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="9f795-107">戻り値</span><span class="sxs-lookup"><span data-stu-id="9f795-107">Return Value</span></span>  
  
|<span data-ttu-id="9f795-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="9f795-108">HRESULT</span></span>|<span data-ttu-id="9f795-109">説明</span><span class="sxs-lookup"><span data-stu-id="9f795-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="9f795-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="9f795-110">S_OK</span></span>|<span data-ttu-id="9f795-111">`SetCLRIoCompletionManager` 正常に返されます。</span><span class="sxs-lookup"><span data-stu-id="9f795-111">`SetCLRIoCompletionManager` returned successfully.</span></span>|  
|<span data-ttu-id="9f795-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="9f795-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="9f795-113">プロセスに CLR が読み込まれていないか、CLR は状態をマネージ コードを実行または呼び出しを正常に処理ができません。</span><span class="sxs-lookup"><span data-stu-id="9f795-113">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="9f795-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="9f795-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="9f795-115">呼び出しがタイムアウトになりました。</span><span class="sxs-lookup"><span data-stu-id="9f795-115">The call timed out.</span></span>|  
|<span data-ttu-id="9f795-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="9f795-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="9f795-117">呼び出し元がロックを所有していません。</span><span class="sxs-lookup"><span data-stu-id="9f795-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="9f795-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="9f795-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="9f795-119">イベントがキャンセルされましたブロックされたスレッドまたはファイバーが待機しています。</span><span class="sxs-lookup"><span data-stu-id="9f795-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="9f795-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="9f795-120">E_FAIL</span></span>|<span data-ttu-id="9f795-121">不明な致命的なエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="9f795-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="9f795-122">メソッドには、E_FAIL が返される、ときに、CLR は、プロセス内で使用可能ではなくなりました。</span><span class="sxs-lookup"><span data-stu-id="9f795-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="9f795-123">メソッドをホストする後続の呼び出しには、HOST_E_CLRNOTAVAILABLE が返されます。</span><span class="sxs-lookup"><span data-stu-id="9f795-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9f795-124">Remarks</span><span class="sxs-lookup"><span data-stu-id="9f795-124">Remarks</span></span>  
 <span data-ttu-id="9f795-125">CLR が呼び出された後`SetCLRIoCompletionManager`、ホストが呼び出す必要があります[iclriocompletionmanager::oncomplete](../../../../docs/framework/unmanaged-api/hosting/iclriocompletionmanager-oncomplete-method.md)が I/O 要求が完了したときに CLR に通知します。</span><span class="sxs-lookup"><span data-stu-id="9f795-125">After the CLR has called `SetCLRIoCompletionManager`, the host must call [ICLRIoCompletionManager::OnComplete](../../../../docs/framework/unmanaged-api/hosting/iclriocompletionmanager-oncomplete-method.md) to notify the CLR when an I/O request has been completed.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9f795-126">必要条件</span><span class="sxs-lookup"><span data-stu-id="9f795-126">Requirements</span></span>  
 <span data-ttu-id="9f795-127">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="9f795-127">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9f795-128">**ヘッダー:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="9f795-128">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="9f795-129">**ライブラリ:** MSCorEE.dll でリソースとして含まれます</span><span class="sxs-lookup"><span data-stu-id="9f795-129">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="9f795-130">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9f795-130">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9f795-131">関連項目</span><span class="sxs-lookup"><span data-stu-id="9f795-131">See also</span></span>

- [<span data-ttu-id="9f795-132">ICLRIoCompletionManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="9f795-132">ICLRIoCompletionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclriocompletionmanager-interface.md)
- [<span data-ttu-id="9f795-133">IHostIoCompletionManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="9f795-133">IHostIoCompletionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-interface.md)
