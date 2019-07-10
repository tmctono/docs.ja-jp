---
title: FunctionTailcall3WithInfo 関数
ms.date: 03/30/2017
api_name:
- FunctionTailcall3WithInfo
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- FunctionTailcall3WithInfo
helpviewer_keywords:
- FunctionTailcall3WithInfo function [.NET Framework profiling]
ms.assetid: 46380fcc-0198-43ae-a1f5-2d4939425886
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 9cd301ac9d82dd49fc9680d2724714f267ed88ae
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67763289"
---
# <a name="functiontailcall3withinfo-function"></a><span data-ttu-id="92a0f-102">FunctionTailcall3WithInfo 関数</span><span class="sxs-lookup"><span data-stu-id="92a0f-102">FunctionTailcall3WithInfo Function</span></span>
<span data-ttu-id="92a0f-103">現在実行中の関数が別の関数の末尾呼び出しを実行しようとしているプロファイラーに通知しに渡すことができるハンドルを提供します、 [icorprofilerinfo 3::getfunctiontailcall3info メソッド](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-getfunctiontailcall3info-method.md)を取得しますスタック フレーム。</span><span class="sxs-lookup"><span data-stu-id="92a0f-103">Notifies the profiler that the currently executing function is about to perform a tail call to another function, and provides a handle that can be passed to the [ICorProfilerInfo3::GetFunctionTailcall3Info method](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-getfunctiontailcall3info-method.md) to retrieve the stack frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="92a0f-104">構文</span><span class="sxs-lookup"><span data-stu-id="92a0f-104">Syntax</span></span>  
  
```cpp  
void __stdcall FunctionTailcall3WithInfo(  
               [in] FunctionIDOrClientID functionIDOrClientID,  
               [in] COR_PRF_ELT_INFO eltInfo);  
```  
  
## <a name="parameters"></a><span data-ttu-id="92a0f-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="92a0f-105">Parameters</span></span>  
 `functionIDOrClientID`  
 <span data-ttu-id="92a0f-106">[in]Tail の呼び出しを行うには、現在実行中の関数の識別子です。</span><span class="sxs-lookup"><span data-stu-id="92a0f-106">[in] The identifier of the currently executing function that is about to make a tail call.</span></span>  
  
 `eltInfo`  
 <span data-ttu-id="92a0f-107">[in] 特定のスタック フレームに関する情報を表す不透明ハンドル。</span><span class="sxs-lookup"><span data-stu-id="92a0f-107">[in] An opaque handle that represents information about a given stack frame.</span></span> <span data-ttu-id="92a0f-108">このハンドルは、渡されるコールバック中にのみ有効です。</span><span class="sxs-lookup"><span data-stu-id="92a0f-108">This handle is valid only during the callback to which it is passed.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="92a0f-109">Remarks</span><span class="sxs-lookup"><span data-stu-id="92a0f-109">Remarks</span></span>  
 <span data-ttu-id="92a0f-110">`FunctionTailcall3WithInfo`関数が呼び出され、により、プロファイラーを使用するコールバック メソッドをプロファイラーに通知、 [icorprofilerinfo 3::getfunctiontailcall3info メソッド](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-getfunctiontailcall3info-method.md)スタック フレームを検査します。</span><span class="sxs-lookup"><span data-stu-id="92a0f-110">The `FunctionTailcall3WithInfo` callback method notifies the profiler as functions are called, and allows the profiler to use the [ICorProfilerInfo3::GetFunctionTailcall3Info method](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-getfunctiontailcall3info-method.md) to inspect the stack frame.</span></span> <span data-ttu-id="92a0f-111">スタック フレームの情報にアクセスする、`COR_PRF_ENABLE_FRAME_INFO`フラグを設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="92a0f-111">To access stack frame information, the `COR_PRF_ENABLE_FRAME_INFO` flag has to be set.</span></span> <span data-ttu-id="92a0f-112">プロファイラーは、使用、 [icorprofilerinfo::seteventmask メソッド](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-seteventmask-method.md)イベントのフラグを設定し、使用して、 [icorprofilerinfo 3::setenterleavefunctionhooks3withinfo メソッド](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-setenterleavefunctionhooks3withinfo-method.md)を登録する、この関数の実装です。</span><span class="sxs-lookup"><span data-stu-id="92a0f-112">The profiler can use the [ICorProfilerInfo::SetEventMask method](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-seteventmask-method.md) to set the event flags, and then use the [ICorProfilerInfo3::SetEnterLeaveFunctionHooks3WithInfo method](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-setenterleavefunctionhooks3withinfo-method.md) to register your implementation of this function.</span></span>  
  
 <span data-ttu-id="92a0f-113">`FunctionTailcall3WithInfo`関数は、コールバックは、これを実装する必要があります。</span><span class="sxs-lookup"><span data-stu-id="92a0f-113">The `FunctionTailcall3WithInfo` function is a callback; you must implement it.</span></span> <span data-ttu-id="92a0f-114">実装を使用する必要があります、`__declspec(naked)`ストレージ クラス属性。</span><span class="sxs-lookup"><span data-stu-id="92a0f-114">The implementation must use the `__declspec(naked)` storage-class attribute.</span></span>  
  
 <span data-ttu-id="92a0f-115">実行エンジンは、この関数を呼び出す前に、レジスタを保存できません。</span><span class="sxs-lookup"><span data-stu-id="92a0f-115">The execution engine does not save any registers before calling this function.</span></span>  
  
