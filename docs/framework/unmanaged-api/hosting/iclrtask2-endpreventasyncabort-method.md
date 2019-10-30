---
title: ICLRTask2::EndPreventAsyncAbort メソッド
ms.date: 03/30/2017
api_name:
- ICLRTask2.EndPreventAsyncAbort
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRTask2::EndPreventAsyncAbort
helpviewer_keywords:
- EndPreventAsyncAbort method [.NET Framework hosting]
- ICLRTask2::EndPreventAsyncAbort method [.NET Framework hosting]
ms.assetid: d8013659-e3df-44b3-814f-a6b534ce62f8
topic_type:
- apiref
ms.openlocfilehash: 8ae66e0bf96138e5bc2f33e4c14ad86e7dabc6b8
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73124554"
---
# <a name="iclrtask2endpreventasyncabort-method"></a><span data-ttu-id="7a832-102">ICLRTask2::EndPreventAsyncAbort メソッド</span><span class="sxs-lookup"><span data-stu-id="7a832-102">ICLRTask2::EndPreventAsyncAbort Method</span></span>
<span data-ttu-id="7a832-103">新しいまたは保留中のスレッド中止要求に対して、現在のスレッドでのスレッドの中止を許可します。</span><span class="sxs-lookup"><span data-stu-id="7a832-103">Allows new or pending thread abort requests to result in thread aborts on the current thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7a832-104">構文</span><span class="sxs-lookup"><span data-stu-id="7a832-104">Syntax</span></span>  
  
```cpp  
HRESULT EndPreventAsyncAbort();  
```  
  
## <a name="return-value"></a><span data-ttu-id="7a832-105">戻り値</span><span class="sxs-lookup"><span data-stu-id="7a832-105">Return Value</span></span>  
 <span data-ttu-id="7a832-106">このメソッドは、次の特定の HRESULT と、メソッドの失敗を示す HRESULT エラーも返します。</span><span class="sxs-lookup"><span data-stu-id="7a832-106">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="7a832-107">HRESULT</span><span class="sxs-lookup"><span data-stu-id="7a832-107">HRESULT</span></span>|<span data-ttu-id="7a832-108">説明</span><span class="sxs-lookup"><span data-stu-id="7a832-108">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="7a832-109">S_OK</span><span class="sxs-lookup"><span data-stu-id="7a832-109">S_OK</span></span>|<span data-ttu-id="7a832-110">メソッドは正常に完了しました。</span><span class="sxs-lookup"><span data-stu-id="7a832-110">The method completed successfully.</span></span>|  
|<span data-ttu-id="7a832-111">HOST_E_INVALIDOPERATION</span><span class="sxs-lookup"><span data-stu-id="7a832-111">HOST_E_INVALIDOPERATION</span></span>|<span data-ttu-id="7a832-112">メソッドは、現在のスレッドではないスレッドで呼び出されました。</span><span class="sxs-lookup"><span data-stu-id="7a832-112">The method was called on a thread which is not the current thread.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7a832-113">Remarks</span><span class="sxs-lookup"><span data-stu-id="7a832-113">Remarks</span></span>  
 <span data-ttu-id="7a832-114">このメソッドを呼び出すと、現在のスレッドの遅延スレッド中止カウンターが1つ減少します。</span><span class="sxs-lookup"><span data-stu-id="7a832-114">Calling this method decrements the delay-thread-abort counter for the current thread by one.</span></span>  
  
 <span data-ttu-id="7a832-115">[ICLRTask2:: BeginPreventAsyncAbort](../../../../docs/framework/unmanaged-api/hosting/iclrtask2-beginpreventasyncabort-method.md)および `EndPreventAsyncAbort` の呼び出しは入れ子にすることができます。</span><span class="sxs-lookup"><span data-stu-id="7a832-115">Calls to [ICLRTask2::BeginPreventAsyncAbort](../../../../docs/framework/unmanaged-api/hosting/iclrtask2-beginpreventasyncabort-method.md) and `EndPreventAsyncAbort` can be nested.</span></span> <span data-ttu-id="7a832-116">カウンターがゼロより大きい限り、現在のスレッドのスレッド中止は遅延されます。</span><span class="sxs-lookup"><span data-stu-id="7a832-116">As long as the counter is greater than zero, thread aborts for the current thread are delayed.</span></span>  
  
 <span data-ttu-id="7a832-117">この機能によって公開されている機能は、仮想マシン (VM) によって内部的に使用されます。</span><span class="sxs-lookup"><span data-stu-id="7a832-117">The functionality that is exposed by this feature is used internally by the virtual machine (VM).</span></span> <span data-ttu-id="7a832-118">これらの方法を誤用すると、VM で特定できない動作が発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="7a832-118">Misuse of these methods may cause unspecified behavior in the VM.</span></span> <span data-ttu-id="7a832-119">たとえば、最初に `BeginPreventAsyncAbort` を呼び出さずに `EndPreventAsyncAbort` を呼び出すと、VM が以前にインクリメントしたときにカウンターを0に設定できます。</span><span class="sxs-lookup"><span data-stu-id="7a832-119">For example, calling `EndPreventAsyncAbort` without first calling `BeginPreventAsyncAbort` could set the counter to zero when the VM has previously incremented it.</span></span> <span data-ttu-id="7a832-120">同様に、内部カウンターのオーバーフローはチェックされません。</span><span class="sxs-lookup"><span data-stu-id="7a832-120">Similarly, the internal counter is not checked for overflow.</span></span> <span data-ttu-id="7a832-121">ホストと VM の両方によってインクリメントされるために整数の制限を超えた場合、結果として得られる動作は指定されません。</span><span class="sxs-lookup"><span data-stu-id="7a832-121">If it exceeds its integral limit because it is incremented by both the host and the VM, the resulting behavior is unspecified.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7a832-122">［要件］</span><span class="sxs-lookup"><span data-stu-id="7a832-122">Requirements</span></span>  
 <span data-ttu-id="7a832-123">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7a832-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7a832-124">**ヘッダー:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="7a832-124">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="7a832-125">**ライブラリ:** Mscoree.dll にリソースとして含まれています</span><span class="sxs-lookup"><span data-stu-id="7a832-125">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="7a832-126">**.NET Framework のバージョン:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7a832-126">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7a832-127">関連項目</span><span class="sxs-lookup"><span data-stu-id="7a832-127">See also</span></span>

- [<span data-ttu-id="7a832-128">BeginPreventAsyncAbort メソッド</span><span class="sxs-lookup"><span data-stu-id="7a832-128">BeginPreventAsyncAbort Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask2-beginpreventasyncabort-method.md)
- [<span data-ttu-id="7a832-129">ICLRTask2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="7a832-129">ICLRTask2 Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask2-interface.md)
- [<span data-ttu-id="7a832-130">ICLRTaskManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="7a832-130">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [<span data-ttu-id="7a832-131">IHostTask インターフェイス</span><span class="sxs-lookup"><span data-stu-id="7a832-131">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [<span data-ttu-id="7a832-132">IHostTaskManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="7a832-132">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
- [<span data-ttu-id="7a832-133">ホスト インターフェイス</span><span class="sxs-lookup"><span data-stu-id="7a832-133">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
