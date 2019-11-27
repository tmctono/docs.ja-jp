---
title: FunctionEnter 関数
ms.date: 03/30/2017
api_name:
- FunctionEnter
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- FunctionEnter
helpviewer_keywords:
- FunctionEnter function [.NET Framework profiling]
ms.assetid: bf4ffa50-4506-4dd4-aa13-a0457b47ca74
topic_type:
- apiref
ms.openlocfilehash: ad34592223433f0bf541c390674bcf96839b6ca8
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/23/2019
ms.locfileid: "74440819"
---
# <a name="functionenter-function"></a><span data-ttu-id="85bf6-102">FunctionEnter 関数</span><span class="sxs-lookup"><span data-stu-id="85bf6-102">FunctionEnter Function</span></span>
<span data-ttu-id="85bf6-103">コントロールが関数に渡されていることをプロファイラーに通知します。</span><span class="sxs-lookup"><span data-stu-id="85bf6-103">Notifies the profiler that control is being passed to a function.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="85bf6-104">`FunctionEnter` 関数は .NET Framework バージョン2.0 では非推奨とされており、その使用によってパフォーマンスが低下します。</span><span class="sxs-lookup"><span data-stu-id="85bf6-104">The `FunctionEnter` function is deprecated in the .NET Framework version 2.0, and its use will incur a performance penalty.</span></span> <span data-ttu-id="85bf6-105">代わりに、 [FunctionEnter2](../../../../docs/framework/unmanaged-api/profiling/functionenter2-function.md)関数を使用してください。</span><span class="sxs-lookup"><span data-stu-id="85bf6-105">Use the [FunctionEnter2](../../../../docs/framework/unmanaged-api/profiling/functionenter2-function.md) function instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="85bf6-106">構文</span><span class="sxs-lookup"><span data-stu-id="85bf6-106">Syntax</span></span>  
  
```cpp  
void __stdcall FunctionEnter (  
    [in]  FunctionID funcID  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="85bf6-107">パラメーター</span><span class="sxs-lookup"><span data-stu-id="85bf6-107">Parameters</span></span>  
 `funcID`  
 <span data-ttu-id="85bf6-108">からコントロールが渡される関数の識別子。</span><span class="sxs-lookup"><span data-stu-id="85bf6-108">[in] The identifier of the function to which control is passed.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="85bf6-109">コメント</span><span class="sxs-lookup"><span data-stu-id="85bf6-109">Remarks</span></span>  
 <span data-ttu-id="85bf6-110">`FunctionEnter` 関数はコールバックです。実装する必要があります。</span><span class="sxs-lookup"><span data-stu-id="85bf6-110">The `FunctionEnter` function is a callback; you must implement it.</span></span> <span data-ttu-id="85bf6-111">実装では、`__declspec`(`naked`) ストレージクラス属性を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="85bf6-111">The implementation must use the `__declspec`(`naked`) storage-class attribute.</span></span>  
  
 <span data-ttu-id="85bf6-112">この関数を呼び出す前に、実行エンジンはレジスタを保存しません。</span><span class="sxs-lookup"><span data-stu-id="85bf6-112">The execution engine does not save any registers before calling this function.</span></span>  
  
- <span data-ttu-id="85bf6-113">入力時には、浮動小数点単位 (FPU) に含まれるすべてのレジスタを含め、使用するすべてのレジスタを保存する必要があります。</span><span class="sxs-lookup"><span data-stu-id="85bf6-113">On entry, you must save all registers that you use, including those in the floating-point unit (FPU).</span></span>  
  
- <span data-ttu-id="85bf6-114">終了時に、呼び出し元によってプッシュされたすべてのパラメーターをポップして、スタックを復元する必要があります。</span><span class="sxs-lookup"><span data-stu-id="85bf6-114">On exit, you must restore the stack by popping off all the parameters that were pushed by its caller.</span></span>  
  
 <span data-ttu-id="85bf6-115">`FunctionEnter` の実装では、ガベージコレクションが遅延するため、ブロックしないでください。</span><span class="sxs-lookup"><span data-stu-id="85bf6-115">The implementation of `FunctionEnter` should not block because it will delay garbage collection.</span></span> <span data-ttu-id="85bf6-116">スタックがガベージコレクションに対応していない可能性があるため、この実装ではガベージコレクションを実行しないようにしてください。</span><span class="sxs-lookup"><span data-stu-id="85bf6-116">The implementation should not attempt a garbage collection because the stack may not be in a garbage collection-friendly state.</span></span> <span data-ttu-id="85bf6-117">ガベージコレクションを実行しようとすると、ランタイムは `FunctionEnter` が返されるまでブロックします。</span><span class="sxs-lookup"><span data-stu-id="85bf6-117">If a garbage collection is attempted, the runtime will block until `FunctionEnter` returns.</span></span>  
  
 <span data-ttu-id="85bf6-118">また、`FunctionEnter` 関数は、マネージコードを呼び出さないようにするか、マネージメモリ割り当てを発生させることはできません。</span><span class="sxs-lookup"><span data-stu-id="85bf6-118">Also, the `FunctionEnter` function must not call into managed code or in any way cause a managed memory allocation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="85bf6-119">要件</span><span class="sxs-lookup"><span data-stu-id="85bf6-119">Requirements</span></span>  
 <span data-ttu-id="85bf6-120">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="85bf6-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="85bf6-121">**ヘッダー:** Corprof.idl</span><span class="sxs-lookup"><span data-stu-id="85bf6-121">**Header:** CorProf.idl</span></span>  
  
 <span data-ttu-id="85bf6-122">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="85bf6-122">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="85bf6-123">**.NET Framework のバージョン:** 1.1、1.0</span><span class="sxs-lookup"><span data-stu-id="85bf6-123">**.NET Framework Versions:** 1.1, 1.0</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="85bf6-124">関連項目</span><span class="sxs-lookup"><span data-stu-id="85bf6-124">See also</span></span>

- [<span data-ttu-id="85bf6-125">FunctionEnter2 関数</span><span class="sxs-lookup"><span data-stu-id="85bf6-125">FunctionEnter2 Function</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionenter2-function.md)
- [<span data-ttu-id="85bf6-126">FunctionLeave2 関数</span><span class="sxs-lookup"><span data-stu-id="85bf6-126">FunctionLeave2 Function</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionleave2-function.md)
- [<span data-ttu-id="85bf6-127">FunctionTailcall2 関数</span><span class="sxs-lookup"><span data-stu-id="85bf6-127">FunctionTailcall2 Function</span></span>](../../../../docs/framework/unmanaged-api/profiling/functiontailcall2-function.md)
- [<span data-ttu-id="85bf6-128">SetEnterLeaveFunctionHooks2 メソッド</span><span class="sxs-lookup"><span data-stu-id="85bf6-128">SetEnterLeaveFunctionHooks2 Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-setenterleavefunctionhooks2-method.md)
- [<span data-ttu-id="85bf6-129">グローバル静的関数のプロファイル</span><span class="sxs-lookup"><span data-stu-id="85bf6-129">Profiling Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-global-static-functions.md)
