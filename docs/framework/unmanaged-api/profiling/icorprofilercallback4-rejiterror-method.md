---
title: ICorProfilerCallback4::ReJITError メソッド
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback4.ReJITError
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback4::ReJITError
helpviewer_keywords:
- ReJITError method, ICorProfilerCallback4 interface [.NET Framework profiling]
- ICorProfilerCallback4::ReJITError method [.NET Framework profiling]
ms.assetid: d7888aa9-dfaa-420f-9f99-e06ab35ca482
topic_type:
- apiref
ms.openlocfilehash: 6ea9dee6e83870d1f2e0fdccffa53f16e6f18dba
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/23/2019
ms.locfileid: "74430112"
---
# <a name="icorprofilercallback4rejiterror-method"></a><span data-ttu-id="fd9e8-102">ICorProfilerCallback4::ReJITError メソッド</span><span class="sxs-lookup"><span data-stu-id="fd9e8-102">ICorProfilerCallback4::ReJITError Method</span></span>
<span data-ttu-id="fd9e8-103">Notifies the profiler that the just-in-time (JIT) compiler encountered an error in the recompilation process.</span><span class="sxs-lookup"><span data-stu-id="fd9e8-103">Notifies the profiler that the just-in-time (JIT) compiler encountered an error in the recompilation process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fd9e8-104">構文</span><span class="sxs-lookup"><span data-stu-id="fd9e8-104">Syntax</span></span>  
  
```cpp  
HRESULT ReJITError(  
    [in] ModuleID    moduleId,  
    [in] mdMethodDef methodId,  
    [in] FunctionID  functionId,  
    [in] HRESULT     hrStatus);  
```  
  
## <a name="parameters"></a><span data-ttu-id="fd9e8-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="fd9e8-105">Parameters</span></span>  
 `moduleID`  
 <span data-ttu-id="fd9e8-106">[in] The `ModuleID` in which the failed recompilation attempt was made.</span><span class="sxs-lookup"><span data-stu-id="fd9e8-106">[in] The `ModuleID` in which the failed recompilation attempt was made.</span></span>  
  
 `methodId`  
 <span data-ttu-id="fd9e8-107">[in] The `MethodDef` of the method on which the failed recompilation attempt was made.</span><span class="sxs-lookup"><span data-stu-id="fd9e8-107">[in] The `MethodDef` of the method on which the failed recompilation attempt was made.</span></span>  
  
 `functionId`  
 <span data-ttu-id="fd9e8-108">[in] The function instance that is being recompiled or marked for recompilation.</span><span class="sxs-lookup"><span data-stu-id="fd9e8-108">[in] The function instance that is being recompiled or marked for recompilation.</span></span> <span data-ttu-id="fd9e8-109">This value may be `NULL` if the failure occurred on a per-method basis instead of a per-instantiation basis (for example, if the profiler specified an invalid metadata token for the method to be recompiled).</span><span class="sxs-lookup"><span data-stu-id="fd9e8-109">This value may be `NULL` if the failure occurred on a per-method basis instead of a per-instantiation basis (for example, if the profiler specified an invalid metadata token for the method to be recompiled).</span></span>  
  
 `hrStatus`  
 <span data-ttu-id="fd9e8-110">[in] An HRESULT that indicates the nature of the failure.</span><span class="sxs-lookup"><span data-stu-id="fd9e8-110">[in] An HRESULT that indicates the nature of the failure.</span></span> <span data-ttu-id="fd9e8-111">See the Status HRESULTS section for a list of values.</span><span class="sxs-lookup"><span data-stu-id="fd9e8-111">See the Status HRESULTS section for a list of values.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="fd9e8-112">戻り値</span><span class="sxs-lookup"><span data-stu-id="fd9e8-112">Return Value</span></span>  
 <span data-ttu-id="fd9e8-113">このコールバックからの戻り値は無視されます。</span><span class="sxs-lookup"><span data-stu-id="fd9e8-113">Return values from this callback are ignored.</span></span>  
  
## <a name="status-hresults"></a><span data-ttu-id="fd9e8-114">状態 HRESULT</span><span class="sxs-lookup"><span data-stu-id="fd9e8-114">Status HRESULTS</span></span>  
  
