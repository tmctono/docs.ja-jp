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
ms.openlocfilehash: 050af068579d84b984ed83377d0c201e281bd154
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73130530"
---
# <a name="ihostcrstleave-method"></a><span data-ttu-id="31043-102">IHostCrst::Leave メソッド</span><span class="sxs-lookup"><span data-stu-id="31043-102">IHostCrst::Leave Method</span></span>
<span data-ttu-id="31043-103">[IHostCrst](../../../../docs/framework/unmanaged-api/hosting/ihostcrst-interface.md)の現在のインスタンスによって表されるクリティカルセクションを残します。</span><span class="sxs-lookup"><span data-stu-id="31043-103">Leaves the critical section that is represented by the current instance of [IHostCrst](../../../../docs/framework/unmanaged-api/hosting/ihostcrst-interface.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="31043-104">構文</span><span class="sxs-lookup"><span data-stu-id="31043-104">Syntax</span></span>  
  
```cpp  
HRESULT Leave ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="31043-105">戻り値</span><span class="sxs-lookup"><span data-stu-id="31043-105">Return Value</span></span>  
  
|<span data-ttu-id="31043-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="31043-106">HRESULT</span></span>|<span data-ttu-id="31043-107">説明</span><span class="sxs-lookup"><span data-stu-id="31043-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="31043-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="31043-108">S_OK</span></span>|<span data-ttu-id="31043-109">`Leave` が正常に返されました。</span><span class="sxs-lookup"><span data-stu-id="31043-109">`Leave` returned successfully.</span></span>|  
|<span data-ttu-id="31043-110">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="31043-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="31043-111">共通言語ランタイム (CLR) がプロセスに読み込まれていないか、CLR がマネージコードを実行できない状態であるか、または呼び出しが正常に処理されていません。</span><span class="sxs-lookup"><span data-stu-id="31043-111">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="31043-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="31043-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="31043-113">呼び出しがタイムアウトしました。</span><span class="sxs-lookup"><span data-stu-id="31043-113">The call timed out.</span></span>|  
|<span data-ttu-id="31043-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="31043-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="31043-115">呼び出し元がロックを所有していません。</span><span class="sxs-lookup"><span data-stu-id="31043-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="31043-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="31043-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="31043-117">ブロックされたスレッドまたはファイバーが待機しているときに、イベントが取り消されました。</span><span class="sxs-lookup"><span data-stu-id="31043-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="31043-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="31043-118">E_FAIL</span></span>|<span data-ttu-id="31043-119">原因不明の致命的なエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="31043-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="31043-120">メソッドから E_FAIL が返された場合、そのプロセス内で CLR は使用できなくなります。</span><span class="sxs-lookup"><span data-stu-id="31043-120">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="31043-121">後続のホストメソッドの呼び出しでは、HOST_E_CLRNOTAVAILABLE が返されます。</span><span class="sxs-lookup"><span data-stu-id="31043-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="31043-122">Remarks</span><span class="sxs-lookup"><span data-stu-id="31043-122">Remarks</span></span>  
 <span data-ttu-id="31043-123">`Leave` は、対応する Win32 `LeaveCriticalSection` 関数を使用するのではなく、CLR がホストのスレッド実装と直接通信できるようにします。</span><span class="sxs-lookup"><span data-stu-id="31043-123">`Leave` allows the CLR to communicate directly with the host's threading implementation, rather than using the corresponding Win32 `LeaveCriticalSection` function.</span></span> <span data-ttu-id="31043-124">現在の `IHostCrst` インスタンスによって表されるクリティカルセクションの所有権を取得するスレッドは、そのクリティカルセクションに入るたびに `Leave` を呼び出す必要があります。</span><span class="sxs-lookup"><span data-stu-id="31043-124">A thread that takes ownership of the critical section represented by the current `IHostCrst` instance must call `Leave` once for each time it enters that critical section.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="31043-125">［要件］</span><span class="sxs-lookup"><span data-stu-id="31043-125">Requirements</span></span>  
 <span data-ttu-id="31043-126">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="31043-126">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="31043-127">**ヘッダー:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="31043-127">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="31043-128">**ライブラリ:** Mscoree.dll にリソースとして含まれています</span><span class="sxs-lookup"><span data-stu-id="31043-128">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="31043-129">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="31043-129">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="31043-130">関連項目</span><span class="sxs-lookup"><span data-stu-id="31043-130">See also</span></span>

- [<span data-ttu-id="31043-131">ICLRSyncManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="31043-131">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)
- [<span data-ttu-id="31043-132">IHostCrst インターフェイス</span><span class="sxs-lookup"><span data-stu-id="31043-132">IHostCrst Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostcrst-interface.md)
- [<span data-ttu-id="31043-133">IHostSyncManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="31043-133">IHostSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)
