---
title: ICorProfilerInfo10::RequestReJITWithInliners
ms.date: 08/06/2019
dev_langs:
- cpp
api_name:
- ICorProfilerInfo10.RequestReJITWithInliners
api_location:
- mscorwks.dll
api_type:
- COM
author: davmason
ms.author: davmason
ms.openlocfilehash: c33a868b643cb3e3fd5dfaf436e3078bc590705c
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/23/2019
ms.locfileid: "74449808"
---
# <a name="icorprofilerinfo10requestrejitwithinliners-method"></a><span data-ttu-id="f5732-102">ICorProfilerInfo10::RequestReJITWithInliners Method</span><span class="sxs-lookup"><span data-stu-id="f5732-102">ICorProfilerInfo10::RequestReJITWithInliners Method</span></span>

<span data-ttu-id="f5732-103">ReJITs the methods requested, as well as any inliners of the methods requested.</span><span class="sxs-lookup"><span data-stu-id="f5732-103">ReJITs the methods requested, as well as any inliners of the methods requested.</span></span>

## <a name="syntax"></a><span data-ttu-id="f5732-104">構文</span><span class="sxs-lookup"><span data-stu-id="f5732-104">Syntax</span></span>

```cpp
HRESULT RequestReJITWithInliners( [in]                       DWORD       dwRejitFlags,
                                  [in]                       ULONG       cFunctions,
                                  [in, size_is(cFunctions)]  ModuleID    moduleIds[],
                                  [in, size_is(cFunctions)]  mdMethodDef methodIds[]);
```

#### <a name="parameters"></a><span data-ttu-id="f5732-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="f5732-105">Parameters</span></span>

`dwRejitFlags` \
<span data-ttu-id="f5732-106">[in] A bitmask of [COR_PRF_REJIT_FLAGS](../../../../docs/framework/unmanaged-api/profiling/cor-prf-rejit-flags-enumeration.md).</span><span class="sxs-lookup"><span data-stu-id="f5732-106">[in] A bitmask of [COR_PRF_REJIT_FLAGS](../../../../docs/framework/unmanaged-api/profiling/cor-prf-rejit-flags-enumeration.md).</span></span>

`cFunctions` \
<span data-ttu-id="f5732-107">[in] 再コンパイルする関数の数。</span><span class="sxs-lookup"><span data-stu-id="f5732-107">[in] The number of functions to recompile.</span></span>

`moduleIds` \
<span data-ttu-id="f5732-108">[in] 再コンパイルする関数を識別する (`module`、`methodDef`) ペアの `moduleId` の部分を指定します。</span><span class="sxs-lookup"><span data-stu-id="f5732-108">[in] Specifies the `moduleId` portion of the (`module`, `methodDef`) pairs that identify the functions to be recompiled.</span></span>

`methodIds` \
<span data-ttu-id="f5732-109">[in] 再コンパイルする関数を識別する (`module`、`methodDef`) ペアの `methodId` の部分を指定します。</span><span class="sxs-lookup"><span data-stu-id="f5732-109">[in] Specifies the `methodId` portion of the (`module`, `methodDef`) pairs that identify the functions to be recompiled.</span></span>

## <a name="remarks"></a><span data-ttu-id="f5732-110">Remarks</span><span class="sxs-lookup"><span data-stu-id="f5732-110">Remarks</span></span>

<span data-ttu-id="f5732-111">[RequestReJIT](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-requestrejit-method.md) does not do any tracking of inlined methods.</span><span class="sxs-lookup"><span data-stu-id="f5732-111">[RequestReJIT](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-requestrejit-method.md) does not do any tracking of inlined methods.</span></span> <span data-ttu-id="f5732-112">The profiler was expected to either block inlining or track inlining and call `RequestReJIT` for all inliners to make sure every instance of an inlined method was ReJITted.</span><span class="sxs-lookup"><span data-stu-id="f5732-112">The profiler was expected to either block inlining or track inlining and call `RequestReJIT` for all inliners to make sure every instance of an inlined method was ReJITted.</span></span> <span data-ttu-id="f5732-113">This poses a problem with ReJIT on attach, since the profiler is not present to monitor inlining.</span><span class="sxs-lookup"><span data-stu-id="f5732-113">This poses a problem with ReJIT on attach, since the profiler is not present to monitor inlining.</span></span> <span data-ttu-id="f5732-114">This method can be called to guarantee that the full set of inliners will be ReJITted as well.</span><span class="sxs-lookup"><span data-stu-id="f5732-114">This method can be called to guarantee that the full set of inliners will be ReJITted as well.</span></span>

## <a name="requirements"></a><span data-ttu-id="f5732-115">［要件］</span><span class="sxs-lookup"><span data-stu-id="f5732-115">Requirements</span></span>

<span data-ttu-id="f5732-116">**Platforms:** See [.NET Core supported operating systems](../../../core/install/dependencies.md?tabs=netcore30&pivots=os-windows).</span><span class="sxs-lookup"><span data-stu-id="f5732-116">**Platforms:** See [.NET Core supported operating systems](../../../core/install/dependencies.md?tabs=netcore30&pivots=os-windows).</span></span>

<span data-ttu-id="f5732-117">**ヘッダー** : CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="f5732-117">**Header:** CorProf.idl, CorProf.h</span></span>

<span data-ttu-id="f5732-118">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f5732-118">**Library:** CorGuids.lib</span></span>

<span data-ttu-id="f5732-119">**.NET Versions:** [!INCLUDE[net_core_22](../../../../includes/net-core-30-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f5732-119">**.NET Versions:** [!INCLUDE[net_core_22](../../../../includes/net-core-30-md.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="f5732-120">関連項目</span><span class="sxs-lookup"><span data-stu-id="f5732-120">See also</span></span>

- [<span data-ttu-id="f5732-121">ICorProfilerInfo10 Interface</span><span class="sxs-lookup"><span data-stu-id="f5732-121">ICorProfilerInfo10 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo10-interface.md)
