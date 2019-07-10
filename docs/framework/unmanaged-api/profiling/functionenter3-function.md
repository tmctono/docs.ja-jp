---
title: FunctionEnter3 関数
ms.date: 03/30/2017
api_name:
- FunctionEnter3
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- FunctionEnter3
helpviewer_keywords:
- FunctionEnter3 function [.NET Framework profiling]
ms.assetid: ef782c53-dae7-4990-b4ad-fddb1e690d4e
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 24c9077863ada4d1208f29755a70d2cf8abc1208
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67782699"
---
# <a name="functionenter3-function"></a><span data-ttu-id="7e248-102">FunctionEnter3 関数</span><span class="sxs-lookup"><span data-stu-id="7e248-102">FunctionEnter3 Function</span></span>
<span data-ttu-id="7e248-103">コントロールが関数に渡されることをプロファイラーに通知します。</span><span class="sxs-lookup"><span data-stu-id="7e248-103">Notifies the profiler that control is being passed to a function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7e248-104">構文</span><span class="sxs-lookup"><span data-stu-id="7e248-104">Syntax</span></span>  
  
```cpp  
void __stdcall FunctionEnter3(FunctionOrRemappedID functionOrRemappedID);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7e248-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="7e248-105">Parameters</span></span>  
 `functionOrRemappedID`  
 <span data-ttu-id="7e248-106">[in]コントロールが渡される関数の識別子。</span><span class="sxs-lookup"><span data-stu-id="7e248-106">[in] The identifier of the function to which control is passed.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7e248-107">Remarks</span><span class="sxs-lookup"><span data-stu-id="7e248-107">Remarks</span></span>  
 <span data-ttu-id="7e248-108">`FunctionEnter3`関数が呼び出されるがサポート引数検査しないのコールバック関数がプロファイラーに通知します。</span><span class="sxs-lookup"><span data-stu-id="7e248-108">The `FunctionEnter3` callback function notifies the profiler as functions are being called, but does not support argument inspection.</span></span> <span data-ttu-id="7e248-109">使用して、 [icorprofilerinfo 3::setenterleavefunctionhooks3 メソッド](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-setenterleavefunctionhooks3-method.md)をこの関数の実装を登録します。</span><span class="sxs-lookup"><span data-stu-id="7e248-109">Use the [ICorProfilerInfo3::SetEnterLeaveFunctionHooks3 method](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-setenterleavefunctionhooks3-method.md) to register your implementation of this function.</span></span>  
  
 <span data-ttu-id="7e248-110">`FunctionEnter3`関数は、コールバックは、これを実装する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7e248-110">The `FunctionEnter3` function is a callback; you must implement it.</span></span> <span data-ttu-id="7e248-111">実装を使用する必要があります、`__declspec(naked)`ストレージ クラス属性。</span><span class="sxs-lookup"><span data-stu-id="7e248-111">The implementation must use the `__declspec(naked)` storage-class attribute.</span></span>  
  
 <span data-ttu-id="7e248-112">実行エンジンは、この関数を呼び出す前に、レジスタを保存できません。</span><span class="sxs-lookup"><span data-stu-id="7e248-112">The execution engine does not save any registers before calling this function.</span></span>  
  
- <span data-ttu-id="7e248-113">項目で、浮動小数点ユニット (FPU) にあるなど、使用するすべてのレジスタを保存する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7e248-113">On entry, you must save all registers that you use, including those in the floating-point unit (FPU).</span></span>  
  
- <span data-ttu-id="7e248-114">終了時に、その呼び出し元によってプッシュされたすべてのパラメーターをポップしてスタックを復元する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7e248-114">On exit, you must restore the stack by popping off all the parameters that were pushed by its caller.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7e248-115">必要条件</span><span class="sxs-lookup"><span data-stu-id="7e248-115">Requirements</span></span>  
 <span data-ttu-id="7e248-116">**プラットフォーム:** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="7e248-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7e248-117">**ヘッダー:** CorProf.idl</span><span class="sxs-lookup"><span data-stu-id="7e248-117">**Header:** CorProf.idl</span></span>  
  
 <span data-ttu-id="7e248-118">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7e248-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7e248-119">**.NET Framework のバージョン:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7e248-119">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7e248-120">関連項目</span><span class="sxs-lookup"><span data-stu-id="7e248-120">See also</span></span>

- [<span data-ttu-id="7e248-121">FunctionLeave3</span><span class="sxs-lookup"><span data-stu-id="7e248-121">FunctionLeave3</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionleave3-function.md)
- [<span data-ttu-id="7e248-122">FunctionTailcall3</span><span class="sxs-lookup"><span data-stu-id="7e248-122">FunctionTailcall3</span></span>](../../../../docs/framework/unmanaged-api/profiling/functiontailcall3-function.md)
- [<span data-ttu-id="7e248-123">FunctionEnter3WithInfo</span><span class="sxs-lookup"><span data-stu-id="7e248-123">FunctionEnter3WithInfo</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionenter3withinfo-function.md)
- [<span data-ttu-id="7e248-124">FunctionLeave3WithInfo</span><span class="sxs-lookup"><span data-stu-id="7e248-124">FunctionLeave3WithInfo</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionleave3withinfo-function.md)
- [<span data-ttu-id="7e248-125">FunctionTailcall3WithInfo</span><span class="sxs-lookup"><span data-stu-id="7e248-125">FunctionTailcall3WithInfo</span></span>](../../../../docs/framework/unmanaged-api/profiling/functiontailcall3withinfo-function.md)
- [<span data-ttu-id="7e248-126">SetEnterLeaveFunctionHooks3</span><span class="sxs-lookup"><span data-stu-id="7e248-126">SetEnterLeaveFunctionHooks3</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-setenterleavefunctionhooks3-method.md)
- [<span data-ttu-id="7e248-127">SetEnterLeaveFunctionHooks3WithInfo</span><span class="sxs-lookup"><span data-stu-id="7e248-127">SetEnterLeaveFunctionHooks3WithInfo</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-setenterleavefunctionhooks3withinfo-method.md)
- [<span data-ttu-id="7e248-128">SetFunctionIDMapper</span><span class="sxs-lookup"><span data-stu-id="7e248-128">SetFunctionIDMapper</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-setfunctionidmapper-method.md)
- [<span data-ttu-id="7e248-129">SetFunctionIDMapper2</span><span class="sxs-lookup"><span data-stu-id="7e248-129">SetFunctionIDMapper2</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-setfunctionidmapper2-method.md)
- [<span data-ttu-id="7e248-130">グローバル静的関数のプロファイル</span><span class="sxs-lookup"><span data-stu-id="7e248-130">Profiling Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-global-static-functions.md)
