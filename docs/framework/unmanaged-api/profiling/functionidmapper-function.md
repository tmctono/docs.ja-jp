---
title: FunctionIDMapper 関数
ms.date: 03/30/2017
api_name:
- FunctionIDMapper
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- FunctionIDMapper
helpviewer_keywords:
- FunctionIDMapper function [.NET Framework profiling]
ms.assetid: b8205b60-1893-4303-8cff-7ac5a00892aa
topic_type:
- apiref
ms.openlocfilehash: d5bf6626e2c6ba15fa9a5da08bcf2d9052866750
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/29/2020
ms.locfileid: "76866945"
---
# <a name="functionidmapper-function"></a><span data-ttu-id="62d76-102">FunctionIDMapper 関数</span><span class="sxs-lookup"><span data-stu-id="62d76-102">FunctionIDMapper Function</span></span>
<span data-ttu-id="62d76-103">関数の特定の識別子が、その関数の[FunctionEnter2](functionenter2-function.md)、 [FunctionLeave2](functionleave2-function.md)、および[FunctionTailcall2](functiontailcall2-function.md)コールバックで使用される代替 ID に再マップされる可能性があることをプロファイラーに通知します。</span><span class="sxs-lookup"><span data-stu-id="62d76-103">Notifies the profiler that the given identifier of a function may be remapped to an alternative ID to be used in the [FunctionEnter2](functionenter2-function.md), [FunctionLeave2](functionleave2-function.md), and [FunctionTailcall2](functiontailcall2-function.md) callbacks for that function.</span></span> <span data-ttu-id="62d76-104">また `FunctionIDMapper` により、プロファイラーはその関数のコールバックを受信するかどうかを示すことができます。</span><span class="sxs-lookup"><span data-stu-id="62d76-104">`FunctionIDMapper` also enables the profiler to indicate whether it wants to receive callbacks for that function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="62d76-105">構文</span><span class="sxs-lookup"><span data-stu-id="62d76-105">Syntax</span></span>  
  
