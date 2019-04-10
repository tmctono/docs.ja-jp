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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 939f100e8ee386642a29c33827a8339caf0467b9
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2019
ms.locfileid: "59193188"
---
# <a name="ihostcrst-interface"></a><span data-ttu-id="3aa6c-102">IHostCrst インターフェイス</span><span class="sxs-lookup"><span data-stu-id="3aa6c-102">IHostCrst Interface</span></span>
<span data-ttu-id="3aa6c-103">ホストのスレッドのクリティカル セクションの表現として機能します。</span><span class="sxs-lookup"><span data-stu-id="3aa6c-103">Serves as the host's representation of a critical section for threading.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="3aa6c-104">メソッド</span><span class="sxs-lookup"><span data-stu-id="3aa6c-104">Methods</span></span>  
  
|<span data-ttu-id="3aa6c-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="3aa6c-105">Method</span></span>|<span data-ttu-id="3aa6c-106">説明</span><span class="sxs-lookup"><span data-stu-id="3aa6c-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="3aa6c-107">Enter メソッド</span><span class="sxs-lookup"><span data-stu-id="3aa6c-107">Enter Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostcrst-enter-method.md)|<span data-ttu-id="3aa6c-108">クリティカル セクションに入ります。</span><span class="sxs-lookup"><span data-stu-id="3aa6c-108">Enters the critical section.</span></span>|  
|[<span data-ttu-id="3aa6c-109">Leave メソッド</span><span class="sxs-lookup"><span data-stu-id="3aa6c-109">Leave Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostcrst-leave-method.md)|<span data-ttu-id="3aa6c-110">クリティカル セクションを残します。</span><span class="sxs-lookup"><span data-stu-id="3aa6c-110">Leaves the critical section.</span></span>|  
|[<span data-ttu-id="3aa6c-111">SetSpinCount メソッド</span><span class="sxs-lookup"><span data-stu-id="3aa6c-111">SetSpinCount Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostcrst-setspincount-method.md)|<span data-ttu-id="3aa6c-112">クリティカル セクションのスピン カウントを設定します。</span><span class="sxs-lookup"><span data-stu-id="3aa6c-112">Sets the spin count for the critical section.</span></span>|  
|[<span data-ttu-id="3aa6c-113">TryEnter メソッド</span><span class="sxs-lookup"><span data-stu-id="3aa6c-113">TryEnter Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostcrst-tryenter-method.md)|<span data-ttu-id="3aa6c-114">クリティカル セクション、およびレポートの成功または失敗をすぐに入力しようとします。</span><span class="sxs-lookup"><span data-stu-id="3aa6c-114">Attempts to enter the critical section, and reports success or failure immediately.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3aa6c-115">Remarks</span><span class="sxs-lookup"><span data-stu-id="3aa6c-115">Remarks</span></span>  
 `IHostCrst` <span data-ttu-id="3aa6c-116">などの Win32 関数を使用するのではなく、共通言語ランタイム (CLR) のクリティカル セクションでは、ホストの表現と直接通信するためには、`EnterCriticalSection`または`LeaveCriticalSection`します。</span><span class="sxs-lookup"><span data-stu-id="3aa6c-116">allows the common language runtime (CLR) to communicate directly with the host's representation of a critical section, rather than using Win32 functions such as `EnterCriticalSection` or `LeaveCriticalSection`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3aa6c-117">必要条件</span><span class="sxs-lookup"><span data-stu-id="3aa6c-117">Requirements</span></span>  
 <span data-ttu-id="3aa6c-118">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="3aa6c-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3aa6c-119">**ヘッダー:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="3aa6c-119">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="3aa6c-120">**ライブラリ:** MSCorEE.dll でリソースとして含まれます</span><span class="sxs-lookup"><span data-stu-id="3aa6c-120">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="3aa6c-121">.NET Framework のバージョン: </span><span class="sxs-lookup"><span data-stu-id="3aa6c-121">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="3aa6c-122">関連項目</span><span class="sxs-lookup"><span data-stu-id="3aa6c-122">See also</span></span>

- [<span data-ttu-id="3aa6c-123">ICLRSyncManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="3aa6c-123">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)
- [<span data-ttu-id="3aa6c-124">IHostSyncManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="3aa6c-124">IHostSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)
- [<span data-ttu-id="3aa6c-125">ホスト インターフェイス</span><span class="sxs-lookup"><span data-stu-id="3aa6c-125">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
