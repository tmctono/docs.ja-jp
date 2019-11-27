---
title: FunctionIDMapper2 関数
ms.date: 03/30/2017
api_name:
- FunctionIDMapper2
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- FunctionIDMapper2
helpviewer_keywords:
- FunctionIDMapper2 function [.NET Framework profiling]
ms.assetid: 466ad51b-8f0c-41d9-81f7-371aac3374cb
topic_type:
- apiref
ms.openlocfilehash: 7f83469920956d73a275f510b0d3c3e94a4caa8d
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/23/2019
ms.locfileid: "74440670"
---
# <a name="functionidmapper2-function"></a><span data-ttu-id="e2993-102">FunctionIDMapper2 関数</span><span class="sxs-lookup"><span data-stu-id="e2993-102">FunctionIDMapper2 Function</span></span>
<span data-ttu-id="e2993-103">指定された関数の識別子が、その関数の[FunctionEnter3](../../../../docs/framework/unmanaged-api/profiling/functionenter3-function.md)、 [FunctionLeave3](../../../../docs/framework/unmanaged-api/profiling/functionleave3-function.md)、 [FunctionTailcall3](../../../../docs/framework/unmanaged-api/profiling/functiontailcall3-function.md)、または[FunctionEnter3WithInfo](../../../../docs/framework/unmanaged-api/profiling/functionenter3withinfo-function.md)、 [FunctionLeave3WithInfo](../../../../docs/framework/unmanaged-api/profiling/functionleave3withinfo-function.md)、および[FunctionTailcall3WithInfo](../../../../docs/framework/unmanaged-api/profiling/functiontailcall3withinfo-function.md)コールバックで使用される代替 ID に再マップされる可能性があることをプロファイラーに通知します。</span><span class="sxs-lookup"><span data-stu-id="e2993-103">Notifies the profiler that the given identifier of a function may be remapped to an alternative ID to be used in the [FunctionEnter3](../../../../docs/framework/unmanaged-api/profiling/functionenter3-function.md), [FunctionLeave3](../../../../docs/framework/unmanaged-api/profiling/functionleave3-function.md), and [FunctionTailcall3](../../../../docs/framework/unmanaged-api/profiling/functiontailcall3-function.md), or[FunctionEnter3WithInfo](../../../../docs/framework/unmanaged-api/profiling/functionenter3withinfo-function.md), [FunctionLeave3WithInfo](../../../../docs/framework/unmanaged-api/profiling/functionleave3withinfo-function.md), and [FunctionTailcall3WithInfo](../../../../docs/framework/unmanaged-api/profiling/functiontailcall3withinfo-function.md) callbacks for that function.</span></span> <span data-ttu-id="e2993-104">また、`FunctionIDMapper2` では、その関数のコールバックを受信するかどうかをプロファイラーが示すことができます。</span><span class="sxs-lookup"><span data-stu-id="e2993-104">`FunctionIDMapper2` also enables the profiler to indicate whether it wants to receive callbacks for that function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e2993-105">構文</span><span class="sxs-lookup"><span data-stu-id="e2993-105">Syntax</span></span>  
  
