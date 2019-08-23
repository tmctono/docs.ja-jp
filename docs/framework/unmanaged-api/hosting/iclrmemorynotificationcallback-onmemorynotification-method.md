---
title: ICLRMemoryNotificationCallback::OnMemoryNotification メソッド
ms.date: 03/30/2017
api_name:
- ICLRMemoryNotificationCallback.OnMemoryNotification
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRMemoryNotificationCallback::OnMemoryNotification
helpviewer_keywords:
- ICLRMemoryNotificationCallback::OnMemoryNotification method [.NET Framework hosting]
- OnMemoryNotification method [.NET Framework hosting]
ms.assetid: 5612a44d-56cc-4f34-af31-8c9809ba9431
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 899d0cf6a0475846b749bd0b7cbda41b1b88253d
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2019
ms.locfileid: "69949704"
---
# <a name="iclrmemorynotificationcallbackonmemorynotification-method"></a><span data-ttu-id="36c4d-102">ICLRMemoryNotificationCallback::OnMemoryNotification メソッド</span><span class="sxs-lookup"><span data-stu-id="36c4d-102">ICLRMemoryNotificationCallback::OnMemoryNotification Method</span></span>
<span data-ttu-id="36c4d-103">コンピューターのメモリ負荷の共通言語ランタイム (CLR) に通知します。</span><span class="sxs-lookup"><span data-stu-id="36c4d-103">Notifies the common language runtime (CLR) of the memory load on the computer.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="36c4d-104">構文</span><span class="sxs-lookup"><span data-stu-id="36c4d-104">Syntax</span></span>  
  
```cpp  
HRESULT OnMemoryNotification (  
    [in] EMemoryAvailable eMemoryAvailable  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="36c4d-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="36c4d-105">Parameters</span></span>  
 `eMemoryAvailable`  
 <span data-ttu-id="36c4d-106">から[EMemoryAvailable](../../../../docs/framework/unmanaged-api/hosting/ememoryavailable-enumeration.md)値の1つ。コンピューターが現在発生しているメモリ不足を示します。</span><span class="sxs-lookup"><span data-stu-id="36c4d-106">[in] One of the [EMemoryAvailable](../../../../docs/framework/unmanaged-api/hosting/ememoryavailable-enumeration.md) values, indicating the memory pressure the computer is currently experiencing.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="36c4d-107">戻り値</span><span class="sxs-lookup"><span data-stu-id="36c4d-107">Return Value</span></span>  
  
|<span data-ttu-id="36c4d-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="36c4d-108">HRESULT</span></span>|<span data-ttu-id="36c4d-109">説明</span><span class="sxs-lookup"><span data-stu-id="36c4d-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="36c4d-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="36c4d-110">S_OK</span></span>|<span data-ttu-id="36c4d-111">`OnMemoryNotification`正常に返されました。</span><span class="sxs-lookup"><span data-stu-id="36c4d-111">`OnMemoryNotification` returned successfully.</span></span>|  
|<span data-ttu-id="36c4d-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="36c4d-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="36c4d-113">CLR がプロセスに読み込まれていないか、CLR がマネージドコードを実行できない状態であるか、または呼び出しが正常に処理されていません。</span><span class="sxs-lookup"><span data-stu-id="36c4d-113">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="36c4d-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="36c4d-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="36c4d-115">呼び出しがタイムアウトしました。</span><span class="sxs-lookup"><span data-stu-id="36c4d-115">The call timed out.</span></span>|  
|<span data-ttu-id="36c4d-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="36c4d-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="36c4d-117">呼び出し元がロックを所有していません。</span><span class="sxs-lookup"><span data-stu-id="36c4d-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="36c4d-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="36c4d-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="36c4d-119">ブロックされたスレッドまたはファイバーが待機しているときに、イベントが取り消されました。</span><span class="sxs-lookup"><span data-stu-id="36c4d-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="36c4d-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="36c4d-120">E_FAIL</span></span>|<span data-ttu-id="36c4d-121">原因不明の致命的なエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="36c4d-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="36c4d-122">メソッドから E_FAIL が返された後は、そのプロセス内で CLR を使用できなくなります。</span><span class="sxs-lookup"><span data-stu-id="36c4d-122">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="36c4d-123">後続のホストメソッドの呼び出しでは、HOST_E_CLRNOTAVAILABLE が返されます。</span><span class="sxs-lookup"><span data-stu-id="36c4d-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="36c4d-124">Remarks</span><span class="sxs-lookup"><span data-stu-id="36c4d-124">Remarks</span></span>  
 <span data-ttu-id="36c4d-125">CLR は、 `OnMemoryNotification` [IHostMemoryManager:: registermemorynotificationcallback](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-registermemorynotificationcallback-method.md)メソッドの呼び出しを使用して、コールバックをに登録します。</span><span class="sxs-lookup"><span data-stu-id="36c4d-125">The CLR registers a callback to `OnMemoryNotification` by using a call to the [IHostMemoryManager::RegisterMemoryNotificationCallback](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-registermemorynotificationcallback-method.md) method.</span></span> <span data-ttu-id="36c4d-126">ランタイムは、コールバックで返された情報を使用して、メモリリソースが不足していることをホストが報告したときに追加のメモリを解放します。</span><span class="sxs-lookup"><span data-stu-id="36c4d-126">The runtime uses the information returned in the callback to free additional memory when the host reports that memory resources are running low.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="36c4d-127">を`OnMemoryNotification`呼び出してもブロックされません。</span><span class="sxs-lookup"><span data-stu-id="36c4d-127">Calls to `OnMemoryNotification` never block.</span></span> <span data-ttu-id="36c4d-128">常に直ちに返されます。</span><span class="sxs-lookup"><span data-stu-id="36c4d-128">They always return immediately.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="36c4d-129">必要条件</span><span class="sxs-lookup"><span data-stu-id="36c4d-129">Requirements</span></span>  
 <span data-ttu-id="36c4d-130">**・** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="36c4d-130">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="36c4d-131">**ヘッダー:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="36c4d-131">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="36c4d-132">**ライブラリ**Mscoree.dll にリソースとして含まれています</span><span class="sxs-lookup"><span data-stu-id="36c4d-132">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="36c4d-133">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="36c4d-133">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="36c4d-134">関連項目</span><span class="sxs-lookup"><span data-stu-id="36c4d-134">See also</span></span>

- [<span data-ttu-id="36c4d-135">IHostMemoryManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="36c4d-135">IHostMemoryManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-interface.md)
- [<span data-ttu-id="36c4d-136">RegisterMemoryNotificationCallback メソッド</span><span class="sxs-lookup"><span data-stu-id="36c4d-136">RegisterMemoryNotificationCallback Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-registermemorynotificationcallback-method.md)
- [<span data-ttu-id="36c4d-137">ICLRMemoryNotificationCallback インターフェイス</span><span class="sxs-lookup"><span data-stu-id="36c4d-137">ICLRMemoryNotificationCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrmemorynotificationcallback-interface.md)
