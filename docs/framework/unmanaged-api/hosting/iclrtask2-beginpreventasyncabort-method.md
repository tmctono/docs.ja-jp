---
title: ICLRTask2::BeginPreventAsyncAbort メソッド
ms.date: 03/30/2017
api_name:
- ICLRTask2.BeginPreventAsyncAbort
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRTask2::BeginPreventAsyncAbort
helpviewer_keywords:
- ICLRTask2::BeginPreventAsyncAbort method [.NET Framework hosting]
- BeginPreventAsyncAbort method [.NET Framework hosting]
ms.assetid: 75754c2f-38c7-4707-85fe-559db4542729
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 85a43fef7f6dfa6dbe0bb9f1c4caec2c9c224b93
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61763432"
---
# <a name="iclrtask2beginpreventasyncabort-method"></a><span data-ttu-id="d4f1e-102">ICLRTask2::BeginPreventAsyncAbort メソッド</span><span class="sxs-lookup"><span data-stu-id="d4f1e-102">ICLRTask2::BeginPreventAsyncAbort Method</span></span>
<span data-ttu-id="d4f1e-103">新しいスレッドの遅延は、現在のスレッドでスレッドの中止の結果からの要求を中止します。</span><span class="sxs-lookup"><span data-stu-id="d4f1e-103">Delays new thread abort requests from resulting in thread aborts on the current thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d4f1e-104">構文</span><span class="sxs-lookup"><span data-stu-id="d4f1e-104">Syntax</span></span>  
  
```  
HRESULT BeginPreventAsyncAbort();  
```  
  
## <a name="return-value"></a><span data-ttu-id="d4f1e-105">戻り値</span><span class="sxs-lookup"><span data-stu-id="d4f1e-105">Return Value</span></span>  
 <span data-ttu-id="d4f1e-106">このメソッドは、次の特定の HRESULT と、メソッドの失敗を示す HRESULT エラーも返します。</span><span class="sxs-lookup"><span data-stu-id="d4f1e-106">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="d4f1e-107">HRESULT</span><span class="sxs-lookup"><span data-stu-id="d4f1e-107">HRESULT</span></span>|<span data-ttu-id="d4f1e-108">説明</span><span class="sxs-lookup"><span data-stu-id="d4f1e-108">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="d4f1e-109">S_OK</span><span class="sxs-lookup"><span data-stu-id="d4f1e-109">S_OK</span></span>|<span data-ttu-id="d4f1e-110">メソッドは正常に完了しました。</span><span class="sxs-lookup"><span data-stu-id="d4f1e-110">The method completed successfully.</span></span>|  
