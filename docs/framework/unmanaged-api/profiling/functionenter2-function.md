---
title: FunctionEnter2 関数
ms.date: 03/30/2017
api_name:
- FunctionEnter2
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- FunctionEnter2
helpviewer_keywords:
- FunctionEnter2 function [.NET Framework profiling]
ms.assetid: ce7a21f9-0ca3-4b92-bc4b-bb803cae3f51
topic_type:
- apiref
ms.openlocfilehash: 9aeb7a294beb10f9c2968e6161c72fdc362c4991
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177060"
---
# <a name="functionenter2-function"></a><span data-ttu-id="3ca1c-102">FunctionEnter2 関数</span><span class="sxs-lookup"><span data-stu-id="3ca1c-102">FunctionEnter2 Function</span></span>
<span data-ttu-id="3ca1c-103">コントロールが関数に渡されることをプロファイラーに通知し、スタック フレームと関数の引数に関する情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="3ca1c-103">Notifies the profiler that control is being passed to a function and provides information about the stack frame and function arguments.</span></span> <span data-ttu-id="3ca1c-104">この関数は[関数の関数を置](functionenter-function.md)き換えます。</span><span class="sxs-lookup"><span data-stu-id="3ca1c-104">This function supersedes the [FunctionEnter](functionenter-function.md) function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3ca1c-105">構文</span><span class="sxs-lookup"><span data-stu-id="3ca1c-105">Syntax</span></span>  
  
