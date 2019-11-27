---
title: ICorProfilerFunctionControl::SetCodegenFlags メソッド
ms.date: 03/30/2017
api_name:
- ICorProfilerFunctionControl.SetCodegenFlags
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerFunctionControl::SetCodegenFlags
helpviewer_keywords:
- ICorProfilerFunctionControl::SetCodegenFlags method [.NET Framework profiling]
- SetCodegenFlags method, ICorProfilerFunctionControl interface [.NET Framework profiling]
ms.assetid: a2d5daa5-b990-4ae5-bf2a-c0862fe58bd7
topic_type:
- apiref
ms.openlocfilehash: 88c9f552b73af69ea4e1f64b75ed74ea762dcdfb
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/23/2019
ms.locfileid: "74429939"
---
# <a name="icorprofilerfunctioncontrolsetcodegenflags-method"></a><span data-ttu-id="f40c8-102">ICorProfilerFunctionControl::SetCodegenFlags メソッド</span><span class="sxs-lookup"><span data-stu-id="f40c8-102">ICorProfilerFunctionControl::SetCodegenFlags Method</span></span>
<span data-ttu-id="f40c8-103">[COR_PRF_CODEGEN_FLAGS](../../../../docs/framework/unmanaged-api/profiling/cor-prf-codegen-flags-enumeration.md)列挙型の1つ以上のフラグを設定して、JUST-IN-TIME (JIT) 再コンパイル関数のコード生成を制御します。</span><span class="sxs-lookup"><span data-stu-id="f40c8-103">Sets one or more flags from the [COR_PRF_CODEGEN_FLAGS](../../../../docs/framework/unmanaged-api/profiling/cor-prf-codegen-flags-enumeration.md) enumeration to control code generation for a just-in-time (JIT) recompiled function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f40c8-104">構文</span><span class="sxs-lookup"><span data-stu-id="f40c8-104">Syntax</span></span>  
  
```cpp  
HRESULT SetCodegenFlags(  
    [in] DWORD flags);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f40c8-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="f40c8-105">Parameters</span></span>  
 `flags`  
 <span data-ttu-id="f40c8-106">から[COR_PRF_CODEGEN_FLAGS](../../../../docs/framework/unmanaged-api/profiling/cor-prf-codegen-flags-enumeration.md)列挙体の1つ以上のフラグ。</span><span class="sxs-lookup"><span data-stu-id="f40c8-106">[in] One or more flags from the [COR_PRF_CODEGEN_FLAGS](../../../../docs/framework/unmanaged-api/profiling/cor-prf-codegen-flags-enumeration.md) enumeration.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f40c8-107">コメント</span><span class="sxs-lookup"><span data-stu-id="f40c8-107">Remarks</span></span>  
 <span data-ttu-id="f40c8-108">プロファイラーは、 [ICorProfilerCallback4:: GetReJITParameters](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-getrejitparameters-method.md)コールバックを使用して、このインターフェイスのインスタンスを取得します。</span><span class="sxs-lookup"><span data-stu-id="f40c8-108">The profiler obtains an instance of this interface through the [ICorProfilerCallback4::GetReJITParameters](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-getrejitparameters-method.md) callback.</span></span> <span data-ttu-id="f40c8-109">`SetCodegenFlags` を使用すると、再コンパイルされた関数のコード生成をプロファイラーで制御できます。</span><span class="sxs-lookup"><span data-stu-id="f40c8-109">`SetCodegenFlags` allows the profiler to control the code generation for the recompiled function.</span></span> <span data-ttu-id="f40c8-110">他のすべての JIT 再コンパイルパラメーターと同様に、コード生成フラグは関数のすべてのインスタンスに適用されます。</span><span class="sxs-lookup"><span data-stu-id="f40c8-110">As with all other JIT recompilation parameters, the code generation flags apply to all instances of the function.</span></span>  
  
 <span data-ttu-id="f40c8-111">JIT コンパイラは、関数をコンパイルするときに、これらのコンパイルフラグを他のソースによって指定された他のフラグと共に考慮します。</span><span class="sxs-lookup"><span data-stu-id="f40c8-111">The JIT compiler considers these compilation flags, along with other flags specified by other sources, when compiling a function.</span></span>  <span data-ttu-id="f40c8-112">その他のソースには、デバッガー、 [ICorProfilerInfo:: SetEventMask](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-seteventmask-method.md)メソッド (値 `COR_PRF_DISABLE_INLINING` と `COR_PRF_DISABLE_OPTIMIZATIONS`)、およびプロファイラーの[ICorProfilerCallback:: JITInlining](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-jitinlining-method.md) callback を使用して、起動時にプロファイラーによって設定されるグローバルフラグが含まれます。</span><span class="sxs-lookup"><span data-stu-id="f40c8-112">The other sources include the debugger, global flags set by the profiler on startup by using the [ICorProfilerInfo::SetEventMask](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-seteventmask-method.md) method (with the values `COR_PRF_DISABLE_INLINING` and `COR_PRF_DISABLE_OPTIMIZATIONS`), and the profiler’s [ICorProfilerCallback::JITInlining](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-jitinlining-method.md) callback.</span></span>  <span data-ttu-id="f40c8-113">JIT コンパイラは、最小限の最適化を要求するソースに優先順位を付けます。</span><span class="sxs-lookup"><span data-stu-id="f40c8-113">The JIT compiler gives precedence to a source that requests the least amount of optimizing.</span></span>  <span data-ttu-id="f40c8-114">たとえば、プロファイラーが起動時に `COR_PRF_DISABLE_INLINING` を指定していても、 [ICorProfilerFunctionControl:: SetCodegenFlags](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctioncontrol-setcodegenflags-method.md)コールバックで `COR_PRF_CODEGEN_DISABLE_INLINING` を指定していない場合でも、インライン展開は無効になります。</span><span class="sxs-lookup"><span data-stu-id="f40c8-114">For example, if the profiler specifies `COR_PRF_DISABLE_INLINING` on startup, but does not specify `COR_PRF_CODEGEN_DISABLE_INLINING` in the [ICorProfilerFunctionControl::SetCodegenFlags](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctioncontrol-setcodegenflags-method.md) callback, inlining is still disabled.</span></span>  <span data-ttu-id="f40c8-115">同様に、プロファイラーが `SetCodegenFlags`で `COR_PRF_CODEGEN_DISABLE_INLINING` を指定せず、 [ICorProfilerCallback:: JITInlining](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-jitinlining-method.md)コールバックを使用してインライン展開を無効にした場合、インライン展開は無効になります。</span><span class="sxs-lookup"><span data-stu-id="f40c8-115">Similarly, if the profiler does not specify `COR_PRF_CODEGEN_DISABLE_INLINING` in `SetCodegenFlags`, but then disables inlining by using the [ICorProfilerCallback::JITInlining](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-jitinlining-method.md) callback, inlining is disabled.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f40c8-116">要件</span><span class="sxs-lookup"><span data-stu-id="f40c8-116">Requirements</span></span>  
 <span data-ttu-id="f40c8-117">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f40c8-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f40c8-118">**ヘッダー** : CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="f40c8-118">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="f40c8-119">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f40c8-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f40c8-120">**.NET Framework のバージョン:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f40c8-120">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f40c8-121">参照</span><span class="sxs-lookup"><span data-stu-id="f40c8-121">See also</span></span>

- [<span data-ttu-id="f40c8-122">ICorProfilerFunctionControl インターフェイス</span><span class="sxs-lookup"><span data-stu-id="f40c8-122">ICorProfilerFunctionControl Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctioncontrol-interface.md)