|<span data-ttu-id="d4f1e-111">HOST_E_INVALIDOPERATION</span><span class="sxs-lookup"><span data-stu-id="d4f1e-111">HOST_E_INVALIDOPERATION</span></span>|<span data-ttu-id="d4f1e-112">メソッドは、現在のスレッドではないスレッドで呼び出されました。</span><span class="sxs-lookup"><span data-stu-id="d4f1e-112">The method was called on a thread which is not the current thread.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d4f1e-113">Remarks</span><span class="sxs-lookup"><span data-stu-id="d4f1e-113">Remarks</span></span>  
 <span data-ttu-id="d4f1e-114">このメソッドを呼び出すいずれかによって、現在のスレッドのスレッド中止を遅延カウンターをインクリメントします。</span><span class="sxs-lookup"><span data-stu-id="d4f1e-114">Calling this method increments the delay-thread-abort counter for the current thread by one.</span></span>  
  
 <span data-ttu-id="d4f1e-115">呼び出す`BeginPreventAsyncAbort`と[iclrtask 2::endpreventasyncabort](../../../../docs/framework/unmanaged-api/hosting/iclrtask2-endpreventasyncabort-method.md)入れ子にすることができます。</span><span class="sxs-lookup"><span data-stu-id="d4f1e-115">Calls to `BeginPreventAsyncAbort` and [ICLRTask2::EndPreventAsyncAbort](../../../../docs/framework/unmanaged-api/hosting/iclrtask2-endpreventasyncabort-method.md) can be nested.</span></span> <span data-ttu-id="d4f1e-116">カウンターが 0 より大きい場合に限り、現在のスレッドのスレッドの中止が遅延します。</span><span class="sxs-lookup"><span data-stu-id="d4f1e-116">As long as the counter is greater than zero, thread aborts for the current thread are delayed.</span></span> <span data-ttu-id="d4f1e-117">この呼び出しはへの呼び出しと組み合わせて使用しないかどうか、`EndPreventAsyncAbort`メソッドでは、どのスレッドの中止を現在のスレッドに配信できない状態に到達することはできます。</span><span class="sxs-lookup"><span data-stu-id="d4f1e-117">If this call is not paired with a call to the `EndPreventAsyncAbort` method, it is possible to reach a state in which thread aborts cannot be delivered to the current thread.</span></span>  
  
 <span data-ttu-id="d4f1e-118">遅延自体を中止するスレッドを有効になりません。</span><span class="sxs-lookup"><span data-stu-id="d4f1e-118">The delay is not honored for a thread that aborts itself.</span></span>  
  
 <span data-ttu-id="d4f1e-119">この機能によって公開される機能は、仮想マシン (VM) で内部的に使用されます。</span><span class="sxs-lookup"><span data-stu-id="d4f1e-119">The functionality that is exposed by this feature is used internally by the virtual machine (VM).</span></span> <span data-ttu-id="d4f1e-120">これらのメソッドの誤用によっては、VM の未定義の動作があります。</span><span class="sxs-lookup"><span data-stu-id="d4f1e-120">Misuse of these methods may cause unspecified behavior in the VM.</span></span> <span data-ttu-id="d4f1e-121">たとえば、呼び出し`EndPreventAsyncAbort`最初に呼び出さず`BeginPreventAsyncAbort`VM がインクリメントしていたときに、カウンターを 0 に設定でした。</span><span class="sxs-lookup"><span data-stu-id="d4f1e-121">For example, calling `EndPreventAsyncAbort` without first calling `BeginPreventAsyncAbort` could set the counter to zero when the VM has previously incremented it.</span></span> <span data-ttu-id="d4f1e-122">同様に、内部カウンターは、オーバーフローはチェックされません。</span><span class="sxs-lookup"><span data-stu-id="d4f1e-122">Similarly, the internal counter is not checked for overflow.</span></span> <span data-ttu-id="d4f1e-123">ホストと VM の両方でインクリメントされますので、その整数の制限を超えている場合、結果として得られる動作は指定されていません。</span><span class="sxs-lookup"><span data-stu-id="d4f1e-123">If it exceeds its integral limit because it is incremented by both the host and the VM, the resulting behavior is unspecified.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d4f1e-124">必要条件</span><span class="sxs-lookup"><span data-stu-id="d4f1e-124">Requirements</span></span>  
 <span data-ttu-id="d4f1e-125">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="d4f1e-125">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d4f1e-126">**ヘッダー:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="d4f1e-126">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="d4f1e-127">**ライブラリ:** MSCorEE.dll でリソースとして含まれます</span><span class="sxs-lookup"><span data-stu-id="d4f1e-127">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="d4f1e-128">**.NET Framework のバージョン:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d4f1e-128">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d4f1e-129">関連項目</span><span class="sxs-lookup"><span data-stu-id="d4f1e-129">See also</span></span>

- [<span data-ttu-id="d4f1e-130">EndPreventAsyncAbort メソッド</span><span class="sxs-lookup"><span data-stu-id="d4f1e-130">EndPreventAsyncAbort Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask2-endpreventasyncabort-method.md)
- [<span data-ttu-id="d4f1e-131">ICLRTask2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="d4f1e-131">ICLRTask2 Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask2-interface.md)
- [<span data-ttu-id="d4f1e-132">ICLRTaskManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="d4f1e-132">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [<span data-ttu-id="d4f1e-133">IHostTask インターフェイス</span><span class="sxs-lookup"><span data-stu-id="d4f1e-133">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [<span data-ttu-id="d4f1e-134">IHostTaskManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="d4f1e-134">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
- [<span data-ttu-id="d4f1e-135">ホスト インターフェイス</span><span class="sxs-lookup"><span data-stu-id="d4f1e-135">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
