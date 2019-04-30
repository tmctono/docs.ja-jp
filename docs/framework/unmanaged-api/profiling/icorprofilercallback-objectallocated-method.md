---
title: ICorProfilerCallback::ObjectAllocated メソッド
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.ObjectAllocated
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::ObjectAllocated
helpviewer_keywords:
- ObjectAllocated method [.NET Framework profiling]
- ICorProfilerCallback::ObjectAllocated method [.NET Framework profiling]
ms.assetid: eb412622-77cc-4abd-a2cd-c910fe8edd54
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: c07b37e58141f7aff747bd3772be265ae0da42ac
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62041991"
---
# <a name="icorprofilercallbackobjectallocated-method"></a><span data-ttu-id="2bda2-102">ICorProfilerCallback::ObjectAllocated メソッド</span><span class="sxs-lookup"><span data-stu-id="2bda2-102">ICorProfilerCallback::ObjectAllocated Method</span></span>
<span data-ttu-id="2bda2-103">オブジェクトの割り当てられたヒープ内のメモリ プロファイラーに通知します。</span><span class="sxs-lookup"><span data-stu-id="2bda2-103">Notifies the profiler that memory within the heap has been allocated for an object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2bda2-104">構文</span><span class="sxs-lookup"><span data-stu-id="2bda2-104">Syntax</span></span>  
  
```  
HRESULT ObjectAllocated(  
    [in] ObjectID objectId,  
    [in] ClassID classId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2bda2-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="2bda2-105">Parameters</span></span>  
 `objectId`  
 <span data-ttu-id="2bda2-106">[in]メモリが割り当てられたオブジェクトの ID。</span><span class="sxs-lookup"><span data-stu-id="2bda2-106">[in] The ID of the object for which memory was allocated.</span></span>  
  
 `classId`  
 <span data-ttu-id="2bda2-107">[in]オブジェクトがインスタンス クラスの ID。</span><span class="sxs-lookup"><span data-stu-id="2bda2-107">[in] The ID of the class of which the object is an instance.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2bda2-108">Remarks</span><span class="sxs-lookup"><span data-stu-id="2bda2-108">Remarks</span></span>  
 <span data-ttu-id="2bda2-109">`ObjectedAllocated`メソッドは、スタックまたはアンマネージ メモリからの割り当てに対しては呼び出されません。</span><span class="sxs-lookup"><span data-stu-id="2bda2-109">The `ObjectedAllocated` method is not called for allocations from either the stack or unmanaged memory.</span></span> <span data-ttu-id="2bda2-110">`classId`パラメーターがまだ読み込まれていないマネージ コード内のクラスを参照できます。</span><span class="sxs-lookup"><span data-stu-id="2bda2-110">The `classId` parameter can refer to a class in managed code that has not been loaded yet.</span></span> <span data-ttu-id="2bda2-111">プロファイラーはそのクラスのクラスのロード コールバックの直後に、`ObjectAllocated`コールバック。</span><span class="sxs-lookup"><span data-stu-id="2bda2-111">The profiler will receive a class load callback for that class immediately after the `ObjectAllocated` callback.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2bda2-112">必要条件</span><span class="sxs-lookup"><span data-stu-id="2bda2-112">Requirements</span></span>  
 <span data-ttu-id="2bda2-113">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="2bda2-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2bda2-114">**ヘッダー:** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="2bda2-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="2bda2-115">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2bda2-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2bda2-116">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2bda2-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2bda2-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="2bda2-117">See also</span></span>

- [<span data-ttu-id="2bda2-118">ICorProfilerCallback インターフェイス</span><span class="sxs-lookup"><span data-stu-id="2bda2-118">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [<span data-ttu-id="2bda2-119">ClassLoadStarted メソッド</span><span class="sxs-lookup"><span data-stu-id="2bda2-119">ClassLoadStarted Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-classloadstarted-method.md)
- [<span data-ttu-id="2bda2-120">ClassLoadFinished メソッド</span><span class="sxs-lookup"><span data-stu-id="2bda2-120">ClassLoadFinished Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-classloadfinished-method.md)
