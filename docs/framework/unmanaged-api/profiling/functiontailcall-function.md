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
ms.openlocfilehash: 4686710c105ef002fe30f8b6e167d760088913ce
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/28/2019
ms.locfileid: "64586991"
---
# <a name="functiontailcall-function"></a><span data-ttu-id="fa20d-102">FunctionTailcall 関数</span><span class="sxs-lookup"><span data-stu-id="fa20d-102">FunctionTailcall Function</span></span>
<span data-ttu-id="fa20d-103">現在実行中の関数が別の関数の末尾呼び出しを実行しようとすることをプロファイラーに通知します。</span><span class="sxs-lookup"><span data-stu-id="fa20d-103">Notifies the profiler that the currently executing function is about to perform a tail call to another function.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="fa20d-104">`FunctionTailcall`関数が、.NET Framework version 2.0 で非推奨とされます。</span><span class="sxs-lookup"><span data-stu-id="fa20d-104">The `FunctionTailcall` function is deprecated in the .NET Framework version 2.0.</span></span> <span data-ttu-id="fa20d-105">引き続き、動作しますが、パフォーマンスの低下が発生します。</span><span class="sxs-lookup"><span data-stu-id="fa20d-105">It will continue to work, but will incur a performance penalty.</span></span> <span data-ttu-id="fa20d-106">使用して、 [FunctionTailcall2](../../../../docs/framework/unmanaged-api/profiling/functiontailcall2-function.md)関数を使用します。</span><span class="sxs-lookup"><span data-stu-id="fa20d-106">Use the [FunctionTailcall2](../../../../docs/framework/unmanaged-api/profiling/functiontailcall2-function.md) function instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fa20d-107">構文</span><span class="sxs-lookup"><span data-stu-id="fa20d-107">Syntax</span></span>  
  
