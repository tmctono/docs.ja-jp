---
title: FunctionEnter3WithInfo 関数
ms.date: 03/30/2017
api_name:
- FunctionEnter3WithInfo
api_location:
- mscorwks.cll
api_type:
- COM
f1_keywords:
- FunctionEnter3WithInfo
helpviewer_keywords:
- FunctionEnter3WithInfo function [.NET Framework profiling]
ms.assetid: 277c3344-d0cb-431e-beae-eb1eeeba8eea
topic_type:
- apiref
ms.openlocfilehash: 86b1c8b3f5bd88b216c59f5cc6846f83f3c094ee
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/23/2019
ms.locfileid: "74440753"
---
# <a name="functionenter3withinfo-function"></a><span data-ttu-id="55ac9-102">FunctionEnter3WithInfo 関数</span><span class="sxs-lookup"><span data-stu-id="55ac9-102">FunctionEnter3WithInfo Function</span></span>
<span data-ttu-id="55ac9-103">Notifies the profiler that control is being passed to a function, and provides a handle that can be passed to the [ICorProfilerInfo3::GetFunctionEnter3Info method](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-getfunctionenter3info-method.md) to retrieve the stack frame and function arguments.</span><span class="sxs-lookup"><span data-stu-id="55ac9-103">Notifies the profiler that control is being passed to a function, and provides a handle that can be passed to the [ICorProfilerInfo3::GetFunctionEnter3Info method](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-getfunctionenter3info-method.md) to retrieve the stack frame and function arguments.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="55ac9-104">構文</span><span class="sxs-lookup"><span data-stu-id="55ac9-104">Syntax</span></span>  
  
```cpp  
void __stdcall FunctionEnter3WithInfo(  
               [in] FunctionIDOrClientID functionIDOrClientID,  
               [in] COR_PRF_ELT_INFO eltInfo);  
```  
  
## <a name="parameters"></a><span data-ttu-id="55ac9-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="55ac9-105">Parameters</span></span>  
 `functionIDOrClientID`  
 <span data-ttu-id="55ac9-106">[in] The identifier of the function to which control is passed.</span><span class="sxs-lookup"><span data-stu-id="55ac9-106">[in] The identifier of the function to which control is passed.</span></span>  
  
 `eltInfo`  
 <span data-ttu-id="55ac9-107">[in] 特定のスタック フレームに関する情報を表す不透明ハンドル。</span><span class="sxs-lookup"><span data-stu-id="55ac9-107">[in] An opaque handle that represents information about a given stack frame.</span></span> <span data-ttu-id="55ac9-108">This handle is valid only during the callback to which it is passed.</span><span class="sxs-lookup"><span data-stu-id="55ac9-108">This handle is valid only during the callback to which it is passed.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="55ac9-109">Remarks</span><span class="sxs-lookup"><span data-stu-id="55ac9-109">Remarks</span></span>  
 <span data-ttu-id="55ac9-110">The `FunctionEnter3WithInfo` callback method notifies the profiler as functions are called, and enables the profiler to use the [ICorProfilerInfo3::GetFunctionEnter3Info method](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-getfunctionenter3info-method.md) to inspect argument values.</span><span class="sxs-lookup"><span data-stu-id="55ac9-110">The `FunctionEnter3WithInfo` callback method notifies the profiler as functions are called, and enables the profiler to use the [ICorProfilerInfo3::GetFunctionEnter3Info method](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-getfunctionenter3info-method.md) to inspect argument values.</span></span> <span data-ttu-id="55ac9-111">To access argument information, the `COR_PRF_ENABLE_FUNCTION_ARGS` flag has to be set.</span><span class="sxs-lookup"><span data-stu-id="55ac9-111">To access argument information, the `COR_PRF_ENABLE_FUNCTION_ARGS` flag has to be set.</span></span> <span data-ttu-id="55ac9-112">The profiler can use the [ICorProfilerInfo::SetEventMask method](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-seteventmask-method.md) to set the event flags, and then use the [ICorProfilerInfo3::SetEnterLeaveFunctionHooks3WithInfo method](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-setenterleavefunctionhooks3withinfo-method.md) to register your implementation of this function.</span><span class="sxs-lookup"><span data-stu-id="55ac9-112">The profiler can use the [ICorProfilerInfo::SetEventMask method](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-seteventmask-method.md) to set the event flags, and then use the [ICorProfilerInfo3::SetEnterLeaveFunctionHooks3WithInfo method](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-setenterleavefunctionhooks3withinfo-method.md) to register your implementation of this function.</span></span>  
  
 <span data-ttu-id="55ac9-113">The `FunctionEnter3WithInfo` function is a callback; you must implement it.</span><span class="sxs-lookup"><span data-stu-id="55ac9-113">The `FunctionEnter3WithInfo` function is a callback; you must implement it.</span></span> <span data-ttu-id="55ac9-114">The implementation must use the `__declspec(naked)` storage-class attribute.</span><span class="sxs-lookup"><span data-stu-id="55ac9-114">The implementation must use the `__declspec(naked)` storage-class attribute.</span></span>  
  
 <span data-ttu-id="55ac9-115">The execution engine does not save any registers before calling this function.</span><span class="sxs-lookup"><span data-stu-id="55ac9-115">The execution engine does not save any registers before calling this function.</span></span>  
  
