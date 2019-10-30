---
title: IHostCrst インターフェイス
ms.date: 03/30/2017
api_name:
- IHostCrst
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostCrst
helpviewer_keywords:
- IHostCrst interface [.NET Framework hosting]
ms.assetid: ac298ebd-0815-47e4-a823-30b31baab903
topic_type:
- apiref
ms.openlocfilehash: 108492ba298e9f8429b2acd890ab3404365bc602
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73130525"
---
# <a name="ihostcrst-interface"></a><span data-ttu-id="5da47-102">IHostCrst インターフェイス</span><span class="sxs-lookup"><span data-stu-id="5da47-102">IHostCrst Interface</span></span>
<span data-ttu-id="5da47-103">スレッド処理のためのクリティカルセクションのホストの表現として機能します。</span><span class="sxs-lookup"><span data-stu-id="5da47-103">Serves as the host's representation of a critical section for threading.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="5da47-104">メソッド</span><span class="sxs-lookup"><span data-stu-id="5da47-104">Methods</span></span>  
  
|<span data-ttu-id="5da47-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="5da47-105">Method</span></span>|<span data-ttu-id="5da47-106">説明</span><span class="sxs-lookup"><span data-stu-id="5da47-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="5da47-107">Enter メソッド</span><span class="sxs-lookup"><span data-stu-id="5da47-107">Enter Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostcrst-enter-method.md)|<span data-ttu-id="5da47-108">クリティカルセクションに入ります。</span><span class="sxs-lookup"><span data-stu-id="5da47-108">Enters the critical section.</span></span>|  
|[<span data-ttu-id="5da47-109">Leave メソッド</span><span class="sxs-lookup"><span data-stu-id="5da47-109">Leave Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostcrst-leave-method.md)|<span data-ttu-id="5da47-110">クリティカルセクションを残します。</span><span class="sxs-lookup"><span data-stu-id="5da47-110">Leaves the critical section.</span></span>|  
|[<span data-ttu-id="5da47-111">SetSpinCount メソッド</span><span class="sxs-lookup"><span data-stu-id="5da47-111">SetSpinCount Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostcrst-setspincount-method.md)|<span data-ttu-id="5da47-112">クリティカルセクションのスピンカウントを設定します。</span><span class="sxs-lookup"><span data-stu-id="5da47-112">Sets the spin count for the critical section.</span></span>|  
|[<span data-ttu-id="5da47-113">TryEnter メソッド</span><span class="sxs-lookup"><span data-stu-id="5da47-113">TryEnter Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostcrst-tryenter-method.md)|<span data-ttu-id="5da47-114">クリティカルセクションへの入力を試行し、成功または失敗を直ちに報告します。</span><span class="sxs-lookup"><span data-stu-id="5da47-114">Attempts to enter the critical section, and reports success or failure immediately.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5da47-115">Remarks</span><span class="sxs-lookup"><span data-stu-id="5da47-115">Remarks</span></span>  
 <span data-ttu-id="5da47-116">`IHostCrst` を使用すると、共通言語ランタイム (CLR) は、`EnterCriticalSection` や `LeaveCriticalSection`などの Win32 関数を使用するのではなく、クリティカルセクションのホストの表現と直接通信できます。</span><span class="sxs-lookup"><span data-stu-id="5da47-116">`IHostCrst` allows the common language runtime (CLR) to communicate directly with the host's representation of a critical section, rather than using Win32 functions such as `EnterCriticalSection` or `LeaveCriticalSection`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5da47-117">［要件］</span><span class="sxs-lookup"><span data-stu-id="5da47-117">Requirements</span></span>  
 <span data-ttu-id="5da47-118">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5da47-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5da47-119">**ヘッダー:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="5da47-119">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="5da47-120">**ライブラリ:** Mscoree.dll にリソースとして含まれています</span><span class="sxs-lookup"><span data-stu-id="5da47-120">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="5da47-121">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5da47-121">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5da47-122">関連項目</span><span class="sxs-lookup"><span data-stu-id="5da47-122">See also</span></span>

- [<span data-ttu-id="5da47-123">ICLRSyncManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="5da47-123">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)
- [<span data-ttu-id="5da47-124">IHostSyncManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="5da47-124">IHostSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)
- [<span data-ttu-id="5da47-125">ホスト インターフェイス</span><span class="sxs-lookup"><span data-stu-id="5da47-125">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
