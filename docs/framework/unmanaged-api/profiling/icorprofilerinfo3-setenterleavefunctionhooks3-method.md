---
title: ICorProfilerInfo3::SetEnterLeaveFunctionHooks3 メソッド
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo3.SetEnterLeaveFunctionHooks3 Method
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo3::SetEnterLeaveFunctionHooks3
helpviewer_keywords:
- SetEnterLeaveFunctionHooks3 method [.NET Framework profiling]
- ICorProfilerInfo3::SetEnterLeaveFunctionHooks3 method [.NET Framework profiling]
ms.assetid: f0621465-b84f-40ab-a4e5-56a7abc776a7
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: d72b336f9d71d0b7b7252ba907e8eebd3b42c200
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/06/2019
ms.locfileid: "57473163"
---
# <a name="icorprofilerinfo3setenterleavefunctionhooks3-method"></a><span data-ttu-id="ac3a5-102">ICorProfilerInfo3::SetEnterLeaveFunctionHooks3 メソッド</span><span class="sxs-lookup"><span data-stu-id="ac3a5-102">ICorProfilerInfo3::SetEnterLeaveFunctionHooks3 Method</span></span>
<span data-ttu-id="ac3a5-103">呼び出されるプロファイラー実装関数を指定します、 [FunctionEnter3](../../../../docs/framework/unmanaged-api/profiling/functionenter3-function.md)、 [FunctionLeave3](../../../../docs/framework/unmanaged-api/profiling/functionleave3-function.md)、および[FunctionTailcall3](../../../../docs/framework/unmanaged-api/profiling/functiontailcall3-function.md)関数。</span><span class="sxs-lookup"><span data-stu-id="ac3a5-103">Specifies the profiler-implemented functions that will be called on the [FunctionEnter3](../../../../docs/framework/unmanaged-api/profiling/functionenter3-function.md), [FunctionLeave3](../../../../docs/framework/unmanaged-api/profiling/functionleave3-function.md), and [FunctionTailcall3](../../../../docs/framework/unmanaged-api/profiling/functiontailcall3-function.md) functions.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ac3a5-104">構文</span><span class="sxs-lookup"><span data-stu-id="ac3a5-104">Syntax</span></span>  
  
