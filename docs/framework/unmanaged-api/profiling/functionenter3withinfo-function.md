---
title: FunctionEnter3WithInfo 関数
ms.date: 03/30/2017
api_name:
- FunctionEnter3WithInfo
api_location:
- mscorwks.cll
api_type:
- COM
f1_keywords:
- FunctionEnter3WithInfo
helpviewer_keywords:
- FunctionEnter3WithInfo function [.NET Framework profiling]
ms.assetid: 277c3344-d0cb-431e-beae-eb1eeeba8eea
topic_type:
- apiref
ms.openlocfilehash: 75a9a7174f105d99e9d1c9b220cfc5bf928d46ec
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/29/2020
ms.locfileid: "76866971"
---
# <a name="functionenter3withinfo-function"></a><span data-ttu-id="b751a-102">FunctionEnter3WithInfo 関数</span><span class="sxs-lookup"><span data-stu-id="b751a-102">FunctionEnter3WithInfo Function</span></span>
<span data-ttu-id="b751a-103">コントロールが関数に渡されていることをプロファイラーに通知し、 [ICorProfilerInfo3:: GetFunctionEnter3Info メソッド](icorprofilerinfo3-getfunctionenter3info-method.md)に渡すことができるハンドルを提供して、スタックフレームと関数の引数を取得します。</span><span class="sxs-lookup"><span data-stu-id="b751a-103">Notifies the profiler that control is being passed to a function, and provides a handle that can be passed to the [ICorProfilerInfo3::GetFunctionEnter3Info method](icorprofilerinfo3-getfunctionenter3info-method.md) to retrieve the stack frame and function arguments.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b751a-104">構文</span><span class="sxs-lookup"><span data-stu-id="b751a-104">Syntax</span></span>  
  
