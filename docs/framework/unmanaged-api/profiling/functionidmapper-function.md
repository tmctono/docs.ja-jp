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
ms.openlocfilehash: 0cf2014d7007593c51868eff0b488fdab136e362
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175175"
---
# <a name="functionidmapper-function"></a><span data-ttu-id="2b24a-102">FunctionIDMapper 関数</span><span class="sxs-lookup"><span data-stu-id="2b24a-102">FunctionIDMapper Function</span></span>
<span data-ttu-id="2b24a-103">関数の指定された識別子が[、関数の FunctionEnter2](functionenter2-function.md) [、FunctionLeave2](functionleave2-function.md)、および[FunctionTailcall2](functiontailcall2-function.md)コールバックで使用される代替 ID に再マップされる可能性があることをプロファイラーに通知します。</span><span class="sxs-lookup"><span data-stu-id="2b24a-103">Notifies the profiler that the given identifier of a function may be remapped to an alternative ID to be used in the [FunctionEnter2](functionenter2-function.md), [FunctionLeave2](functionleave2-function.md), and [FunctionTailcall2](functiontailcall2-function.md) callbacks for that function.</span></span> <span data-ttu-id="2b24a-104">また `FunctionIDMapper` により、プロファイラーはその関数のコールバックを受信するかどうかを示すことができます。</span><span class="sxs-lookup"><span data-stu-id="2b24a-104">`FunctionIDMapper` also enables the profiler to indicate whether it wants to receive callbacks for that function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2b24a-105">構文</span><span class="sxs-lookup"><span data-stu-id="2b24a-105">Syntax</span></span>  
  
