---
title: IHostMemoryManager::RegisterMemoryNotificationCallback メソッド
ms.date: 03/30/2017
api_name:
- IHostMemoryManager.RegisterMemoryNotificationCallback
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostMemoryManager::RegisterMemoryNotificationCallback
helpviewer_keywords:
- IHostMemoryManager::RegisterMemoryNotificationCallback method [.NET Framework hosting]
- RegisterMemoryNotificationCallback method [.NET Framework hosting]
ms.assetid: 65d301f6-4dbb-4b5f-8eff-82540e2b6465
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 87dfbe85d279aa191253857887c1d9b5b5f8c7cc
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2019
ms.locfileid: "59088523"
---
# <a name="ihostmemorymanagerregistermemorynotificationcallback-method"></a><span data-ttu-id="ebede-102">IHostMemoryManager::RegisterMemoryNotificationCallback メソッド</span><span class="sxs-lookup"><span data-stu-id="ebede-102">IHostMemoryManager::RegisterMemoryNotificationCallback Method</span></span>
<span data-ttu-id="ebede-103">コンピューターの現在のメモリ負荷のホストが共通言語ランタイム (CLR) に通知するために呼び出すコールバック関数へのポインターを登録します。</span><span class="sxs-lookup"><span data-stu-id="ebede-103">Registers a pointer to a callback function that the host invokes to notify the common language runtime (CLR) of the current memory load on the computer.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ebede-104">構文</span><span class="sxs-lookup"><span data-stu-id="ebede-104">Syntax</span></span>  
  
```  
HRESULT RegisterMemoryNotificationCallback (  
    [in] ICLRMemoryNotificationCallback* pCallback  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ebede-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="ebede-105">Parameters</span></span>  
 `pCallback`  
 <span data-ttu-id="ebede-106">[in]インターフェイス ポインターを[ICLRMemoryNotificationCallback](../../../../docs/framework/unmanaged-api/hosting/iclrmemorynotificationcallback-interface.md) CLR によって実装されているインスタンス。</span><span class="sxs-lookup"><span data-stu-id="ebede-106">[in] An interface pointer to an [ICLRMemoryNotificationCallback](../../../../docs/framework/unmanaged-api/hosting/iclrmemorynotificationcallback-interface.md) instance that is implemented by the CLR.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="ebede-107">戻り値</span><span class="sxs-lookup"><span data-stu-id="ebede-107">Return Value</span></span>  
  
|<span data-ttu-id="ebede-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="ebede-108">HRESULT</span></span>|<span data-ttu-id="ebede-109">説明</span><span class="sxs-lookup"><span data-stu-id="ebede-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="ebede-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="ebede-110">S_OK</span></span>|`RegisterMemoryNotificationCallback` <span data-ttu-id="ebede-111">正常に返されます。</span><span class="sxs-lookup"><span data-stu-id="ebede-111">returned successfully.</span></span>|  
|<span data-ttu-id="ebede-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="ebede-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="ebede-113">プロセスに CLR が読み込まれていないか、CLR は状態をマネージ コードを実行または呼び出しを正常に処理ができません。</span><span class="sxs-lookup"><span data-stu-id="ebede-113">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="ebede-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="ebede-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="ebede-115">呼び出しがタイムアウトになりました。</span><span class="sxs-lookup"><span data-stu-id="ebede-115">The call timed out.</span></span>|  
|<span data-ttu-id="ebede-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="ebede-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="ebede-117">呼び出し元がロックを所有していません。</span><span class="sxs-lookup"><span data-stu-id="ebede-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="ebede-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="ebede-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="ebede-119">イベントがキャンセルされましたブロックされたスレッドまたはファイバーが待機しています。</span><span class="sxs-lookup"><span data-stu-id="ebede-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="ebede-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="ebede-120">E_FAIL</span></span>|<span data-ttu-id="ebede-121">不明な致命的なエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="ebede-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="ebede-122">メソッドには、E_FAIL が返される、ときに、CLR は、プロセス内で使用可能ではなくなりました。</span><span class="sxs-lookup"><span data-stu-id="ebede-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="ebede-123">メソッドをホストする後続の呼び出しには、HOST_E_CLRNOTAVAILABLE が返されます。</span><span class="sxs-lookup"><span data-stu-id="ebede-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ebede-124">Remarks</span><span class="sxs-lookup"><span data-stu-id="ebede-124">Remarks</span></span>  
 <span data-ttu-id="ebede-125">`ICLRMemoryNotificationCallback`インターフェイスが 1 つのメソッドを定義します ([iclrmemorynotificationcallback::onmemorynotification](../../../../docs/framework/unmanaged-api/hosting/iclrmemorynotificationcallback-onmemorynotification-method.md))、ためと`pCallback`へのポインター、 `ICLRMemoryNotificationCallback` CLR によって提供されるインスタンス、コールバック関数自体の登録で効果的にあります。</span><span class="sxs-lookup"><span data-stu-id="ebede-125">Because the `ICLRMemoryNotificationCallback` interface defines only one method ([ICLRMemoryNotificationCallback::OnMemoryNotification](../../../../docs/framework/unmanaged-api/hosting/iclrmemorynotificationcallback-onmemorynotification-method.md)), and because `pCallback` is a pointer to an `ICLRMemoryNotificationCallback` instance provided by the CLR, the registration is effectively for the callback function itself.</span></span> <span data-ttu-id="ebede-126">ホストが呼び出す`OnMemoryNotification`標準の Win32 を使用するのではなく、メモリ不足の状態を報告する、`CreateMemoryResourceNotification`関数。</span><span class="sxs-lookup"><span data-stu-id="ebede-126">The host invokes `OnMemoryNotification` to report memory pressure conditions, rather than using the standard Win32 `CreateMemoryResourceNotification` function.</span></span> <span data-ttu-id="ebede-127">詳細については、Windows プラットフォームのドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="ebede-127">For more information, see the Windows Platform documentation.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ebede-128">呼び出す`OnMemoryNotification`ブロックことはありません。</span><span class="sxs-lookup"><span data-stu-id="ebede-128">Calls to `OnMemoryNotification` never block.</span></span> <span data-ttu-id="ebede-129">常に直ちに戻ります。</span><span class="sxs-lookup"><span data-stu-id="ebede-129">They always return immediately.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ebede-130">必要条件</span><span class="sxs-lookup"><span data-stu-id="ebede-130">Requirements</span></span>  
 <span data-ttu-id="ebede-131">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="ebede-131">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ebede-132">**ヘッダー:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="ebede-132">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="ebede-133">**ライブラリ:** MSCorEE.dll でリソースとして含まれます</span><span class="sxs-lookup"><span data-stu-id="ebede-133">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="ebede-134">.NET Framework のバージョン: </span><span class="sxs-lookup"><span data-stu-id="ebede-134">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="ebede-135">関連項目</span><span class="sxs-lookup"><span data-stu-id="ebede-135">See also</span></span>

- [<span data-ttu-id="ebede-136">ICLRMemoryNotificationCallback インターフェイス</span><span class="sxs-lookup"><span data-stu-id="ebede-136">ICLRMemoryNotificationCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrmemorynotificationcallback-interface.md)
- [<span data-ttu-id="ebede-137">IHostMemoryManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="ebede-137">IHostMemoryManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-interface.md)