- <span data-ttu-id="92a0f-116">項目で、浮動小数点ユニット (FPU) にあるなど、使用するすべてのレジスタを保存する必要があります。</span><span class="sxs-lookup"><span data-stu-id="92a0f-116">On entry, you must save all registers that you use, including those in the floating-point unit (FPU).</span></span>  
  
- <span data-ttu-id="92a0f-117">終了時に、その呼び出し元によってプッシュされたすべてのパラメーターをポップしてスタックを復元する必要があります。</span><span class="sxs-lookup"><span data-stu-id="92a0f-117">On exit, you must restore the stack by popping off all the parameters that were pushed by its caller.</span></span>  
  
 <span data-ttu-id="92a0f-118">実装`FunctionTailcall3WithInfo`をブロックしないでください、ガベージ コレクションは延期されます。</span><span class="sxs-lookup"><span data-stu-id="92a0f-118">The implementation of `FunctionTailcall3WithInfo` should not block, because it will delay garbage collection.</span></span> <span data-ttu-id="92a0f-119">実装は、ガベージ コレクションをしないで、スタックはガベージ コレクションに適した状態ではない可能性が。</span><span class="sxs-lookup"><span data-stu-id="92a0f-119">The implementation should not attempt a garbage collection, because the stack may not be in a garbage collection-friendly state.</span></span> <span data-ttu-id="92a0f-120">ランタイムがまでブロックはガベージ コレクションが試行されると、`FunctionTailcall3WithInfo`を返します。</span><span class="sxs-lookup"><span data-stu-id="92a0f-120">If a garbage collection is attempted, the runtime will block until `FunctionTailcall3WithInfo` returns.</span></span>  
  
 <span data-ttu-id="92a0f-121">また、FunctionTailcall3WithInfo 関数がマネージ コードを呼び出していない、または任意の方法でマネージ メモリの割り当てが発生する必要があります。</span><span class="sxs-lookup"><span data-stu-id="92a0f-121">Also, the FunctionTailcall3WithInfo function must not call into managed code or cause a managed memory allocation in any way.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="92a0f-122">必要条件</span><span class="sxs-lookup"><span data-stu-id="92a0f-122">Requirements</span></span>  
 <span data-ttu-id="92a0f-123">**プラットフォーム:** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="92a0f-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="92a0f-124">**ヘッダー:** CorProf.idl</span><span class="sxs-lookup"><span data-stu-id="92a0f-124">**Header:** CorProf.idl</span></span>  
  
 <span data-ttu-id="92a0f-125">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="92a0f-125">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="92a0f-126">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="92a0f-126">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="92a0f-127">関連項目</span><span class="sxs-lookup"><span data-stu-id="92a0f-127">See also</span></span>

- [<span data-ttu-id="92a0f-128">FunctionEnter3</span><span class="sxs-lookup"><span data-stu-id="92a0f-128">FunctionEnter3</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionenter3-function.md)
- [<span data-ttu-id="92a0f-129">FunctionLeave3</span><span class="sxs-lookup"><span data-stu-id="92a0f-129">FunctionLeave3</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionleave3-function.md)
- [<span data-ttu-id="92a0f-130">FunctionTailcall3</span><span class="sxs-lookup"><span data-stu-id="92a0f-130">FunctionTailcall3</span></span>](../../../../docs/framework/unmanaged-api/profiling/functiontailcall3-function.md)
- [<span data-ttu-id="92a0f-131">FunctionEnter3WithInfo</span><span class="sxs-lookup"><span data-stu-id="92a0f-131">FunctionEnter3WithInfo</span></span>](../../../../docs/framework/unmanaged-api/profiling/functiontailcall3-function.md)
- [<span data-ttu-id="92a0f-132">FunctionLeave3WithInfo</span><span class="sxs-lookup"><span data-stu-id="92a0f-132">FunctionLeave3WithInfo</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionleave3withinfo-function.md)
- [<span data-ttu-id="92a0f-133">SetEnterLeaveFunctionHooks3</span><span class="sxs-lookup"><span data-stu-id="92a0f-133">SetEnterLeaveFunctionHooks3</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-setenterleavefunctionhooks3-method.md)
- [<span data-ttu-id="92a0f-134">SetEnterLeaveFunctionHooks3WithInfo</span><span class="sxs-lookup"><span data-stu-id="92a0f-134">SetEnterLeaveFunctionHooks3WithInfo</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-setenterleavefunctionhooks3withinfo-method.md)
- [<span data-ttu-id="92a0f-135">SetFunctionIDMapper</span><span class="sxs-lookup"><span data-stu-id="92a0f-135">SetFunctionIDMapper</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-setfunctionidmapper-method.md)
- [<span data-ttu-id="92a0f-136">SetFunctionIDMapper2</span><span class="sxs-lookup"><span data-stu-id="92a0f-136">SetFunctionIDMapper2</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-setfunctionidmapper2-method.md)
- [<span data-ttu-id="92a0f-137">グローバル静的関数のプロファイル</span><span class="sxs-lookup"><span data-stu-id="92a0f-137">Profiling Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-global-static-functions.md)