```  
void __stdcall FunctionTailcall (  
    [in] FunctionID funcID  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="fa20d-108">パラメーター</span><span class="sxs-lookup"><span data-stu-id="fa20d-108">Parameters</span></span>  
 `funcID`  
 <span data-ttu-id="fa20d-109">[in]Tail の呼び出しを行うには、現在実行中の関数の識別子です。</span><span class="sxs-lookup"><span data-stu-id="fa20d-109">[in] The identifier of the currently executing function that is about to make a tail call.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="fa20d-110">Remarks</span><span class="sxs-lookup"><span data-stu-id="fa20d-110">Remarks</span></span>  
 <span data-ttu-id="fa20d-111">末尾呼び出しの対象の関数は、現在のスタック フレームを使用し、直接 tail 呼び出しを行った関数の呼び出し元に戻ります。</span><span class="sxs-lookup"><span data-stu-id="fa20d-111">The target function of the tail call will use the current stack frame, and will return directly to the caller of the function that made the tail call.</span></span> <span data-ttu-id="fa20d-112">つまり、 [FunctionLeave](../../../../docs/framework/unmanaged-api/profiling/functionleave-function.md)末尾呼び出しの対象となっている関数のコールバックは発行されません。</span><span class="sxs-lookup"><span data-stu-id="fa20d-112">This means that a [FunctionLeave](../../../../docs/framework/unmanaged-api/profiling/functionleave-function.md) callback will not be issued for a function that is the target of a tail call.</span></span>  
  
 <span data-ttu-id="fa20d-113">`FunctionTailcall`関数は、コールバックは、これを実装する必要があります。</span><span class="sxs-lookup"><span data-stu-id="fa20d-113">The `FunctionTailcall` function is a callback; you must implement it.</span></span> <span data-ttu-id="fa20d-114">実装を使用する必要があります、 `__declspec`(`naked`) ストレージ クラス属性。</span><span class="sxs-lookup"><span data-stu-id="fa20d-114">The implementation must use the `__declspec`(`naked`) storage-class attribute.</span></span>  
  
 <span data-ttu-id="fa20d-115">実行エンジンは、この関数を呼び出す前に、レジスタを保存できません。</span><span class="sxs-lookup"><span data-stu-id="fa20d-115">The execution engine does not save any registers before calling this function.</span></span>  
  
- <span data-ttu-id="fa20d-116">項目で、浮動小数点ユニット (FPU) にあるなど、使用するすべてのレジスタを保存する必要があります。</span><span class="sxs-lookup"><span data-stu-id="fa20d-116">On entry, you must save all registers that you use, including those in the floating-point unit (FPU).</span></span>  
  
- <span data-ttu-id="fa20d-117">終了時に、その呼び出し元によってプッシュされたすべてのパラメーターをポップしてスタックを復元する必要があります。</span><span class="sxs-lookup"><span data-stu-id="fa20d-117">On exit, you must restore the stack by popping off all the parameters that were pushed by its caller.</span></span>  
  
 <span data-ttu-id="fa20d-118">実装`FunctionTailcall`ガベージ コレクションは延期されますブロックしないでください。</span><span class="sxs-lookup"><span data-stu-id="fa20d-118">The implementation of `FunctionTailcall` should not block because it will delay garbage collection.</span></span> <span data-ttu-id="fa20d-119">実装は、ガベージ コレクションをしないで、スタックはガベージ コレクションに適した状態ではない可能性が。</span><span class="sxs-lookup"><span data-stu-id="fa20d-119">The implementation should not attempt a garbage collection because the stack may not be in a garbage collection-friendly state.</span></span> <span data-ttu-id="fa20d-120">ランタイムがまでブロックはガベージ コレクションが試行されると、`FunctionTailcall`を返します。</span><span class="sxs-lookup"><span data-stu-id="fa20d-120">If a garbage collection is attempted, the runtime will block until `FunctionTailcall` returns.</span></span>  
  
 <span data-ttu-id="fa20d-121">また、`FunctionTailcall`関数を呼び出してはならないようにまたはマネージ コードにマネージ メモリの割り当て。</span><span class="sxs-lookup"><span data-stu-id="fa20d-121">Also, the `FunctionTailcall` function must not call into managed code or in any way cause a managed memory allocation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fa20d-122">必要条件</span><span class="sxs-lookup"><span data-stu-id="fa20d-122">Requirements</span></span>  
 <span data-ttu-id="fa20d-123">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="fa20d-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fa20d-124">**ヘッダー:** CorProf.idl</span><span class="sxs-lookup"><span data-stu-id="fa20d-124">**Header:** CorProf.idl</span></span>  
  
 <span data-ttu-id="fa20d-125">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="fa20d-125">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="fa20d-126">**.NET framework のバージョン:** 1.1, 1.0</span><span class="sxs-lookup"><span data-stu-id="fa20d-126">**.NET Framework Versions:** 1.1, 1.0</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fa20d-127">関連項目</span><span class="sxs-lookup"><span data-stu-id="fa20d-127">See also</span></span>

- [<span data-ttu-id="fa20d-128">FunctionEnter2 関数</span><span class="sxs-lookup"><span data-stu-id="fa20d-128">FunctionEnter2 Function</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionenter2-function.md)
- [<span data-ttu-id="fa20d-129">FunctionLeave2 関数</span><span class="sxs-lookup"><span data-stu-id="fa20d-129">FunctionLeave2 Function</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionleave2-function.md)
- [<span data-ttu-id="fa20d-130">SetEnterLeaveFunctionHooks2 メソッド</span><span class="sxs-lookup"><span data-stu-id="fa20d-130">SetEnterLeaveFunctionHooks2 Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-setenterleavefunctionhooks2-method.md)
- [<span data-ttu-id="fa20d-131">グローバル静的関数のプロファイル</span><span class="sxs-lookup"><span data-stu-id="fa20d-131">Profiling Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-global-static-functions.md)