```cpp  
UINT_PTR __stdcall FunctionIDMapper (  
    [in]  FunctionID  funcId,   
    [out] BOOL       *pbHookFunction  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="62d76-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="62d76-106">Parameters</span></span>

- `funcId`

  <span data-ttu-id="62d76-107">\[] マップを再マップする関数の識別子。</span><span class="sxs-lookup"><span data-stu-id="62d76-107">\[in] The function identifier to be remapped.</span></span>

- `pbHookFunction`

  <span data-ttu-id="62d76-108">\[out] `FunctionEnter2`、`FunctionLeave2`、および `FunctionTailcall2` のコールバックを受信する必要がある場合にプロファイラーが `true` するように設定する値へのポインター。それ以外の場合は、この値を `false`に設定します。</span><span class="sxs-lookup"><span data-stu-id="62d76-108">\[out] A pointer to a value that the profiler sets to `true` if it wants to receive `FunctionEnter2`, `FunctionLeave2`, and `FunctionTailcall2` callbacks; otherwise, it sets this value to `false`.</span></span>

## <a name="return-value"></a><span data-ttu-id="62d76-109">戻り値</span><span class="sxs-lookup"><span data-stu-id="62d76-109">Return Value</span></span>  
 <span data-ttu-id="62d76-110">プロファイラーは、実行エンジンが代替関数識別子として使用する値を返します。</span><span class="sxs-lookup"><span data-stu-id="62d76-110">The profiler returns a value that the execution engine uses as an alternative function identifier.</span></span> <span data-ttu-id="62d76-111">`false` で `pbHookFunction` を返さない限り、戻り値を null にすることはできません。</span><span class="sxs-lookup"><span data-stu-id="62d76-111">The return value cannot be null unless `false` is returned in `pbHookFunction`.</span></span> <span data-ttu-id="62d76-112">それ以外の場合、null 値が返されると、処理が停止する可能性があるなど、予測できない結果が生成されます。</span><span class="sxs-lookup"><span data-stu-id="62d76-112">Otherwise, a null return value will produce unpredictable results, including possibly halting the process.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="62d76-113">Remarks</span><span class="sxs-lookup"><span data-stu-id="62d76-113">Remarks</span></span>  
 <span data-ttu-id="62d76-114">`FunctionIDMapper` 関数はコールバックです。</span><span class="sxs-lookup"><span data-stu-id="62d76-114">The `FunctionIDMapper` function is a callback.</span></span> <span data-ttu-id="62d76-115">プロファイラーによって実装され、関数 ID を他の識別子にマップし直すことができます。これは、プロファイラーにとって便利です。</span><span class="sxs-lookup"><span data-stu-id="62d76-115">It is implemented by the profiler to remap a function ID to some other identifier that is more useful for the profiler.</span></span> <span data-ttu-id="62d76-116">`FunctionIDMapper` は、指定された関数に使用される代替 ID を返します。</span><span class="sxs-lookup"><span data-stu-id="62d76-116">The `FunctionIDMapper` returns the alternate ID to be used for any given function.</span></span> <span data-ttu-id="62d76-117">その後、実行エンジンは、従来の関数 ID に加えて、この代替 ID を渡してプロファイラーの要求を受け入れ、`FunctionEnter2`、`FunctionLeave2`、および `FunctionTailcall2` フックの `clientData` パラメーターのプロファイラーに戻り、フックが呼び出されている関数を識別します。</span><span class="sxs-lookup"><span data-stu-id="62d76-117">The execution engine then honors the profiler's request by passing this alternate ID, in addition to the traditional function ID, back to the profiler in the `clientData` parameter of the `FunctionEnter2`, `FunctionLeave2`, and `FunctionTailcall2` hooks, to identify the function for which the hook is being called.</span></span>  
  
 <span data-ttu-id="62d76-118">[ICorProfilerInfo:: SetFunctionIDMapper](icorprofilerinfo-setfunctionidmapper-method.md)メソッドを使用して、`FunctionIDMapper` 関数の実装を指定できます。</span><span class="sxs-lookup"><span data-stu-id="62d76-118">You can use the [ICorProfilerInfo::SetFunctionIDMapper](icorprofilerinfo-setfunctionidmapper-method.md) method to specify the implementation of the `FunctionIDMapper` function.</span></span> <span data-ttu-id="62d76-119">`ICorProfilerInfo::SetFunctionIDMapper` メソッドは1回だけ呼び出すことができ、 [ICorProfilerCallback:: Initialize](icorprofilercallback-initialize-method.md)コールバックで呼び出すことをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="62d76-119">You can call the `ICorProfilerInfo::SetFunctionIDMapper` method only once, and we recommend that you do so in the [ICorProfilerCallback::Initialize](icorprofilercallback-initialize-method.md) callback.</span></span>  
  
 <span data-ttu-id="62d76-120">既定では、 [ICorProfilerInfo:: SetEventMask](icorprofilerinfo-seteventmask-method.md)を使用して COR_PRF_MONITOR_ENTERLEAVE フラグを設定し、 [ICorProfilerInfo:: SetEnterLeaveFunctionHooks](icorprofilerinfo-setenterleavefunctionhooks-method.md)または[ICorProfilerInfo2:: SetEnterLeaveFunctionHooks2](icorprofilerinfo2-setenterleavefunctionhooks2-method.md)を介してフックを設定するプロファイラーは、すべての関数に対して `FunctionEnter2`、`FunctionLeave2`、および `FunctionTailcall2` コールバックを受け取る必要があることを前提としています。</span><span class="sxs-lookup"><span data-stu-id="62d76-120">By default, it is assumed that a profiler that sets the COR_PRF_MONITOR_ENTERLEAVE flag by using [ICorProfilerInfo::SetEventMask](icorprofilerinfo-seteventmask-method.md), and which sets hooks via [ICorProfilerInfo::SetEnterLeaveFunctionHooks](icorprofilerinfo-setenterleavefunctionhooks-method.md) or [ICorProfilerInfo2::SetEnterLeaveFunctionHooks2](icorprofilerinfo2-setenterleavefunctionhooks2-method.md), should receive the `FunctionEnter2`, `FunctionLeave2`, and `FunctionTailcall2` callbacks for every function.</span></span> <span data-ttu-id="62d76-121">ただし、`pbHookFunction` を `false`に設定することによって、特定の関数に対してこれらのコールバックが受信されないように、`FunctionIDMapper` を実装する場合があります。</span><span class="sxs-lookup"><span data-stu-id="62d76-121">However, profilers may implement `FunctionIDMapper` to selectively avoid receiving these callbacks for certain functions by setting `pbHookFunction` to `false`.</span></span>  
  
 <span data-ttu-id="62d76-122">プロファイラーは、プロファイルされたアプリケーションの複数のスレッドが同時に同じメソッドまたは関数を呼び出す場合を許容します。</span><span class="sxs-lookup"><span data-stu-id="62d76-122">Profilers should be tolerant of cases where multiple threads of a profiled application are calling the same method/function simultaneously.</span></span> <span data-ttu-id="62d76-123">このような場合、プロファイラーは同じ `FunctionID`に対して複数の `FunctionIDMapper` コールバックを受け取ることがあります。</span><span class="sxs-lookup"><span data-stu-id="62d76-123">In such cases, the profiler may receive multiple `FunctionIDMapper` callbacks for the same `FunctionID`.</span></span> <span data-ttu-id="62d76-124">同じ `FunctionID`で複数回呼び出された場合、このコールバックから同じ値が返されるようにするには、プロファイラーが適切である必要があります。</span><span class="sxs-lookup"><span data-stu-id="62d76-124">The profiler should be certain to return the same values from this callback when it is called multiple times with the same `FunctionID`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="62d76-125">要件</span><span class="sxs-lookup"><span data-stu-id="62d76-125">Requirements</span></span>  
 <span data-ttu-id="62d76-126">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="62d76-126">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="62d76-127">**ヘッダー:** Corprof.idl</span><span class="sxs-lookup"><span data-stu-id="62d76-127">**Header:** CorProf.idl</span></span>  
  
 <span data-ttu-id="62d76-128">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="62d76-128">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="62d76-129">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="62d76-129">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="62d76-130">関連項目</span><span class="sxs-lookup"><span data-stu-id="62d76-130">See also</span></span>

- [<span data-ttu-id="62d76-131">SetFunctionIDMapper メソッド</span><span class="sxs-lookup"><span data-stu-id="62d76-131">SetFunctionIDMapper Method</span></span>](icorprofilerinfo-setfunctionidmapper-method.md)
- [<span data-ttu-id="62d76-132">FunctionIDMapper2 関数</span><span class="sxs-lookup"><span data-stu-id="62d76-132">FunctionIDMapper2 Function</span></span>](functionidmapper2-function.md)
- [<span data-ttu-id="62d76-133">FunctionEnter2 関数</span><span class="sxs-lookup"><span data-stu-id="62d76-133">FunctionEnter2 Function</span></span>](functionenter2-function.md)
- [<span data-ttu-id="62d76-134">FunctionLeave2 関数</span><span class="sxs-lookup"><span data-stu-id="62d76-134">FunctionLeave2 Function</span></span>](functionleave2-function.md)
- [<span data-ttu-id="62d76-135">FunctionTailcall2 関数</span><span class="sxs-lookup"><span data-stu-id="62d76-135">FunctionTailcall2 Function</span></span>](functiontailcall2-function.md)
- [<span data-ttu-id="62d76-136">グローバル静的関数のプロファイル</span><span class="sxs-lookup"><span data-stu-id="62d76-136">Profiling Global Static Functions</span></span>](profiling-global-static-functions.md)
