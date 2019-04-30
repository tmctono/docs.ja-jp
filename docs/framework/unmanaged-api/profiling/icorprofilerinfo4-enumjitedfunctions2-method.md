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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 92bc16091abd3e21ebd226fb13dd47b55b0c9cc4
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62049467"
---
# <a name="icorprofilerinfo4enumjitedfunctions2-method"></a><span data-ttu-id="43a12-102">ICorProfilerInfo4::EnumJITedFunctions2 メソッド</span><span class="sxs-lookup"><span data-stu-id="43a12-102">ICorProfilerInfo4::EnumJITedFunctions2 Method</span></span>
<span data-ttu-id="43a12-103">以前に JIT コンパイル、JIT 再コンパイルしていたすべての関数の列挙子を返します。</span><span class="sxs-lookup"><span data-stu-id="43a12-103">Returns an enumerator for all functions that were previously JIT-compiled and JIT-recompiled.</span></span> <span data-ttu-id="43a12-104">このメソッドは、置換、 [icorprofilerinfo 3::enumjitedfunctions](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-enumjitedfunctions-method.md)メソッドを JIT 再コンパイルの Id を列挙できません。</span><span class="sxs-lookup"><span data-stu-id="43a12-104">This method replaces the [ICorProfilerInfo3::EnumJITedFunctions](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-enumjitedfunctions-method.md) method, which does not enumerate JIT-recompiled IDs.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="43a12-105">構文</span><span class="sxs-lookup"><span data-stu-id="43a12-105">Syntax</span></span>  
  
```  
HRESULT EnumJITedFunctions([out] ICorProfilerFunctionEnum** ppEnum);  
```  
  
## <a name="parameters"></a><span data-ttu-id="43a12-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="43a12-106">Parameters</span></span>  
 `ppEnum`  
 <span data-ttu-id="43a12-107">[out]ポインター、 [ICorProfilerFunctionEnum](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctionenum-interface.md)列挙子。</span><span class="sxs-lookup"><span data-stu-id="43a12-107">[out] A pointer to the [ICorProfilerFunctionEnum](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctionenum-interface.md) enumerator.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="43a12-108">Remarks</span><span class="sxs-lookup"><span data-stu-id="43a12-108">Remarks</span></span>  
 <span data-ttu-id="43a12-109">このメソッドが重複する`JITCompilation`コールバックなど、 [icorprofilercallback::jitcompilationstarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-jitcompilationstarted-method.md)メソッド。</span><span class="sxs-lookup"><span data-stu-id="43a12-109">This method may overlap with `JITCompilation` callbacks such as the [ICorProfilerCallback::JITCompilationStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-jitcompilationstarted-method.md) method.</span></span> <span data-ttu-id="43a12-110">返された列挙体には値が含まれています、`COR_PRF_FUNCTION::reJitId`フィールド。</span><span class="sxs-lookup"><span data-stu-id="43a12-110">The returned enumeration includes values for the `COR_PRF_FUNCTION::reJitId` field.</span></span> <span data-ttu-id="43a12-111">[Icorprofilerinfo 3::enumjitedfunctions](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-enumjitedfunctions-method.md)ので、メソッドは、このメソッドに代わるが JIT 再コンパイルの Id を列挙できません、`COR_PRF_FUNCTION::reJitId`フィールドは常に 0 に設定します。</span><span class="sxs-lookup"><span data-stu-id="43a12-111">The [ICorProfilerInfo3::EnumJITedFunctions](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-enumjitedfunctions-method.md) method, which this method replaces, does not enumerate JIT-recompiled IDs, because the `COR_PRF_FUNCTION::reJitId` field is always set to 0.</span></span> <span data-ttu-id="43a12-112">`ICorProfilerInfo4::EnumJITedFunctions`ので、メソッドが JIT 再コンパイルの Id を列挙は、`COR_PRF_FUNCTION::reJitId`フィールドが適切に設定します。</span><span class="sxs-lookup"><span data-stu-id="43a12-112">The `ICorProfilerInfo4::EnumJITedFunctions` method does enumerate JIT-recompiled IDs, because the `COR_PRF_FUNCTION::reJitId` field is set properly.</span></span> <span data-ttu-id="43a12-113">なお、 [icorprofilerinfo 4::enumjitedfunctions2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-enumjitedfunctions2-method.md)メソッドは、ガベージ コレクションをトリガーできますが、 [icorprofilerinfo 3::enumjitedfunctions メソッド](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-enumjitedfunctions-method.md)されません。</span><span class="sxs-lookup"><span data-stu-id="43a12-113">Note that the [ICorProfilerInfo4::EnumJITedFunctions2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-enumjitedfunctions2-method.md) method can trigger a garbage collection, whereas [ICorProfilerInfo3::EnumJITedFunctions method](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-enumjitedfunctions-method.md) will not.</span></span>  <span data-ttu-id="43a12-114">詳細については、次を参照してください。 [CORPROF_E_UNSUPPORTED_CALL_SEQUENCE HRESULT](../../../../docs/framework/unmanaged-api/profiling/corprof-e-unsupported-call-sequence-hresult.md)します。</span><span class="sxs-lookup"><span data-stu-id="43a12-114">For more information, see [CORPROF_E_UNSUPPORTED_CALL_SEQUENCE HRESULT](../../../../docs/framework/unmanaged-api/profiling/corprof-e-unsupported-call-sequence-hresult.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="43a12-115">必要条件</span><span class="sxs-lookup"><span data-stu-id="43a12-115">Requirements</span></span>  
 <span data-ttu-id="43a12-116">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="43a12-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="43a12-117">**ヘッダー:** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="43a12-117">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="43a12-118">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="43a12-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="43a12-119">**.NET Framework のバージョン:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="43a12-119">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="43a12-120">関連項目</span><span class="sxs-lookup"><span data-stu-id="43a12-120">See also</span></span>

- [<span data-ttu-id="43a12-121">EnumJITedFunctions メソッド</span><span class="sxs-lookup"><span data-stu-id="43a12-121">EnumJITedFunctions Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-enumjitedfunctions-method.md)
- [<span data-ttu-id="43a12-122">ICorProfilerInfo4 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="43a12-122">ICorProfilerInfo4 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-interface.md)
- [<span data-ttu-id="43a12-123">プロファイリングのインターフェイス</span><span class="sxs-lookup"><span data-stu-id="43a12-123">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
- [<span data-ttu-id="43a12-124">プロファイル</span><span class="sxs-lookup"><span data-stu-id="43a12-124">Profiling</span></span>](../../../../docs/framework/unmanaged-api/profiling/index.md)
