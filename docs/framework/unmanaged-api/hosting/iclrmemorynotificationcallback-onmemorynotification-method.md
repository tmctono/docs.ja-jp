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
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61984621"
---
# <a name="iclrmemorynotificationcallbackonmemorynotification-method"></a><span data-ttu-id="d2771-102">ICLRMemoryNotificationCallback::OnMemoryNotification メソッド</span><span class="sxs-lookup"><span data-stu-id="d2771-102">ICLRMemoryNotificationCallback::OnMemoryNotification Method</span></span>
<span data-ttu-id="d2771-103">コンピューターのメモリ負荷の共通言語ランタイム (CLR) に通知します。</span><span class="sxs-lookup"><span data-stu-id="d2771-103">Notifies the common language runtime (CLR) of the memory load on the computer.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d2771-104">構文</span><span class="sxs-lookup"><span data-stu-id="d2771-104">Syntax</span></span>  
  
```  
HRESULT OnMemoryNotification (  
    [in] EMemoryAvailable eMemoryAvailable  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d2771-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="d2771-105">Parameters</span></span>  
 `eMemoryAvailable`  
 <span data-ttu-id="d2771-106">[in]1 つ、 [EMemoryAvailable](../../../../docs/framework/unmanaged-api/hosting/ememoryavailable-enumeration.md)値、コンピューターのメモリの負荷を示すが現在発生しています。</span><span class="sxs-lookup"><span data-stu-id="d2771-106">[in] One of the [EMemoryAvailable](../../../../docs/framework/unmanaged-api/hosting/ememoryavailable-enumeration.md) values, indicating the memory pressure the computer is currently experiencing.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="d2771-107">戻り値</span><span class="sxs-lookup"><span data-stu-id="d2771-107">Return Value</span></span>  
  
|<span data-ttu-id="d2771-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="d2771-108">HRESULT</span></span>|<span data-ttu-id="d2771-109">説明</span><span class="sxs-lookup"><span data-stu-id="d2771-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="d2771-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="d2771-110">S_OK</span></span>|<span data-ttu-id="d2771-111">`OnMemoryNotification` 正常に返されます。</span><span class="sxs-lookup"><span data-stu-id="d2771-111">`OnMemoryNotification` returned successfully.</span></span>|  
|<span data-ttu-id="d2771-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="d2771-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="d2771-113">プロセスに CLR が読み込まれていないか、CLR は状態をマネージ コードを実行または呼び出しを正常に処理ができません。</span><span class="sxs-lookup"><span data-stu-id="d2771-113">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="d2771-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="d2771-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="d2771-115">呼び出しがタイムアウトになりました。</span><span class="sxs-lookup"><span data-stu-id="d2771-115">The call timed out.</span></span>|  
|<span data-ttu-id="d2771-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="d2771-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="d2771-117">呼び出し元がロックを所有していません。</span><span class="sxs-lookup"><span data-stu-id="d2771-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="d2771-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="d2771-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="d2771-119">イベントがキャンセルされましたブロックされたスレッドまたはファイバーが待機しています。</span><span class="sxs-lookup"><span data-stu-id="d2771-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="d2771-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="d2771-120">E_FAIL</span></span>|<span data-ttu-id="d2771-121">不明な致命的なエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="d2771-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="d2771-122">メソッドには、E_FAIL が返された、後に、CLR は、プロセス内で使用可能ではなくなりました。</span><span class="sxs-lookup"><span data-stu-id="d2771-122">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="d2771-123">メソッドをホストする後続の呼び出しには、HOST_E_CLRNOTAVAILABLE が返されます。</span><span class="sxs-lookup"><span data-stu-id="d2771-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d2771-124">Remarks</span><span class="sxs-lookup"><span data-stu-id="d2771-124">Remarks</span></span>  
 <span data-ttu-id="d2771-125">CLR は、コールバックを登録`OnMemoryNotification`への呼び出しを使用して、 [ihostmemorymanager::registermemorynotificationcallback](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-registermemorynotificationcallback-method.md)メソッド。</span><span class="sxs-lookup"><span data-stu-id="d2771-125">The CLR registers a callback to `OnMemoryNotification` by using a call to the [IHostMemoryManager::RegisterMemoryNotificationCallback](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-registermemorynotificationcallback-method.md) method.</span></span> <span data-ttu-id="d2771-126">ランタイムは、ホストは、リソースが不足するメモリを報告したときに、追加のメモリを解放するのにコールバックに返される情報を使用します。</span><span class="sxs-lookup"><span data-stu-id="d2771-126">The runtime uses the information returned in the callback to free additional memory when the host reports that memory resources are running low.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d2771-127">呼び出す`OnMemoryNotification`ブロックことはありません。</span><span class="sxs-lookup"><span data-stu-id="d2771-127">Calls to `OnMemoryNotification` never block.</span></span> <span data-ttu-id="d2771-128">常に直ちに戻ります。</span><span class="sxs-lookup"><span data-stu-id="d2771-128">They always return immediately.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d2771-129">必要条件</span><span class="sxs-lookup"><span data-stu-id="d2771-129">Requirements</span></span>  
 <span data-ttu-id="d2771-130">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="d2771-130">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d2771-131">**ヘッダー:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="d2771-131">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="d2771-132">**ライブラリ:** MSCorEE.dll でリソースとして含まれます</span><span class="sxs-lookup"><span data-stu-id="d2771-132">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="d2771-133">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d2771-133">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d2771-134">関連項目</span><span class="sxs-lookup"><span data-stu-id="d2771-134">See also</span></span>

- [<span data-ttu-id="d2771-135">IHostMemoryManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="d2771-135">IHostMemoryManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-interface.md)
- [<span data-ttu-id="d2771-136">RegisterMemoryNotificationCallback メソッド</span><span class="sxs-lookup"><span data-stu-id="d2771-136">RegisterMemoryNotificationCallback Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-registermemorynotificationcallback-method.md)
- [<span data-ttu-id="d2771-137">ICLRMemoryNotificationCallback インターフェイス</span><span class="sxs-lookup"><span data-stu-id="d2771-137">ICLRMemoryNotificationCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrmemorynotificationcallback-interface.md)
