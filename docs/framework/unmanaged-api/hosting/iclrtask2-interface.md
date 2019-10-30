---
title: ICLRTask2 インターフェイス
ms.date: 03/30/2017
api_name:
- ICLRTask2
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRTask2
helpviewer_keywords:
- ICLRTask2 interface [.NET Framework hosting]
ms.assetid: b5a22ebc-0582-49de-91f9-97a3d9789290
topic_type:
- apiref
ms.openlocfilehash: 47c6dd9045636bcfbe07c909fec3fda515d28ee8
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73124526"
---
# <a name="iclrtask2-interface"></a><span data-ttu-id="ea17b-102">ICLRTask2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="ea17b-102">ICLRTask2 Interface</span></span>
<span data-ttu-id="ea17b-103">には、 [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)インターフェイスのすべての機能が用意されています。また、には、現在のスレッドでスレッドの中止を遅延させることができるメソッドが用意されています。</span><span class="sxs-lookup"><span data-stu-id="ea17b-103">Provides all the functionality of the [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) interface; in addition, provides methods that allow thread aborts to be delayed on the current thread.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="ea17b-104">メソッド</span><span class="sxs-lookup"><span data-stu-id="ea17b-104">Methods</span></span>  
  
|<span data-ttu-id="ea17b-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="ea17b-105">Method</span></span>|<span data-ttu-id="ea17b-106">説明</span><span class="sxs-lookup"><span data-stu-id="ea17b-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="ea17b-107">BeginPreventAsyncAbort メソッド</span><span class="sxs-lookup"><span data-stu-id="ea17b-107">BeginPreventAsyncAbort Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask2-beginpreventasyncabort-method.md)|<span data-ttu-id="ea17b-108">現在のスレッドの新しいスレッド中止要求を遅延します。</span><span class="sxs-lookup"><span data-stu-id="ea17b-108">Delays new thread abort requests on the current thread.</span></span>|  
|[<span data-ttu-id="ea17b-109">EndPreventAsyncAbort メソッド</span><span class="sxs-lookup"><span data-stu-id="ea17b-109">EndPreventAsyncAbort Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask2-endpreventasyncabort-method.md)|<span data-ttu-id="ea17b-110">新しいまたは保留中のスレッド中止要求に対して、現在のスレッドでのスレッドの中止を許可します。</span><span class="sxs-lookup"><span data-stu-id="ea17b-110">Allows new or pending thread abort requests to result in thread aborts on the current thread.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ea17b-111">Remarks</span><span class="sxs-lookup"><span data-stu-id="ea17b-111">Remarks</span></span>  
 <span data-ttu-id="ea17b-112">`ICLRTask2` インターフェイスは、`ICLRTask` インターフェイスを継承し、ホストがスレッドの中止を遅延させて、失敗しないコードの領域を保護できるようにするメソッドを追加します。</span><span class="sxs-lookup"><span data-stu-id="ea17b-112">The `ICLRTask2` interface inherits the `ICLRTask` interface and adds methods that allow the host to delay thread aborts, to protect a region of code that must not fail.</span></span> <span data-ttu-id="ea17b-113">`BeginPreventAsyncAbort` を呼び出すと、現在のスレッドの遅延スレッド中止カウンターがインクリメントされ、`EndPreventAsyncAbort` を呼び出すとデクリメントされます。</span><span class="sxs-lookup"><span data-stu-id="ea17b-113">Calling `BeginPreventAsyncAbort` increments the delay-thread-abort counter for the current thread, and calling `EndPreventAsyncAbort` decrements it.</span></span> <span data-ttu-id="ea17b-114">`BeginPreventAsyncAbort` および `EndPreventAsyncAbort` の呼び出しは入れ子にすることができます。</span><span class="sxs-lookup"><span data-stu-id="ea17b-114">Calls to `BeginPreventAsyncAbort` and `EndPreventAsyncAbort` can be nested.</span></span> <span data-ttu-id="ea17b-115">カウンターがゼロより大きい限り、現在のスレッドのスレッド中止は遅延されます。</span><span class="sxs-lookup"><span data-stu-id="ea17b-115">As long as the counter is greater than zero, thread aborts for the current thread are delayed.</span></span>  
  
 <span data-ttu-id="ea17b-116">`BeginPreventAsyncAbort` と `EndPreventAsyncAbort` の呼び出しがペアになっていない場合、現在のスレッドにスレッド中止を配信できない状態になる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="ea17b-116">If calls to `BeginPreventAsyncAbort` and `EndPreventAsyncAbort` are not paired, it is possible to reach a state in which thread aborts cannot be delivered to the current thread.</span></span>  
  
 <span data-ttu-id="ea17b-117">遅延は、それ自体を中止するスレッドには適用されません。</span><span class="sxs-lookup"><span data-stu-id="ea17b-117">The delay is not honored for a thread that aborts itself.</span></span>  
  
 <span data-ttu-id="ea17b-118">この機能によって公開されている機能は、仮想マシン (VM) によって内部的に使用されます。</span><span class="sxs-lookup"><span data-stu-id="ea17b-118">The functionality that is exposed by this feature is used internally by the virtual machine (VM).</span></span> <span data-ttu-id="ea17b-119">これらの方法を誤用すると、VM で特定できない動作が発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="ea17b-119">Misuse of these methods may cause unspecified behavior in the VM.</span></span> <span data-ttu-id="ea17b-120">たとえば、最初に `BeginPreventAsyncAbort` を呼び出さずに `EndPreventAsyncAbort` を呼び出すと、VM が以前にインクリメントしたときにカウンターを0に設定できます。</span><span class="sxs-lookup"><span data-stu-id="ea17b-120">For example, calling `EndPreventAsyncAbort` without first calling `BeginPreventAsyncAbort` could set the counter to zero when the VM has previously incremented it.</span></span> <span data-ttu-id="ea17b-121">同様に、内部カウンターのオーバーフローはチェックされません。</span><span class="sxs-lookup"><span data-stu-id="ea17b-121">Similarly, the internal counter is not checked for overflow.</span></span> <span data-ttu-id="ea17b-122">ホストと VM の両方によってインクリメントされるために整数の制限を超えた場合、結果として得られる動作は指定されません。</span><span class="sxs-lookup"><span data-stu-id="ea17b-122">If it exceeds its integral limit because it is incremented by both the host and the VM, the resulting behavior is unspecified.</span></span>  
  
 <span data-ttu-id="ea17b-123">`ICLRTask` から継承されたメンバーと、このインターフェイスの他の用途については、「 [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)インターフェイス」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ea17b-123">For information about members inherited from `ICLRTask` and about the other uses of this interface, see the [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ea17b-124">［要件］</span><span class="sxs-lookup"><span data-stu-id="ea17b-124">Requirements</span></span>  
 <span data-ttu-id="ea17b-125">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ea17b-125">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ea17b-126">**ヘッダー:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="ea17b-126">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="ea17b-127">**ライブラリ:** Mscoree.dll にリソースとして含まれています</span><span class="sxs-lookup"><span data-stu-id="ea17b-127">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="ea17b-128">**.NET Framework のバージョン:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ea17b-128">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ea17b-129">関連項目</span><span class="sxs-lookup"><span data-stu-id="ea17b-129">See also</span></span>

- [<span data-ttu-id="ea17b-130">ICLRTask インターフェイス</span><span class="sxs-lookup"><span data-stu-id="ea17b-130">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [<span data-ttu-id="ea17b-131">ICLRTaskManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="ea17b-131">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [<span data-ttu-id="ea17b-132">IHostTask インターフェイス</span><span class="sxs-lookup"><span data-stu-id="ea17b-132">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [<span data-ttu-id="ea17b-133">IHostTaskManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="ea17b-133">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
- [<span data-ttu-id="ea17b-134">ホスト インターフェイス</span><span class="sxs-lookup"><span data-stu-id="ea17b-134">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
