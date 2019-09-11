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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 9495624f7eca57a79518036937a5fb63d01d9c4b
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/10/2019
ms.locfileid: "70851209"
---
# <a name="functiontailcall2-function"></a><span data-ttu-id="c506b-102">FunctionTailcall2 関数</span><span class="sxs-lookup"><span data-stu-id="c506b-102">FunctionTailcall2 Function</span></span>
<span data-ttu-id="c506b-103">現在実行中の関数が別の関数の末尾呼び出しを実行しようとしていることをプロファイラーに通知し、スタックフレームに関する情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="c506b-103">Notifies the profiler that the currently executing function is about to perform a tail call to another function and provides information about the stack frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c506b-104">構文</span><span class="sxs-lookup"><span data-stu-id="c506b-104">Syntax</span></span>  
  
```cpp
void __stdcall FunctionTailcall2 (  
    [in] FunctionID         funcId,   
    [in] UINT_PTR           clientData,   
    [in] COR_PRF_FRAME_INFO func  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c506b-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="c506b-105">Parameters</span></span>  
 `funcId`  
 <span data-ttu-id="c506b-106">から末尾呼び出しを実行しようとしている現在実行中の関数の識別子。</span><span class="sxs-lookup"><span data-stu-id="c506b-106">[in] The identifier of the currently executing function that is about to make a tail call.</span></span>  
  
 `clientData`  
 <span data-ttu-id="c506b-107">から末尾呼び出しを実行しようとしている現在実行中の関数の、プロファイラーが以前に[Functionidmapper](../../../../docs/framework/unmanaged-api/profiling/functionidmapper-function.md)を使用して指定した、再マップされた関数識別子。</span><span class="sxs-lookup"><span data-stu-id="c506b-107">[in] The remapped function identifier, which the profiler previously specified via [FunctionIDMapper](../../../../docs/framework/unmanaged-api/profiling/functionidmapper-function.md), of the currently executing function that is about to make a tail call.</span></span>  
  
 `func`  
 <span data-ttu-id="c506b-108">からスタックフレームに関する情報を示す値。`COR_PRF_FRAME_INFO`</span><span class="sxs-lookup"><span data-stu-id="c506b-108">[in] A `COR_PRF_FRAME_INFO` value that points to information about the stack frame.</span></span>  
  
 <span data-ttu-id="c506b-109">プロファイラーは、これを[ICorProfilerInfo2:: GetFunctionInfo2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getfunctioninfo2-method.md)メソッドの実行エンジンに渡すことができる不透明なハンドルとして処理する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c506b-109">The profiler should treat this as an opaque handle that can be passed back to the execution engine in the [ICorProfilerInfo2::GetFunctionInfo2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getfunctioninfo2-method.md) method.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c506b-110">Remarks</span><span class="sxs-lookup"><span data-stu-id="c506b-110">Remarks</span></span>  
 <span data-ttu-id="c506b-111">Tail 呼び出しの対象となる関数は、現在のスタックフレームを使用し、末尾呼び出しを行った関数の呼び出し元に直接戻ります。</span><span class="sxs-lookup"><span data-stu-id="c506b-111">The target function of the tail call will use the current stack frame, and will return directly to the caller of the function that made the tail call.</span></span> <span data-ttu-id="c506b-112">つまり、 [FunctionLeave2](../../../../docs/framework/unmanaged-api/profiling/functionleave2-function.md)コールバックは、末尾呼び出しのターゲットである関数に対しては発行されません。</span><span class="sxs-lookup"><span data-stu-id="c506b-112">This means that a [FunctionLeave2](../../../../docs/framework/unmanaged-api/profiling/functionleave2-function.md) callback will not be issued for a function that is the target of a tail call.</span></span>  
  
 <span data-ttu-id="c506b-113">値が変更また`func`は破棄される可能性が`FunctionTailcall2`あるため、関数がを返すと、パラメーターの値が無効になります。</span><span class="sxs-lookup"><span data-stu-id="c506b-113">The value of the `func` parameter is not valid after the `FunctionTailcall2` function returns because the value may change or be destroyed.</span></span>  
  
 <span data-ttu-id="c506b-114">`FunctionTailcall2`関数はコールバックであるため、実装する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c506b-114">The `FunctionTailcall2` function is a callback; you must implement it.</span></span> <span data-ttu-id="c506b-115">実装では、 `__declspec`(`naked`) ストレージクラス属性を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c506b-115">The implementation must use the `__declspec`(`naked`) storage-class attribute.</span></span>  
  
 <span data-ttu-id="c506b-116">この関数を呼び出す前に、実行エンジンはレジスタを保存しません。</span><span class="sxs-lookup"><span data-stu-id="c506b-116">The execution engine does not save any registers before calling this function.</span></span>  
  
- <span data-ttu-id="c506b-117">入力時には、浮動小数点単位 (FPU) に含まれるすべてのレジスタを含め、使用するすべてのレジスタを保存する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c506b-117">On entry, you must save all registers that you use, including those in the floating-point unit (FPU).</span></span>  
  
- <span data-ttu-id="c506b-118">終了時に、呼び出し元によってプッシュされたすべてのパラメーターをポップして、スタックを復元する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c506b-118">On exit, you must restore the stack by popping off all the parameters that were pushed by its caller.</span></span>  
  
 <span data-ttu-id="c506b-119">の`FunctionTailcall2`実装は、ガベージコレクションを遅延させるため、ブロックしないでください。</span><span class="sxs-lookup"><span data-stu-id="c506b-119">The implementation of `FunctionTailcall2` should not block because it will delay garbage collection.</span></span> <span data-ttu-id="c506b-120">スタックがガベージコレクションに対応していない可能性があるため、この実装ではガベージコレクションを実行しないようにしてください。</span><span class="sxs-lookup"><span data-stu-id="c506b-120">The implementation should not attempt a garbage collection because the stack may not be in a garbage collection-friendly state.</span></span> <span data-ttu-id="c506b-121">ガベージコレクションが試行された場合、ランタイムはが`FunctionTailcall2`返されるまでブロックします。</span><span class="sxs-lookup"><span data-stu-id="c506b-121">If a garbage collection is attempted, the runtime will block until `FunctionTailcall2` returns.</span></span>  
  
 <span data-ttu-id="c506b-122">また、関数`FunctionTailcall2`はマネージコードを呼び出さないようにするか、マネージメモリ割り当てを発生させることはできません。</span><span class="sxs-lookup"><span data-stu-id="c506b-122">Also, the `FunctionTailcall2` function must not call into managed code or in any way cause a managed memory allocation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c506b-123">必要条件</span><span class="sxs-lookup"><span data-stu-id="c506b-123">Requirements</span></span>  
 <span data-ttu-id="c506b-124">**・** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="c506b-124">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c506b-125">**ヘッダー:** Corprof.idl</span><span class="sxs-lookup"><span data-stu-id="c506b-125">**Header:** CorProf.idl</span></span>  
  
 <span data-ttu-id="c506b-126">**ライブラリ**CorGuids .lib</span><span class="sxs-lookup"><span data-stu-id="c506b-126">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c506b-127">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c506b-127">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c506b-128">関連項目</span><span class="sxs-lookup"><span data-stu-id="c506b-128">See also</span></span>

- [<span data-ttu-id="c506b-129">FunctionEnter2 関数</span><span class="sxs-lookup"><span data-stu-id="c506b-129">FunctionEnter2 Function</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionenter2-function.md)
- [<span data-ttu-id="c506b-130">FunctionLeave2 関数</span><span class="sxs-lookup"><span data-stu-id="c506b-130">FunctionLeave2 Function</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionleave2-function.md)
- [<span data-ttu-id="c506b-131">SetEnterLeaveFunctionHooks2 メソッド</span><span class="sxs-lookup"><span data-stu-id="c506b-131">SetEnterLeaveFunctionHooks2 Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-setenterleavefunctionhooks2-method.md)
- [<span data-ttu-id="c506b-132">グローバル静的関数のプロファイル</span><span class="sxs-lookup"><span data-stu-id="c506b-132">Profiling Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-global-static-functions.md)
