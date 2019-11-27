---
title: ICorProfilerInfo3::SetFunctionIDMapper2 メソッド
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo3.SetFunctionIDMapper2 Method
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo3::SetFunctionIDMapper2
helpviewer_keywords:
- SetFunctionIDMapper2 method [.NET Framework profiling]
- ICorProfilerInfo3::SetFunctionIDMapper2 method [.NET Framework profiling]
ms.assetid: 8cdb1188-952a-4ba8-9f05-bfebc18cdd29
topic_type:
- apiref
ms.openlocfilehash: 2c06b9b7933245dc0e69e430a3fe4a515f8a50f1
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/23/2019
ms.locfileid: "74449581"
---
# <a name="icorprofilerinfo3setfunctionidmapper2-method"></a><span data-ttu-id="4dcb2-102">ICorProfilerInfo3::SetFunctionIDMapper2 メソッド</span><span class="sxs-lookup"><span data-stu-id="4dcb2-102">ICorProfilerInfo3::SetFunctionIDMapper2 Method</span></span>
<span data-ttu-id="4dcb2-103">`FunctionID` 値を代替値に対応付けるために呼び出すプロファイラー実装関数を指定します。代替値は、プロファイラーの関数の開始フックと終了フックに渡されます。</span><span class="sxs-lookup"><span data-stu-id="4dcb2-103">Specifies the profiler-implemented function that will be called to map `FunctionID` values to alternative values, which are passed to the profiler's function entry/exit hooks.</span></span> <span data-ttu-id="4dcb2-104">このメソッドは、追加のデータパラメーターを使用して[ICorProfilerInfo:: SetFunctionIDMapper](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-setfunctionidmapper-method.md)メソッドを拡張します。これは、プロファイラーがランタイムを明確に区別するために使用する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="4dcb2-104">This method extends the [ICorProfilerInfo::SetFunctionIDMapper](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-setfunctionidmapper-method.md) method with an additional data parameter, which profilers may use to disambiguate among runtimes.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4dcb2-105">構文</span><span class="sxs-lookup"><span data-stu-id="4dcb2-105">Syntax</span></span>  
  
