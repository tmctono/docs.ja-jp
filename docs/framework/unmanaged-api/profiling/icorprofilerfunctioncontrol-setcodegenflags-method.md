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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: e4103925462732fa8ddc509a9538ef5b485266a6
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67780366"
---
# <a name="icorprofilerfunctioncontrolsetcodegenflags-method"></a><span data-ttu-id="51054-102">ICorProfilerFunctionControl::SetCodegenFlags メソッド</span><span class="sxs-lookup"><span data-stu-id="51054-102">ICorProfilerFunctionControl::SetCodegenFlags Method</span></span>
<span data-ttu-id="51054-103">1 つまたは複数のフラグを設定、 [COR_PRF_CODEGEN_FLAGS](../../../../docs/framework/unmanaged-api/profiling/cor-prf-codegen-flags-enumeration.md)を - just-in-time (JIT) のコード生成を制御する列挙型の再コンパイルされた関数。</span><span class="sxs-lookup"><span data-stu-id="51054-103">Sets one or more flags from the [COR_PRF_CODEGEN_FLAGS](../../../../docs/framework/unmanaged-api/profiling/cor-prf-codegen-flags-enumeration.md) enumeration to control code generation for a just-in-time (JIT) recompiled function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="51054-104">構文</span><span class="sxs-lookup"><span data-stu-id="51054-104">Syntax</span></span>  
  
```cpp  
HRESULT SetCodegenFlags(  
    [in] DWORD flags);  
```  
  
## <a name="parameters"></a><span data-ttu-id="51054-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="51054-105">Parameters</span></span>  
 `flags`  
 <span data-ttu-id="51054-106">[in]1 つまたは複数のフラグ、 [COR_PRF_CODEGEN_FLAGS](../../../../docs/framework/unmanaged-api/profiling/cor-prf-codegen-flags-enumeration.md)列挙体。</span><span class="sxs-lookup"><span data-stu-id="51054-106">[in] One or more flags from the [COR_PRF_CODEGEN_FLAGS](../../../../docs/framework/unmanaged-api/profiling/cor-prf-codegen-flags-enumeration.md) enumeration.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="51054-107">Remarks</span><span class="sxs-lookup"><span data-stu-id="51054-107">Remarks</span></span>  
 <span data-ttu-id="51054-108">プロファイラーは、使用して、このインターフェイスのインスタンスを取得、 [icorprofilercallback 4::getrejitparameters](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-getrejitparameters-method.md)コールバック。</span><span class="sxs-lookup"><span data-stu-id="51054-108">The profiler obtains an instance of this interface through the [ICorProfilerCallback4::GetReJITParameters](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-getrejitparameters-method.md) callback.</span></span> <span data-ttu-id="51054-109">`SetCodegenFlags` 再コンパイルされた関数のコード生成を制御するプロファイラーを使用できます。</span><span class="sxs-lookup"><span data-stu-id="51054-109">`SetCodegenFlags` allows the profiler to control the code generation for the recompiled function.</span></span> <span data-ttu-id="51054-110">他のすべての JIT 再コンパイル パラメーターと同様、コード生成フラグは、関数のすべてのインスタンスに適用されます。</span><span class="sxs-lookup"><span data-stu-id="51054-110">As with all other JIT recompilation parameters, the code generation flags apply to all instances of the function.</span></span>  
  
 <span data-ttu-id="51054-111">JIT コンパイラでは、関数をコンパイルするときに、その他のソースで指定されたその他のフラグと共に、これらのコンパイル フラグと見なします。</span><span class="sxs-lookup"><span data-stu-id="51054-111">The JIT compiler considers these compilation flags, along with other flags specified by other sources, when compiling a function.</span></span>  <span data-ttu-id="51054-112">その他のソースには、デバッガーが含まれます、、を使用して、起動時にプロファイラーがグローバル フラグが設定、 [icorprofilerinfo::seteventmask](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-seteventmask-method.md)メソッド (値を持つ`COR_PRF_DISABLE_INLINING`と`COR_PRF_DISABLE_OPTIMIZATIONS`)、およびプロファイラーの[。Icorprofilercallback::jitinlining](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-jitinlining-method.md)コールバック。</span><span class="sxs-lookup"><span data-stu-id="51054-112">The other sources include the debugger, global flags set by the profiler on startup by using the [ICorProfilerInfo::SetEventMask](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-seteventmask-method.md) method (with the values `COR_PRF_DISABLE_INLINING` and `COR_PRF_DISABLE_OPTIMIZATIONS`), and the profiler’s [ICorProfilerCallback::JITInlining](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-jitinlining-method.md) callback.</span></span>  <span data-ttu-id="51054-113">JIT コンパイラでは、最小限の最適化を要求するソースを優先します。</span><span class="sxs-lookup"><span data-stu-id="51054-113">The JIT compiler gives precedence to a source that requests the least amount of optimizing.</span></span>  <span data-ttu-id="51054-114">たとえば、プロファイラーを指定します`COR_PRF_DISABLE_INLINING`スタートアップ時が指定されていません`COR_PRF_CODEGEN_DISABLE_INLINING`で、 [icorprofilerfunctioncontrol::setcodegenflags](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctioncontrol-setcodegenflags-method.md)コールバック、インライン展開は引き続き無効です。</span><span class="sxs-lookup"><span data-stu-id="51054-114">For example, if the profiler specifies `COR_PRF_DISABLE_INLINING` on startup, but does not specify `COR_PRF_CODEGEN_DISABLE_INLINING` in the [ICorProfilerFunctionControl::SetCodegenFlags](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctioncontrol-setcodegenflags-method.md) callback, inlining is still disabled.</span></span>  <span data-ttu-id="51054-115">同様に、プロファイラーが指定されていない場合`COR_PRF_CODEGEN_DISABLE_INLINING`で`SetCodegenFlags`を使用してインライン化、無効、 [icorprofilercallback::jitinlining](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-jitinlining-method.md)コールバック、インライン化が無効になっています。</span><span class="sxs-lookup"><span data-stu-id="51054-115">Similarly, if the profiler does not specify `COR_PRF_CODEGEN_DISABLE_INLINING` in `SetCodegenFlags`, but then disables inlining by using the [ICorProfilerCallback::JITInlining](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-jitinlining-method.md) callback, inlining is disabled.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="51054-116">必要条件</span><span class="sxs-lookup"><span data-stu-id="51054-116">Requirements</span></span>  
 <span data-ttu-id="51054-117">**プラットフォーム:** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="51054-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="51054-118">**ヘッダー:** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="51054-118">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="51054-119">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="51054-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="51054-120">**.NET Framework のバージョン:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="51054-120">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="51054-121">関連項目</span><span class="sxs-lookup"><span data-stu-id="51054-121">See also</span></span>

- [<span data-ttu-id="51054-122">ICorProfilerFunctionControl インターフェイス</span><span class="sxs-lookup"><span data-stu-id="51054-122">ICorProfilerFunctionControl Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctioncontrol-interface.md)
