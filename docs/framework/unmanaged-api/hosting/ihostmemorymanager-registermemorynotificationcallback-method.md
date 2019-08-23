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
ms.openlocfilehash: 34701642a9e76ec52141e00fe9dde92878faccd2
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2019
ms.locfileid: "69945436"
---
# <a name="ihostmemorymanagerregistermemorynotificationcallback-method"></a><span data-ttu-id="87f7b-102">IHostMemoryManager::RegisterMemoryNotificationCallback メソッド</span><span class="sxs-lookup"><span data-stu-id="87f7b-102">IHostMemoryManager::RegisterMemoryNotificationCallback Method</span></span>
<span data-ttu-id="87f7b-103">コンピューターの現在のメモリ負荷を共通言語ランタイム (CLR) に通知するために、ホストが呼び出すコールバック関数へのポインターを登録します。</span><span class="sxs-lookup"><span data-stu-id="87f7b-103">Registers a pointer to a callback function that the host invokes to notify the common language runtime (CLR) of the current memory load on the computer.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="87f7b-104">構文</span><span class="sxs-lookup"><span data-stu-id="87f7b-104">Syntax</span></span>  
  
```cpp  
HRESULT RegisterMemoryNotificationCallback (  
    [in] ICLRMemoryNotificationCallback* pCallback  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="87f7b-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="87f7b-105">Parameters</span></span>  
 `pCallback`  
 <span data-ttu-id="87f7b-106">からCLR によって実装される[ICLRMemoryNotificationCallback](../../../../docs/framework/unmanaged-api/hosting/iclrmemorynotificationcallback-interface.md)インスタンスへのインターフェイスポインター。</span><span class="sxs-lookup"><span data-stu-id="87f7b-106">[in] An interface pointer to an [ICLRMemoryNotificationCallback](../../../../docs/framework/unmanaged-api/hosting/iclrmemorynotificationcallback-interface.md) instance that is implemented by the CLR.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="87f7b-107">戻り値</span><span class="sxs-lookup"><span data-stu-id="87f7b-107">Return Value</span></span>  
  
|<span data-ttu-id="87f7b-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="87f7b-108">HRESULT</span></span>|<span data-ttu-id="87f7b-109">説明</span><span class="sxs-lookup"><span data-stu-id="87f7b-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="87f7b-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="87f7b-110">S_OK</span></span>|<span data-ttu-id="87f7b-111">`RegisterMemoryNotificationCallback`正常に返されました。</span><span class="sxs-lookup"><span data-stu-id="87f7b-111">`RegisterMemoryNotificationCallback` returned successfully.</span></span>|  
|<span data-ttu-id="87f7b-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="87f7b-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="87f7b-113">CLR がプロセスに読み込まれていないか、CLR がマネージドコードを実行できない状態であるか、または呼び出しが正常に処理されていません。</span><span class="sxs-lookup"><span data-stu-id="87f7b-113">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="87f7b-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="87f7b-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="87f7b-115">呼び出しがタイムアウトしました。</span><span class="sxs-lookup"><span data-stu-id="87f7b-115">The call timed out.</span></span>|  
|<span data-ttu-id="87f7b-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="87f7b-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="87f7b-117">呼び出し元がロックを所有していません。</span><span class="sxs-lookup"><span data-stu-id="87f7b-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="87f7b-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="87f7b-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="87f7b-119">ブロックされたスレッドまたはファイバーが待機しているときに、イベントが取り消されました。</span><span class="sxs-lookup"><span data-stu-id="87f7b-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="87f7b-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="87f7b-120">E_FAIL</span></span>|<span data-ttu-id="87f7b-121">原因不明の致命的なエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="87f7b-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="87f7b-122">メソッドから E_FAIL が返された場合、そのプロセス内で CLR は使用できなくなります。</span><span class="sxs-lookup"><span data-stu-id="87f7b-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="87f7b-123">後続のホストメソッドの呼び出しでは、HOST_E_CLRNOTAVAILABLE が返されます。</span><span class="sxs-lookup"><span data-stu-id="87f7b-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="87f7b-124">Remarks</span><span class="sxs-lookup"><span data-stu-id="87f7b-124">Remarks</span></span>  
 <span data-ttu-id="87f7b-125">インターフェイスは`ICLRMemoryNotificationCallback` 1 つのメソッド ([ICLRMemoryNotificationCallback:: onmemorynotification](../../../../docs/framework/unmanaged-api/hosting/iclrmemorynotificationcallback-onmemorynotification-method.md)) のみを定義する`pCallback`ため、は CLR に`ICLRMemoryNotificationCallback`よって提供されるインスタンスへのポインターであるため、コールバック関数自体。</span><span class="sxs-lookup"><span data-stu-id="87f7b-125">Because the `ICLRMemoryNotificationCallback` interface defines only one method ([ICLRMemoryNotificationCallback::OnMemoryNotification](../../../../docs/framework/unmanaged-api/hosting/iclrmemorynotificationcallback-onmemorynotification-method.md)), and because `pCallback` is a pointer to an `ICLRMemoryNotificationCallback` instance provided by the CLR, the registration is effectively for the callback function itself.</span></span> <span data-ttu-id="87f7b-126">ホストは、 `OnMemoryNotification`標準の Win32 `CreateMemoryResourceNotification`関数を使用するのではなく、メモリ不足状態を報告するためにを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="87f7b-126">The host invokes `OnMemoryNotification` to report memory pressure conditions, rather than using the standard Win32 `CreateMemoryResourceNotification` function.</span></span> <span data-ttu-id="87f7b-127">詳細については、Windows プラットフォームのドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="87f7b-127">For more information, see the Windows Platform documentation.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="87f7b-128">を`OnMemoryNotification`呼び出してもブロックされません。</span><span class="sxs-lookup"><span data-stu-id="87f7b-128">Calls to `OnMemoryNotification` never block.</span></span> <span data-ttu-id="87f7b-129">常に直ちに返されます。</span><span class="sxs-lookup"><span data-stu-id="87f7b-129">They always return immediately.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="87f7b-130">必要条件</span><span class="sxs-lookup"><span data-stu-id="87f7b-130">Requirements</span></span>  
 <span data-ttu-id="87f7b-131">**・** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="87f7b-131">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="87f7b-132">**ヘッダー:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="87f7b-132">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="87f7b-133">**ライブラリ**Mscoree.dll にリソースとして含まれています</span><span class="sxs-lookup"><span data-stu-id="87f7b-133">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="87f7b-134">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="87f7b-134">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="87f7b-135">関連項目</span><span class="sxs-lookup"><span data-stu-id="87f7b-135">See also</span></span>

- [<span data-ttu-id="87f7b-136">ICLRMemoryNotificationCallback インターフェイス</span><span class="sxs-lookup"><span data-stu-id="87f7b-136">ICLRMemoryNotificationCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrmemorynotificationcallback-interface.md)
- [<span data-ttu-id="87f7b-137">IHostMemoryManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="87f7b-137">IHostMemoryManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-interface.md)