```cpp  
void __stdcall FunctionEnter3WithInfo(  
               [in] FunctionIDOrClientID functionIDOrClientID,  
               [in] COR_PRF_ELT_INFO eltInfo);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b751a-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="b751a-105">Parameters</span></span>

- `functionIDOrClientID`

  <span data-ttu-id="b751a-106">\[] には、コントロールが渡される関数の識別子を指定します。</span><span class="sxs-lookup"><span data-stu-id="b751a-106">\[in] The identifier of the function to which control is passed.</span></span>

- `eltInfo`

  <span data-ttu-id="b751a-107">\[in] 特定のスタックフレームに関する情報を表す不透明なハンドル。</span><span class="sxs-lookup"><span data-stu-id="b751a-107">\[in] An opaque handle that represents information about a given stack frame.</span></span> <span data-ttu-id="b751a-108">このハンドルは、渡されるコールバック中にのみ有効です。</span><span class="sxs-lookup"><span data-stu-id="b751a-108">This handle is valid only during the callback to which it is passed.</span></span>

## <a name="remarks"></a><span data-ttu-id="b751a-109">コメント</span><span class="sxs-lookup"><span data-stu-id="b751a-109">Remarks</span></span>  
 <span data-ttu-id="b751a-110">`FunctionEnter3WithInfo` のコールバックメソッドは、関数が呼び出されたことをプロファイラーに通知します。また、プロファイラーは[ICorProfilerInfo3:: GetFunctionEnter3Info メソッド](icorprofilerinfo3-getfunctionenter3info-method.md)を使用して引数値を検査できます。</span><span class="sxs-lookup"><span data-stu-id="b751a-110">The `FunctionEnter3WithInfo` callback method notifies the profiler as functions are called, and enables the profiler to use the [ICorProfilerInfo3::GetFunctionEnter3Info method](icorprofilerinfo3-getfunctionenter3info-method.md) to inspect argument values.</span></span> <span data-ttu-id="b751a-111">引数情報にアクセスするには、`COR_PRF_ENABLE_FUNCTION_ARGS` フラグを設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b751a-111">To access argument information, the `COR_PRF_ENABLE_FUNCTION_ARGS` flag has to be set.</span></span> <span data-ttu-id="b751a-112">プロファイラーは、 [ICorProfilerInfo:: SetEventMask メソッド](icorprofilerinfo-seteventmask-method.md)を使用してイベントフラグを設定し、 [ICorProfilerInfo3:: SetEnterLeaveFunctionHooks3WithInfo メソッド](icorprofilerinfo3-setenterleavefunctionhooks3withinfo-method.md)を使用してこの関数の実装を登録できます。</span><span class="sxs-lookup"><span data-stu-id="b751a-112">The profiler can use the [ICorProfilerInfo::SetEventMask method](icorprofilerinfo-seteventmask-method.md) to set the event flags, and then use the [ICorProfilerInfo3::SetEnterLeaveFunctionHooks3WithInfo method](icorprofilerinfo3-setenterleavefunctionhooks3withinfo-method.md) to register your implementation of this function.</span></span>  
  
 <span data-ttu-id="b751a-113">`FunctionEnter3WithInfo` 関数はコールバックです。実装する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b751a-113">The `FunctionEnter3WithInfo` function is a callback; you must implement it.</span></span> <span data-ttu-id="b751a-114">実装では、`__declspec(naked)` のストレージクラス属性を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b751a-114">The implementation must use the `__declspec(naked)` storage-class attribute.</span></span>  
  
 <span data-ttu-id="b751a-115">この関数を呼び出す前に、実行エンジンはレジスタを保存しません。</span><span class="sxs-lookup"><span data-stu-id="b751a-115">The execution engine does not save any registers before calling this function.</span></span>  
  
- <span data-ttu-id="b751a-116">入力時には、浮動小数点単位 (FPU) に含まれるすべてのレジスタを含め、使用するすべてのレジスタを保存する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b751a-116">On entry, you must save all registers that you use, including those in the floating-point unit (FPU).</span></span>  
  
- <span data-ttu-id="b751a-117">終了時に、呼び出し元によってプッシュされたすべてのパラメーターをポップして、スタックを復元する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b751a-117">On exit, you must restore the stack by popping off all the parameters that were pushed by its caller.</span></span>  
  
 <span data-ttu-id="b751a-118">`FunctionEnter3WithInfo` の実装では、ガベージコレクションが遅延するため、ブロックしないでください。</span><span class="sxs-lookup"><span data-stu-id="b751a-118">The implementation of `FunctionEnter3WithInfo` should not block, because it will delay garbage collection.</span></span> <span data-ttu-id="b751a-119">スタックがガベージコレクションに対応していない可能性があるため、この実装ではガベージコレクションを実行しないようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="b751a-119">The implementation should not attempt a garbage collection, because the stack may not be in a garbage collection-friendly state.</span></span> <span data-ttu-id="b751a-120">ガベージコレクションを実行しようとすると、ランタイムは `FunctionEnter3WithInfo` が返されるまでブロックします。</span><span class="sxs-lookup"><span data-stu-id="b751a-120">If a garbage collection is attempted, the runtime will block until `FunctionEnter3WithInfo` returns.</span></span>  
  
 <span data-ttu-id="b751a-121">`FunctionEnter3WithInfo` 関数は、マネージコードを呼び出さないようにするか、マネージメモリの割り当てを任意の方法で発生させることはできません。</span><span class="sxs-lookup"><span data-stu-id="b751a-121">The `FunctionEnter3WithInfo` function must not call into managed code or cause a managed memory allocation in any way.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b751a-122">要件</span><span class="sxs-lookup"><span data-stu-id="b751a-122">Requirements</span></span>  
 <span data-ttu-id="b751a-123">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b751a-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b751a-124">**ヘッダー:** Corprof.idl</span><span class="sxs-lookup"><span data-stu-id="b751a-124">**Header:** CorProf.idl</span></span>  
  
 <span data-ttu-id="b751a-125">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b751a-125">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b751a-126">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b751a-126">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b751a-127">関連項目</span><span class="sxs-lookup"><span data-stu-id="b751a-127">See also</span></span>

- [<span data-ttu-id="b751a-128">GetFunctionEnter3Info</span><span class="sxs-lookup"><span data-stu-id="b751a-128">GetFunctionEnter3Info</span></span>](icorprofilerinfo3-getfunctionenter3info-method.md)
- [<span data-ttu-id="b751a-129">FunctionEnter3</span><span class="sxs-lookup"><span data-stu-id="b751a-129">FunctionEnter3</span></span>](functionenter3-function.md)
- [<span data-ttu-id="b751a-130">FunctionLeave3</span><span class="sxs-lookup"><span data-stu-id="b751a-130">FunctionLeave3</span></span>](functionleave3-function.md)
- [<span data-ttu-id="b751a-131">グローバル静的関数のプロファイル</span><span class="sxs-lookup"><span data-stu-id="b751a-131">Profiling Global Static Functions</span></span>](profiling-global-static-functions.md)