```cpp  
void __stdcall FunctionEnter2 (  
    [in]  FunctionID                       funcId,
    [in]  UINT_PTR                         clientData,
    [in]  COR_PRF_FRAME_INFO               func,
    [in]  COR_PRF_FUNCTION_ARGUMENT_INFO  *argumentInfo  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3ca1c-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="3ca1c-106">Parameters</span></span>

- `funcId`

  <span data-ttu-id="3ca1c-107">\[in] コントロールの受け渡し先の関数の識別子。</span><span class="sxs-lookup"><span data-stu-id="3ca1c-107">\[in] The identifier of the function to which control is passed.</span></span>

- `clientData`

  <span data-ttu-id="3ca1c-108">\[in] 再マップされた関数識別子。 [FunctionIDMapper](functionidmapper-function.md)</span><span class="sxs-lookup"><span data-stu-id="3ca1c-108">\[in] The remapped function identifier, which the profiler previously specified by using the [FunctionIDMapper](functionidmapper-function.md) function.</span></span>
  
- `func`

  <span data-ttu-id="3ca1c-109">\[in]`COR_PRF_FRAME_INFO`スタック フレームに関する情報を指す値。</span><span class="sxs-lookup"><span data-stu-id="3ca1c-109">\[in] A `COR_PRF_FRAME_INFO` value that points to information about the stack frame.</span></span>
  
  <span data-ttu-id="3ca1c-110">プロファイラーは、[これを ICorProfilerInfo2::GetFunctionInfo2](icorprofilerinfo2-getfunctioninfo2-method.md)メソッドの実行エンジンに返すことができる不透明なハンドルとして扱う必要があります。</span><span class="sxs-lookup"><span data-stu-id="3ca1c-110">The profiler should treat this as an opaque handle that can be passed back to the execution engine in the [ICorProfilerInfo2::GetFunctionInfo2](icorprofilerinfo2-getfunctioninfo2-method.md) method.</span></span>  
  
- `argumentInfo`

  <span data-ttu-id="3ca1c-111">\[in] 関数の引数のメモリ内の位置を指定する[COR_PRF_FUNCTION_ARGUMENT_INFO](cor-prf-function-argument-info-structure.md)構造体へのポインター。</span><span class="sxs-lookup"><span data-stu-id="3ca1c-111">\[in] A pointer to a [COR_PRF_FUNCTION_ARGUMENT_INFO](cor-prf-function-argument-info-structure.md) structure that specifies the locations in memory of the function's arguments.</span></span>

  <span data-ttu-id="3ca1c-112">引数情報にアクセスするには、フラグを`COR_PRF_ENABLE_FUNCTION_ARGS`設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3ca1c-112">In order to access argument information, the `COR_PRF_ENABLE_FUNCTION_ARGS` flag must be set.</span></span> <span data-ttu-id="3ca1c-113">プロファイラーは、イベント フラグを設定するのに[は、](icorprofilerinfo-seteventmask-method.md)メソッドを使用できます。</span><span class="sxs-lookup"><span data-stu-id="3ca1c-113">The profiler can use the [ICorProfilerInfo::SetEventMask](icorprofilerinfo-seteventmask-method.md) method to set the event flags.</span></span>

## <a name="remarks"></a><span data-ttu-id="3ca1c-114">解説</span><span class="sxs-lookup"><span data-stu-id="3ca1c-114">Remarks</span></span>  
 <span data-ttu-id="3ca1c-115">値が変更されたり`func`破棄`argumentInfo`されたりする可能性があるため、`FunctionEnter2`関数が戻った後は、 および パラメーターの値は無効になります。</span><span class="sxs-lookup"><span data-stu-id="3ca1c-115">The values of the `func` and `argumentInfo` parameters are not valid after the `FunctionEnter2` function returns because the values may change or be destroyed.</span></span>  
  
 <span data-ttu-id="3ca1c-116">関数`FunctionEnter2`はコールバックです。それを実装する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3ca1c-116">The `FunctionEnter2` function is a callback; you must implement it.</span></span> <span data-ttu-id="3ca1c-117">実装では、 ( `__declspec``naked`) ストレージ クラス属性を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3ca1c-117">The implementation must use the `__declspec`(`naked`) storage-class attribute.</span></span>  
  
 <span data-ttu-id="3ca1c-118">実行エンジンは、この関数を呼び出す前にレジスタを保存しません。</span><span class="sxs-lookup"><span data-stu-id="3ca1c-118">The execution engine does not save any registers before calling this function.</span></span>  
  
- <span data-ttu-id="3ca1c-119">入力時には、使用するすべてのレジスタ (浮動小数点単位 (FPU) 内のレジスタも含む) を保存する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3ca1c-119">On entry, you must save all registers that you use, including those in the floating-point unit (FPU).</span></span>  
  
- <span data-ttu-id="3ca1c-120">終了時に、呼び出し元によってプッシュされたすべてのパラメーターをポップオフしてスタックを復元する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3ca1c-120">On exit, you must restore the stack by popping off all the parameters that were pushed by its caller.</span></span>  
  
 <span data-ttu-id="3ca1c-121">の実装`FunctionEnter2`はガベージ コレクションを遅延するため、ブロックしないでください。</span><span class="sxs-lookup"><span data-stu-id="3ca1c-121">The implementation of `FunctionEnter2` should not block because it will delay garbage collection.</span></span> <span data-ttu-id="3ca1c-122">スタックがガベージ コレクションに優しい状態ではない可能性があるため、実装はガベージ コレクションを試行しないでください。</span><span class="sxs-lookup"><span data-stu-id="3ca1c-122">The implementation should not attempt a garbage collection because the stack may not be in a garbage collection-friendly state.</span></span> <span data-ttu-id="3ca1c-123">ガベージ コレクションが試行されると、ランタイムは、戻るまで`FunctionEnter2`ブロックします。</span><span class="sxs-lookup"><span data-stu-id="3ca1c-123">If a garbage collection is attempted, the runtime will block until `FunctionEnter2` returns.</span></span>  
  
 <span data-ttu-id="3ca1c-124">また、この`FunctionEnter2`関数はマネージ コードを呼び出したり、マネージ メモリ割り当てを引き起こしたりしないでください。</span><span class="sxs-lookup"><span data-stu-id="3ca1c-124">Also, the `FunctionEnter2` function must not call into managed code or in any way cause a managed memory allocation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3ca1c-125">必要条件</span><span class="sxs-lookup"><span data-stu-id="3ca1c-125">Requirements</span></span>  
 <span data-ttu-id="3ca1c-126">**:**「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3ca1c-126">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3ca1c-127">**ヘッダー:** コルプロフ.idl</span><span class="sxs-lookup"><span data-stu-id="3ca1c-127">**Header:** CorProf.idl</span></span>  
  
 <span data-ttu-id="3ca1c-128">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3ca1c-128">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3ca1c-129">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3ca1c-129">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3ca1c-130">関連項目</span><span class="sxs-lookup"><span data-stu-id="3ca1c-130">See also</span></span>

- [<span data-ttu-id="3ca1c-131">FunctionLeave2 関数</span><span class="sxs-lookup"><span data-stu-id="3ca1c-131">FunctionLeave2 Function</span></span>](functionleave2-function.md)
- [<span data-ttu-id="3ca1c-132">FunctionTailcall2 関数</span><span class="sxs-lookup"><span data-stu-id="3ca1c-132">FunctionTailcall2 Function</span></span>](functiontailcall2-function.md)
- [<span data-ttu-id="3ca1c-133">SetEnterLeaveFunctionHooks2 メソッド</span><span class="sxs-lookup"><span data-stu-id="3ca1c-133">SetEnterLeaveFunctionHooks2 Method</span></span>](icorprofilerinfo2-setenterleavefunctionhooks2-method.md)
- [<span data-ttu-id="3ca1c-134">グローバル静的関数のプロファイル</span><span class="sxs-lookup"><span data-stu-id="3ca1c-134">Profiling Global Static Functions</span></span>](profiling-global-static-functions.md)
