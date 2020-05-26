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
ms.openlocfilehash: e8cb1486ccea11ba6edcf7bbb781a9bf210b496d
ms.sourcegitcommit: d223616e7e6fe2139079052e6fcbe25413fb9900
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/22/2020
ms.locfileid: "83804901"
---
# <a name="ihostcrst-interface"></a><span data-ttu-id="ce74f-102">IHostCrst インターフェイス</span><span class="sxs-lookup"><span data-stu-id="ce74f-102">IHostCrst Interface</span></span>
<span data-ttu-id="ce74f-103">スレッド処理のためのクリティカルセクションのホストの表現として機能します。</span><span class="sxs-lookup"><span data-stu-id="ce74f-103">Serves as the host's representation of a critical section for threading.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="ce74f-104">メソッド</span><span class="sxs-lookup"><span data-stu-id="ce74f-104">Methods</span></span>  
  
|<span data-ttu-id="ce74f-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="ce74f-105">Method</span></span>|<span data-ttu-id="ce74f-106">説明</span><span class="sxs-lookup"><span data-stu-id="ce74f-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="ce74f-107">Enter メソッド</span><span class="sxs-lookup"><span data-stu-id="ce74f-107">Enter Method</span></span>](ihostcrst-enter-method.md)|<span data-ttu-id="ce74f-108">クリティカルセクションに入ります。</span><span class="sxs-lookup"><span data-stu-id="ce74f-108">Enters the critical section.</span></span>|  
|[<span data-ttu-id="ce74f-109">Leave メソッド</span><span class="sxs-lookup"><span data-stu-id="ce74f-109">Leave Method</span></span>](ihostcrst-leave-method.md)|<span data-ttu-id="ce74f-110">クリティカルセクションを残します。</span><span class="sxs-lookup"><span data-stu-id="ce74f-110">Leaves the critical section.</span></span>|  
|[<span data-ttu-id="ce74f-111">SetSpinCount メソッド</span><span class="sxs-lookup"><span data-stu-id="ce74f-111">SetSpinCount Method</span></span>](ihostcrst-setspincount-method.md)|<span data-ttu-id="ce74f-112">クリティカルセクションのスピンカウントを設定します。</span><span class="sxs-lookup"><span data-stu-id="ce74f-112">Sets the spin count for the critical section.</span></span>|  
|[<span data-ttu-id="ce74f-113">TryEnter メソッド</span><span class="sxs-lookup"><span data-stu-id="ce74f-113">TryEnter Method</span></span>](ihostcrst-tryenter-method.md)|<span data-ttu-id="ce74f-114">クリティカルセクションへの入力を試行し、成功または失敗を直ちに報告します。</span><span class="sxs-lookup"><span data-stu-id="ce74f-114">Attempts to enter the critical section, and reports success or failure immediately.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ce74f-115">解説</span><span class="sxs-lookup"><span data-stu-id="ce74f-115">Remarks</span></span>  
 <span data-ttu-id="ce74f-116">`IHostCrst`またはなどの Win32 関数を使用するのではなく、共通言語ランタイム (CLR) が、クリティカルセクションのホストの表現と直接通信できるようにし `EnterCriticalSection` `LeaveCriticalSection` ます。</span><span class="sxs-lookup"><span data-stu-id="ce74f-116">`IHostCrst` allows the common language runtime (CLR) to communicate directly with the host's representation of a critical section, rather than using Win32 functions such as `EnterCriticalSection` or `LeaveCriticalSection`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ce74f-117">要件</span><span class="sxs-lookup"><span data-stu-id="ce74f-117">Requirements</span></span>  
 <span data-ttu-id="ce74f-118">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ce74f-118">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ce74f-119">**ヘッダー:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="ce74f-119">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="ce74f-120">**ライブラリ:** Mscoree.dll にリソースとして含まれています</span><span class="sxs-lookup"><span data-stu-id="ce74f-120">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="ce74f-121">**.NET Framework のバージョン:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ce74f-121">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ce74f-122">関連項目</span><span class="sxs-lookup"><span data-stu-id="ce74f-122">See also</span></span>

- [<span data-ttu-id="ce74f-123">ICLRSyncManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="ce74f-123">ICLRSyncManager Interface</span></span>](iclrsyncmanager-interface.md)
- [<span data-ttu-id="ce74f-124">IHostSyncManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="ce74f-124">IHostSyncManager Interface</span></span>](ihostsyncmanager-interface.md)
- [<span data-ttu-id="ce74f-125">ホスト インターフェイス</span><span class="sxs-lookup"><span data-stu-id="ce74f-125">Hosting Interfaces</span></span>](hosting-interfaces.md)
