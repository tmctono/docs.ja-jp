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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 27b2241f7eb0e1ce8b0728a54028f9b4a6112e36
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67781250"
---
# <a name="functionleave3-function"></a><span data-ttu-id="db997-102">FunctionLeave3 関数</span><span class="sxs-lookup"><span data-stu-id="db997-102">FunctionLeave3 Function</span></span>
<span data-ttu-id="db997-103">コントロールが関数から返されることをプロファイラーに通知します。</span><span class="sxs-lookup"><span data-stu-id="db997-103">Notifies the profiler that control is being returned from a function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="db997-104">構文</span><span class="sxs-lookup"><span data-stu-id="db997-104">Syntax</span></span>  
  
```cpp  
void __stdcall FunctionLeave3(FunctionOrRemappedID functionOrRemappedID);  
```  
  
## <a name="parameters"></a><span data-ttu-id="db997-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="db997-105">Parameters</span></span>  
 `functionOrRemappedID`  
 <span data-ttu-id="db997-106">[in]制御が返される関数の識別子。</span><span class="sxs-lookup"><span data-stu-id="db997-106">[in] The identifier of the function from which control is returned.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="db997-107">Remarks</span><span class="sxs-lookup"><span data-stu-id="db997-107">Remarks</span></span>  
 <span data-ttu-id="db997-108">`FunctionLeave3`関数が呼び出される、戻り値の検査をサポートしていませんとしてコールバック関数がプロファイラーに通知します。</span><span class="sxs-lookup"><span data-stu-id="db997-108">The `FunctionLeave3` callback function notifies the profiler as functions are being called, but does not support return value inspection.</span></span> <span data-ttu-id="db997-109">使用して、 [icorprofilerinfo 3::setenterleavefunctionhooks3 メソッド](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-setenterleavefunctionhooks3-method.md)をこの関数の実装を登録します。</span><span class="sxs-lookup"><span data-stu-id="db997-109">Use the [ICorProfilerInfo3::SetEnterLeaveFunctionHooks3 method](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-setenterleavefunctionhooks3-method.md) to register your implementation of this function.</span></span>  
  
 <span data-ttu-id="db997-110">`FunctionLeave3`関数は、コールバックは、これを実装する必要があります。</span><span class="sxs-lookup"><span data-stu-id="db997-110">The `FunctionLeave3` function is a callback; you must implement it.</span></span> <span data-ttu-id="db997-111">実装を使用する必要があります、`__declspec(naked)`ストレージ クラス属性。</span><span class="sxs-lookup"><span data-stu-id="db997-111">The implementation must use the `__declspec(naked)` storage-class attribute.</span></span>  
  
 <span data-ttu-id="db997-112">実行エンジンは、この関数を呼び出す前に、レジスタを保存できません。</span><span class="sxs-lookup"><span data-stu-id="db997-112">The execution engine does not save any registers before calling this function.</span></span>  
  
- <span data-ttu-id="db997-113">項目で、浮動小数点ユニット (FPU) にあるなど、使用するすべてのレジスタを保存する必要があります。</span><span class="sxs-lookup"><span data-stu-id="db997-113">On entry, you must save all registers that you use, including those in the floating-point unit (FPU).</span></span>  
  
