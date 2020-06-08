---
title: FunctionLeave3 関数
ms.date: 03/30/2017
api_name:
- FunctionLeave3
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- FunctionLeave3
helpviewer_keywords:
- FunctionLeave3 function [.NET Framework profiling]
ms.assetid: 5d798088-7992-48a0-ae55-d2a7ee31913f
topic_type:
- apiref
ms.openlocfilehash: 456d9a0e8236948ac69ed069495b1999ebf7e80a
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/08/2020
ms.locfileid: "84500612"
---
# <a name="functionleave3-function"></a><span data-ttu-id="60a49-102">FunctionLeave3 関数</span><span class="sxs-lookup"><span data-stu-id="60a49-102">FunctionLeave3 Function</span></span>
<span data-ttu-id="60a49-103">関数から制御が返されていることをプロファイラーに通知します。</span><span class="sxs-lookup"><span data-stu-id="60a49-103">Notifies the profiler that control is being returned from a function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="60a49-104">構文</span><span class="sxs-lookup"><span data-stu-id="60a49-104">Syntax</span></span>  
  
```cpp  
void __stdcall FunctionLeave3(FunctionOrRemappedID functionOrRemappedID);  
```  
  
## <a name="parameters"></a><span data-ttu-id="60a49-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="60a49-105">Parameters</span></span>  

- `functionOrRemappedID`

  <span data-ttu-id="60a49-106">\[in] コントロールが返される関数の識別子。</span><span class="sxs-lookup"><span data-stu-id="60a49-106">\[in] The identifier of the function from which control is returned.</span></span>
  
## <a name="remarks"></a><span data-ttu-id="60a49-107">解説</span><span class="sxs-lookup"><span data-stu-id="60a49-107">Remarks</span></span>  
 <span data-ttu-id="60a49-108">`FunctionLeave3`コールバック関数は、関数が呼び出されていることをプロファイラーに通知しますが、戻り値の検査はサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="60a49-108">The `FunctionLeave3` callback function notifies the profiler as functions are being called, but does not support return value inspection.</span></span> <span data-ttu-id="60a49-109">[ICorProfilerInfo3:: SetEnterLeaveFunctionHooks3 メソッド](icorprofilerinfo3-setenterleavefunctionhooks3-method.md)を使用して、この関数の実装を登録します。</span><span class="sxs-lookup"><span data-stu-id="60a49-109">Use the [ICorProfilerInfo3::SetEnterLeaveFunctionHooks3 method](icorprofilerinfo3-setenterleavefunctionhooks3-method.md) to register your implementation of this function.</span></span>  
  
 <span data-ttu-id="60a49-110">`FunctionLeave3`関数はコールバックであるため、実装する必要があります。</span><span class="sxs-lookup"><span data-stu-id="60a49-110">The `FunctionLeave3` function is a callback; you must implement it.</span></span> <span data-ttu-id="60a49-111">実装では、ストレージクラス属性を使用する必要があり `__declspec(naked)` ます。</span><span class="sxs-lookup"><span data-stu-id="60a49-111">The implementation must use the `__declspec(naked)` storage-class attribute.</span></span>  
  
 <span data-ttu-id="60a49-112">この関数を呼び出す前に、実行エンジンはレジスタを保存しません。</span><span class="sxs-lookup"><span data-stu-id="60a49-112">The execution engine does not save any registers before calling this function.</span></span>  
  
- <span data-ttu-id="60a49-113">入力時には、浮動小数点単位 (FPU) に含まれるすべてのレジスタを含め、使用するすべてのレジスタを保存する必要があります。</span><span class="sxs-lookup"><span data-stu-id="60a49-113">On entry, you must save all registers that you use, including those in the floating-point unit (FPU).</span></span>  
  
