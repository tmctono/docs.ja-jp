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
ms.openlocfilehash: 2c4a89d5f96ef572518f25bf58a0005454f8e3f0
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/08/2020
ms.locfileid: "84496130"
---
# <a name="icorprofilerinfo4enumjitedfunctions2-method"></a><span data-ttu-id="562c6-102">ICorProfilerInfo4::EnumJITedFunctions2 メソッド</span><span class="sxs-lookup"><span data-stu-id="562c6-102">ICorProfilerInfo4::EnumJITedFunctions2 Method</span></span>
<span data-ttu-id="562c6-103">以前に JIT コンパイルおよび JIT 再コンパイルされたすべての関数の列挙子を返します。</span><span class="sxs-lookup"><span data-stu-id="562c6-103">Returns an enumerator for all functions that were previously JIT-compiled and JIT-recompiled.</span></span> <span data-ttu-id="562c6-104">このメソッドは、JIT 再コンパイルされた Id を列挙しない[ICorProfilerInfo3:: EnumJITedFunctions](icorprofilerinfo3-enumjitedfunctions-method.md)メソッドを置き換えます。</span><span class="sxs-lookup"><span data-stu-id="562c6-104">This method replaces the [ICorProfilerInfo3::EnumJITedFunctions](icorprofilerinfo3-enumjitedfunctions-method.md) method, which does not enumerate JIT-recompiled IDs.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="562c6-105">構文</span><span class="sxs-lookup"><span data-stu-id="562c6-105">Syntax</span></span>  
  
```cpp  
HRESULT EnumJITedFunctions([out] ICorProfilerFunctionEnum** ppEnum);  
```  
  
## <a name="parameters"></a><span data-ttu-id="562c6-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="562c6-106">Parameters</span></span>  
 `ppEnum`  
 <span data-ttu-id="562c6-107">入出力[ICorProfilerFunctionEnum](icorprofilerfunctionenum-interface.md)列挙子へのポインター。</span><span class="sxs-lookup"><span data-stu-id="562c6-107">[out] A pointer to the [ICorProfilerFunctionEnum](icorprofilerfunctionenum-interface.md) enumerator.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="562c6-108">解説</span><span class="sxs-lookup"><span data-stu-id="562c6-108">Remarks</span></span>  
 <span data-ttu-id="562c6-109">このメソッドは `JITCompilation` 、 [ICorProfilerCallback:: JITCompilationStarted](icorprofilercallback-jitcompilationstarted-method.md)メソッドなどのコールバックと重複する場合があります。</span><span class="sxs-lookup"><span data-stu-id="562c6-109">This method may overlap with `JITCompilation` callbacks such as the [ICorProfilerCallback::JITCompilationStarted](icorprofilercallback-jitcompilationstarted-method.md) method.</span></span> <span data-ttu-id="562c6-110">返される列挙体には、フィールドの値が含まれ `COR_PRF_FUNCTION::reJitId` ます。</span><span class="sxs-lookup"><span data-stu-id="562c6-110">The returned enumeration includes values for the `COR_PRF_FUNCTION::reJitId` field.</span></span> <span data-ttu-id="562c6-111">このメソッドで置き換えられる[ICorProfilerInfo3:: EnumJITedFunctions](icorprofilerinfo3-enumjitedfunctions-method.md)メソッドでは、 `COR_PRF_FUNCTION::reJitId` フィールドが常に0に設定されているため、JIT 再コンパイルされた id は列挙されません。</span><span class="sxs-lookup"><span data-stu-id="562c6-111">The [ICorProfilerInfo3::EnumJITedFunctions](icorprofilerinfo3-enumjitedfunctions-method.md) method, which this method replaces, does not enumerate JIT-recompiled IDs, because the `COR_PRF_FUNCTION::reJitId` field is always set to 0.</span></span> <span data-ttu-id="562c6-112">`ICorProfilerInfo4::EnumJITedFunctions`フィールドが適切に設定されているため、メソッドは JIT 再コンパイルされた id を列挙し `COR_PRF_FUNCTION::reJitId` ます。</span><span class="sxs-lookup"><span data-stu-id="562c6-112">The `ICorProfilerInfo4::EnumJITedFunctions` method does enumerate JIT-recompiled IDs, because the `COR_PRF_FUNCTION::reJitId` field is set properly.</span></span> <span data-ttu-id="562c6-113">[ICorProfilerInfo4:: EnumJITedFunctions2](icorprofilerinfo4-enumjitedfunctions2-method.md)メソッドではガベージコレクションをトリガーできるのに対し、 [ICorProfilerInfo3:: EnumJITedFunctions メソッド](icorprofilerinfo3-enumjitedfunctions-method.md)ではトリガーされないことに注意してください。</span><span class="sxs-lookup"><span data-stu-id="562c6-113">Note that the [ICorProfilerInfo4::EnumJITedFunctions2](icorprofilerinfo4-enumjitedfunctions2-method.md) method can trigger a garbage collection, whereas [ICorProfilerInfo3::EnumJITedFunctions method](icorprofilerinfo3-enumjitedfunctions-method.md) will not.</span></span>  <span data-ttu-id="562c6-114">詳細については、「 [HRESULT CORPROF_E_UNSUPPORTED_CALL_SEQUENCE](corprof-e-unsupported-call-sequence-hresult.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="562c6-114">For more information, see [CORPROF_E_UNSUPPORTED_CALL_SEQUENCE HRESULT](corprof-e-unsupported-call-sequence-hresult.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="562c6-115">要件</span><span class="sxs-lookup"><span data-stu-id="562c6-115">Requirements</span></span>  
 <span data-ttu-id="562c6-116">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="562c6-116">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="562c6-117">**ヘッダー** : CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="562c6-117">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="562c6-118">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="562c6-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="562c6-119">**.NET Framework のバージョン:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="562c6-119">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="562c6-120">関連項目</span><span class="sxs-lookup"><span data-stu-id="562c6-120">See also</span></span>

- [<span data-ttu-id="562c6-121">EnumJITedFunctions メソッド</span><span class="sxs-lookup"><span data-stu-id="562c6-121">EnumJITedFunctions Method</span></span>](icorprofilerinfo3-enumjitedfunctions-method.md)
- [<span data-ttu-id="562c6-122">ICorProfilerInfo4 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="562c6-122">ICorProfilerInfo4 Interface</span></span>](icorprofilerinfo4-interface.md)
- [<span data-ttu-id="562c6-123">プロファイリングのインターフェイス</span><span class="sxs-lookup"><span data-stu-id="562c6-123">Profiling Interfaces</span></span>](profiling-interfaces.md)
- [<span data-ttu-id="562c6-124">プロファイル</span><span class="sxs-lookup"><span data-stu-id="562c6-124">Profiling</span></span>](index.md)
