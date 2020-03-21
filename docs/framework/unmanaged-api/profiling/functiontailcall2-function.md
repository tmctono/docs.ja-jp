---
title: FunctionTailcall2 関数
ms.date: 03/30/2017
api_name:
- FunctionTailcall2
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- FunctionTailcall2
helpviewer_keywords:
- FunctionTailcall2 function [.NET Framework profiling]
ms.assetid: 249f9892-b5a9-41e1-b329-28a925904df6
topic_type:
- apiref
ms.openlocfilehash: 60276327617ae24e9bdcebf958613c21d3808429
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175188"
---
# <a name="functiontailcall2-function"></a><span data-ttu-id="e316b-102">FunctionTailcall2 関数</span><span class="sxs-lookup"><span data-stu-id="e316b-102">FunctionTailcall2 Function</span></span>
<span data-ttu-id="e316b-103">現在実行中の関数が別の関数に対して末尾呼び出しを実行しようとしていることをプロファイラーに通知し、スタック フレームに関する情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="e316b-103">Notifies the profiler that the currently executing function is about to perform a tail call to another function and provides information about the stack frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e316b-104">構文</span><span class="sxs-lookup"><span data-stu-id="e316b-104">Syntax</span></span>  
  
```cpp
void __stdcall FunctionTailcall2 (  
    [in] FunctionID         funcId,
    [in] UINT_PTR           clientData,
    [in] COR_PRF_FRAME_INFO func  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e316b-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="e316b-105">Parameters</span></span>

- `funcId`

  <span data-ttu-id="e316b-106">\[in] 末尾呼び出しを行おうとしている現在実行中の関数の識別子。</span><span class="sxs-lookup"><span data-stu-id="e316b-106">\[in] The identifier of the currently executing function that is about to make a tail call.</span></span>

- `clientData`

  <span data-ttu-id="e316b-107">\[in] 再マップされた関数識別子( プロファイラーが以前に[FunctionIDMapper](functionidmapper-function.md)を介して指定した) で、現在実行されている末尾呼び出しを行おうとしている関数の識別子です。</span><span class="sxs-lookup"><span data-stu-id="e316b-107">\[in] The remapped function identifier, which the profiler previously specified via [FunctionIDMapper](functionidmapper-function.md), of the currently executing function that is about to make a tail call.</span></span>
  
- `func`

  <span data-ttu-id="e316b-108">\[in]`COR_PRF_FRAME_INFO`スタック フレームに関する情報を指す値。</span><span class="sxs-lookup"><span data-stu-id="e316b-108">\[in] A `COR_PRF_FRAME_INFO` value that points to information about the stack frame.</span></span>

  <span data-ttu-id="e316b-109">プロファイラーは、[これを ICorProfilerInfo2::GetFunctionInfo2](icorprofilerinfo2-getfunctioninfo2-method.md)メソッドの実行エンジンに返すことができる不透明なハンドルとして扱う必要があります。</span><span class="sxs-lookup"><span data-stu-id="e316b-109">The profiler should treat this as an opaque handle that can be passed back to the execution engine in the [ICorProfilerInfo2::GetFunctionInfo2](icorprofilerinfo2-getfunctioninfo2-method.md) method.</span></span>

## <a name="remarks"></a><span data-ttu-id="e316b-110">解説</span><span class="sxs-lookup"><span data-stu-id="e316b-110">Remarks</span></span>  
 <span data-ttu-id="e316b-111">テールコールのターゲット関数は現在のスタックフレームを使用し、テールコールを行った関数の呼び出し元に直接戻ります。</span><span class="sxs-lookup"><span data-stu-id="e316b-111">The target function of the tail call will use the current stack frame, and will return directly to the caller of the function that made the tail call.</span></span> <span data-ttu-id="e316b-112">これは、Tail 呼び出しの対象である関数に対して[FunctionLeave2](functionleave2-function.md)コールバックが発行されないことを意味します。</span><span class="sxs-lookup"><span data-stu-id="e316b-112">This means that a [FunctionLeave2](functionleave2-function.md) callback will not be issued for a function that is the target of a tail call.</span></span>  
  
 <span data-ttu-id="e316b-113">値が`func`変更されたり破棄されたりする可能性があるため、`FunctionTailcall2`関数が戻った後は、パラメーターの値が無効になります。</span><span class="sxs-lookup"><span data-stu-id="e316b-113">The value of the `func` parameter is not valid after the `FunctionTailcall2` function returns because the value may change or be destroyed.</span></span>  
  
 <span data-ttu-id="e316b-114">関数`FunctionTailcall2`はコールバックです。それを実装する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e316b-114">The `FunctionTailcall2` function is a callback; you must implement it.</span></span> <span data-ttu-id="e316b-115">実装では、 ( `__declspec``naked`) ストレージ クラス属性を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e316b-115">The implementation must use the `__declspec`(`naked`) storage-class attribute.</span></span>  
  
 <span data-ttu-id="e316b-116">実行エンジンは、この関数を呼び出す前にレジスタを保存しません。</span><span class="sxs-lookup"><span data-stu-id="e316b-116">The execution engine does not save any registers before calling this function.</span></span>  
  
- <span data-ttu-id="e316b-117">入力時には、使用するすべてのレジスタ (浮動小数点単位 (FPU) 内のレジスタも含む) を保存する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e316b-117">On entry, you must save all registers that you use, including those in the floating-point unit (FPU).</span></span>  
  
- <span data-ttu-id="e316b-118">終了時に、呼び出し元によってプッシュされたすべてのパラメーターをポップオフしてスタックを復元する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e316b-118">On exit, you must restore the stack by popping off all the parameters that were pushed by its caller.</span></span>  
  
 <span data-ttu-id="e316b-119">の実装`FunctionTailcall2`はガベージ コレクションを遅延するため、ブロックしないでください。</span><span class="sxs-lookup"><span data-stu-id="e316b-119">The implementation of `FunctionTailcall2` should not block because it will delay garbage collection.</span></span> <span data-ttu-id="e316b-120">スタックがガベージ コレクションに優しい状態ではない可能性があるため、実装はガベージ コレクションを試行しないでください。</span><span class="sxs-lookup"><span data-stu-id="e316b-120">The implementation should not attempt a garbage collection because the stack may not be in a garbage collection-friendly state.</span></span> <span data-ttu-id="e316b-121">ガベージ コレクションが試行されると、ランタイムは、戻るまで`FunctionTailcall2`ブロックします。</span><span class="sxs-lookup"><span data-stu-id="e316b-121">If a garbage collection is attempted, the runtime will block until `FunctionTailcall2` returns.</span></span>  
  
 <span data-ttu-id="e316b-122">また、この`FunctionTailcall2`関数はマネージ コードを呼び出したり、マネージ メモリ割り当てを引き起こしたりしないでください。</span><span class="sxs-lookup"><span data-stu-id="e316b-122">Also, the `FunctionTailcall2` function must not call into managed code or in any way cause a managed memory allocation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e316b-123">必要条件</span><span class="sxs-lookup"><span data-stu-id="e316b-123">Requirements</span></span>  
 <span data-ttu-id="e316b-124">**:**「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e316b-124">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e316b-125">**ヘッダー:** コルプロフ.idl</span><span class="sxs-lookup"><span data-stu-id="e316b-125">**Header:** CorProf.idl</span></span>  
  
 <span data-ttu-id="e316b-126">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e316b-126">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e316b-127">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e316b-127">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e316b-128">関連項目</span><span class="sxs-lookup"><span data-stu-id="e316b-128">See also</span></span>

- [<span data-ttu-id="e316b-129">FunctionEnter2 関数</span><span class="sxs-lookup"><span data-stu-id="e316b-129">FunctionEnter2 Function</span></span>](functionenter2-function.md)
- [<span data-ttu-id="e316b-130">FunctionLeave2 関数</span><span class="sxs-lookup"><span data-stu-id="e316b-130">FunctionLeave2 Function</span></span>](functionleave2-function.md)
- [<span data-ttu-id="e316b-131">SetEnterLeaveFunctionHooks2 メソッド</span><span class="sxs-lookup"><span data-stu-id="e316b-131">SetEnterLeaveFunctionHooks2 Method</span></span>](icorprofilerinfo2-setenterleavefunctionhooks2-method.md)
- [<span data-ttu-id="e316b-132">グローバル静的関数のプロファイル</span><span class="sxs-lookup"><span data-stu-id="e316b-132">Profiling Global Static Functions</span></span>](profiling-global-static-functions.md)
