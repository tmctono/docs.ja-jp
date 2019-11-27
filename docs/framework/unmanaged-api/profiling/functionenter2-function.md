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
ms.openlocfilehash: f4deec3e2b49b5cd6a924af8024e775c5c549f97
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/23/2019
ms.locfileid: "74440854"
---
# <a name="functionenter2-function"></a><span data-ttu-id="c32a9-102">FunctionEnter2 関数</span><span class="sxs-lookup"><span data-stu-id="c32a9-102">FunctionEnter2 Function</span></span>
<span data-ttu-id="c32a9-103">コントロールが関数に渡されていることをプロファイラーに通知し、スタックフレームと関数の引数に関する情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="c32a9-103">Notifies the profiler that control is being passed to a function and provides information about the stack frame and function arguments.</span></span> <span data-ttu-id="c32a9-104">この関数は、 [Functionenter](../../../../docs/framework/unmanaged-api/profiling/functionenter-function.md)関数よりも優先されます。</span><span class="sxs-lookup"><span data-stu-id="c32a9-104">This function supersedes the [FunctionEnter](../../../../docs/framework/unmanaged-api/profiling/functionenter-function.md) function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c32a9-105">構文</span><span class="sxs-lookup"><span data-stu-id="c32a9-105">Syntax</span></span>  
  
