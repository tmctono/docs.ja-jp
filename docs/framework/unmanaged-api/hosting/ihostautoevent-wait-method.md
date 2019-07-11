---
title: IHostAutoEvent::Wait メソッド
ms.date: 03/30/2017
api_name:
- IHostAutoEvent.Wait
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostAutoEvent::Wait
helpviewer_keywords:
- Wait method, IHostAutoEvent interface [.NET Framework hosting]
- IHostAutoEvent::Wait method [.NET Framework hosting]
ms.assetid: 535d51c5-9112-401b-8c36-85f35d7ee609
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 127c0c134b287ed7fad73c11fd505ac0de5a0aef
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67763925"
---
# <a name="ihostautoeventwait-method"></a><span data-ttu-id="cd563-102">IHostAutoEvent::Wait メソッド</span><span class="sxs-lookup"><span data-stu-id="cd563-102">IHostAutoEvent::Wait Method</span></span>
<span data-ttu-id="cd563-103">現在[IHostAutoEvent](../../../../docs/framework/unmanaged-api/hosting/ihostautoevent-interface.md)所有者になるまで待機するインスタンスまたは一定の時間が経過するとします。</span><span class="sxs-lookup"><span data-stu-id="cd563-103">Causes the current [IHostAutoEvent](../../../../docs/framework/unmanaged-api/hosting/ihostautoevent-interface.md) instance to wait until it is owned or a specified amount of time elapses.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cd563-104">構文</span><span class="sxs-lookup"><span data-stu-id="cd563-104">Syntax</span></span>  
  
```cpp  
HRESULT Wait (  
    [in] DWORD dwMilliseconds,  
    [in] DWORD option  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="cd563-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="cd563-105">Parameters</span></span>  
 `dwMilliseconds`  
 <span data-ttu-id="cd563-106">[in]ミリ秒数、現在`IHostAutoEvent`場合のスレッドがありませんが、インスタンスを戻る前に待機またはファイバーが所有権を取得します。</span><span class="sxs-lookup"><span data-stu-id="cd563-106">[in] The number of milliseconds the current `IHostAutoEvent` instance should wait before returning, if no thread or fiber takes ownership.</span></span>  
  
 `option`  
 <span data-ttu-id="cd563-107">[in]いずれか、 [WAIT_OPTION](../../../../docs/framework/unmanaged-api/hosting/wait-option-enumeration.md)場合は、このホストが実行するアクションを指定する値は、操作がブロックされます。</span><span class="sxs-lookup"><span data-stu-id="cd563-107">[in] One of the [WAIT_OPTION](../../../../docs/framework/unmanaged-api/hosting/wait-option-enumeration.md) values, specifying the action the host should take if this operation blocks.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="cd563-108">戻り値</span><span class="sxs-lookup"><span data-stu-id="cd563-108">Return Value</span></span>  
  
|<span data-ttu-id="cd563-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="cd563-109">HRESULT</span></span>|<span data-ttu-id="cd563-110">説明</span><span class="sxs-lookup"><span data-stu-id="cd563-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="cd563-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="cd563-111">S_OK</span></span>|<span data-ttu-id="cd563-112">`Wait` 正常に返されます。</span><span class="sxs-lookup"><span data-stu-id="cd563-112">`Wait` returned successfully.</span></span>|  
|<span data-ttu-id="cd563-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="cd563-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="cd563-114">共通言語ランタイム (CLR) は、プロセスに読み込まれていないか、CLR は状態をマネージ コードを実行または呼び出しを正常に処理ができません。</span><span class="sxs-lookup"><span data-stu-id="cd563-114">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="cd563-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="cd563-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="cd563-116">呼び出しがタイムアウトになりました。</span><span class="sxs-lookup"><span data-stu-id="cd563-116">The call timed out.</span></span>|  
|<span data-ttu-id="cd563-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="cd563-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="cd563-118">呼び出し元がロックを所有していません。</span><span class="sxs-lookup"><span data-stu-id="cd563-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="cd563-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="cd563-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="cd563-120">イベントがキャンセルされましたブロックされたスレッドまたはファイバーが待機しています。</span><span class="sxs-lookup"><span data-stu-id="cd563-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="cd563-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="cd563-121">E_FAIL</span></span>|<span data-ttu-id="cd563-122">不明な致命的なエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="cd563-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="cd563-123">メソッドには、E_FAIL が返される、ときに、CLR は、プロセス内で使用可能ではなくなりました。</span><span class="sxs-lookup"><span data-stu-id="cd563-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="cd563-124">メソッドをホストする後続の呼び出しには、HOST_E_CLRNOTAVAILABLE が返されます。</span><span class="sxs-lookup"><span data-stu-id="cd563-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="cd563-125">HOST_E_DEADLOCK</span><span class="sxs-lookup"><span data-stu-id="cd563-125">HOST_E_DEADLOCK</span></span>|<span data-ttu-id="cd563-126">ホストが、待機中にデッドロックを検出し、現在によって表されるイベント`IHostAutoEvent`デッドロックの対象としてインスタンス。</span><span class="sxs-lookup"><span data-stu-id="cd563-126">The host detected a deadlock during the wait interval, and chose the event represented by the current `IHostAutoEvent` instance as the deadlock victim.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="cd563-127">必要条件</span><span class="sxs-lookup"><span data-stu-id="cd563-127">Requirements</span></span>  
 <span data-ttu-id="cd563-128">**プラットフォーム:** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="cd563-128">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cd563-129">**ヘッダー:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="cd563-129">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="cd563-130">**ライブラリ:** MSCorEE.dll でリソースとして含まれます</span><span class="sxs-lookup"><span data-stu-id="cd563-130">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="cd563-131">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cd563-131">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cd563-132">関連項目</span><span class="sxs-lookup"><span data-stu-id="cd563-132">See also</span></span>

- [<span data-ttu-id="cd563-133">ICLRSyncManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="cd563-133">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)
- [<span data-ttu-id="cd563-134">IHostAutoEvent インターフェイス</span><span class="sxs-lookup"><span data-stu-id="cd563-134">IHostAutoEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostautoevent-interface.md)
- [<span data-ttu-id="cd563-135">IHostManualEvent インターフェイス</span><span class="sxs-lookup"><span data-stu-id="cd563-135">IHostManualEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-interface.md)
- [<span data-ttu-id="cd563-136">IHostSyncManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="cd563-136">IHostSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)
