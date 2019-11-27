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
ms.openlocfilehash: 86b1c8b3f5bd88b216c59f5cc6846f83f3c094ee
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/23/2019
ms.locfileid: "74440753"
---
# <a name="functionenter3withinfo-function"></a><span data-ttu-id="00dab-102">FunctionEnter3WithInfo 関数</span><span class="sxs-lookup"><span data-stu-id="00dab-102">FunctionEnter3WithInfo Function</span></span>
<span data-ttu-id="00dab-103">コントロールが関数に渡されていることをプロファイラーに通知し、 [ICorProfilerInfo3:: GetFunctionEnter3Info メソッド](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-getfunctionenter3info-method.md)に渡すことができるハンドルを提供して、スタックフレームと関数の引数を取得します。</span><span class="sxs-lookup"><span data-stu-id="00dab-103">Notifies the profiler that control is being passed to a function, and provides a handle that can be passed to the [ICorProfilerInfo3::GetFunctionEnter3Info method](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-getfunctionenter3info-method.md) to retrieve the stack frame and function arguments.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="00dab-104">構文</span><span class="sxs-lookup"><span data-stu-id="00dab-104">Syntax</span></span>  
  
```cpp  
void __stdcall FunctionEnter3WithInfo(  
               [in] FunctionIDOrClientID functionIDOrClientID,  
               [in] COR_PRF_ELT_INFO eltInfo);  
```  
  
## <a name="parameters"></a><span data-ttu-id="00dab-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="00dab-105">Parameters</span></span>  
 `functionIDOrClientID`  
 <span data-ttu-id="00dab-106">からコントロールが渡される関数の識別子。</span><span class="sxs-lookup"><span data-stu-id="00dab-106">[in] The identifier of the function to which control is passed.</span></span>  
  
 `eltInfo`  
 <span data-ttu-id="00dab-107">[in] 特定のスタック フレームに関する情報を表す不透明ハンドル。</span><span class="sxs-lookup"><span data-stu-id="00dab-107">[in] An opaque handle that represents information about a given stack frame.</span></span> <span data-ttu-id="00dab-108">このハンドルは、渡されるコールバック中にのみ有効です。</span><span class="sxs-lookup"><span data-stu-id="00dab-108">This handle is valid only during the callback to which it is passed.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="00dab-109">コメント</span><span class="sxs-lookup"><span data-stu-id="00dab-109">Remarks</span></span>  
 <span data-ttu-id="00dab-110">`FunctionEnter3WithInfo` のコールバックメソッドは、関数が呼び出されたことをプロファイラーに通知します。また、プロファイラーは[ICorProfilerInfo3:: GetFunctionEnter3Info メソッド](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-getfunctionenter3info-method.md)を使用して引数値を検査できます。</span><span class="sxs-lookup"><span data-stu-id="00dab-110">The `FunctionEnter3WithInfo` callback method notifies the profiler as functions are called, and enables the profiler to use the [ICorProfilerInfo3::GetFunctionEnter3Info method](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-getfunctionenter3info-method.md) to inspect argument values.</span></span> <span data-ttu-id="00dab-111">引数情報にアクセスするには、`COR_PRF_ENABLE_FUNCTION_ARGS` フラグを設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="00dab-111">To access argument information, the `COR_PRF_ENABLE_FUNCTION_ARGS` flag has to be set.</span></span> <span data-ttu-id="00dab-112">プロファイラーは、 [ICorProfilerInfo:: SetEventMask メソッド](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-seteventmask-method.md)を使用してイベントフラグを設定し、 [ICorProfilerInfo3:: SetEnterLeaveFunctionHooks3WithInfo メソッド](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-setenterleavefunctionhooks3withinfo-method.md)を使用してこの関数の実装を登録できます。</span><span class="sxs-lookup"><span data-stu-id="00dab-112">The profiler can use the [ICorProfilerInfo::SetEventMask method](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-seteventmask-method.md) to set the event flags, and then use the [ICorProfilerInfo3::SetEnterLeaveFunctionHooks3WithInfo method](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-setenterleavefunctionhooks3withinfo-method.md) to register your implementation of this function.</span></span>  
  
 <span data-ttu-id="00dab-113">`FunctionEnter3WithInfo` 関数はコールバックです。実装する必要があります。</span><span class="sxs-lookup"><span data-stu-id="00dab-113">The `FunctionEnter3WithInfo` function is a callback; you must implement it.</span></span> <span data-ttu-id="00dab-114">実装では、`__declspec(naked)` のストレージクラス属性を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="00dab-114">The implementation must use the `__declspec(naked)` storage-class attribute.</span></span>  
  
 <span data-ttu-id="00dab-115">この関数を呼び出す前に、実行エンジンはレジスタを保存しません。</span><span class="sxs-lookup"><span data-stu-id="00dab-115">The execution engine does not save any registers before calling this function.</span></span>  
  
