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
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61951745"
---
# <a name="ihostmemorymanagerregistermemorynotificationcallback-method"></a><span data-ttu-id="9c414-102">IHostMemoryManager::RegisterMemoryNotificationCallback メソッド</span><span class="sxs-lookup"><span data-stu-id="9c414-102">IHostMemoryManager::RegisterMemoryNotificationCallback Method</span></span>
<span data-ttu-id="9c414-103">コンピューターの現在のメモリ負荷のホストが共通言語ランタイム (CLR) に通知するために呼び出すコールバック関数へのポインターを登録します。</span><span class="sxs-lookup"><span data-stu-id="9c414-103">Registers a pointer to a callback function that the host invokes to notify the common language runtime (CLR) of the current memory load on the computer.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9c414-104">構文</span><span class="sxs-lookup"><span data-stu-id="9c414-104">Syntax</span></span>  
  
```  
HRESULT RegisterMemoryNotificationCallback (  
    [in] ICLRMemoryNotificationCallback* pCallback  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9c414-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="9c414-105">Parameters</span></span>  
 `pCallback`  
 <span data-ttu-id="9c414-106">[in]インターフェイス ポインターを[ICLRMemoryNotificationCallback](../../../../docs/framework/unmanaged-api/hosting/iclrmemorynotificationcallback-interface.md) CLR によって実装されているインスタンス。</span><span class="sxs-lookup"><span data-stu-id="9c414-106">[in] An interface pointer to an [ICLRMemoryNotificationCallback](../../../../docs/framework/unmanaged-api/hosting/iclrmemorynotificationcallback-interface.md) instance that is implemented by the CLR.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="9c414-107">戻り値</span><span class="sxs-lookup"><span data-stu-id="9c414-107">Return Value</span></span>  
  
|<span data-ttu-id="9c414-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="9c414-108">HRESULT</span></span>|<span data-ttu-id="9c414-109">説明</span><span class="sxs-lookup"><span data-stu-id="9c414-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="9c414-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="9c414-110">S_OK</span></span>|<span data-ttu-id="9c414-111">`RegisterMemoryNotificationCallback` 正常に返されます。</span><span class="sxs-lookup"><span data-stu-id="9c414-111">`RegisterMemoryNotificationCallback` returned successfully.</span></span>|  
|<span data-ttu-id="9c414-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="9c414-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="9c414-113">プロセスに CLR が読み込まれていないか、CLR は状態をマネージ コードを実行または呼び出しを正常に処理ができません。</span><span class="sxs-lookup"><span data-stu-id="9c414-113">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="9c414-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="9c414-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="9c414-115">呼び出しがタイムアウトになりました。</span><span class="sxs-lookup"><span data-stu-id="9c414-115">The call timed out.</span></span>|  
|<span data-ttu-id="9c414-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="9c414-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="9c414-117">呼び出し元がロックを所有していません。</span><span class="sxs-lookup"><span data-stu-id="9c414-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="9c414-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="9c414-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="9c414-119">イベントがキャンセルされましたブロックされたスレッドまたはファイバーが待機しています。</span><span class="sxs-lookup"><span data-stu-id="9c414-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="9c414-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="9c414-120">E_FAIL</span></span>|<span data-ttu-id="9c414-121">不明な致命的なエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="9c414-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="9c414-122">メソッドには、E_FAIL が返される、ときに、CLR は、プロセス内で使用可能ではなくなりました。</span><span class="sxs-lookup"><span data-stu-id="9c414-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="9c414-123">メソッドをホストする後続の呼び出しには、HOST_E_CLRNOTAVAILABLE が返されます。</span><span class="sxs-lookup"><span data-stu-id="9c414-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9c414-124">Remarks</span><span class="sxs-lookup"><span data-stu-id="9c414-124">Remarks</span></span>  
 <span data-ttu-id="9c414-125">`ICLRMemoryNotificationCallback`インターフェイスが 1 つのメソッドを定義します ([iclrmemorynotificationcallback::onmemorynotification](../../../../docs/framework/unmanaged-api/hosting/iclrmemorynotificationcallback-onmemorynotification-method.md))、ためと`pCallback`へのポインター、 `ICLRMemoryNotificationCallback` CLR によって提供されるインスタンス、コールバック関数自体の登録で効果的にあります。</span><span class="sxs-lookup"><span data-stu-id="9c414-125">Because the `ICLRMemoryNotificationCallback` interface defines only one method ([ICLRMemoryNotificationCallback::OnMemoryNotification](../../../../docs/framework/unmanaged-api/hosting/iclrmemorynotificationcallback-onmemorynotification-method.md)), and because `pCallback` is a pointer to an `ICLRMemoryNotificationCallback` instance provided by the CLR, the registration is effectively for the callback function itself.</span></span> <span data-ttu-id="9c414-126">ホストが呼び出す`OnMemoryNotification`標準の Win32 を使用するのではなく、メモリ不足の状態を報告する、`CreateMemoryResourceNotification`関数。</span><span class="sxs-lookup"><span data-stu-id="9c414-126">The host invokes `OnMemoryNotification` to report memory pressure conditions, rather than using the standard Win32 `CreateMemoryResourceNotification` function.</span></span> <span data-ttu-id="9c414-127">詳細については、Windows プラットフォームのドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="9c414-127">For more information, see the Windows Platform documentation.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="9c414-128">呼び出す`OnMemoryNotification`ブロックことはありません。</span><span class="sxs-lookup"><span data-stu-id="9c414-128">Calls to `OnMemoryNotification` never block.</span></span> <span data-ttu-id="9c414-129">常に直ちに戻ります。</span><span class="sxs-lookup"><span data-stu-id="9c414-129">They always return immediately.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9c414-130">必要条件</span><span class="sxs-lookup"><span data-stu-id="9c414-130">Requirements</span></span>  
 <span data-ttu-id="9c414-131">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="9c414-131">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9c414-132">**ヘッダー:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="9c414-132">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="9c414-133">**ライブラリ:** MSCorEE.dll でリソースとして含まれます</span><span class="sxs-lookup"><span data-stu-id="9c414-133">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="9c414-134">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9c414-134">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9c414-135">関連項目</span><span class="sxs-lookup"><span data-stu-id="9c414-135">See also</span></span>

- [<span data-ttu-id="9c414-136">ICLRMemoryNotificationCallback インターフェイス</span><span class="sxs-lookup"><span data-stu-id="9c414-136">ICLRMemoryNotificationCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrmemorynotificationcallback-interface.md)
- [<span data-ttu-id="9c414-137">IHostMemoryManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="9c414-137">IHostMemoryManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-interface.md)