- <span data-ttu-id="db997-114">終了時に、その呼び出し元によってプッシュされたすべてのパラメーターをポップしてスタックを復元する必要があります。</span><span class="sxs-lookup"><span data-stu-id="db997-114">On exit, you must restore the stack by popping off all the parameters that were pushed by its caller.</span></span>  
  
 <span data-ttu-id="db997-115">実装`FunctionLeave3`をブロックしないでください、ガベージ コレクションは延期されます。</span><span class="sxs-lookup"><span data-stu-id="db997-115">The implementation of `FunctionLeave3` should not block, because it will delay garbage collection.</span></span> <span data-ttu-id="db997-116">実装は、ガベージ コレクションをしないで、スタックはガベージ コレクションに適した状態ではない可能性が。</span><span class="sxs-lookup"><span data-stu-id="db997-116">The implementation should not attempt a garbage collection, because the stack may not be in a garbage collection-friendly state.</span></span> <span data-ttu-id="db997-117">ランタイムがまでブロックはガベージ コレクションが試行されると、`FunctionLeave3`を返します。</span><span class="sxs-lookup"><span data-stu-id="db997-117">If a garbage collection is attempted, the runtime will block until `FunctionLeave3` returns.</span></span>  
  
 <span data-ttu-id="db997-118">`FunctionLeave3`関数がマネージ コードを呼び出していない、または何らかの方法でマネージ メモリの割り当てが発生する必要があります。</span><span class="sxs-lookup"><span data-stu-id="db997-118">The `FunctionLeave3` function must not call into managed code or cause a managed memory allocation in any way.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="db997-119">必要条件</span><span class="sxs-lookup"><span data-stu-id="db997-119">Requirements</span></span>  
 <span data-ttu-id="db997-120">**プラットフォーム:** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="db997-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="db997-121">**ヘッダー:** CorProf.idl</span><span class="sxs-lookup"><span data-stu-id="db997-121">**Header:** CorProf.idl</span></span>  
  
 <span data-ttu-id="db997-122">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="db997-122">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="db997-123">**.NET Framework のバージョン:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="db997-123">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="db997-124">関連項目</span><span class="sxs-lookup"><span data-stu-id="db997-124">See also</span></span>

- [<span data-ttu-id="db997-125">FunctionEnter3</span><span class="sxs-lookup"><span data-stu-id="db997-125">FunctionEnter3</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionenter3-function.md)
- [<span data-ttu-id="db997-126">FunctionTailcall3</span><span class="sxs-lookup"><span data-stu-id="db997-126">FunctionTailcall3</span></span>](../../../../docs/framework/unmanaged-api/profiling/functiontailcall3-function.md)
- [<span data-ttu-id="db997-127">FunctionEnter3WithInfo</span><span class="sxs-lookup"><span data-stu-id="db997-127">FunctionEnter3WithInfo</span></span>](../../../../docs/framework/unmanaged-api/profiling/functiontailcall3-function.md)
- [<span data-ttu-id="db997-128">FunctionLeave3WithInfo</span><span class="sxs-lookup"><span data-stu-id="db997-128">FunctionLeave3WithInfo</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionleave3withinfo-function.md)
- [<span data-ttu-id="db997-129">FunctionTailcall3WithInfo</span><span class="sxs-lookup"><span data-stu-id="db997-129">FunctionTailcall3WithInfo</span></span>](../../../../docs/framework/unmanaged-api/profiling/functiontailcall3withinfo-function.md)
- [<span data-ttu-id="db997-130">SetEnterLeaveFunctionHooks3</span><span class="sxs-lookup"><span data-stu-id="db997-130">SetEnterLeaveFunctionHooks3</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-setenterleavefunctionhooks3-method.md)
- [<span data-ttu-id="db997-131">SetEnterLeaveFunctionHooks3WithInfo</span><span class="sxs-lookup"><span data-stu-id="db997-131">SetEnterLeaveFunctionHooks3WithInfo</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-setenterleavefunctionhooks3withinfo-method.md)
- [<span data-ttu-id="db997-132">SetFunctionIDMapper</span><span class="sxs-lookup"><span data-stu-id="db997-132">SetFunctionIDMapper</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-setfunctionidmapper-method.md)
- [<span data-ttu-id="db997-133">SetFunctionIDMapper2</span><span class="sxs-lookup"><span data-stu-id="db997-133">SetFunctionIDMapper2</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-setfunctionidmapper2-method.md)
- [<span data-ttu-id="db997-134">グローバル静的関数のプロファイル</span><span class="sxs-lookup"><span data-stu-id="db997-134">Profiling Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-global-static-functions.md)