- <span data-ttu-id="00dab-116">入力時には、浮動小数点単位 (FPU) に含まれるすべてのレジスタを含め、使用するすべてのレジスタを保存する必要があります。</span><span class="sxs-lookup"><span data-stu-id="00dab-116">On entry, you must save all registers that you use, including those in the floating-point unit (FPU).</span></span>  
  
- <span data-ttu-id="00dab-117">終了時に、呼び出し元によってプッシュされたすべてのパラメーターをポップして、スタックを復元する必要があります。</span><span class="sxs-lookup"><span data-stu-id="00dab-117">On exit, you must restore the stack by popping off all the parameters that were pushed by its caller.</span></span>  
  
 <span data-ttu-id="00dab-118">`FunctionEnter3WithInfo` の実装では、ガベージコレクションが遅延するため、ブロックしないでください。</span><span class="sxs-lookup"><span data-stu-id="00dab-118">The implementation of `FunctionEnter3WithInfo` should not block, because it will delay garbage collection.</span></span> <span data-ttu-id="00dab-119">スタックがガベージコレクションに対応していない可能性があるため、この実装ではガベージコレクションを実行しないようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="00dab-119">The implementation should not attempt a garbage collection, because the stack may not be in a garbage collection-friendly state.</span></span> <span data-ttu-id="00dab-120">ガベージコレクションを実行しようとすると、ランタイムは `FunctionEnter3WithInfo` が返されるまでブロックします。</span><span class="sxs-lookup"><span data-stu-id="00dab-120">If a garbage collection is attempted, the runtime will block until `FunctionEnter3WithInfo` returns.</span></span>  
  
 <span data-ttu-id="00dab-121">`FunctionEnter3WithInfo` 関数は、マネージコードを呼び出さないようにするか、マネージメモリの割り当てを任意の方法で発生させることはできません。</span><span class="sxs-lookup"><span data-stu-id="00dab-121">The `FunctionEnter3WithInfo` function must not call into managed code or cause a managed memory allocation in any way.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="00dab-122">要件</span><span class="sxs-lookup"><span data-stu-id="00dab-122">Requirements</span></span>  
 <span data-ttu-id="00dab-123">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="00dab-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="00dab-124">**ヘッダー:** Corprof.idl</span><span class="sxs-lookup"><span data-stu-id="00dab-124">**Header:** CorProf.idl</span></span>  
  
 <span data-ttu-id="00dab-125">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="00dab-125">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="00dab-126">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="00dab-126">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="00dab-127">参照</span><span class="sxs-lookup"><span data-stu-id="00dab-127">See also</span></span>

- [<span data-ttu-id="00dab-128">GetFunctionEnter3Info</span><span class="sxs-lookup"><span data-stu-id="00dab-128">GetFunctionEnter3Info</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-getfunctionenter3info-method.md)
- [<span data-ttu-id="00dab-129">FunctionEnter3</span><span class="sxs-lookup"><span data-stu-id="00dab-129">FunctionEnter3</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionenter3-function.md)
- [<span data-ttu-id="00dab-130">FunctionLeave3</span><span class="sxs-lookup"><span data-stu-id="00dab-130">FunctionLeave3</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionleave3-function.md)
- [<span data-ttu-id="00dab-131">グローバル静的関数のプロファイル</span><span class="sxs-lookup"><span data-stu-id="00dab-131">Profiling Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-global-static-functions.md)
