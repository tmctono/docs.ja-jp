---
title: IHostCrst::Leave メソッド
ms.date: 03/30/2017
api_name:
- IHostCrst.Leave
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostCrst::Leave
helpviewer_keywords:
- IHostCrst::Leave method [.NET Framework hosting]
- Leave method [.NET Framework hosting]
ms.assetid: dfc51d9e-b36d-4dba-9ea1-4f63fa0601ae
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f260e1351c8aa14961a10e0f7087bd076752785d
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67763771"
---
# <a name="ihostcrstleave-method"></a><span data-ttu-id="deece-102">IHostCrst::Leave メソッド</span><span class="sxs-lookup"><span data-stu-id="deece-102">IHostCrst::Leave Method</span></span>
<span data-ttu-id="deece-103">現在のインスタンスで表される、クリティカル セクションを離れる[IHostCrst](../../../../docs/framework/unmanaged-api/hosting/ihostcrst-interface.md)します。</span><span class="sxs-lookup"><span data-stu-id="deece-103">Leaves the critical section that is represented by the current instance of [IHostCrst](../../../../docs/framework/unmanaged-api/hosting/ihostcrst-interface.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="deece-104">構文</span><span class="sxs-lookup"><span data-stu-id="deece-104">Syntax</span></span>  
  
```cpp  
HRESULT Leave ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="deece-105">戻り値</span><span class="sxs-lookup"><span data-stu-id="deece-105">Return Value</span></span>  
  
|<span data-ttu-id="deece-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="deece-106">HRESULT</span></span>|<span data-ttu-id="deece-107">説明</span><span class="sxs-lookup"><span data-stu-id="deece-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="deece-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="deece-108">S_OK</span></span>|<span data-ttu-id="deece-109">`Leave` 正常に返されます。</span><span class="sxs-lookup"><span data-stu-id="deece-109">`Leave` returned successfully.</span></span>|  
|<span data-ttu-id="deece-110">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="deece-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="deece-111">共通言語ランタイム (CLR) は、プロセスに読み込まれていないか、CLR は状態をマネージ コードを実行または呼び出しを正常に処理ができません。</span><span class="sxs-lookup"><span data-stu-id="deece-111">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="deece-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="deece-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="deece-113">呼び出しがタイムアウトになりました。</span><span class="sxs-lookup"><span data-stu-id="deece-113">The call timed out.</span></span>|  
|<span data-ttu-id="deece-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="deece-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="deece-115">呼び出し元がロックを所有していません。</span><span class="sxs-lookup"><span data-stu-id="deece-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="deece-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="deece-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="deece-117">イベントがキャンセルされましたブロックされたスレッドまたはファイバーが待機しています。</span><span class="sxs-lookup"><span data-stu-id="deece-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="deece-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="deece-118">E_FAIL</span></span>|<span data-ttu-id="deece-119">不明な致命的なエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="deece-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="deece-120">メソッドには、E_FAIL が返される、ときに、CLR は、プロセス内で使用可能ではなくなりました。</span><span class="sxs-lookup"><span data-stu-id="deece-120">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="deece-121">メソッドをホストする後続の呼び出しには、HOST_E_CLRNOTAVAILABLE が返されます。</span><span class="sxs-lookup"><span data-stu-id="deece-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="deece-122">Remarks</span><span class="sxs-lookup"><span data-stu-id="deece-122">Remarks</span></span>  
 <span data-ttu-id="deece-123">`Leave` により、ホストのスレッド、実装ではなく、対応する Win32 を使用して直接通信する CLR`LeaveCriticalSection`関数。</span><span class="sxs-lookup"><span data-stu-id="deece-123">`Leave` allows the CLR to communicate directly with the host's threading implementation, rather than using the corresponding Win32 `LeaveCriticalSection` function.</span></span> <span data-ttu-id="deece-124">現在によって表される、クリティカル セクションの所有権を取得したスレッド`IHostCrst`インスタンスを呼び出す必要があります`Leave`たびに、そのクリティカル セクションに入った。</span><span class="sxs-lookup"><span data-stu-id="deece-124">A thread that takes ownership of the critical section represented by the current `IHostCrst` instance must call `Leave` once for each time it enters that critical section.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="deece-125">必要条件</span><span class="sxs-lookup"><span data-stu-id="deece-125">Requirements</span></span>  
 <span data-ttu-id="deece-126">**プラットフォーム:** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="deece-126">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="deece-127">**ヘッダー:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="deece-127">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="deece-128">**ライブラリ:** MSCorEE.dll でリソースとして含まれます</span><span class="sxs-lookup"><span data-stu-id="deece-128">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="deece-129">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="deece-129">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="deece-130">関連項目</span><span class="sxs-lookup"><span data-stu-id="deece-130">See also</span></span>

- [<span data-ttu-id="deece-131">ICLRSyncManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="deece-131">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)
- [<span data-ttu-id="deece-132">IHostCrst インターフェイス</span><span class="sxs-lookup"><span data-stu-id="deece-132">IHostCrst Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostcrst-interface.md)
- [<span data-ttu-id="deece-133">IHostSyncManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="deece-133">IHostSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)