- <span data-ttu-id="60a49-114">終了時に、呼び出し元によってプッシュされたすべてのパラメーターをポップして、スタックを復元する必要があります。</span><span class="sxs-lookup"><span data-stu-id="60a49-114">On exit, you must restore the stack by popping off all the parameters that were pushed by its caller.</span></span>  
  
 <span data-ttu-id="60a49-115">の実装では `FunctionLeave3` 、ガベージコレクションが遅延するため、ブロックしないでください。</span><span class="sxs-lookup"><span data-stu-id="60a49-115">The implementation of `FunctionLeave3` should not block, because it will delay garbage collection.</span></span> <span data-ttu-id="60a49-116">スタックがガベージコレクションに対応していない可能性があるため、この実装ではガベージコレクションを実行しないようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="60a49-116">The implementation should not attempt a garbage collection, because the stack may not be in a garbage collection-friendly state.</span></span> <span data-ttu-id="60a49-117">ガベージコレクションが試行された場合、ランタイムはが返されるまでブロックし `FunctionLeave3` ます。</span><span class="sxs-lookup"><span data-stu-id="60a49-117">If a garbage collection is attempted, the runtime will block until `FunctionLeave3` returns.</span></span>  
  
 <span data-ttu-id="60a49-118">関数は、 `FunctionLeave3` マネージコードを呼び出さないようにするか、マネージメモリの割り当てを任意の方法で発生させることはできません。</span><span class="sxs-lookup"><span data-stu-id="60a49-118">The `FunctionLeave3` function must not call into managed code or cause a managed memory allocation in any way.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="60a49-119">要件</span><span class="sxs-lookup"><span data-stu-id="60a49-119">Requirements</span></span>  
 <span data-ttu-id="60a49-120">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="60a49-120">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="60a49-121">**ヘッダー:** Corprof.idl</span><span class="sxs-lookup"><span data-stu-id="60a49-121">**Header:** CorProf.idl</span></span>  
  
 <span data-ttu-id="60a49-122">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="60a49-122">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="60a49-123">**.NET Framework のバージョン:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="60a49-123">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="60a49-124">関連項目</span><span class="sxs-lookup"><span data-stu-id="60a49-124">See also</span></span>

- [<span data-ttu-id="60a49-125">FunctionEnter3</span><span class="sxs-lookup"><span data-stu-id="60a49-125">FunctionEnter3</span></span>](functionenter3-function.md)
- [<span data-ttu-id="60a49-126">FunctionTailcall3</span><span class="sxs-lookup"><span data-stu-id="60a49-126">FunctionTailcall3</span></span>](functiontailcall3-function.md)
- [<span data-ttu-id="60a49-127">FunctionEnter3WithInfo</span><span class="sxs-lookup"><span data-stu-id="60a49-127">FunctionEnter3WithInfo</span></span>](functiontailcall3-function.md)
- [<span data-ttu-id="60a49-128">FunctionLeave3WithInfo</span><span class="sxs-lookup"><span data-stu-id="60a49-128">FunctionLeave3WithInfo</span></span>](functionleave3withinfo-function.md)
- [<span data-ttu-id="60a49-129">FunctionTailcall3WithInfo</span><span class="sxs-lookup"><span data-stu-id="60a49-129">FunctionTailcall3WithInfo</span></span>](functiontailcall3withinfo-function.md)
- [<span data-ttu-id="60a49-130">SetEnterLeaveFunctionHooks3</span><span class="sxs-lookup"><span data-stu-id="60a49-130">SetEnterLeaveFunctionHooks3</span></span>](icorprofilerinfo3-setenterleavefunctionhooks3-method.md)
- [<span data-ttu-id="60a49-131">SetEnterLeaveFunctionHooks3WithInfo</span><span class="sxs-lookup"><span data-stu-id="60a49-131">SetEnterLeaveFunctionHooks3WithInfo</span></span>](icorprofilerinfo3-setenterleavefunctionhooks3withinfo-method.md)
- [<span data-ttu-id="60a49-132">SetFunctionIDMapper</span><span class="sxs-lookup"><span data-stu-id="60a49-132">SetFunctionIDMapper</span></span>](icorprofilerinfo-setfunctionidmapper-method.md)
- [<span data-ttu-id="60a49-133">SetFunctionIDMapper2</span><span class="sxs-lookup"><span data-stu-id="60a49-133">SetFunctionIDMapper2</span></span>](icorprofilerinfo3-setfunctionidmapper2-method.md)
- [<span data-ttu-id="60a49-134">グローバル静的関数のプロファイル</span><span class="sxs-lookup"><span data-stu-id="60a49-134">Profiling Global Static Functions</span></span>](profiling-global-static-functions.md)