```cpp  
void __stdcall FunctionEnter2 (  
    [in]  FunctionID                       funcId,   
    [in]  UINT_PTR                         clientData,   
    [in]  COR_PRF_FRAME_INFO               func,   
    [in]  COR_PRF_FUNCTION_ARGUMENT_INFO  *argumentInfo  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c32a9-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="c32a9-106">Parameters</span></span>  
 `funcId`  
 <span data-ttu-id="c32a9-107">からコントロールが渡される関数の識別子。</span><span class="sxs-lookup"><span data-stu-id="c32a9-107">[in] The identifier of the function to which control is passed.</span></span>  
  
 `clientData`  
 <span data-ttu-id="c32a9-108">からマップされた関数の識別子。これは、プロファイラーが以前に[Functionidmapper](../../../../docs/framework/unmanaged-api/profiling/functionidmapper-function.md)関数を使用して指定したものです。</span><span class="sxs-lookup"><span data-stu-id="c32a9-108">[in] The remapped function identifier, which the profiler previously specified by using the [FunctionIDMapper](../../../../docs/framework/unmanaged-api/profiling/functionidmapper-function.md) function.</span></span>  
  
 `func`  
 <span data-ttu-id="c32a9-109">からスタックフレームに関する情報を指す `COR_PRF_FRAME_INFO` 値。</span><span class="sxs-lookup"><span data-stu-id="c32a9-109">[in] A `COR_PRF_FRAME_INFO` value that points to information about the stack frame.</span></span>  
  
 <span data-ttu-id="c32a9-110">プロファイラーは、これを[ICorProfilerInfo2:: GetFunctionInfo2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getfunctioninfo2-method.md)メソッドの実行エンジンに渡すことができる不透明なハンドルとして処理する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c32a9-110">The profiler should treat this as an opaque handle that can be passed back to the execution engine in the [ICorProfilerInfo2::GetFunctionInfo2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getfunctioninfo2-method.md) method.</span></span>  
  
 `argumentInfo`  
 <span data-ttu-id="c32a9-111">から関数の引数のメモリ内の場所を指定する[COR_PRF_FUNCTION_ARGUMENT_INFO](../../../../docs/framework/unmanaged-api/profiling/cor-prf-function-argument-info-structure.md)構造体へのポインター。</span><span class="sxs-lookup"><span data-stu-id="c32a9-111">[in] A pointer to a [COR_PRF_FUNCTION_ARGUMENT_INFO](../../../../docs/framework/unmanaged-api/profiling/cor-prf-function-argument-info-structure.md) structure that specifies the locations in memory of the function's arguments.</span></span>  
  
 <span data-ttu-id="c32a9-112">引数情報にアクセスするには、`COR_PRF_ENABLE_FUNCTION_ARGS` フラグを設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c32a9-112">In order to access argument information, the `COR_PRF_ENABLE_FUNCTION_ARGS` flag must be set.</span></span> <span data-ttu-id="c32a9-113">プロファイラーは、 [ICorProfilerInfo:: SetEventMask](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-seteventmask-method.md)メソッドを使用してイベントフラグを設定できます。</span><span class="sxs-lookup"><span data-stu-id="c32a9-113">The profiler can use the [ICorProfilerInfo::SetEventMask](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-seteventmask-method.md) method to set the event flags.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c32a9-114">コメント</span><span class="sxs-lookup"><span data-stu-id="c32a9-114">Remarks</span></span>  
 <span data-ttu-id="c32a9-115">`func` パラメーターと `argumentInfo` パラメーターの値は、値が変更されるか、または破棄される可能性があるため、`FunctionEnter2` 関数から制御が戻った後に無効になります。</span><span class="sxs-lookup"><span data-stu-id="c32a9-115">The values of the `func` and `argumentInfo` parameters are not valid after the `FunctionEnter2` function returns because the values may change or be destroyed.</span></span>  
  
 <span data-ttu-id="c32a9-116">`FunctionEnter2` 関数はコールバックです。実装する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c32a9-116">The `FunctionEnter2` function is a callback; you must implement it.</span></span> <span data-ttu-id="c32a9-117">実装では、`__declspec`(`naked`) ストレージクラス属性を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c32a9-117">The implementation must use the `__declspec`(`naked`) storage-class attribute.</span></span>  
  
 <span data-ttu-id="c32a9-118">この関数を呼び出す前に、実行エンジンはレジスタを保存しません。</span><span class="sxs-lookup"><span data-stu-id="c32a9-118">The execution engine does not save any registers before calling this function.</span></span>  
  
- <span data-ttu-id="c32a9-119">入力時には、浮動小数点単位 (FPU) に含まれるすべてのレジスタを含め、使用するすべてのレジスタを保存する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c32a9-119">On entry, you must save all registers that you use, including those in the floating-point unit (FPU).</span></span>  
  
- <span data-ttu-id="c32a9-120">終了時に、呼び出し元によってプッシュされたすべてのパラメーターをポップして、スタックを復元する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c32a9-120">On exit, you must restore the stack by popping off all the parameters that were pushed by its caller.</span></span>  
  
 <span data-ttu-id="c32a9-121">`FunctionEnter2` の実装では、ガベージコレクションが遅延するため、ブロックしないでください。</span><span class="sxs-lookup"><span data-stu-id="c32a9-121">The implementation of `FunctionEnter2` should not block because it will delay garbage collection.</span></span> <span data-ttu-id="c32a9-122">スタックがガベージコレクションに対応していない可能性があるため、この実装ではガベージコレクションを実行しないようにしてください。</span><span class="sxs-lookup"><span data-stu-id="c32a9-122">The implementation should not attempt a garbage collection because the stack may not be in a garbage collection-friendly state.</span></span> <span data-ttu-id="c32a9-123">ガベージコレクションを実行しようとすると、ランタイムは `FunctionEnter2` が返されるまでブロックします。</span><span class="sxs-lookup"><span data-stu-id="c32a9-123">If a garbage collection is attempted, the runtime will block until `FunctionEnter2` returns.</span></span>  
  
 <span data-ttu-id="c32a9-124">また、`FunctionEnter2` 関数は、マネージコードを呼び出さないようにするか、マネージメモリ割り当てを発生させることはできません。</span><span class="sxs-lookup"><span data-stu-id="c32a9-124">Also, the `FunctionEnter2` function must not call into managed code or in any way cause a managed memory allocation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c32a9-125">要件</span><span class="sxs-lookup"><span data-stu-id="c32a9-125">Requirements</span></span>  
 <span data-ttu-id="c32a9-126">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c32a9-126">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c32a9-127">**ヘッダー:** Corprof.idl</span><span class="sxs-lookup"><span data-stu-id="c32a9-127">**Header:** CorProf.idl</span></span>  
  
 <span data-ttu-id="c32a9-128">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c32a9-128">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c32a9-129">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c32a9-129">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c32a9-130">関連項目</span><span class="sxs-lookup"><span data-stu-id="c32a9-130">See also</span></span>

- [<span data-ttu-id="c32a9-131">FunctionLeave2 関数</span><span class="sxs-lookup"><span data-stu-id="c32a9-131">FunctionLeave2 Function</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionleave2-function.md)
- [<span data-ttu-id="c32a9-132">FunctionTailcall2 関数</span><span class="sxs-lookup"><span data-stu-id="c32a9-132">FunctionTailcall2 Function</span></span>](../../../../docs/framework/unmanaged-api/profiling/functiontailcall2-function.md)
- [<span data-ttu-id="c32a9-133">SetEnterLeaveFunctionHooks2 メソッド</span><span class="sxs-lookup"><span data-stu-id="c32a9-133">SetEnterLeaveFunctionHooks2 Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-setenterleavefunctionhooks2-method.md)
- [<span data-ttu-id="c32a9-134">グローバル静的関数のプロファイル</span><span class="sxs-lookup"><span data-stu-id="c32a9-134">Profiling Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-global-static-functions.md)