```cpp  
HRESULT SetFunctionIDMapper2(  
       [in] FunctionIDMapper2 *pFunc,  
       [in] void *clientData);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4dcb2-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="4dcb2-106">Parameters</span></span>  
 `pFunc`  
 <span data-ttu-id="4dcb2-107">から`FunctionID` 値を代替値にマップするために呼び出される[FunctionIDMapper2](../../../../docs/framework/unmanaged-api/profiling/functionidmapper2-function.md)実装へのポインター。</span><span class="sxs-lookup"><span data-stu-id="4dcb2-107">[in] A pointer to a [FunctionIDMapper2](../../../../docs/framework/unmanaged-api/profiling/functionidmapper2-function.md) implementation that will be called to map the `FunctionID` values to their alternative values.</span></span>  
  
 `clientData`  
 <span data-ttu-id="4dcb2-108">から現在のランタイムによって行われたすべての[FunctionIDMapper2](../../../../docs/framework/unmanaged-api/profiling/functionidmapper2-function.md)関数呼び出しに渡されるポインター。</span><span class="sxs-lookup"><span data-stu-id="4dcb2-108">[in] A pointer that is passed to every [FunctionIDMapper2](../../../../docs/framework/unmanaged-api/profiling/functionidmapper2-function.md) function call made by the current runtime.</span></span> <span data-ttu-id="4dcb2-109">プロファイラーはこの情報を使用して、ランタイム間を明確に区別できます。</span><span class="sxs-lookup"><span data-stu-id="4dcb2-109">The profiler can use this information to disambiguate among runtimes.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="4dcb2-110">戻り値</span><span class="sxs-lookup"><span data-stu-id="4dcb2-110">Return Value</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4dcb2-111">コメント</span><span class="sxs-lookup"><span data-stu-id="4dcb2-111">Remarks</span></span>  
 <span data-ttu-id="4dcb2-112">FunctionID 値の代替手段は、 [FunctionLeave3WithInfo](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-setenterleavefunctionhooks3-method.md)または[FunctionTailcall3WithInfo](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-setenterleavefunctionhooks3withinfo-method.md)メソッドによって指定されたプロファイラーの関数の開始/終了フック ([FunctionEnter3](../../../../docs/framework/unmanaged-api/profiling/functionenter3-function.md)、 [FunctionLeave3](../../../../docs/framework/unmanaged-api/profiling/functionleave3-function.md)、 [FunctionTailcall3](../../../../docs/framework/unmanaged-api/profiling/functiontailcall3-function.md)、 [FunctionEnter3WithInfo](../../../../docs/framework/unmanaged-api/profiling/functionenter3withinfo-function.md)、 [SetEnterLeaveFunctionHooks3](../../../../docs/framework/unmanaged-api/profiling/functionleave3withinfo-function.md)、および[SetEnterLeaveFunctionHooks3WithInfo](../../../../docs/framework/unmanaged-api/profiling/functiontailcall3withinfo-function.md)) に渡されます。</span><span class="sxs-lookup"><span data-stu-id="4dcb2-112">The alternatives for the FunctionID values will be passed to the profiler's function entry/exit hooks ([FunctionEnter3](../../../../docs/framework/unmanaged-api/profiling/functionenter3-function.md), [FunctionLeave3](../../../../docs/framework/unmanaged-api/profiling/functionleave3-function.md), and [FunctionTailcall3](../../../../docs/framework/unmanaged-api/profiling/functiontailcall3-function.md); or [FunctionEnter3WithInfo](../../../../docs/framework/unmanaged-api/profiling/functionenter3withinfo-function.md), [FunctionLeave3WithInfo](../../../../docs/framework/unmanaged-api/profiling/functionleave3withinfo-function.md), and [FunctionTailcall3WithInfo](../../../../docs/framework/unmanaged-api/profiling/functiontailcall3withinfo-function.md)) that are specified by the [SetEnterLeaveFunctionHooks3](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-setenterleavefunctionhooks3-method.md) or [SetEnterLeaveFunctionHooks3WithInfo](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-setenterleavefunctionhooks3withinfo-method.md) method.</span></span>  
  
 <span data-ttu-id="4dcb2-113">`FunctionIDMapper2` メソッドは、1回だけ設定できます。[ICorProfilerCallback:: Initialize](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-initialize-method.md)コールバックで設定することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="4dcb2-113">The `FunctionIDMapper2` method can be set only once; we recommend that you set it in the [ICorProfilerCallback::Initialize](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-initialize-method.md) callback.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4dcb2-114">要件</span><span class="sxs-lookup"><span data-stu-id="4dcb2-114">Requirements</span></span>  
 <span data-ttu-id="4dcb2-115">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4dcb2-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4dcb2-116">**ヘッダー** : CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="4dcb2-116">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="4dcb2-117">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4dcb2-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4dcb2-118">**.NET Framework のバージョン:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4dcb2-118">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4dcb2-119">参照</span><span class="sxs-lookup"><span data-stu-id="4dcb2-119">See also</span></span>

- [<span data-ttu-id="4dcb2-120">SetFunctionIDMapper</span><span class="sxs-lookup"><span data-stu-id="4dcb2-120">SetFunctionIDMapper</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-setfunctionidmapper-method.md)
- [<span data-ttu-id="4dcb2-121">ICorProfilerInfo3 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="4dcb2-121">ICorProfilerInfo3 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-interface.md)
- [<span data-ttu-id="4dcb2-122">プロファイリングのインターフェイス</span><span class="sxs-lookup"><span data-stu-id="4dcb2-122">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
- [<span data-ttu-id="4dcb2-123">プロファイル</span><span class="sxs-lookup"><span data-stu-id="4dcb2-123">Profiling</span></span>](../../../../docs/framework/unmanaged-api/profiling/index.md)
