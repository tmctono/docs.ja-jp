---
title: FunctionTailcall 関数
ms.date: 03/30/2017
api_name:
- FunctionTailcall
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- FunctionTailcall
helpviewer_keywords:
- FunctionTailcall function [.NET Framework profiling]
ms.assetid: 66347e03-9a97-41e8-8f9d-89b80803f7b5
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: afc0929b8f1b12f4e0b4551d826b8a1d59990154
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2019
ms.locfileid: "69952887"
---
# <a name="functiontailcall-function"></a><span data-ttu-id="d80db-102">FunctionTailcall 関数</span><span class="sxs-lookup"><span data-stu-id="d80db-102">FunctionTailcall Function</span></span>
<span data-ttu-id="d80db-103">現在実行中の関数が別の関数の末尾呼び出しを実行しようとしていることをプロファイラーに通知します。</span><span class="sxs-lookup"><span data-stu-id="d80db-103">Notifies the profiler that the currently executing function is about to perform a tail call to another function.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="d80db-104">`FunctionTailcall`関数は .NET Framework バージョン2.0 では非推奨とされます。</span><span class="sxs-lookup"><span data-stu-id="d80db-104">The `FunctionTailcall` function is deprecated in the .NET Framework version 2.0.</span></span> <span data-ttu-id="d80db-105">これは引き続き機能しますが、パフォーマンスが低下します。</span><span class="sxs-lookup"><span data-stu-id="d80db-105">It will continue to work, but will incur a performance penalty.</span></span> <span data-ttu-id="d80db-106">代わりに、 [FunctionTailcall2](../../../../docs/framework/unmanaged-api/profiling/functiontailcall2-function.md)関数を使用してください。</span><span class="sxs-lookup"><span data-stu-id="d80db-106">Use the [FunctionTailcall2](../../../../docs/framework/unmanaged-api/profiling/functiontailcall2-function.md) function instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d80db-107">構文</span><span class="sxs-lookup"><span data-stu-id="d80db-107">Syntax</span></span>  
  
```  
void __stdcall FunctionTailcall (  
    [in] FunctionID funcID  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d80db-108">パラメーター</span><span class="sxs-lookup"><span data-stu-id="d80db-108">Parameters</span></span>  
 `funcID`  
 <span data-ttu-id="d80db-109">から末尾呼び出しを実行しようとしている現在実行中の関数の識別子。</span><span class="sxs-lookup"><span data-stu-id="d80db-109">[in] The identifier of the currently executing function that is about to make a tail call.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d80db-110">Remarks</span><span class="sxs-lookup"><span data-stu-id="d80db-110">Remarks</span></span>  
 <span data-ttu-id="d80db-111">Tail 呼び出しの対象となる関数は、現在のスタックフレームを使用し、末尾呼び出しを行った関数の呼び出し元に直接戻ります。</span><span class="sxs-lookup"><span data-stu-id="d80db-111">The target function of the tail call will use the current stack frame, and will return directly to the caller of the function that made the tail call.</span></span> <span data-ttu-id="d80db-112">これは、tail 呼び出しの対象である関数に対して[Functionleave](../../../../docs/framework/unmanaged-api/profiling/functionleave-function.md)コールバックが発行されないことを意味します。</span><span class="sxs-lookup"><span data-stu-id="d80db-112">This means that a [FunctionLeave](../../../../docs/framework/unmanaged-api/profiling/functionleave-function.md) callback will not be issued for a function that is the target of a tail call.</span></span>  
  
 <span data-ttu-id="d80db-113">`FunctionTailcall`関数はコールバックであるため、実装する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d80db-113">The `FunctionTailcall` function is a callback; you must implement it.</span></span> <span data-ttu-id="d80db-114">実装では、 `__declspec`(`naked`) ストレージクラス属性を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d80db-114">The implementation must use the `__declspec`(`naked`) storage-class attribute.</span></span>  
  
 <span data-ttu-id="d80db-115">この関数を呼び出す前に、実行エンジンはレジスタを保存しません。</span><span class="sxs-lookup"><span data-stu-id="d80db-115">The execution engine does not save any registers before calling this function.</span></span>  
  
- <span data-ttu-id="d80db-116">入力時には、浮動小数点単位 (FPU) に含まれるすべてのレジスタを含め、使用するすべてのレジスタを保存する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d80db-116">On entry, you must save all registers that you use, including those in the floating-point unit (FPU).</span></span>  
  
- <span data-ttu-id="d80db-117">終了時に、呼び出し元によってプッシュされたすべてのパラメーターをポップして、スタックを復元する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d80db-117">On exit, you must restore the stack by popping off all the parameters that were pushed by its caller.</span></span>  
  
 <span data-ttu-id="d80db-118">の`FunctionTailcall`実装は、ガベージコレクションを遅延させるため、ブロックしないでください。</span><span class="sxs-lookup"><span data-stu-id="d80db-118">The implementation of `FunctionTailcall` should not block because it will delay garbage collection.</span></span> <span data-ttu-id="d80db-119">スタックがガベージコレクションに対応していない可能性があるため、この実装ではガベージコレクションを実行しないようにしてください。</span><span class="sxs-lookup"><span data-stu-id="d80db-119">The implementation should not attempt a garbage collection because the stack may not be in a garbage collection-friendly state.</span></span> <span data-ttu-id="d80db-120">ガベージコレクションが試行された場合、ランタイムはが`FunctionTailcall`返されるまでブロックします。</span><span class="sxs-lookup"><span data-stu-id="d80db-120">If a garbage collection is attempted, the runtime will block until `FunctionTailcall` returns.</span></span>  
  
 <span data-ttu-id="d80db-121">また、関数`FunctionTailcall`はマネージコードを呼び出さないようにするか、マネージメモリ割り当てを発生させることはできません。</span><span class="sxs-lookup"><span data-stu-id="d80db-121">Also, the `FunctionTailcall` function must not call into managed code or in any way cause a managed memory allocation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d80db-122">必要条件</span><span class="sxs-lookup"><span data-stu-id="d80db-122">Requirements</span></span>  
 <span data-ttu-id="d80db-123">**・** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="d80db-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d80db-124">**ヘッダー:** Corprof.idl</span><span class="sxs-lookup"><span data-stu-id="d80db-124">**Header:** CorProf.idl</span></span>  
  
 <span data-ttu-id="d80db-125">**ライブラリ**CorGuids .lib</span><span class="sxs-lookup"><span data-stu-id="d80db-125">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d80db-126">**.NET Framework のバージョン:** 1.1、1.0</span><span class="sxs-lookup"><span data-stu-id="d80db-126">**.NET Framework Versions:** 1.1, 1.0</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d80db-127">関連項目</span><span class="sxs-lookup"><span data-stu-id="d80db-127">See also</span></span>

- [<span data-ttu-id="d80db-128">FunctionEnter2 関数</span><span class="sxs-lookup"><span data-stu-id="d80db-128">FunctionEnter2 Function</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionenter2-function.md)
- [<span data-ttu-id="d80db-129">FunctionLeave2 関数</span><span class="sxs-lookup"><span data-stu-id="d80db-129">FunctionLeave2 Function</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionleave2-function.md)
- [<span data-ttu-id="d80db-130">SetEnterLeaveFunctionHooks2 メソッド</span><span class="sxs-lookup"><span data-stu-id="d80db-130">SetEnterLeaveFunctionHooks2 Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-setenterleavefunctionhooks2-method.md)
- [<span data-ttu-id="d80db-131">グローバル静的関数のプロファイル</span><span class="sxs-lookup"><span data-stu-id="d80db-131">Profiling Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-global-static-functions.md)
