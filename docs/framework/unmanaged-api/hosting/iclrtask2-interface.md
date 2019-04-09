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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 518248651de6d8afdf25692c5f48da52b11eb0f7
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2019
ms.locfileid: "59172472"
---
# <a name="iclrtask2-interface"></a><span data-ttu-id="3e3fb-102">ICLRTask2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="3e3fb-102">ICLRTask2 Interface</span></span>
<span data-ttu-id="3e3fb-103">すべての機能を提供、 [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)インターフェイスは、さらに、現在のスレッドが遅延するスレッドの中止できるようにするメソッドを提供します。</span><span class="sxs-lookup"><span data-stu-id="3e3fb-103">Provides all the functionality of the [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) interface; in addition, provides methods that allow thread aborts to be delayed on the current thread.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="3e3fb-104">メソッド</span><span class="sxs-lookup"><span data-stu-id="3e3fb-104">Methods</span></span>  
  
|<span data-ttu-id="3e3fb-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="3e3fb-105">Method</span></span>|<span data-ttu-id="3e3fb-106">説明</span><span class="sxs-lookup"><span data-stu-id="3e3fb-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="3e3fb-107">BeginPreventAsyncAbort メソッド</span><span class="sxs-lookup"><span data-stu-id="3e3fb-107">BeginPreventAsyncAbort Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask2-beginpreventasyncabort-method.md)|<span data-ttu-id="3e3fb-108">新しいスレッドの遅延は、現在のスレッドで要求を中止します。</span><span class="sxs-lookup"><span data-stu-id="3e3fb-108">Delays new thread abort requests on the current thread.</span></span>|  
|[<span data-ttu-id="3e3fb-109">EndPreventAsyncAbort メソッド</span><span class="sxs-lookup"><span data-stu-id="3e3fb-109">EndPreventAsyncAbort Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask2-endpreventasyncabort-method.md)|<span data-ttu-id="3e3fb-110">保留中のスレッドで発生するスレッドの中止要求を現在のスレッドの中止または新規作成できます。</span><span class="sxs-lookup"><span data-stu-id="3e3fb-110">Allows new or pending thread abort requests to result in thread aborts on the current thread.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3e3fb-111">Remarks</span><span class="sxs-lookup"><span data-stu-id="3e3fb-111">Remarks</span></span>  
 <span data-ttu-id="3e3fb-112">`ICLRTask2`インターフェイスの継承、`ICLRTask`インターフェイスし、ホストが失敗する必要がありますしないコードの領域を保護するために、スレッドの中止を遅延できるようにするメソッドを追加します。</span><span class="sxs-lookup"><span data-stu-id="3e3fb-112">The `ICLRTask2` interface inherits the `ICLRTask` interface and adds methods that allow the host to delay thread aborts, to protect a region of code that must not fail.</span></span> <span data-ttu-id="3e3fb-113">呼び出す`BeginPreventAsyncAbort`、現在のスレッドと呼び出し元のスレッド中止を遅延カウンターをインクリメント`EndPreventAsyncAbort`デクリメントこと。</span><span class="sxs-lookup"><span data-stu-id="3e3fb-113">Calling `BeginPreventAsyncAbort` increments the delay-thread-abort counter for the current thread, and calling `EndPreventAsyncAbort` decrements it.</span></span> <span data-ttu-id="3e3fb-114">呼び出す`BeginPreventAsyncAbort`と`EndPreventAsyncAbort`入れ子にすることができます。</span><span class="sxs-lookup"><span data-stu-id="3e3fb-114">Calls to `BeginPreventAsyncAbort` and `EndPreventAsyncAbort` can be nested.</span></span> <span data-ttu-id="3e3fb-115">カウンターが 0 より大きい場合に限り、現在のスレッドのスレッドの中止が遅延します。</span><span class="sxs-lookup"><span data-stu-id="3e3fb-115">As long as the counter is greater than zero, thread aborts for the current thread are delayed.</span></span>  
  
 <span data-ttu-id="3e3fb-116">場合呼び出し`BeginPreventAsyncAbort`と`EndPreventAsyncAbort`が対になっていない、することは、現在のスレッドにスレッドの中止を配信できない状態に到達します。</span><span class="sxs-lookup"><span data-stu-id="3e3fb-116">If calls to `BeginPreventAsyncAbort` and `EndPreventAsyncAbort` are not paired, it is possible to reach a state in which thread aborts cannot be delivered to the current thread.</span></span>  
  
 <span data-ttu-id="3e3fb-117">遅延自体を中止するスレッドを有効になりません。</span><span class="sxs-lookup"><span data-stu-id="3e3fb-117">The delay is not honored for a thread that aborts itself.</span></span>  
  
 <span data-ttu-id="3e3fb-118">この機能によって公開される機能は、仮想マシン (VM) で内部的に使用されます。</span><span class="sxs-lookup"><span data-stu-id="3e3fb-118">The functionality that is exposed by this feature is used internally by the virtual machine (VM).</span></span> <span data-ttu-id="3e3fb-119">これらのメソッドの誤用によっては、VM の未定義の動作があります。</span><span class="sxs-lookup"><span data-stu-id="3e3fb-119">Misuse of these methods may cause unspecified behavior in the VM.</span></span> <span data-ttu-id="3e3fb-120">たとえば、呼び出し`EndPreventAsyncAbort`最初に呼び出さず`BeginPreventAsyncAbort`VM がインクリメントしていたときに、カウンターを 0 に設定でした。</span><span class="sxs-lookup"><span data-stu-id="3e3fb-120">For example, calling `EndPreventAsyncAbort` without first calling `BeginPreventAsyncAbort` could set the counter to zero when the VM has previously incremented it.</span></span> <span data-ttu-id="3e3fb-121">同様に、内部カウンターは、オーバーフローはチェックされません。</span><span class="sxs-lookup"><span data-stu-id="3e3fb-121">Similarly, the internal counter is not checked for overflow.</span></span> <span data-ttu-id="3e3fb-122">ホストと VM の両方でインクリメントされますので、その整数の制限を超えている場合、結果として得られる動作は指定されていません。</span><span class="sxs-lookup"><span data-stu-id="3e3fb-122">If it exceeds its integral limit because it is incremented by both the host and the VM, the resulting behavior is unspecified.</span></span>  
  
 <span data-ttu-id="3e3fb-123">継承されたメンバーに関する情報の`ICLRTask`このインターフェイスの他の使用の詳細についてを参照してください。 および、 [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)インターフェイス。</span><span class="sxs-lookup"><span data-stu-id="3e3fb-123">For information about members inherited from `ICLRTask` and about the other uses of this interface, see the [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3e3fb-124">必要条件</span><span class="sxs-lookup"><span data-stu-id="3e3fb-124">Requirements</span></span>  
 <span data-ttu-id="3e3fb-125">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="3e3fb-125">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3e3fb-126">**ヘッダー:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="3e3fb-126">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="3e3fb-127">**ライブラリ:** MSCorEE.dll でリソースとして含まれます</span><span class="sxs-lookup"><span data-stu-id="3e3fb-127">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="3e3fb-128">.NET Framework のバージョン: </span><span class="sxs-lookup"><span data-stu-id="3e3fb-128">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="3e3fb-129">関連項目</span><span class="sxs-lookup"><span data-stu-id="3e3fb-129">See also</span></span>

- [<span data-ttu-id="3e3fb-130">ICLRTask インターフェイス</span><span class="sxs-lookup"><span data-stu-id="3e3fb-130">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [<span data-ttu-id="3e3fb-131">ICLRTaskManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="3e3fb-131">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [<span data-ttu-id="3e3fb-132">IHostTask インターフェイス</span><span class="sxs-lookup"><span data-stu-id="3e3fb-132">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [<span data-ttu-id="3e3fb-133">IHostTaskManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="3e3fb-133">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
- [<span data-ttu-id="3e3fb-134">ホスト インターフェイス</span><span class="sxs-lookup"><span data-stu-id="3e3fb-134">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
