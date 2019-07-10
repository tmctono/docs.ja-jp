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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 36947eb33460fe3f15cf4ade1cad55cb5e77f1cc
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67770235"
---
# <a name="iclrtask2endpreventasyncabort-method"></a><span data-ttu-id="f1462-102">ICLRTask2::EndPreventAsyncAbort メソッド</span><span class="sxs-lookup"><span data-stu-id="f1462-102">ICLRTask2::EndPreventAsyncAbort Method</span></span>
<span data-ttu-id="f1462-103">保留中のスレッドで発生するスレッドの中止要求を現在のスレッドの中止または新規作成できます。</span><span class="sxs-lookup"><span data-stu-id="f1462-103">Allows new or pending thread abort requests to result in thread aborts on the current thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f1462-104">構文</span><span class="sxs-lookup"><span data-stu-id="f1462-104">Syntax</span></span>  
  
```cpp  
HRESULT EndPreventAsyncAbort();  
```  
  
## <a name="return-value"></a><span data-ttu-id="f1462-105">戻り値</span><span class="sxs-lookup"><span data-stu-id="f1462-105">Return Value</span></span>  
 <span data-ttu-id="f1462-106">このメソッドは、次の特定の HRESULT と、メソッドの失敗を示す HRESULT エラーも返します。</span><span class="sxs-lookup"><span data-stu-id="f1462-106">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="f1462-107">HRESULT</span><span class="sxs-lookup"><span data-stu-id="f1462-107">HRESULT</span></span>|<span data-ttu-id="f1462-108">説明</span><span class="sxs-lookup"><span data-stu-id="f1462-108">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="f1462-109">S_OK</span><span class="sxs-lookup"><span data-stu-id="f1462-109">S_OK</span></span>|<span data-ttu-id="f1462-110">メソッドは正常に完了しました。</span><span class="sxs-lookup"><span data-stu-id="f1462-110">The method completed successfully.</span></span>|  
|<span data-ttu-id="f1462-111">HOST_E_INVALIDOPERATION</span><span class="sxs-lookup"><span data-stu-id="f1462-111">HOST_E_INVALIDOPERATION</span></span>|<span data-ttu-id="f1462-112">メソッドは、現在のスレッドではないスレッドで呼び出されました。</span><span class="sxs-lookup"><span data-stu-id="f1462-112">The method was called on a thread which is not the current thread.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f1462-113">Remarks</span><span class="sxs-lookup"><span data-stu-id="f1462-113">Remarks</span></span>  
 <span data-ttu-id="f1462-114">現在のスレッドのいずれかでこのメソッドをデクリメント遅延スレッド中止のカウンターを呼び出しています。</span><span class="sxs-lookup"><span data-stu-id="f1462-114">Calling this method decrements the delay-thread-abort counter for the current thread by one.</span></span>  
  
 <span data-ttu-id="f1462-115">呼び出す[iclrtask 2::beginpreventasyncabort](../../../../docs/framework/unmanaged-api/hosting/iclrtask2-beginpreventasyncabort-method.md)と`EndPreventAsyncAbort`入れ子にすることができます。</span><span class="sxs-lookup"><span data-stu-id="f1462-115">Calls to [ICLRTask2::BeginPreventAsyncAbort](../../../../docs/framework/unmanaged-api/hosting/iclrtask2-beginpreventasyncabort-method.md) and `EndPreventAsyncAbort` can be nested.</span></span> <span data-ttu-id="f1462-116">カウンターが 0 より大きい場合に限り、現在のスレッドのスレッドの中止が遅延します。</span><span class="sxs-lookup"><span data-stu-id="f1462-116">As long as the counter is greater than zero, thread aborts for the current thread are delayed.</span></span>  
  
 <span data-ttu-id="f1462-117">この機能によって公開される機能は、仮想マシン (VM) で内部的に使用されます。</span><span class="sxs-lookup"><span data-stu-id="f1462-117">The functionality that is exposed by this feature is used internally by the virtual machine (VM).</span></span> <span data-ttu-id="f1462-118">これらのメソッドの誤用によっては、VM の未定義の動作があります。</span><span class="sxs-lookup"><span data-stu-id="f1462-118">Misuse of these methods may cause unspecified behavior in the VM.</span></span> <span data-ttu-id="f1462-119">たとえば、呼び出し`EndPreventAsyncAbort`最初に呼び出さず`BeginPreventAsyncAbort`VM がインクリメントしていたときに、カウンターを 0 に設定でした。</span><span class="sxs-lookup"><span data-stu-id="f1462-119">For example, calling `EndPreventAsyncAbort` without first calling `BeginPreventAsyncAbort` could set the counter to zero when the VM has previously incremented it.</span></span> <span data-ttu-id="f1462-120">同様に、内部カウンターは、オーバーフローはチェックされません。</span><span class="sxs-lookup"><span data-stu-id="f1462-120">Similarly, the internal counter is not checked for overflow.</span></span> <span data-ttu-id="f1462-121">ホストと VM の両方でインクリメントされますので、その整数の制限を超えている場合、結果として得られる動作は指定されていません。</span><span class="sxs-lookup"><span data-stu-id="f1462-121">If it exceeds its integral limit because it is incremented by both the host and the VM, the resulting behavior is unspecified.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f1462-122">必要条件</span><span class="sxs-lookup"><span data-stu-id="f1462-122">Requirements</span></span>  
 <span data-ttu-id="f1462-123">**プラットフォーム:** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="f1462-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f1462-124">**ヘッダー:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="f1462-124">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="f1462-125">**ライブラリ:** MSCorEE.dll でリソースとして含まれます</span><span class="sxs-lookup"><span data-stu-id="f1462-125">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="f1462-126">**.NET Framework のバージョン:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f1462-126">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f1462-127">関連項目</span><span class="sxs-lookup"><span data-stu-id="f1462-127">See also</span></span>

- [<span data-ttu-id="f1462-128">BeginPreventAsyncAbort メソッド</span><span class="sxs-lookup"><span data-stu-id="f1462-128">BeginPreventAsyncAbort Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask2-beginpreventasyncabort-method.md)
- [<span data-ttu-id="f1462-129">ICLRTask2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="f1462-129">ICLRTask2 Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask2-interface.md)
- [<span data-ttu-id="f1462-130">ICLRTaskManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="f1462-130">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [<span data-ttu-id="f1462-131">IHostTask インターフェイス</span><span class="sxs-lookup"><span data-stu-id="f1462-131">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [<span data-ttu-id="f1462-132">IHostTaskManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="f1462-132">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
- [<span data-ttu-id="f1462-133">ホスト インターフェイス</span><span class="sxs-lookup"><span data-stu-id="f1462-133">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