- <span data-ttu-id="55ac9-116">On entry, you must save all registers that you use, including those in the floating-point unit (FPU).</span><span class="sxs-lookup"><span data-stu-id="55ac9-116">On entry, you must save all registers that you use, including those in the floating-point unit (FPU).</span></span>  
  
- <span data-ttu-id="55ac9-117">On exit, you must restore the stack by popping off all the parameters that were pushed by its caller.</span><span class="sxs-lookup"><span data-stu-id="55ac9-117">On exit, you must restore the stack by popping off all the parameters that were pushed by its caller.</span></span>  
  
 <span data-ttu-id="55ac9-118">The implementation of `FunctionEnter3WithInfo` should not block, because it will delay garbage collection.</span><span class="sxs-lookup"><span data-stu-id="55ac9-118">The implementation of `FunctionEnter3WithInfo` should not block, because it will delay garbage collection.</span></span> <span data-ttu-id="55ac9-119">The implementation should not attempt a garbage collection, because the stack may not be in a garbage collection-friendly state.</span><span class="sxs-lookup"><span data-stu-id="55ac9-119">The implementation should not attempt a garbage collection, because the stack may not be in a garbage collection-friendly state.</span></span> <span data-ttu-id="55ac9-120">If a garbage collection is attempted, the runtime will block until `FunctionEnter3WithInfo` returns.</span><span class="sxs-lookup"><span data-stu-id="55ac9-120">If a garbage collection is attempted, the runtime will block until `FunctionEnter3WithInfo` returns.</span></span>  
  
 <span data-ttu-id="55ac9-121">The `FunctionEnter3WithInfo` function must not call into managed code or cause a managed memory allocation in any way.</span><span class="sxs-lookup"><span data-stu-id="55ac9-121">The `FunctionEnter3WithInfo` function must not call into managed code or cause a managed memory allocation in any way.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="55ac9-122">［要件］</span><span class="sxs-lookup"><span data-stu-id="55ac9-122">Requirements</span></span>  
 <span data-ttu-id="55ac9-123">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="55ac9-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="55ac9-124">**Header:** CorProf.idl</span><span class="sxs-lookup"><span data-stu-id="55ac9-124">**Header:** CorProf.idl</span></span>  
  
 <span data-ttu-id="55ac9-125">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="55ac9-125">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="55ac9-126">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="55ac9-126">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="55ac9-127">関連項目</span><span class="sxs-lookup"><span data-stu-id="55ac9-127">See also</span></span>

- [<span data-ttu-id="55ac9-128">GetFunctionEnter3Info</span><span class="sxs-lookup"><span data-stu-id="55ac9-128">GetFunctionEnter3Info</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-getfunctionenter3info-method.md)
- [<span data-ttu-id="55ac9-129">FunctionEnter3</span><span class="sxs-lookup"><span data-stu-id="55ac9-129">FunctionEnter3</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionenter3-function.md)
- [<span data-ttu-id="55ac9-130">FunctionLeave3</span><span class="sxs-lookup"><span data-stu-id="55ac9-130">FunctionLeave3</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionleave3-function.md)
- [<span data-ttu-id="55ac9-131">グローバル静的関数のプロファイル</span><span class="sxs-lookup"><span data-stu-id="55ac9-131">Profiling Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-global-static-functions.md)