```cpp  
UINT_PTR __stdcall FunctionIDMapper (  
    [in]  FunctionID  funcId,
    [out] BOOL       *pbHookFunction  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2b24a-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="2b24a-106">Parameters</span></span>

- `funcId`

  <span data-ttu-id="2b24a-107">\[in] 再マップする関数識別子。</span><span class="sxs-lookup"><span data-stu-id="2b24a-107">\[in] The function identifier to be remapped.</span></span>

- `pbHookFunction`

  <span data-ttu-id="2b24a-108">\[out] プロファイラーが 、 `true` 、および`FunctionEnter2``FunctionLeave2``FunctionTailcall2`コールバックを受け取る場合に設定する値へのポインター。それ以外の場合は、この`false`値を に設定します。</span><span class="sxs-lookup"><span data-stu-id="2b24a-108">\[out] A pointer to a value that the profiler sets to `true` if it wants to receive `FunctionEnter2`, `FunctionLeave2`, and `FunctionTailcall2` callbacks; otherwise, it sets this value to `false`.</span></span>

## <a name="return-value"></a><span data-ttu-id="2b24a-109">戻り値</span><span class="sxs-lookup"><span data-stu-id="2b24a-109">Return Value</span></span>  
 <span data-ttu-id="2b24a-110">プロファイラーは、実行エンジンが代替関数識別子として使用する値を返します。</span><span class="sxs-lookup"><span data-stu-id="2b24a-110">The profiler returns a value that the execution engine uses as an alternative function identifier.</span></span> <span data-ttu-id="2b24a-111">`false` で `pbHookFunction` を返さない限り、戻り値を null にすることはできません。</span><span class="sxs-lookup"><span data-stu-id="2b24a-111">The return value cannot be null unless `false` is returned in `pbHookFunction`.</span></span> <span data-ttu-id="2b24a-112">それ以外の場合、null 戻り値は、プロセスを停止する可能性を含む、予測できない結果を生成します。</span><span class="sxs-lookup"><span data-stu-id="2b24a-112">Otherwise, a null return value will produce unpredictable results, including possibly halting the process.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2b24a-113">解説</span><span class="sxs-lookup"><span data-stu-id="2b24a-113">Remarks</span></span>  
 <span data-ttu-id="2b24a-114">関数`FunctionIDMapper`はコールバックです。</span><span class="sxs-lookup"><span data-stu-id="2b24a-114">The `FunctionIDMapper` function is a callback.</span></span> <span data-ttu-id="2b24a-115">プロファイラーは、関数 ID を、プロファイラーに役立つ他の識別子に再マップするために実装されます。</span><span class="sxs-lookup"><span data-stu-id="2b24a-115">It is implemented by the profiler to remap a function ID to some other identifier that is more useful for the profiler.</span></span> <span data-ttu-id="2b24a-116">は`FunctionIDMapper`、任意の関数に使用される代替 ID を返します。</span><span class="sxs-lookup"><span data-stu-id="2b24a-116">The `FunctionIDMapper` returns the alternate ID to be used for any given function.</span></span> <span data-ttu-id="2b24a-117">実行エンジンは、従来の関数 ID に加えて、この代替 ID を渡すことによってプロファイラーの要求を受け入れ、 `clientData` `FunctionEnter2`、`FunctionLeave2`および`FunctionTailcall2`フックのパラメーターのプロファイラーに戻して、フックが呼び出される関数を識別します。</span><span class="sxs-lookup"><span data-stu-id="2b24a-117">The execution engine then honors the profiler's request by passing this alternate ID, in addition to the traditional function ID, back to the profiler in the `clientData` parameter of the `FunctionEnter2`, `FunctionLeave2`, and `FunctionTailcall2` hooks, to identify the function for which the hook is being called.</span></span>  
  
 <span data-ttu-id="2b24a-118">関数の実装を指定するには、メソッドを使用します。 [ICorProfilerInfo::SetFunctionIDMapper](icorprofilerinfo-setfunctionidmapper-method.md) `FunctionIDMapper`</span><span class="sxs-lookup"><span data-stu-id="2b24a-118">You can use the [ICorProfilerInfo::SetFunctionIDMapper](icorprofilerinfo-setfunctionidmapper-method.md) method to specify the implementation of the `FunctionIDMapper` function.</span></span> <span data-ttu-id="2b24a-119">メソッドを呼び`ICorProfilerInfo::SetFunctionIDMapper`出すことができるのは 1 回だけであり[、ICorProfilerCallback::初期化](icorprofilercallback-initialize-method.md)コールバックで呼び出す方法をお勧めします。</span><span class="sxs-lookup"><span data-stu-id="2b24a-119">You can call the `ICorProfilerInfo::SetFunctionIDMapper` method only once, and we recommend that you do so in the [ICorProfilerCallback::Initialize](icorprofilercallback-initialize-method.md) callback.</span></span>  
  
 <span data-ttu-id="2b24a-120">既定では[、ICorProfilerInfo::SetEventMask](icorprofilerinfo-seteventmask-method.md)を使用してCOR_PRF_MONITOR_ENTERLEAVEフラグを設定し[、ICorProfilerInfo:::SetEnterLeaveFunctionHooks または ICorProfilerInfo2:::SetEnterLeaveFunctionHooks2](icorprofilerinfo-setenterleavefunctionhooks-method.md)を介してフックを設定するプロファイラー`FunctionEnter2`は`FunctionLeave2`、すべての`FunctionTailcall2`関数のコールバックを受け取る必要があると仮定されます。 [ICorProfilerInfo2::SetEnterLeaveFunctionHooks2](icorprofilerinfo2-setenterleavefunctionhooks2-method.md)</span><span class="sxs-lookup"><span data-stu-id="2b24a-120">By default, it is assumed that a profiler that sets the COR_PRF_MONITOR_ENTERLEAVE flag by using [ICorProfilerInfo::SetEventMask](icorprofilerinfo-seteventmask-method.md), and which sets hooks via [ICorProfilerInfo::SetEnterLeaveFunctionHooks](icorprofilerinfo-setenterleavefunctionhooks-method.md) or [ICorProfilerInfo2::SetEnterLeaveFunctionHooks2](icorprofilerinfo2-setenterleavefunctionhooks2-method.md), should receive the `FunctionEnter2`, `FunctionLeave2`, and `FunctionTailcall2` callbacks for every function.</span></span> <span data-ttu-id="2b24a-121">ただし、プロファイラーは`FunctionIDMapper`、 に設定`pbHookFunction`することで、特定の関数に対してこれらのコールバック`false`を受け取ることを選択的に回避するために実装できます。</span><span class="sxs-lookup"><span data-stu-id="2b24a-121">However, profilers may implement `FunctionIDMapper` to selectively avoid receiving these callbacks for certain functions by setting `pbHookFunction` to `false`.</span></span>  
  
 <span data-ttu-id="2b24a-122">プロファイラーは、プロファイルされたアプリケーションの複数のスレッドが同じメソッド/関数を同時に呼び出している場合に許容する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2b24a-122">Profilers should be tolerant of cases where multiple threads of a profiled application are calling the same method/function simultaneously.</span></span> <span data-ttu-id="2b24a-123">このような場合、プロファイラーは`FunctionIDMapper`同じ`FunctionID`.</span><span class="sxs-lookup"><span data-stu-id="2b24a-123">In such cases, the profiler may receive multiple `FunctionIDMapper` callbacks for the same `FunctionID`.</span></span> <span data-ttu-id="2b24a-124">プロファイラーは、同じ を使用して複数回呼び出された場合、このコールバックから同じ`FunctionID`値を返すようにしてください。</span><span class="sxs-lookup"><span data-stu-id="2b24a-124">The profiler should be certain to return the same values from this callback when it is called multiple times with the same `FunctionID`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2b24a-125">必要条件</span><span class="sxs-lookup"><span data-stu-id="2b24a-125">Requirements</span></span>  
 <span data-ttu-id="2b24a-126">**:**「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2b24a-126">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2b24a-127">**ヘッダー:** コルプロフ.idl</span><span class="sxs-lookup"><span data-stu-id="2b24a-127">**Header:** CorProf.idl</span></span>  
  
 <span data-ttu-id="2b24a-128">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2b24a-128">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2b24a-129">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2b24a-129">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2b24a-130">関連項目</span><span class="sxs-lookup"><span data-stu-id="2b24a-130">See also</span></span>

- [<span data-ttu-id="2b24a-131">SetFunctionIDMapper メソッド</span><span class="sxs-lookup"><span data-stu-id="2b24a-131">SetFunctionIDMapper Method</span></span>](icorprofilerinfo-setfunctionidmapper-method.md)
- [<span data-ttu-id="2b24a-132">FunctionIDMapper2 関数</span><span class="sxs-lookup"><span data-stu-id="2b24a-132">FunctionIDMapper2 Function</span></span>](functionidmapper2-function.md)
- [<span data-ttu-id="2b24a-133">FunctionEnter2 関数</span><span class="sxs-lookup"><span data-stu-id="2b24a-133">FunctionEnter2 Function</span></span>](functionenter2-function.md)
- [<span data-ttu-id="2b24a-134">FunctionLeave2 関数</span><span class="sxs-lookup"><span data-stu-id="2b24a-134">FunctionLeave2 Function</span></span>](functionleave2-function.md)
- [<span data-ttu-id="2b24a-135">FunctionTailcall2 関数</span><span class="sxs-lookup"><span data-stu-id="2b24a-135">FunctionTailcall2 Function</span></span>](functiontailcall2-function.md)
- [<span data-ttu-id="2b24a-136">グローバル静的関数のプロファイル</span><span class="sxs-lookup"><span data-stu-id="2b24a-136">Profiling Global Static Functions</span></span>](profiling-global-static-functions.md)
