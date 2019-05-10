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
ms.openlocfilehash: 9dce2f961a01b70c0cba50894d670a586a40b605
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/28/2019
ms.locfileid: "64586835"
---
# <a name="functionleave3-function"></a><span data-ttu-id="d0bfc-102">FunctionLeave3 関数</span><span class="sxs-lookup"><span data-stu-id="d0bfc-102">FunctionLeave3 Function</span></span>
<span data-ttu-id="d0bfc-103">コントロールが関数から返されることをプロファイラーに通知します。</span><span class="sxs-lookup"><span data-stu-id="d0bfc-103">Notifies the profiler that control is being returned from a function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d0bfc-104">構文</span><span class="sxs-lookup"><span data-stu-id="d0bfc-104">Syntax</span></span>  
  
```  
void __stdcall FunctionLeave3(FunctionOrRemappedID functionOrRemappedID);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d0bfc-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="d0bfc-105">Parameters</span></span>  
 `functionOrRemappedID`  
 <span data-ttu-id="d0bfc-106">[in]制御が返される関数の識別子。</span><span class="sxs-lookup"><span data-stu-id="d0bfc-106">[in] The identifier of the function from which control is returned.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d0bfc-107">Remarks</span><span class="sxs-lookup"><span data-stu-id="d0bfc-107">Remarks</span></span>  
 <span data-ttu-id="d0bfc-108">`FunctionLeave3`関数が呼び出される、戻り値の検査をサポートしていませんとしてコールバック関数がプロファイラーに通知します。</span><span class="sxs-lookup"><span data-stu-id="d0bfc-108">The `FunctionLeave3` callback function notifies the profiler as functions are being called, but does not support return value inspection.</span></span> <span data-ttu-id="d0bfc-109">使用して、 [icorprofilerinfo 3::setenterleavefunctionhooks3 メソッド](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-setenterleavefunctionhooks3-method.md)をこの関数の実装を登録します。</span><span class="sxs-lookup"><span data-stu-id="d0bfc-109">Use the [ICorProfilerInfo3::SetEnterLeaveFunctionHooks3 method](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-setenterleavefunctionhooks3-method.md) to register your implementation of this function.</span></span>  
  
 <span data-ttu-id="d0bfc-110">`FunctionLeave3`関数は、コールバックは、これを実装する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d0bfc-110">The `FunctionLeave3` function is a callback; you must implement it.</span></span> <span data-ttu-id="d0bfc-111">実装を使用する必要があります、`__declspec(naked)`ストレージ クラス属性。</span><span class="sxs-lookup"><span data-stu-id="d0bfc-111">The implementation must use the `__declspec(naked)` storage-class attribute.</span></span>  
  
 <span data-ttu-id="d0bfc-112">実行エンジンは、この関数を呼び出す前に、レジスタを保存できません。</span><span class="sxs-lookup"><span data-stu-id="d0bfc-112">The execution engine does not save any registers before calling this function.</span></span>  
  
- <span data-ttu-id="d0bfc-113">項目で、浮動小数点ユニット (FPU) にあるなど、使用するすべてのレジスタを保存する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d0bfc-113">On entry, you must save all registers that you use, including those in the floating-point unit (FPU).</span></span>  
  
- <span data-ttu-id="d0bfc-114">終了時に、その呼び出し元によってプッシュされたすべてのパラメーターをポップしてスタックを復元する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d0bfc-114">On exit, you must restore the stack by popping off all the parameters that were pushed by its caller.</span></span>  
  
 <span data-ttu-id="d0bfc-115">実装`FunctionLeave3`をブロックしないでください、ガベージ コレクションは延期されます。</span><span class="sxs-lookup"><span data-stu-id="d0bfc-115">The implementation of `FunctionLeave3` should not block, because it will delay garbage collection.</span></span> <span data-ttu-id="d0bfc-116">実装は、ガベージ コレクションをしないで、スタックはガベージ コレクションに適した状態ではない可能性が。</span><span class="sxs-lookup"><span data-stu-id="d0bfc-116">The implementation should not attempt a garbage collection, because the stack may not be in a garbage collection-friendly state.</span></span> <span data-ttu-id="d0bfc-117">ランタイムがまでブロックはガベージ コレクションが試行されると、`FunctionLeave3`を返します。</span><span class="sxs-lookup"><span data-stu-id="d0bfc-117">If a garbage collection is attempted, the runtime will block until `FunctionLeave3` returns.</span></span>  
  
 <span data-ttu-id="d0bfc-118">`FunctionLeave3`関数がマネージ コードを呼び出していない、または何らかの方法でマネージ メモリの割り当てが発生する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d0bfc-118">The `FunctionLeave3` function must not call into managed code or cause a managed memory allocation in any way.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d0bfc-119">必要条件</span><span class="sxs-lookup"><span data-stu-id="d0bfc-119">Requirements</span></span>  
 <span data-ttu-id="d0bfc-120">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="d0bfc-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d0bfc-121">**ヘッダー:** CorProf.idl</span><span class="sxs-lookup"><span data-stu-id="d0bfc-121">**Header:** CorProf.idl</span></span>  
  
 <span data-ttu-id="d0bfc-122">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d0bfc-122">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d0bfc-123">**.NET Framework のバージョン:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d0bfc-123">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d0bfc-124">関連項目</span><span class="sxs-lookup"><span data-stu-id="d0bfc-124">See also</span></span>

- [<span data-ttu-id="d0bfc-125">FunctionEnter3</span><span class="sxs-lookup"><span data-stu-id="d0bfc-125">FunctionEnter3</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionenter3-function.md)
- [<span data-ttu-id="d0bfc-126">FunctionTailcall3</span><span class="sxs-lookup"><span data-stu-id="d0bfc-126">FunctionTailcall3</span></span>](../../../../docs/framework/unmanaged-api/profiling/functiontailcall3-function.md)
- [<span data-ttu-id="d0bfc-127">FunctionEnter3WithInfo</span><span class="sxs-lookup"><span data-stu-id="d0bfc-127">FunctionEnter3WithInfo</span></span>](../../../../docs/framework/unmanaged-api/profiling/functiontailcall3-function.md)
- [<span data-ttu-id="d0bfc-128">FunctionLeave3WithInfo</span><span class="sxs-lookup"><span data-stu-id="d0bfc-128">FunctionLeave3WithInfo</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionleave3withinfo-function.md)
- [<span data-ttu-id="d0bfc-129">FunctionTailcall3WithInfo</span><span class="sxs-lookup"><span data-stu-id="d0bfc-129">FunctionTailcall3WithInfo</span></span>](../../../../docs/framework/unmanaged-api/profiling/functiontailcall3withinfo-function.md)
- [<span data-ttu-id="d0bfc-130">SetEnterLeaveFunctionHooks3</span><span class="sxs-lookup"><span data-stu-id="d0bfc-130">SetEnterLeaveFunctionHooks3</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-setenterleavefunctionhooks3-method.md)
- [<span data-ttu-id="d0bfc-131">SetEnterLeaveFunctionHooks3WithInfo</span><span class="sxs-lookup"><span data-stu-id="d0bfc-131">SetEnterLeaveFunctionHooks3WithInfo</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-setenterleavefunctionhooks3withinfo-method.md)
- [<span data-ttu-id="d0bfc-132">SetFunctionIDMapper</span><span class="sxs-lookup"><span data-stu-id="d0bfc-132">SetFunctionIDMapper</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-setfunctionidmapper-method.md)
- [<span data-ttu-id="d0bfc-133">SetFunctionIDMapper2</span><span class="sxs-lookup"><span data-stu-id="d0bfc-133">SetFunctionIDMapper2</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-setfunctionidmapper2-method.md)
- [<span data-ttu-id="d0bfc-134">グローバル静的関数のプロファイル</span><span class="sxs-lookup"><span data-stu-id="d0bfc-134">Profiling Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-global-static-functions.md)
