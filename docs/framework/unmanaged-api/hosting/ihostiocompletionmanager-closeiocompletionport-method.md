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
ms.openlocfilehash: 32a7c8b1c1c61eddb18ade1e77af5ea973fbaadc
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2019
ms.locfileid: "59107563"
---
# <a name="ihostiocompletionmanagercloseiocompletionport-method"></a><span data-ttu-id="b013a-102">IHostIoCompletionManager::CloseIoCompletionPort メソッド</span><span class="sxs-lookup"><span data-stu-id="b013a-102">IHostIoCompletionManager::CloseIoCompletionPort Method</span></span>
<span data-ttu-id="b013a-103">ホストが事前に呼び出したが開かれたポートを閉じることを要求[CreateIoCompletionPort](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-createiocompletionport-method.md)します。</span><span class="sxs-lookup"><span data-stu-id="b013a-103">Requests that the host close a port that was opened through an earlier call to [CreateIoCompletionPort](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-createiocompletionport-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b013a-104">構文</span><span class="sxs-lookup"><span data-stu-id="b013a-104">Syntax</span></span>  
  
```  
HRESULT CloseIoCompletionPort (  
    [in] HANDLE hPort  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b013a-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="b013a-105">Parameters</span></span>  
 `hPort`  
 <span data-ttu-id="b013a-106">[in]ポートを閉じるのハンドル。</span><span class="sxs-lookup"><span data-stu-id="b013a-106">[in] The handle of the port to close.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="b013a-107">戻り値</span><span class="sxs-lookup"><span data-stu-id="b013a-107">Return Value</span></span>  
  
|<span data-ttu-id="b013a-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="b013a-108">HRESULT</span></span>|<span data-ttu-id="b013a-109">説明</span><span class="sxs-lookup"><span data-stu-id="b013a-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="b013a-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="b013a-110">S_OK</span></span>|`CloseIoCompletionPort` <span data-ttu-id="b013a-111">正常に返されます。</span><span class="sxs-lookup"><span data-stu-id="b013a-111">returned successfully.</span></span>|  
|<span data-ttu-id="b013a-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="b013a-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="b013a-113">共通言語ランタイム (CLR) は、プロセスに読み込まれていないか、CLR は状態をマネージ コードを実行または呼び出しを正常に処理ができません。</span><span class="sxs-lookup"><span data-stu-id="b013a-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="b013a-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="b013a-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="b013a-115">呼び出しがタイムアウトになりました。</span><span class="sxs-lookup"><span data-stu-id="b013a-115">The call timed out.</span></span>|  
|<span data-ttu-id="b013a-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="b013a-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="b013a-117">呼び出し元がロックを所有していません。</span><span class="sxs-lookup"><span data-stu-id="b013a-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="b013a-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="b013a-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="b013a-119">イベントがキャンセルされましたブロックされたスレッドまたはファイバーが待機しています。</span><span class="sxs-lookup"><span data-stu-id="b013a-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="b013a-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="b013a-120">E_FAIL</span></span>|<span data-ttu-id="b013a-121">不明な致命的なエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="b013a-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="b013a-122">メソッドには、E_FAIL が返される、ときに、CLR は、プロセス内で使用可能ではなくなりました。</span><span class="sxs-lookup"><span data-stu-id="b013a-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="b013a-123">メソッドをホストする後続の呼び出しには、HOST_E_CLRNOTAVAILABLE が返されます。</span><span class="sxs-lookup"><span data-stu-id="b013a-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="b013a-124">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="b013a-124">E_INVALIDARG</span></span>|<span data-ttu-id="b013a-125">無効なポート ハンドルが渡されました。</span><span class="sxs-lookup"><span data-stu-id="b013a-125">An invalid port handle was passed.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b013a-126">Remarks</span><span class="sxs-lookup"><span data-stu-id="b013a-126">Remarks</span></span>  
 `hPort` <span data-ttu-id="b013a-127">以前の呼び出しによって作成されたポートを識別するハンドルである必要があります`CreateIoCompletionPort`します。</span><span class="sxs-lookup"><span data-stu-id="b013a-127">must be a handle to a port that was created by an earlier call to `CreateIoCompletionPort`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b013a-128">必要条件</span><span class="sxs-lookup"><span data-stu-id="b013a-128">Requirements</span></span>  
 <span data-ttu-id="b013a-129">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="b013a-129">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b013a-130">**ヘッダー:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="b013a-130">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="b013a-131">**ライブラリ:** MSCorEE.dll でリソースとして含まれます</span><span class="sxs-lookup"><span data-stu-id="b013a-131">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="b013a-132">.NET Framework のバージョン: </span><span class="sxs-lookup"><span data-stu-id="b013a-132">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="b013a-133">関連項目</span><span class="sxs-lookup"><span data-stu-id="b013a-133">See also</span></span>

- [<span data-ttu-id="b013a-134">ICLRIoCompletionManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="b013a-134">ICLRIoCompletionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclriocompletionmanager-interface.md)
- [<span data-ttu-id="b013a-135">IHostIoCompletionManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="b013a-135">IHostIoCompletionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-interface.md)
