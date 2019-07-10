---
title: IHostIoCompletionManager::CloseIoCompletionPort メソッド
ms.date: 03/30/2017
api_name:
- IHostIoCompletionManager.CloseIoCompletionPort
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostIoCompletionManager::CloseIoCompletionPort
helpviewer_keywords:
- IHostIoCompletionManager::CloseIoCompletionPort method [.NET Framework hosting]
- CloseIoCompletionPort method [.NET Framework hosting]
ms.assetid: e86ad7be-3758-498a-a972-5522d69dfbb3
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: cceced01b34f10cf38b41cfcb2a17059650f9ad9
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67736540"
---
# <a name="ihostiocompletionmanagercloseiocompletionport-method"></a><span data-ttu-id="4dea4-102">IHostIoCompletionManager::CloseIoCompletionPort メソッド</span><span class="sxs-lookup"><span data-stu-id="4dea4-102">IHostIoCompletionManager::CloseIoCompletionPort Method</span></span>
<span data-ttu-id="4dea4-103">ホストが事前に呼び出したが開かれたポートを閉じることを要求[CreateIoCompletionPort](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-createiocompletionport-method.md)します。</span><span class="sxs-lookup"><span data-stu-id="4dea4-103">Requests that the host close a port that was opened through an earlier call to [CreateIoCompletionPort](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-createiocompletionport-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4dea4-104">構文</span><span class="sxs-lookup"><span data-stu-id="4dea4-104">Syntax</span></span>  
  
```cpp  
HRESULT CloseIoCompletionPort (  
    [in] HANDLE hPort  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4dea4-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="4dea4-105">Parameters</span></span>  
 `hPort`  
 <span data-ttu-id="4dea4-106">[in]ポートを閉じるのハンドル。</span><span class="sxs-lookup"><span data-stu-id="4dea4-106">[in] The handle of the port to close.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="4dea4-107">戻り値</span><span class="sxs-lookup"><span data-stu-id="4dea4-107">Return Value</span></span>  
  
|<span data-ttu-id="4dea4-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="4dea4-108">HRESULT</span></span>|<span data-ttu-id="4dea4-109">説明</span><span class="sxs-lookup"><span data-stu-id="4dea4-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="4dea4-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="4dea4-110">S_OK</span></span>|<span data-ttu-id="4dea4-111">`CloseIoCompletionPort` 正常に返されます。</span><span class="sxs-lookup"><span data-stu-id="4dea4-111">`CloseIoCompletionPort` returned successfully.</span></span>|  
|<span data-ttu-id="4dea4-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="4dea4-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="4dea4-113">共通言語ランタイム (CLR) は、プロセスに読み込まれていないか、CLR は状態をマネージ コードを実行または呼び出しを正常に処理ができません。</span><span class="sxs-lookup"><span data-stu-id="4dea4-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="4dea4-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="4dea4-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="4dea4-115">呼び出しがタイムアウトになりました。</span><span class="sxs-lookup"><span data-stu-id="4dea4-115">The call timed out.</span></span>|  
|<span data-ttu-id="4dea4-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="4dea4-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="4dea4-117">呼び出し元がロックを所有していません。</span><span class="sxs-lookup"><span data-stu-id="4dea4-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="4dea4-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="4dea4-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="4dea4-119">イベントがキャンセルされましたブロックされたスレッドまたはファイバーが待機しています。</span><span class="sxs-lookup"><span data-stu-id="4dea4-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="4dea4-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="4dea4-120">E_FAIL</span></span>|<span data-ttu-id="4dea4-121">不明な致命的なエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="4dea4-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="4dea4-122">メソッドには、E_FAIL が返される、ときに、CLR は、プロセス内で使用可能ではなくなりました。</span><span class="sxs-lookup"><span data-stu-id="4dea4-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="4dea4-123">メソッドをホストする後続の呼び出しには、HOST_E_CLRNOTAVAILABLE が返されます。</span><span class="sxs-lookup"><span data-stu-id="4dea4-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="4dea4-124">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="4dea4-124">E_INVALIDARG</span></span>|<span data-ttu-id="4dea4-125">無効なポート ハンドルが渡されました。</span><span class="sxs-lookup"><span data-stu-id="4dea4-125">An invalid port handle was passed.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4dea4-126">Remarks</span><span class="sxs-lookup"><span data-stu-id="4dea4-126">Remarks</span></span>  
 <span data-ttu-id="4dea4-127">`hPort` 以前の呼び出しによって作成されたポートを識別するハンドルである必要があります`CreateIoCompletionPort`します。</span><span class="sxs-lookup"><span data-stu-id="4dea4-127">`hPort` must be a handle to a port that was created by an earlier call to `CreateIoCompletionPort`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4dea4-128">必要条件</span><span class="sxs-lookup"><span data-stu-id="4dea4-128">Requirements</span></span>  
 <span data-ttu-id="4dea4-129">**プラットフォーム:** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="4dea4-129">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4dea4-130">**ヘッダー:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="4dea4-130">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="4dea4-131">**ライブラリ:** MSCorEE.dll でリソースとして含まれます</span><span class="sxs-lookup"><span data-stu-id="4dea4-131">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="4dea4-132">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4dea4-132">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4dea4-133">関連項目</span><span class="sxs-lookup"><span data-stu-id="4dea4-133">See also</span></span>

- [<span data-ttu-id="4dea4-134">ICLRIoCompletionManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="4dea4-134">ICLRIoCompletionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclriocompletionmanager-interface.md)
- [<span data-ttu-id="4dea4-135">IHostIoCompletionManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="4dea4-135">IHostIoCompletionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-interface.md)
