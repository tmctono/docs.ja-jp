---
title: FunctionTailcall3 関数
ms.date: 03/30/2017
api_name:
- FunctionTailcall3
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- FunctionTailcall3
helpviewer_keywords:
- FunctionTailcall3 function [.NET Framework profiling]
ms.assetid: 1e48243f-5de6-4bd6-a1d0-e1d248bca4b8
topic_type:
- apiref
ms.openlocfilehash: 8d7c226d26d677a8b10df29e0343b71682c46699
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/23/2019
ms.locfileid: "74427362"
---
# <a name="functiontailcall3-function"></a><span data-ttu-id="e629e-102">FunctionTailcall3 関数</span><span class="sxs-lookup"><span data-stu-id="e629e-102">FunctionTailcall3 Function</span></span>
<span data-ttu-id="e629e-103">現在実行中の関数が別の関数の末尾呼び出しを実行しようとしていることをプロファイラーに通知します。</span><span class="sxs-lookup"><span data-stu-id="e629e-103">Notifies the profiler that the currently executing function is about to perform a tail call to another function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e629e-104">構文</span><span class="sxs-lookup"><span data-stu-id="e629e-104">Syntax</span></span>  
  
```cpp  
void __stdcall FunctionTailcall3 (FunctionOrRemappedID functionOrRemappedID);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e629e-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="e629e-105">Parameters</span></span>  
 `functionOrRemappedID`  
 <span data-ttu-id="e629e-106">から末尾呼び出しを実行しようとしている現在実行中の関数の識別子。</span><span class="sxs-lookup"><span data-stu-id="e629e-106">[in] The identifier of the currently executing function that is about to make a tail call.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e629e-107">コメント</span><span class="sxs-lookup"><span data-stu-id="e629e-107">Remarks</span></span>  
 <span data-ttu-id="e629e-108">`FunctionTailcall3` コールバック関数は、関数が呼び出されていることをプロファイラーに通知します。</span><span class="sxs-lookup"><span data-stu-id="e629e-108">The `FunctionTailcall3` callback function notifies the profiler as functions are being called.</span></span> <span data-ttu-id="e629e-109">[ICorProfilerInfo3:: SetEnterLeaveFunctionHooks3 メソッド](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-setenterleavefunctionhooks3-method.md)を使用して、この関数の実装を登録します。</span><span class="sxs-lookup"><span data-stu-id="e629e-109">Use the [ICorProfilerInfo3::SetEnterLeaveFunctionHooks3 method](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-setenterleavefunctionhooks3-method.md) to register your implementation of this function.</span></span>  
  
 <span data-ttu-id="e629e-110">`FunctionTailcall3` 関数はコールバックです。実装する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e629e-110">The `FunctionTailcall3` function is a callback; you must implement it.</span></span> <span data-ttu-id="e629e-111">実装では、`__declspec(naked)` のストレージクラス属性を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e629e-111">The implementation must use the `__declspec(naked)` storage-class attribute.</span></span>  
  
 <span data-ttu-id="e629e-112">この関数を呼び出す前に、実行エンジンはレジスタを保存しません。</span><span class="sxs-lookup"><span data-stu-id="e629e-112">The execution engine does not save any registers before calling this function.</span></span>  
  
- <span data-ttu-id="e629e-113">入力時には、浮動小数点単位 (FPU) に含まれるすべてのレジスタを含め、使用するすべてのレジスタを保存する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e629e-113">On entry, you must save all registers that you use, including those in the floating-point unit (FPU).</span></span>  
  
- <span data-ttu-id="e629e-114">終了時に、呼び出し元によってプッシュされたすべてのパラメーターをポップして、スタックを復元する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e629e-114">On exit, you must restore the stack by popping off all the parameters that were pushed by its caller.</span></span>  
  
 <span data-ttu-id="e629e-115">`FunctionTailcall3` の実装では、ガベージコレクションが遅延するため、ブロックしないでください。</span><span class="sxs-lookup"><span data-stu-id="e629e-115">The implementation of `FunctionTailcall3` should not block, because it will delay garbage collection.</span></span> <span data-ttu-id="e629e-116">スタックがガベージコレクションに対応していない可能性があるため、この実装ではガベージコレクションを実行しないようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="e629e-116">The implementation should not attempt a garbage collection, because the stack may not be in a garbage collection-friendly state.</span></span> <span data-ttu-id="e629e-117">ガベージコレクションを実行しようとすると、ランタイムは `FunctionTailcall3` が返されるまでブロックします。</span><span class="sxs-lookup"><span data-stu-id="e629e-117">If a garbage collection is attempted, the runtime will block until `FunctionTailcall3` returns.</span></span>  
  
 <span data-ttu-id="e629e-118">`FunctionTailcall3` 関数は、マネージコードを呼び出さないようにするか、マネージメモリの割り当てを任意の方法で発生させることはできません。</span><span class="sxs-lookup"><span data-stu-id="e629e-118">The `FunctionTailcall3` function must not call into managed code or cause a managed memory allocation in any way.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e629e-119">要件</span><span class="sxs-lookup"><span data-stu-id="e629e-119">Requirements</span></span>  
 <span data-ttu-id="e629e-120">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e629e-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e629e-121">**ヘッダー:** Corprof.idl</span><span class="sxs-lookup"><span data-stu-id="e629e-121">**Header:** CorProf.idl</span></span>  
  
 <span data-ttu-id="e629e-122">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e629e-122">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e629e-123">**.NET Framework のバージョン:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e629e-123">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e629e-124">参照</span><span class="sxs-lookup"><span data-stu-id="e629e-124">See also</span></span>

- [<span data-ttu-id="e629e-125">FunctionEnter3</span><span class="sxs-lookup"><span data-stu-id="e629e-125">FunctionEnter3</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionenter3-function.md)
- [<span data-ttu-id="e629e-126">FunctionLeave3</span><span class="sxs-lookup"><span data-stu-id="e629e-126">FunctionLeave3</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionleave3-function.md)
- [<span data-ttu-id="e629e-127">FunctionEnter3WithInfo</span><span class="sxs-lookup"><span data-stu-id="e629e-127">FunctionEnter3WithInfo</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionenter3withinfo-function.md)
- [<span data-ttu-id="e629e-128">FunctionLeave3WithInfo</span><span class="sxs-lookup"><span data-stu-id="e629e-128">FunctionLeave3WithInfo</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionleave3withinfo-function.md)
- [<span data-ttu-id="e629e-129">FunctionTailcall3WithInfo 関数</span><span class="sxs-lookup"><span data-stu-id="e629e-129">FunctionTailcall3WithInfo Function</span></span>](../../../../docs/framework/unmanaged-api/profiling/functiontailcall3withinfo-function.md)
- [<span data-ttu-id="e629e-130">SetEnterLeaveFunctionHooks3</span><span class="sxs-lookup"><span data-stu-id="e629e-130">SetEnterLeaveFunctionHooks3</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-setenterleavefunctionhooks3-method.md)
- [<span data-ttu-id="e629e-131">SetEnterLeaveFunctionHooks3WithInfo</span><span class="sxs-lookup"><span data-stu-id="e629e-131">SetEnterLeaveFunctionHooks3WithInfo</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-setenterleavefunctionhooks3withinfo-method.md)
- [<span data-ttu-id="e629e-132">SetFunctionIDMapper</span><span class="sxs-lookup"><span data-stu-id="e629e-132">SetFunctionIDMapper</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-setfunctionidmapper-method.md)
- [<span data-ttu-id="e629e-133">SetFunctionIDMapper2</span><span class="sxs-lookup"><span data-stu-id="e629e-133">SetFunctionIDMapper2</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-setfunctionidmapper2-method.md)
- [<span data-ttu-id="e629e-134">グローバル静的関数のプロファイル</span><span class="sxs-lookup"><span data-stu-id="e629e-134">Profiling Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-global-static-functions.md)