|<span data-ttu-id="fd9e8-115">状態配列 HRESULT</span><span class="sxs-lookup"><span data-stu-id="fd9e8-115">Status array HRESULT</span></span>|<span data-ttu-id="fd9e8-116">説明</span><span class="sxs-lookup"><span data-stu-id="fd9e8-116">Description</span></span>|  
|--------------------------|-----------------|  
|<span data-ttu-id="fd9e8-117">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="fd9e8-117">E_INVALIDARG</span></span>|<span data-ttu-id="fd9e8-118">The `moduleID` or `methodDef` token is `NULL`.</span><span class="sxs-lookup"><span data-stu-id="fd9e8-118">The `moduleID` or `methodDef` token is `NULL`.</span></span>|  
|<span data-ttu-id="fd9e8-119">CORPROF_E_DATAINCOMPLETE</span><span class="sxs-lookup"><span data-stu-id="fd9e8-119">CORPROF_E_DATAINCOMPLETE</span></span>|<span data-ttu-id="fd9e8-120">モジュールが完全に読み込まれていないか、またはアンロード中です。</span><span class="sxs-lookup"><span data-stu-id="fd9e8-120">The module is not fully loaded yet, or it is in the process of being unloaded.</span></span>|  
|<span data-ttu-id="fd9e8-121">CORPROF_E_MODULE_IS_DYNAMIC</span><span class="sxs-lookup"><span data-stu-id="fd9e8-121">CORPROF_E_MODULE_IS_DYNAMIC</span></span>|<span data-ttu-id="fd9e8-122">The specified module was dynamically generated (for example, by `Reflection.Emit`), and is thus not supported by this method.</span><span class="sxs-lookup"><span data-stu-id="fd9e8-122">The specified module was dynamically generated (for example, by `Reflection.Emit`), and is thus not supported by this method.</span></span>|  
|<span data-ttu-id="fd9e8-123">CORPROF_E_FUNCTION_IS_COLLECTIBLE</span><span class="sxs-lookup"><span data-stu-id="fd9e8-123">CORPROF_E_FUNCTION_IS_COLLECTIBLE</span></span>|<span data-ttu-id="fd9e8-124">The method is instantiated into a collectible assembly, and is therefore not able to be recompiled.</span><span class="sxs-lookup"><span data-stu-id="fd9e8-124">The method is instantiated into a collectible assembly, and is therefore not able to be recompiled.</span></span> <span data-ttu-id="fd9e8-125">Note that types and functions defined in a non-reflection context (for example, `List<MyCollectibleStruct>`) can be instantiated into a collectible assembly.</span><span class="sxs-lookup"><span data-stu-id="fd9e8-125">Note that types and functions defined in a non-reflection context (for example, `List<MyCollectibleStruct>`) can be instantiated into a collectible assembly.</span></span>|  
|<span data-ttu-id="fd9e8-126">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="fd9e8-126">E_OUTOFMEMORY</span></span>|<span data-ttu-id="fd9e8-127">The CLR ran out of memory while trying to mark the specified method for JIT recompilation.</span><span class="sxs-lookup"><span data-stu-id="fd9e8-127">The CLR ran out of memory while trying to mark the specified method for JIT recompilation.</span></span>|  
|<span data-ttu-id="fd9e8-128">その他</span><span class="sxs-lookup"><span data-stu-id="fd9e8-128">Other</span></span>|<span data-ttu-id="fd9e8-129">オペレーティング システムは、CLR 制御範囲外のエラーを返しました。</span><span class="sxs-lookup"><span data-stu-id="fd9e8-129">The operating system returned a failure outside the control of the CLR.</span></span> <span data-ttu-id="fd9e8-130">For example, if a system call to change the access protection of a page of memory fails, the operating system error is displayed.</span><span class="sxs-lookup"><span data-stu-id="fd9e8-130">For example, if a system call to change the access protection of a page of memory fails, the operating system error is displayed.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="fd9e8-131">［要件］</span><span class="sxs-lookup"><span data-stu-id="fd9e8-131">Requirements</span></span>  
 <span data-ttu-id="fd9e8-132">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fd9e8-132">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fd9e8-133">**ヘッダー** : CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="fd9e8-133">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="fd9e8-134">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="fd9e8-134">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="fd9e8-135">**.NET Framework のバージョン:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fd9e8-135">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fd9e8-136">関連項目</span><span class="sxs-lookup"><span data-stu-id="fd9e8-136">See also</span></span>

- [<span data-ttu-id="fd9e8-137">ICorProfilerCallback インターフェイス</span><span class="sxs-lookup"><span data-stu-id="fd9e8-137">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [<span data-ttu-id="fd9e8-138">ICorProfilerCallback4 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="fd9e8-138">ICorProfilerCallback4 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-interface.md)
