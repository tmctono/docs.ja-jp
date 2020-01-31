---
title: FunctionLeave 関数
ms.date: 03/30/2017
api_name:
- FunctionLeave
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- FunctionLeave
helpviewer_keywords:
- FunctionLeave function [.NET Framework profiling]
ms.assetid: 18e89f45-e068-426a-be16-9f53a4346860
topic_type:
- apiref
ms.openlocfilehash: a9ab8c81c995bbec41db217c904e03dd70351aee
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/29/2020
ms.locfileid: "76866885"
---
# <a name="functionleave-function"></a><span data-ttu-id="1bba9-102">FunctionLeave 関数</span><span class="sxs-lookup"><span data-stu-id="1bba9-102">FunctionLeave Function</span></span>
<span data-ttu-id="1bba9-103">関数が呼び出し元に戻りようとしていることをプロファイラーに通知します。</span><span class="sxs-lookup"><span data-stu-id="1bba9-103">Notifies the profiler that a function is about to return to the caller.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="1bba9-104">`FunctionLeave` 関数は、.NET Framework 2.0 では非推奨とされます。</span><span class="sxs-lookup"><span data-stu-id="1bba9-104">The `FunctionLeave` function is deprecated in the .NET Framework 2.0.</span></span> <span data-ttu-id="1bba9-105">これは引き続き機能しますが、パフォーマンスが低下します。</span><span class="sxs-lookup"><span data-stu-id="1bba9-105">It will continue to work, but will incur a performance penalty.</span></span> <span data-ttu-id="1bba9-106">代わりに、 [FunctionLeave2](functionleave2-function.md)関数を使用してください。</span><span class="sxs-lookup"><span data-stu-id="1bba9-106">Use the [FunctionLeave2](functionleave2-function.md) function instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1bba9-107">構文</span><span class="sxs-lookup"><span data-stu-id="1bba9-107">Syntax</span></span>  
  
```cpp  
void __stdcall FunctionLeave (  
    [in] FunctionID funcID  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1bba9-108">パラメーター</span><span class="sxs-lookup"><span data-stu-id="1bba9-108">Parameters</span></span>

- `funcID`

  <span data-ttu-id="1bba9-109">\[] を返す関数の識別子。</span><span class="sxs-lookup"><span data-stu-id="1bba9-109">\[in] The identifier of the function that is returning.</span></span>

## <a name="remarks"></a><span data-ttu-id="1bba9-110">Remarks</span><span class="sxs-lookup"><span data-stu-id="1bba9-110">Remarks</span></span>  
 <span data-ttu-id="1bba9-111">`FunctionLeave` 関数はコールバックです。実装する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1bba9-111">The `FunctionLeave` function is a callback; you must implement it.</span></span> <span data-ttu-id="1bba9-112">実装では、`__declspec`(`naked`) ストレージクラス属性を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1bba9-112">The implementation must use the `__declspec`(`naked`) storage-class attribute.</span></span>  
  
 <span data-ttu-id="1bba9-113">この関数を呼び出す前に、実行エンジンはレジスタを保存しません。</span><span class="sxs-lookup"><span data-stu-id="1bba9-113">The execution engine does not save any registers before calling this function.</span></span>  
  
- <span data-ttu-id="1bba9-114">入力時には、浮動小数点単位 (FPU) に含まれるすべてのレジスタを含め、使用するすべてのレジスタを保存する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1bba9-114">On entry, you must save all registers that you use, including those in the floating-point unit (FPU).</span></span>  
  
- <span data-ttu-id="1bba9-115">終了時に、呼び出し元によってプッシュされたすべてのパラメーターをポップして、スタックを復元する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1bba9-115">On exit, you must restore the stack by popping off all the parameters that were pushed by its caller.</span></span>  
  
 <span data-ttu-id="1bba9-116">`FunctionLeave` の実装では、ガベージコレクションが遅延するため、ブロックしないでください。</span><span class="sxs-lookup"><span data-stu-id="1bba9-116">The implementation of `FunctionLeave` should not block because it will delay garbage collection.</span></span> <span data-ttu-id="1bba9-117">スタックがガベージコレクションに対応していない可能性があるため、この実装ではガベージコレクションを実行しないようにしてください。</span><span class="sxs-lookup"><span data-stu-id="1bba9-117">The implementation should not attempt a garbage collection because the stack may not be in a garbage collection-friendly state.</span></span> <span data-ttu-id="1bba9-118">ガベージコレクションを実行しようとすると、ランタイムは `FunctionLeave` が返されるまでブロックします。</span><span class="sxs-lookup"><span data-stu-id="1bba9-118">If a garbage collection is attempted, the runtime will block until `FunctionLeave` returns.</span></span>  
  
 <span data-ttu-id="1bba9-119">また、`FunctionLeave` 関数は、マネージコードを呼び出さないようにするか、マネージメモリ割り当てを発生させることはできません。</span><span class="sxs-lookup"><span data-stu-id="1bba9-119">Also, the `FunctionLeave` function must not call into managed code or in any way cause a managed memory allocation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1bba9-120">要件</span><span class="sxs-lookup"><span data-stu-id="1bba9-120">Requirements</span></span>  
 <span data-ttu-id="1bba9-121">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1bba9-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1bba9-122">**ヘッダー:** Corprof.idl</span><span class="sxs-lookup"><span data-stu-id="1bba9-122">**Header:** CorProf.idl</span></span>  
  
 <span data-ttu-id="1bba9-123">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1bba9-123">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="1bba9-124">**.NET Framework のバージョン:** 1.1、1.0</span><span class="sxs-lookup"><span data-stu-id="1bba9-124">**.NET Framework Versions:** 1.1, 1.0</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1bba9-125">関連項目</span><span class="sxs-lookup"><span data-stu-id="1bba9-125">See also</span></span>

- [<span data-ttu-id="1bba9-126">FunctionEnter2 関数</span><span class="sxs-lookup"><span data-stu-id="1bba9-126">FunctionEnter2 Function</span></span>](functionenter2-function.md)
- [<span data-ttu-id="1bba9-127">FunctionLeave2 関数</span><span class="sxs-lookup"><span data-stu-id="1bba9-127">FunctionLeave2 Function</span></span>](functionleave2-function.md)
- [<span data-ttu-id="1bba9-128">FunctionTailcall2 関数</span><span class="sxs-lookup"><span data-stu-id="1bba9-128">FunctionTailcall2 Function</span></span>](functiontailcall2-function.md)
- [<span data-ttu-id="1bba9-129">SetEnterLeaveFunctionHooks2 メソッド</span><span class="sxs-lookup"><span data-stu-id="1bba9-129">SetEnterLeaveFunctionHooks2 Method</span></span>](icorprofilerinfo2-setenterleavefunctionhooks2-method.md)
- [<span data-ttu-id="1bba9-130">グローバル静的関数のプロファイル</span><span class="sxs-lookup"><span data-stu-id="1bba9-130">Profiling Global Static Functions</span></span>](profiling-global-static-functions.md)
