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
ms.openlocfilehash: 3903ebf1ad35bd7eb1ba49b4f1acda9024678423
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/29/2020
ms.locfileid: "76862205"
---
# <a name="icorprofilerinfo4enumjitedfunctions2-method"></a><span data-ttu-id="42e7f-102">ICorProfilerInfo4::EnumJITedFunctions2 メソッド</span><span class="sxs-lookup"><span data-stu-id="42e7f-102">ICorProfilerInfo4::EnumJITedFunctions2 Method</span></span>
<span data-ttu-id="42e7f-103">以前に JIT コンパイルおよび JIT 再コンパイルされたすべての関数の列挙子を返します。</span><span class="sxs-lookup"><span data-stu-id="42e7f-103">Returns an enumerator for all functions that were previously JIT-compiled and JIT-recompiled.</span></span> <span data-ttu-id="42e7f-104">このメソッドは、JIT 再コンパイルされた Id を列挙しない[ICorProfilerInfo3:: EnumJITedFunctions](icorprofilerinfo3-enumjitedfunctions-method.md)メソッドを置き換えます。</span><span class="sxs-lookup"><span data-stu-id="42e7f-104">This method replaces the [ICorProfilerInfo3::EnumJITedFunctions](icorprofilerinfo3-enumjitedfunctions-method.md) method, which does not enumerate JIT-recompiled IDs.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="42e7f-105">構文</span><span class="sxs-lookup"><span data-stu-id="42e7f-105">Syntax</span></span>  
  
```cpp  
HRESULT EnumJITedFunctions([out] ICorProfilerFunctionEnum** ppEnum);  
```  
  
## <a name="parameters"></a><span data-ttu-id="42e7f-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="42e7f-106">Parameters</span></span>  
 `ppEnum`  
 <span data-ttu-id="42e7f-107">入出力[ICorProfilerFunctionEnum](icorprofilerfunctionenum-interface.md)列挙子へのポインター。</span><span class="sxs-lookup"><span data-stu-id="42e7f-107">[out] A pointer to the [ICorProfilerFunctionEnum](icorprofilerfunctionenum-interface.md) enumerator.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="42e7f-108">コメント</span><span class="sxs-lookup"><span data-stu-id="42e7f-108">Remarks</span></span>  
 <span data-ttu-id="42e7f-109">このメソッドは、 [ICorProfilerCallback:: JITCompilationStarted](icorprofilercallback-jitcompilationstarted-method.md)メソッドなどの `JITCompilation` コールバックと重複する場合があります。</span><span class="sxs-lookup"><span data-stu-id="42e7f-109">This method may overlap with `JITCompilation` callbacks such as the [ICorProfilerCallback::JITCompilationStarted](icorprofilercallback-jitcompilationstarted-method.md) method.</span></span> <span data-ttu-id="42e7f-110">返される列挙体には、`COR_PRF_FUNCTION::reJitId` フィールドの値が含まれます。</span><span class="sxs-lookup"><span data-stu-id="42e7f-110">The returned enumeration includes values for the `COR_PRF_FUNCTION::reJitId` field.</span></span> <span data-ttu-id="42e7f-111">`COR_PRF_FUNCTION::reJitId` フィールドは常に0に設定されているため、このメソッドで置き換える[ICorProfilerInfo3:: EnumJITedFunctions](icorprofilerinfo3-enumjitedfunctions-method.md)メソッドは、JIT 再コンパイルされた id を列挙しません。</span><span class="sxs-lookup"><span data-stu-id="42e7f-111">The [ICorProfilerInfo3::EnumJITedFunctions](icorprofilerinfo3-enumjitedfunctions-method.md) method, which this method replaces, does not enumerate JIT-recompiled IDs, because the `COR_PRF_FUNCTION::reJitId` field is always set to 0.</span></span> <span data-ttu-id="42e7f-112">`COR_PRF_FUNCTION::reJitId` フィールドが適切に設定されているため、`ICorProfilerInfo4::EnumJITedFunctions` メソッドは JIT 再コンパイルされた Id を列挙します。</span><span class="sxs-lookup"><span data-stu-id="42e7f-112">The `ICorProfilerInfo4::EnumJITedFunctions` method does enumerate JIT-recompiled IDs, because the `COR_PRF_FUNCTION::reJitId` field is set properly.</span></span> <span data-ttu-id="42e7f-113">[ICorProfilerInfo4:: EnumJITedFunctions2](icorprofilerinfo4-enumjitedfunctions2-method.md)メソッドではガベージコレクションをトリガーできるのに対し、 [ICorProfilerInfo3:: EnumJITedFunctions メソッド](icorprofilerinfo3-enumjitedfunctions-method.md)ではトリガーされないことに注意してください。</span><span class="sxs-lookup"><span data-stu-id="42e7f-113">Note that the [ICorProfilerInfo4::EnumJITedFunctions2](icorprofilerinfo4-enumjitedfunctions2-method.md) method can trigger a garbage collection, whereas [ICorProfilerInfo3::EnumJITedFunctions method](icorprofilerinfo3-enumjitedfunctions-method.md) will not.</span></span>  <span data-ttu-id="42e7f-114">詳細については、「 [HRESULT CORPROF_E_UNSUPPORTED_CALL_SEQUENCE](corprof-e-unsupported-call-sequence-hresult.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="42e7f-114">For more information, see [CORPROF_E_UNSUPPORTED_CALL_SEQUENCE HRESULT](corprof-e-unsupported-call-sequence-hresult.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="42e7f-115">要件</span><span class="sxs-lookup"><span data-stu-id="42e7f-115">Requirements</span></span>  
 <span data-ttu-id="42e7f-116">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="42e7f-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="42e7f-117">**ヘッダー** : CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="42e7f-117">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="42e7f-118">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="42e7f-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="42e7f-119">**.NET Framework のバージョン:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="42e7f-119">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="42e7f-120">関連項目</span><span class="sxs-lookup"><span data-stu-id="42e7f-120">See also</span></span>

- [<span data-ttu-id="42e7f-121">EnumJITedFunctions メソッド</span><span class="sxs-lookup"><span data-stu-id="42e7f-121">EnumJITedFunctions Method</span></span>](icorprofilerinfo3-enumjitedfunctions-method.md)
- [<span data-ttu-id="42e7f-122">ICorProfilerInfo4 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="42e7f-122">ICorProfilerInfo4 Interface</span></span>](icorprofilerinfo4-interface.md)
- [<span data-ttu-id="42e7f-123">プロファイリングのインターフェイス</span><span class="sxs-lookup"><span data-stu-id="42e7f-123">Profiling Interfaces</span></span>](profiling-interfaces.md)
- [<span data-ttu-id="42e7f-124">プロファイル</span><span class="sxs-lookup"><span data-stu-id="42e7f-124">Profiling</span></span>](index.md)