```cpp  
UINT_PTR __stdcall FunctionIDMapper2 (  
    [in]  FunctionID  funcId,  
    [in]  void * clientData,  
    [out] BOOL       *pbHookFunction  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e2993-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="e2993-106">Parameters</span></span>  
 `funcId`  
 <span data-ttu-id="e2993-107">[入力] 再割り当てされる関数識別子。</span><span class="sxs-lookup"><span data-stu-id="e2993-107">[in] The function identifier to be remapped.</span></span>  
  
 `clientData`  
 <span data-ttu-id="e2993-108">[入力] ランタイム間のあいまいさを解消するために使用されるデータへのポインター。</span><span class="sxs-lookup"><span data-stu-id="e2993-108">[in] A pointer to data that is used to disambiguate among runtimes.</span></span>  
  
 `pbHookFunction`  
 <span data-ttu-id="e2993-109">[出力] 出力プロファイラーが `true`、`FunctionEnter3`、`FunctionLeave3`、または  `FunctionTailcall3`、`FunctionEnter3WithInfo`、`FunctionLeave3WithInfo` の各コールバックを受信する場合は `FunctionTailcall3WithInfo` に設定される値へのポインター。それ以外の場合、この値は  `false` に設定されます。</span><span class="sxs-lookup"><span data-stu-id="e2993-109">[out] A pointer to a value that the profiler sets to `true` if it wants to receive `FunctionEnter3`, `FunctionLeave3`, and `FunctionTailcall3`, or `FunctionEnter3WithInfo`, `FunctionLeave3WithInfo`, and `FunctionTailcall3WithInfo` callbacks; otherwise, it sets this value to `false`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="e2993-110">戻り値</span><span class="sxs-lookup"><span data-stu-id="e2993-110">Return Value</span></span>  
 <span data-ttu-id="e2993-111">プロファイラーは、実行エンジンが代替関数識別子として使用する値を返します。</span><span class="sxs-lookup"><span data-stu-id="e2993-111">The profiler returns a value that the execution engine uses as an alternative function identifier.</span></span> <span data-ttu-id="e2993-112">`false` で `pbHookFunction` を返さない限り、戻り値を null にすることはできません。</span><span class="sxs-lookup"><span data-stu-id="e2993-112">The return value cannot be null unless `false` is returned in `pbHookFunction`.</span></span> <span data-ttu-id="e2993-113">これ以外の状況で戻り値を null にすると、プロセスの中止など、予測できない結果が発生します。</span><span class="sxs-lookup"><span data-stu-id="e2993-113">Otherwise, a null return value produces unpredictable results, including possibly halting the process.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e2993-114">コメント</span><span class="sxs-lookup"><span data-stu-id="e2993-114">Remarks</span></span>  
 <span data-ttu-id="e2993-115">このメソッドは、クライアントデータを渡すために使用される追加のパラメーターを使用して[Functionidmapper](../../../../docs/framework/unmanaged-api/profiling/functionidmapper-function.md)関数を拡張します。</span><span class="sxs-lookup"><span data-stu-id="e2993-115">This method extends the [FunctionIDMapper](../../../../docs/framework/unmanaged-api/profiling/functionidmapper-function.md) function with an additional parameter that is used to pass client data.</span></span> <span data-ttu-id="e2993-116">クライアント データを使用すると、ランタイム間のあいまいさが解消されます。</span><span class="sxs-lookup"><span data-stu-id="e2993-116">The client data is used to disambiguate among runtimes.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e2993-117">要件</span><span class="sxs-lookup"><span data-stu-id="e2993-117">Requirements</span></span>  
 <span data-ttu-id="e2993-118">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e2993-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e2993-119">**ヘッダー:** Corprof.idl</span><span class="sxs-lookup"><span data-stu-id="e2993-119">**Header:** CorProf.idl</span></span>  
  
 <span data-ttu-id="e2993-120">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e2993-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e2993-121">**.NET Framework のバージョン:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e2993-121">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e2993-122">参照</span><span class="sxs-lookup"><span data-stu-id="e2993-122">See also</span></span>

- [<span data-ttu-id="e2993-123">ICorProfilerInfo:: SetFunctionIDMapper</span><span class="sxs-lookup"><span data-stu-id="e2993-123">ICorProfilerInfo::SetFunctionIDMapper</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-setfunctionidmapper-method.md)
- [<span data-ttu-id="e2993-124">ICorProfilerInfo3:: SetFunctionIDMapper2</span><span class="sxs-lookup"><span data-stu-id="e2993-124">ICorProfilerInfo3::SetFunctionIDMapper2</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-setfunctionidmapper2-method.md)
- [<span data-ttu-id="e2993-125">FunctionEnter3</span><span class="sxs-lookup"><span data-stu-id="e2993-125">FunctionEnter3</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionenter3-function.md)
- [<span data-ttu-id="e2993-126">FunctionLeave3</span><span class="sxs-lookup"><span data-stu-id="e2993-126">FunctionLeave3</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionleave3-function.md)
- [<span data-ttu-id="e2993-127">FunctionTailcall3</span><span class="sxs-lookup"><span data-stu-id="e2993-127">FunctionTailcall3</span></span>](../../../../docs/framework/unmanaged-api/profiling/functiontailcall3-function.md)
- [<span data-ttu-id="e2993-128">FunctionEnter3WithInfo</span><span class="sxs-lookup"><span data-stu-id="e2993-128">FunctionEnter3WithInfo</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionenter3withinfo-function.md)
- [<span data-ttu-id="e2993-129">FunctionLeave3WithInfo</span><span class="sxs-lookup"><span data-stu-id="e2993-129">FunctionLeave3WithInfo</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionleave3withinfo-function.md)
- [<span data-ttu-id="e2993-130">FunctionTailcall3WithInfo</span><span class="sxs-lookup"><span data-stu-id="e2993-130">FunctionTailcall3WithInfo</span></span>](../../../../docs/framework/unmanaged-api/profiling/functiontailcall3withinfo-function.md)
- [<span data-ttu-id="e2993-131">グローバル静的関数のプロファイル</span><span class="sxs-lookup"><span data-stu-id="e2993-131">Profiling Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-global-static-functions.md)
