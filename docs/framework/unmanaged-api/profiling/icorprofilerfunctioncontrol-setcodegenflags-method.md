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
ms.openlocfilehash: 75414ec3d2b30fe8afc5db1e97c81f34b29a3115
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/29/2020
ms.locfileid: "76864675"
---
# <a name="icorprofilerfunctioncontrolsetcodegenflags-method"></a><span data-ttu-id="a653d-102">ICorProfilerFunctionControl::SetCodegenFlags メソッド</span><span class="sxs-lookup"><span data-stu-id="a653d-102">ICorProfilerFunctionControl::SetCodegenFlags Method</span></span>
<span data-ttu-id="a653d-103">[COR_PRF_CODEGEN_FLAGS](cor-prf-codegen-flags-enumeration.md)列挙型の1つ以上のフラグを設定して、JUST-IN-TIME (JIT) 再コンパイル関数のコード生成を制御します。</span><span class="sxs-lookup"><span data-stu-id="a653d-103">Sets one or more flags from the [COR_PRF_CODEGEN_FLAGS](cor-prf-codegen-flags-enumeration.md) enumeration to control code generation for a just-in-time (JIT) recompiled function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a653d-104">構文</span><span class="sxs-lookup"><span data-stu-id="a653d-104">Syntax</span></span>  
  
```cpp  
HRESULT SetCodegenFlags(  
    [in] DWORD flags);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a653d-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="a653d-105">Parameters</span></span>  
 `flags`  
 <span data-ttu-id="a653d-106">から[COR_PRF_CODEGEN_FLAGS](cor-prf-codegen-flags-enumeration.md)列挙体の1つ以上のフラグ。</span><span class="sxs-lookup"><span data-stu-id="a653d-106">[in] One or more flags from the [COR_PRF_CODEGEN_FLAGS](cor-prf-codegen-flags-enumeration.md) enumeration.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a653d-107">コメント</span><span class="sxs-lookup"><span data-stu-id="a653d-107">Remarks</span></span>  
 <span data-ttu-id="a653d-108">プロファイラーは、 [ICorProfilerCallback4:: GetReJITParameters](icorprofilercallback4-getrejitparameters-method.md)コールバックを使用して、このインターフェイスのインスタンスを取得します。</span><span class="sxs-lookup"><span data-stu-id="a653d-108">The profiler obtains an instance of this interface through the [ICorProfilerCallback4::GetReJITParameters](icorprofilercallback4-getrejitparameters-method.md) callback.</span></span> <span data-ttu-id="a653d-109">`SetCodegenFlags` を使用すると、再コンパイルされた関数のコード生成をプロファイラーで制御できます。</span><span class="sxs-lookup"><span data-stu-id="a653d-109">`SetCodegenFlags` allows the profiler to control the code generation for the recompiled function.</span></span> <span data-ttu-id="a653d-110">他のすべての JIT 再コンパイルパラメーターと同様に、コード生成フラグは関数のすべてのインスタンスに適用されます。</span><span class="sxs-lookup"><span data-stu-id="a653d-110">As with all other JIT recompilation parameters, the code generation flags apply to all instances of the function.</span></span>  
  
 <span data-ttu-id="a653d-111">JIT コンパイラは、関数をコンパイルするときに、これらのコンパイルフラグを他のソースによって指定された他のフラグと共に考慮します。</span><span class="sxs-lookup"><span data-stu-id="a653d-111">The JIT compiler considers these compilation flags, along with other flags specified by other sources, when compiling a function.</span></span>  <span data-ttu-id="a653d-112">その他のソースには、デバッガー、 [ICorProfilerInfo:: SetEventMask](icorprofilerinfo-seteventmask-method.md)メソッド (値 `COR_PRF_DISABLE_INLINING` と `COR_PRF_DISABLE_OPTIMIZATIONS`)、およびプロファイラーの[ICorProfilerCallback:: JITInlining](icorprofilercallback-jitinlining-method.md) callback を使用して、起動時にプロファイラーによって設定されるグローバルフラグが含まれます。</span><span class="sxs-lookup"><span data-stu-id="a653d-112">The other sources include the debugger, global flags set by the profiler on startup by using the [ICorProfilerInfo::SetEventMask](icorprofilerinfo-seteventmask-method.md) method (with the values `COR_PRF_DISABLE_INLINING` and `COR_PRF_DISABLE_OPTIMIZATIONS`), and the profiler’s [ICorProfilerCallback::JITInlining](icorprofilercallback-jitinlining-method.md) callback.</span></span>  <span data-ttu-id="a653d-113">JIT コンパイラは、最小限の最適化を要求するソースに優先順位を付けます。</span><span class="sxs-lookup"><span data-stu-id="a653d-113">The JIT compiler gives precedence to a source that requests the least amount of optimizing.</span></span>  <span data-ttu-id="a653d-114">たとえば、プロファイラーが起動時に `COR_PRF_DISABLE_INLINING` を指定していても、 [ICorProfilerFunctionControl:: SetCodegenFlags](icorprofilerfunctioncontrol-setcodegenflags-method.md)コールバックで `COR_PRF_CODEGEN_DISABLE_INLINING` を指定していない場合でも、インライン展開は無効になります。</span><span class="sxs-lookup"><span data-stu-id="a653d-114">For example, if the profiler specifies `COR_PRF_DISABLE_INLINING` on startup, but does not specify `COR_PRF_CODEGEN_DISABLE_INLINING` in the [ICorProfilerFunctionControl::SetCodegenFlags](icorprofilerfunctioncontrol-setcodegenflags-method.md) callback, inlining is still disabled.</span></span>  <span data-ttu-id="a653d-115">同様に、プロファイラーが `SetCodegenFlags`で `COR_PRF_CODEGEN_DISABLE_INLINING` を指定せず、 [ICorProfilerCallback:: JITInlining](icorprofilercallback-jitinlining-method.md)コールバックを使用してインライン展開を無効にした場合、インライン展開は無効になります。</span><span class="sxs-lookup"><span data-stu-id="a653d-115">Similarly, if the profiler does not specify `COR_PRF_CODEGEN_DISABLE_INLINING` in `SetCodegenFlags`, but then disables inlining by using the [ICorProfilerCallback::JITInlining](icorprofilercallback-jitinlining-method.md) callback, inlining is disabled.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a653d-116">要件</span><span class="sxs-lookup"><span data-stu-id="a653d-116">Requirements</span></span>  
 <span data-ttu-id="a653d-117">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a653d-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a653d-118">**ヘッダー** : CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="a653d-118">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="a653d-119">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a653d-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a653d-120">**.NET Framework のバージョン:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a653d-120">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a653d-121">関連項目</span><span class="sxs-lookup"><span data-stu-id="a653d-121">See also</span></span>

- [<span data-ttu-id="a653d-122">ICorProfilerFunctionControl インターフェイス</span><span class="sxs-lookup"><span data-stu-id="a653d-122">ICorProfilerFunctionControl Interface</span></span>](icorprofilerfunctioncontrol-interface.md)
