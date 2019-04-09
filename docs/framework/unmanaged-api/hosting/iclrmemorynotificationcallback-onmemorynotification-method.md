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
ms.openlocfilehash: 5c7866e0ecc62f037284a5329cb5785be90088f7
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2019
ms.locfileid: "59115844"
---
# <a name="iclrmemorynotificationcallbackonmemorynotification-method"></a><span data-ttu-id="e1fdc-102">ICLRMemoryNotificationCallback::OnMemoryNotification メソッド</span><span class="sxs-lookup"><span data-stu-id="e1fdc-102">ICLRMemoryNotificationCallback::OnMemoryNotification Method</span></span>
<span data-ttu-id="e1fdc-103">コンピューターのメモリ負荷の共通言語ランタイム (CLR) に通知します。</span><span class="sxs-lookup"><span data-stu-id="e1fdc-103">Notifies the common language runtime (CLR) of the memory load on the computer.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e1fdc-104">構文</span><span class="sxs-lookup"><span data-stu-id="e1fdc-104">Syntax</span></span>  
  
```  
HRESULT OnMemoryNotification (  
    [in] EMemoryAvailable eMemoryAvailable  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e1fdc-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="e1fdc-105">Parameters</span></span>  
 `eMemoryAvailable`  
 <span data-ttu-id="e1fdc-106">[in]1 つ、 [EMemoryAvailable](../../../../docs/framework/unmanaged-api/hosting/ememoryavailable-enumeration.md)値、コンピューターのメモリの負荷を示すが現在発生しています。</span><span class="sxs-lookup"><span data-stu-id="e1fdc-106">[in] One of the [EMemoryAvailable](../../../../docs/framework/unmanaged-api/hosting/ememoryavailable-enumeration.md) values, indicating the memory pressure the computer is currently experiencing.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="e1fdc-107">戻り値</span><span class="sxs-lookup"><span data-stu-id="e1fdc-107">Return Value</span></span>  
  
|<span data-ttu-id="e1fdc-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="e1fdc-108">HRESULT</span></span>|<span data-ttu-id="e1fdc-109">説明</span><span class="sxs-lookup"><span data-stu-id="e1fdc-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="e1fdc-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="e1fdc-110">S_OK</span></span>|`OnMemoryNotification` <span data-ttu-id="e1fdc-111">正常に返されます。</span><span class="sxs-lookup"><span data-stu-id="e1fdc-111">returned successfully.</span></span>|  
|<span data-ttu-id="e1fdc-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="e1fdc-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="e1fdc-113">プロセスに CLR が読み込まれていないか、CLR は状態をマネージ コードを実行または呼び出しを正常に処理ができません。</span><span class="sxs-lookup"><span data-stu-id="e1fdc-113">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="e1fdc-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="e1fdc-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="e1fdc-115">呼び出しがタイムアウトになりました。</span><span class="sxs-lookup"><span data-stu-id="e1fdc-115">The call timed out.</span></span>|  
|<span data-ttu-id="e1fdc-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="e1fdc-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="e1fdc-117">呼び出し元がロックを所有していません。</span><span class="sxs-lookup"><span data-stu-id="e1fdc-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="e1fdc-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="e1fdc-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="e1fdc-119">イベントがキャンセルされましたブロックされたスレッドまたはファイバーが待機しています。</span><span class="sxs-lookup"><span data-stu-id="e1fdc-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="e1fdc-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="e1fdc-120">E_FAIL</span></span>|<span data-ttu-id="e1fdc-121">不明な致命的なエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="e1fdc-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="e1fdc-122">メソッドには、E_FAIL が返された、後に、CLR は、プロセス内で使用可能ではなくなりました。</span><span class="sxs-lookup"><span data-stu-id="e1fdc-122">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="e1fdc-123">メソッドをホストする後続の呼び出しには、HOST_E_CLRNOTAVAILABLE が返されます。</span><span class="sxs-lookup"><span data-stu-id="e1fdc-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e1fdc-124">Remarks</span><span class="sxs-lookup"><span data-stu-id="e1fdc-124">Remarks</span></span>  
 <span data-ttu-id="e1fdc-125">CLR は、コールバックを登録`OnMemoryNotification`への呼び出しを使用して、 [ihostmemorymanager::registermemorynotificationcallback](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-registermemorynotificationcallback-method.md)メソッド。</span><span class="sxs-lookup"><span data-stu-id="e1fdc-125">The CLR registers a callback to `OnMemoryNotification` by using a call to the [IHostMemoryManager::RegisterMemoryNotificationCallback](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-registermemorynotificationcallback-method.md) method.</span></span> <span data-ttu-id="e1fdc-126">ランタイムは、ホストは、リソースが不足するメモリを報告したときに、追加のメモリを解放するのにコールバックに返される情報を使用します。</span><span class="sxs-lookup"><span data-stu-id="e1fdc-126">The runtime uses the information returned in the callback to free additional memory when the host reports that memory resources are running low.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="e1fdc-127">呼び出す`OnMemoryNotification`ブロックことはありません。</span><span class="sxs-lookup"><span data-stu-id="e1fdc-127">Calls to `OnMemoryNotification` never block.</span></span> <span data-ttu-id="e1fdc-128">常に直ちに戻ります。</span><span class="sxs-lookup"><span data-stu-id="e1fdc-128">They always return immediately.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e1fdc-129">必要条件</span><span class="sxs-lookup"><span data-stu-id="e1fdc-129">Requirements</span></span>  
 <span data-ttu-id="e1fdc-130">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="e1fdc-130">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e1fdc-131">**ヘッダー:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="e1fdc-131">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="e1fdc-132">**ライブラリ:** MSCorEE.dll でリソースとして含まれます</span><span class="sxs-lookup"><span data-stu-id="e1fdc-132">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="e1fdc-133">.NET Framework のバージョン: </span><span class="sxs-lookup"><span data-stu-id="e1fdc-133">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="e1fdc-134">関連項目</span><span class="sxs-lookup"><span data-stu-id="e1fdc-134">See also</span></span>

- [<span data-ttu-id="e1fdc-135">IHostMemoryManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="e1fdc-135">IHostMemoryManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-interface.md)
- [<span data-ttu-id="e1fdc-136">RegisterMemoryNotificationCallback メソッド</span><span class="sxs-lookup"><span data-stu-id="e1fdc-136">RegisterMemoryNotificationCallback Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-registermemorynotificationcallback-method.md)
- [<span data-ttu-id="e1fdc-137">ICLRMemoryNotificationCallback インターフェイス</span><span class="sxs-lookup"><span data-stu-id="e1fdc-137">ICLRMemoryNotificationCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrmemorynotificationcallback-interface.md)
