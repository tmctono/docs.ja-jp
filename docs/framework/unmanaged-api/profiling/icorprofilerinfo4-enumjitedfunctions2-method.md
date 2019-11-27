---
title: ICorProfilerInfo4::EnumJITedFunctions2 メソッド
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo4.EnumJITedFunctions2
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo4::EnumJITedFunctions2
helpviewer_keywords:
- EnumJITedFunctions2 method, ICorProfilerInfo4 interface [.NET Framework profiling]
- ICorProfilerInfo4::EnumJITedFunctions2 method [.NET Framework profiling]
ms.assetid: 40e9a1be-9bd2-4fad-9921-34a84b61c1e3
topic_type:
- apiref
ms.openlocfilehash: 09d273a81ed4f956508e4fadb628b28e18d00f90
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/23/2019
ms.locfileid: "74449563"
---
# <a name="icorprofilerinfo4enumjitedfunctions2-method"></a><span data-ttu-id="3e429-102">ICorProfilerInfo4::EnumJITedFunctions2 メソッド</span><span class="sxs-lookup"><span data-stu-id="3e429-102">ICorProfilerInfo4::EnumJITedFunctions2 Method</span></span>
<span data-ttu-id="3e429-103">以前に JIT コンパイルおよび JIT 再コンパイルされたすべての関数の列挙子を返します。</span><span class="sxs-lookup"><span data-stu-id="3e429-103">Returns an enumerator for all functions that were previously JIT-compiled and JIT-recompiled.</span></span> <span data-ttu-id="3e429-104">このメソッドは、JIT 再コンパイルされた Id を列挙しない[ICorProfilerInfo3:: EnumJITedFunctions](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-enumjitedfunctions-method.md)メソッドを置き換えます。</span><span class="sxs-lookup"><span data-stu-id="3e429-104">This method replaces the [ICorProfilerInfo3::EnumJITedFunctions](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-enumjitedfunctions-method.md) method, which does not enumerate JIT-recompiled IDs.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3e429-105">構文</span><span class="sxs-lookup"><span data-stu-id="3e429-105">Syntax</span></span>  
  
```cpp  
HRESULT EnumJITedFunctions([out] ICorProfilerFunctionEnum** ppEnum);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3e429-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="3e429-106">Parameters</span></span>  
 `ppEnum`  
 <span data-ttu-id="3e429-107">入出力[ICorProfilerFunctionEnum](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctionenum-interface.md)列挙子へのポインター。</span><span class="sxs-lookup"><span data-stu-id="3e429-107">[out] A pointer to the [ICorProfilerFunctionEnum](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctionenum-interface.md) enumerator.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3e429-108">コメント</span><span class="sxs-lookup"><span data-stu-id="3e429-108">Remarks</span></span>  
 <span data-ttu-id="3e429-109">このメソッドは、 [ICorProfilerCallback:: JITCompilationStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-jitcompilationstarted-method.md)メソッドなどの `JITCompilation` コールバックと重複する場合があります。</span><span class="sxs-lookup"><span data-stu-id="3e429-109">This method may overlap with `JITCompilation` callbacks such as the [ICorProfilerCallback::JITCompilationStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-jitcompilationstarted-method.md) method.</span></span> <span data-ttu-id="3e429-110">返される列挙体には、`COR_PRF_FUNCTION::reJitId` フィールドの値が含まれます。</span><span class="sxs-lookup"><span data-stu-id="3e429-110">The returned enumeration includes values for the `COR_PRF_FUNCTION::reJitId` field.</span></span> <span data-ttu-id="3e429-111">`COR_PRF_FUNCTION::reJitId` フィールドは常に0に設定されているため、このメソッドで置き換える[ICorProfilerInfo3:: EnumJITedFunctions](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-enumjitedfunctions-method.md)メソッドは、JIT 再コンパイルされた id を列挙しません。</span><span class="sxs-lookup"><span data-stu-id="3e429-111">The [ICorProfilerInfo3::EnumJITedFunctions](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-enumjitedfunctions-method.md) method, which this method replaces, does not enumerate JIT-recompiled IDs, because the `COR_PRF_FUNCTION::reJitId` field is always set to 0.</span></span> <span data-ttu-id="3e429-112">`COR_PRF_FUNCTION::reJitId` フィールドが適切に設定されているため、`ICorProfilerInfo4::EnumJITedFunctions` メソッドは JIT 再コンパイルされた Id を列挙します。</span><span class="sxs-lookup"><span data-stu-id="3e429-112">The `ICorProfilerInfo4::EnumJITedFunctions` method does enumerate JIT-recompiled IDs, because the `COR_PRF_FUNCTION::reJitId` field is set properly.</span></span> <span data-ttu-id="3e429-113">[ICorProfilerInfo4:: EnumJITedFunctions2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-enumjitedfunctions2-method.md)メソッドではガベージコレクションをトリガーできるのに対し、 [ICorProfilerInfo3:: EnumJITedFunctions メソッド](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-enumjitedfunctions-method.md)ではトリガーされないことに注意してください。</span><span class="sxs-lookup"><span data-stu-id="3e429-113">Note that the [ICorProfilerInfo4::EnumJITedFunctions2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-enumjitedfunctions2-method.md) method can trigger a garbage collection, whereas [ICorProfilerInfo3::EnumJITedFunctions method](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-enumjitedfunctions-method.md) will not.</span></span>  <span data-ttu-id="3e429-114">詳細については、「 [HRESULT CORPROF_E_UNSUPPORTED_CALL_SEQUENCE](../../../../docs/framework/unmanaged-api/profiling/corprof-e-unsupported-call-sequence-hresult.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3e429-114">For more information, see [CORPROF_E_UNSUPPORTED_CALL_SEQUENCE HRESULT](../../../../docs/framework/unmanaged-api/profiling/corprof-e-unsupported-call-sequence-hresult.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3e429-115">要件</span><span class="sxs-lookup"><span data-stu-id="3e429-115">Requirements</span></span>  
 <span data-ttu-id="3e429-116">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3e429-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3e429-117">**ヘッダー** : CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="3e429-117">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="3e429-118">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3e429-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3e429-119">**.NET Framework のバージョン:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3e429-119">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3e429-120">関連項目</span><span class="sxs-lookup"><span data-stu-id="3e429-120">See also</span></span>

- [<span data-ttu-id="3e429-121">EnumJITedFunctions メソッド</span><span class="sxs-lookup"><span data-stu-id="3e429-121">EnumJITedFunctions Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-enumjitedfunctions-method.md)
- [<span data-ttu-id="3e429-122">ICorProfilerInfo4 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="3e429-122">ICorProfilerInfo4 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-interface.md)
- [<span data-ttu-id="3e429-123">プロファイリングのインターフェイス</span><span class="sxs-lookup"><span data-stu-id="3e429-123">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
- [<span data-ttu-id="3e429-124">プロファイル</span><span class="sxs-lookup"><span data-stu-id="3e429-124">Profiling</span></span>](../../../../docs/framework/unmanaged-api/profiling/index.md)