```  
HRESULT SetEnterLeaveFunctionHooks3(  
            [in] FunctionEnter3    *pFuncEnter3,  
            [in] FunctionLeave3    *pFuncLeave3,  
            [in] FunctionTailcall3 *pFuncTailcall3);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ac3a5-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="ac3a5-105">Parameters</span></span>  
 `pFuncEnter3`  
 <span data-ttu-id="ac3a5-106">[in]として使用する実装へのポインター、`FunctionEnter3`コールバック。</span><span class="sxs-lookup"><span data-stu-id="ac3a5-106">[in] A pointer to the implementation to be used as the `FunctionEnter3` callback.</span></span>  
  
 `pFuncLeave3`  
 <span data-ttu-id="ac3a5-107">[in]として使用する実装へのポインター、`FunctionLeave3`コールバック。</span><span class="sxs-lookup"><span data-stu-id="ac3a5-107">[in] A pointer to the implementation to be used as the `FunctionLeave3` callback.</span></span>  
  
 `pFuncTailcall3`  
 <span data-ttu-id="ac3a5-108">[in]として使用する実装へのポインター、`FunctionTailcall3`コールバック。</span><span class="sxs-lookup"><span data-stu-id="ac3a5-108">[in] A pointer to the implementation to be used as the `FunctionTailcall3` callback.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ac3a5-109">Remarks</span><span class="sxs-lookup"><span data-stu-id="ac3a5-109">Remarks</span></span>  
 <span data-ttu-id="ac3a5-110">[FunctionEnter3](../../../../docs/framework/unmanaged-api/profiling/functionenter3-function.md)、 [FunctionLeave3](../../../../docs/framework/unmanaged-api/profiling/functionleave3-function.md)、および[FunctionTailcall3](../../../../docs/framework/unmanaged-api/profiling/functiontailcall3-function.md)フックはスタック フレームおよび引数の検査に渡さないようにします。</span><span class="sxs-lookup"><span data-stu-id="ac3a5-110">[FunctionEnter3](../../../../docs/framework/unmanaged-api/profiling/functionenter3-function.md), [FunctionLeave3](../../../../docs/framework/unmanaged-api/profiling/functionleave3-function.md), and [FunctionTailcall3](../../../../docs/framework/unmanaged-api/profiling/functiontailcall3-function.md) hooks do not provide stack frame and argument inspection.</span></span> <span data-ttu-id="ac3a5-111">情報にアクセスする、 `COR_PRF_ENABLE_FUNCTION_ARGS`、 `COR_PRF_ENABLE_FUNCTION_RETVAL`、や`COR_PRF_ENABLE_FRAME_INFO`フラグを設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ac3a5-111">To access that information, the `COR_PRF_ENABLE_FUNCTION_ARGS`, `COR_PRF_ENABLE_FUNCTION_RETVAL`, and/or  `COR_PRF_ENABLE_FRAME_INFO` flags have to be set.</span></span> <span data-ttu-id="ac3a5-112">プロファイラーは、使用、 [icorprofilerinfo::seteventmask](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-seteventmask-method.md)メソッド、イベント フラグを設定し、使用して、 [icorprofilerinfo 3::setenterleavefunctionhooks3withinfo](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-setenterleavefunctionhooks3withinfo-method.md)を登録するメソッド、この関数の実装です。</span><span class="sxs-lookup"><span data-stu-id="ac3a5-112">The profiler can use the [ICorProfilerInfo::SetEventMask](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-seteventmask-method.md) method to set the event flags, and then use the [ICorProfilerInfo3::SetEnterLeaveFunctionHooks3WithInfo](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-setenterleavefunctionhooks3withinfo-method.md) method to register your implementation of this function.</span></span>  
  
 <span data-ttu-id="ac3a5-113">時に、1 つだけの一連のコールバックがアクティブなあり、最新のバージョンが優先されます。</span><span class="sxs-lookup"><span data-stu-id="ac3a5-113">Only one set of callbacks may be active at a time, and the newest version takes precedence.</span></span> <span data-ttu-id="ac3a5-114">そのため、プロファイラーは、両方を呼び出す場合、 [SetEnterLeaveFunctionHooks2 メソッド](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-setenterleavefunctionhooks2-method.md)と`SetEnterLeaveFunctionHooks3`メソッド、`SetEnterLeaveFunctionHooks3`使用されます。</span><span class="sxs-lookup"><span data-stu-id="ac3a5-114">Therefore, if a profiler calls both the [SetEnterLeaveFunctionHooks2 Method](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-setenterleavefunctionhooks2-method.md) and the `SetEnterLeaveFunctionHooks3` method, `SetEnterLeaveFunctionHooks3` is used.</span></span>  
  
 <span data-ttu-id="ac3a5-115">`SetEnterLeaveFunctionHooks3`メソッドは、プロファイラーからのみ呼び出すことが[icorprofilercallback::initialize](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-initialize-method.md)コールバック。</span><span class="sxs-lookup"><span data-stu-id="ac3a5-115">The `SetEnterLeaveFunctionHooks3` method may be called only from the profiler's [ICorProfilerCallback::Initialize](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-initialize-method.md) callback.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ac3a5-116">必要条件</span><span class="sxs-lookup"><span data-stu-id="ac3a5-116">Requirements</span></span>  
 <span data-ttu-id="ac3a5-117">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="ac3a5-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ac3a5-118">**ヘッダー:** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="ac3a5-118">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="ac3a5-119">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ac3a5-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ac3a5-120">**.NET Framework のバージョン:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ac3a5-120">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ac3a5-121">関連項目</span><span class="sxs-lookup"><span data-stu-id="ac3a5-121">See also</span></span>
- [<span data-ttu-id="ac3a5-122">SetEnterLeaveFunctionHooks3WithInfo</span><span class="sxs-lookup"><span data-stu-id="ac3a5-122">SetEnterLeaveFunctionHooks3WithInfo</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-setenterleavefunctionhooks3withinfo-method.md)
- [<span data-ttu-id="ac3a5-123">FunctionEnter3</span><span class="sxs-lookup"><span data-stu-id="ac3a5-123">FunctionEnter3</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionenter3-function.md)
- [<span data-ttu-id="ac3a5-124">FunctionLeave3</span><span class="sxs-lookup"><span data-stu-id="ac3a5-124">FunctionLeave3</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionleave3-function.md)
- [<span data-ttu-id="ac3a5-125">FunctionTailcall3</span><span class="sxs-lookup"><span data-stu-id="ac3a5-125">FunctionTailcall3</span></span>](../../../../docs/framework/unmanaged-api/profiling/functiontailcall3-function.md)
- [<span data-ttu-id="ac3a5-126">FunctionEnter3WithInfo</span><span class="sxs-lookup"><span data-stu-id="ac3a5-126">FunctionEnter3WithInfo</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionenter3withinfo-function.md)
- [<span data-ttu-id="ac3a5-127">FunctionLeave3WithInfo</span><span class="sxs-lookup"><span data-stu-id="ac3a5-127">FunctionLeave3WithInfo</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionleave3withinfo-function.md)
- [<span data-ttu-id="ac3a5-128">FunctionTailcall3WithInfo</span><span class="sxs-lookup"><span data-stu-id="ac3a5-128">FunctionTailcall3WithInfo</span></span>](../../../../docs/framework/unmanaged-api/profiling/functiontailcall3withinfo-function.md)
- [<span data-ttu-id="ac3a5-129">グローバル静的関数のプロファイル</span><span class="sxs-lookup"><span data-stu-id="ac3a5-129">Profiling Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-global-static-functions.md)
- [<span data-ttu-id="ac3a5-130">ICorProfilerInfo3</span><span class="sxs-lookup"><span data-stu-id="ac3a5-130">ICorProfilerInfo3</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-interface.md)
- [<span data-ttu-id="ac3a5-131">プロファイリングのインターフェイス</span><span class="sxs-lookup"><span data-stu-id="ac3a5-131">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
- [<span data-ttu-id="ac3a5-132">プロファイル</span><span class="sxs-lookup"><span data-stu-id="ac3a5-132">Profiling</span></span>](../../../../docs/framework/unmanaged-api/profiling/index.md)
