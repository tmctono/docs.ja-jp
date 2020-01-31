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
ms.openlocfilehash: 7f6ef2c410d49e2e63b88d6f47c33c211f2a8dd8
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/28/2020
ms.locfileid: "76790283"
---
# <a name="functiontailcall2-function"></a><span data-ttu-id="a71b7-102">FunctionTailcall2 関数</span><span class="sxs-lookup"><span data-stu-id="a71b7-102">FunctionTailcall2 Function</span></span>
<span data-ttu-id="a71b7-103">現在実行中の関数が別の関数の末尾呼び出しを実行しようとしていることをプロファイラーに通知し、スタックフレームに関する情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="a71b7-103">Notifies the profiler that the currently executing function is about to perform a tail call to another function and provides information about the stack frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a71b7-104">構文</span><span class="sxs-lookup"><span data-stu-id="a71b7-104">Syntax</span></span>  
  
```cpp
void __stdcall FunctionTailcall2 (  
    [in] FunctionID         funcId,   
    [in] UINT_PTR           clientData,   
    [in] COR_PRF_FRAME_INFO func  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a71b7-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="a71b7-105">Parameters</span></span>

- `funcId`

  <span data-ttu-id="a71b7-106">\[] では、末尾呼び出しを実行しようとしている現在実行中の関数の識別子。</span><span class="sxs-lookup"><span data-stu-id="a71b7-106">\[in] The identifier of the currently executing function that is about to make a tail call.</span></span>

- `clientData`

  <span data-ttu-id="a71b7-107">in] を \[します。マップされていない関数識別子。これは、以前に[Functionidmapper](../../../../docs/framework/unmanaged-api/profiling/functionidmapper-function.md)によって指定された、現在実行中の関数の末尾呼び出しを実行しようとしています。</span><span class="sxs-lookup"><span data-stu-id="a71b7-107">\[in] The remapped function identifier, which the profiler previously specified via [FunctionIDMapper](../../../../docs/framework/unmanaged-api/profiling/functionidmapper-function.md), of the currently executing function that is about to make a tail call.</span></span>
  
- `func`

  <span data-ttu-id="a71b7-108">\[] で、スタックフレームに関する情報を指す `COR_PRF_FRAME_INFO` 値です。</span><span class="sxs-lookup"><span data-stu-id="a71b7-108">\[in] A `COR_PRF_FRAME_INFO` value that points to information about the stack frame.</span></span>

  <span data-ttu-id="a71b7-109">プロファイラーは、これを[ICorProfilerInfo2:: GetFunctionInfo2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getfunctioninfo2-method.md)メソッドの実行エンジンに渡すことができる不透明なハンドルとして処理する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a71b7-109">The profiler should treat this as an opaque handle that can be passed back to the execution engine in the [ICorProfilerInfo2::GetFunctionInfo2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getfunctioninfo2-method.md) method.</span></span>

## <a name="remarks"></a><span data-ttu-id="a71b7-110">コメント</span><span class="sxs-lookup"><span data-stu-id="a71b7-110">Remarks</span></span>  
 <span data-ttu-id="a71b7-111">Tail 呼び出しの対象となる関数は、現在のスタックフレームを使用し、末尾呼び出しを行った関数の呼び出し元に直接戻ります。</span><span class="sxs-lookup"><span data-stu-id="a71b7-111">The target function of the tail call will use the current stack frame, and will return directly to the caller of the function that made the tail call.</span></span> <span data-ttu-id="a71b7-112">つまり、 [FunctionLeave2](../../../../docs/framework/unmanaged-api/profiling/functionleave2-function.md)コールバックは、末尾呼び出しのターゲットである関数に対しては発行されません。</span><span class="sxs-lookup"><span data-stu-id="a71b7-112">This means that a [FunctionLeave2](../../../../docs/framework/unmanaged-api/profiling/functionleave2-function.md) callback will not be issued for a function that is the target of a tail call.</span></span>  
  
 <span data-ttu-id="a71b7-113">`func` パラメーターの値は、値が変更または破棄される可能性があるため、`FunctionTailcall2` 関数から制御が戻った後に有効ではありません。</span><span class="sxs-lookup"><span data-stu-id="a71b7-113">The value of the `func` parameter is not valid after the `FunctionTailcall2` function returns because the value may change or be destroyed.</span></span>  
  
 <span data-ttu-id="a71b7-114">`FunctionTailcall2` 関数はコールバックです。実装する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a71b7-114">The `FunctionTailcall2` function is a callback; you must implement it.</span></span> <span data-ttu-id="a71b7-115">実装では、`__declspec`(`naked`) ストレージクラス属性を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a71b7-115">The implementation must use the `__declspec`(`naked`) storage-class attribute.</span></span>  
  
 <span data-ttu-id="a71b7-116">この関数を呼び出す前に、実行エンジンはレジスタを保存しません。</span><span class="sxs-lookup"><span data-stu-id="a71b7-116">The execution engine does not save any registers before calling this function.</span></span>  
  
- <span data-ttu-id="a71b7-117">入力時には、浮動小数点単位 (FPU) に含まれるすべてのレジスタを含め、使用するすべてのレジスタを保存する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a71b7-117">On entry, you must save all registers that you use, including those in the floating-point unit (FPU).</span></span>  
  
- <span data-ttu-id="a71b7-118">終了時に、呼び出し元によってプッシュされたすべてのパラメーターをポップして、スタックを復元する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a71b7-118">On exit, you must restore the stack by popping off all the parameters that were pushed by its caller.</span></span>  
  
 <span data-ttu-id="a71b7-119">`FunctionTailcall2` の実装では、ガベージコレクションが遅延するため、ブロックしないでください。</span><span class="sxs-lookup"><span data-stu-id="a71b7-119">The implementation of `FunctionTailcall2` should not block because it will delay garbage collection.</span></span> <span data-ttu-id="a71b7-120">スタックがガベージコレクションに対応していない可能性があるため、この実装ではガベージコレクションを実行しないようにしてください。</span><span class="sxs-lookup"><span data-stu-id="a71b7-120">The implementation should not attempt a garbage collection because the stack may not be in a garbage collection-friendly state.</span></span> <span data-ttu-id="a71b7-121">ガベージコレクションを実行しようとすると、ランタイムは `FunctionTailcall2` が返されるまでブロックします。</span><span class="sxs-lookup"><span data-stu-id="a71b7-121">If a garbage collection is attempted, the runtime will block until `FunctionTailcall2` returns.</span></span>  
  
 <span data-ttu-id="a71b7-122">また、`FunctionTailcall2` 関数は、マネージコードを呼び出さないようにするか、マネージメモリ割り当てを発生させることはできません。</span><span class="sxs-lookup"><span data-stu-id="a71b7-122">Also, the `FunctionTailcall2` function must not call into managed code or in any way cause a managed memory allocation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a71b7-123">要件</span><span class="sxs-lookup"><span data-stu-id="a71b7-123">Requirements</span></span>  
 <span data-ttu-id="a71b7-124">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a71b7-124">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a71b7-125">**ヘッダー:** Corprof.idl</span><span class="sxs-lookup"><span data-stu-id="a71b7-125">**Header:** CorProf.idl</span></span>  
  
 <span data-ttu-id="a71b7-126">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a71b7-126">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a71b7-127">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a71b7-127">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a71b7-128">関連項目</span><span class="sxs-lookup"><span data-stu-id="a71b7-128">See also</span></span>

- [<span data-ttu-id="a71b7-129">FunctionEnter2 関数</span><span class="sxs-lookup"><span data-stu-id="a71b7-129">FunctionEnter2 Function</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionenter2-function.md)
- [<span data-ttu-id="a71b7-130">FunctionLeave2 関数</span><span class="sxs-lookup"><span data-stu-id="a71b7-130">FunctionLeave2 Function</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionleave2-function.md)
- [<span data-ttu-id="a71b7-131">SetEnterLeaveFunctionHooks2 メソッド</span><span class="sxs-lookup"><span data-stu-id="a71b7-131">SetEnterLeaveFunctionHooks2 Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-setenterleavefunctionhooks2-method.md)
- [<span data-ttu-id="a71b7-132">グローバル静的関数のプロファイル</span><span class="sxs-lookup"><span data-stu-id="a71b7-132">Profiling Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-global-static-functions.md)
