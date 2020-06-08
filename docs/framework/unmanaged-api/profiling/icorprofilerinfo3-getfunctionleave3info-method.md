---
title: ICorProfilerInfo3::GetFunctionLeave3Info メソッド
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo3.GetFunctionLeave3Info Method
api_location:
- Mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo3::GetFunctionLeave3Info
helpviewer_keywords:
- GetFunctionLeave3Info method [.NET Framework profiling]
- ICorProfilerInfo3::GetFunctionLeave3Info method [.NET Framework profiling]
ms.assetid: df7083d2-fd43-44c7-9ce5-912c25cef0ff
topic_type:
- apiref
ms.openlocfilehash: bab52d9179d7454cab4a47e1a2bfe80a49b00c2a
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/08/2020
ms.locfileid: "84502835"
---
# <a name="icorprofilerinfo3getfunctionleave3info-method"></a><span data-ttu-id="a3f1e-102">ICorProfilerInfo3::GetFunctionLeave3Info メソッド</span><span class="sxs-lookup"><span data-stu-id="a3f1e-102">ICorProfilerInfo3::GetFunctionLeave3Info Method</span></span>
<span data-ttu-id="a3f1e-103">[FunctionLeave3WithInfo function](functionleave3withinfo-function.md)関数によってプロファイラーに報告される関数のスタックフレームと戻り値を提供します。</span><span class="sxs-lookup"><span data-stu-id="a3f1e-103">Provides the stack frame and return value of the function that is being reported to the profiler by the [FunctionLeave3WithInfo function](functionleave3withinfo-function.md) function.</span></span> <span data-ttu-id="a3f1e-104">このメソッドは、`FunctionLeave3WithInfo` コールバック中にのみ呼び出すことができます。</span><span class="sxs-lookup"><span data-stu-id="a3f1e-104">This method can be called only during the `FunctionLeave3WithInfo` callback.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a3f1e-105">構文</span><span class="sxs-lookup"><span data-stu-id="a3f1e-105">Syntax</span></span>  
  
```cpp  
HRESULT GetFunctionLeave3Info(  
            [in]  FunctionID functionId,  
            [in]  COR_PRF_ELT_INFO eltInfo,  
            [out] COR_PRF_FRAME_INFO *pFrameInfo,  
            [out] COR_PRF_FUNCTION_ARGUMENT_RANGE *pRetvalRange);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a3f1e-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="a3f1e-106">Parameters</span></span>  
 `functionId`  
 <span data-ttu-id="a3f1e-107">からを `FunctionID` 返す関数の。</span><span class="sxs-lookup"><span data-stu-id="a3f1e-107">[in] The `FunctionID` of the function that is returning.</span></span>  
  
 `eltInfo`  
 <span data-ttu-id="a3f1e-108">[in] 特定のスタック フレームに関する情報を表す不透明ハンドル。</span><span class="sxs-lookup"><span data-stu-id="a3f1e-108">[in] An opaque handle that represents information about a given stack frame.</span></span> <span data-ttu-id="a3f1e-109">プロファイラーは、 `eltInfo` [FunctionLeave3WithInfo](functionleave3withinfo-function.md)関数によってプロファイラーに与えられたものと同じを提供する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a3f1e-109">The profiler should provide the same `eltInfo` that was given to the profiler by the [FunctionLeave3WithInfo](functionleave3withinfo-function.md) function.</span></span>  
  
 `pFrameInfo`  
 <span data-ttu-id="a3f1e-110">[out] 特定のスタック フレームに関するジェネリック情報を表す不透明ハンドル。</span><span class="sxs-lookup"><span data-stu-id="a3f1e-110">[out] An opaque handle that represents generics information about a given stack frame.</span></span> <span data-ttu-id="a3f1e-111">このハンドルは、プロファイラーが `FunctionLeave3WithInfo` メソッドを呼び出した `GetFunctionLeave3Info` コールバック内でのみ有効です。</span><span class="sxs-lookup"><span data-stu-id="a3f1e-111">This handle is valid only during the `FunctionLeave3WithInfo` callback in which the profiler called the `GetFunctionLeave3Info` method.</span></span>  
  
 `pRetvalRange`  
 <span data-ttu-id="a3f1e-112">入出力関数から返される値を格納している[COR_PRF_FUNCTION_ARGUMENT_RANGE](cor-prf-function-argument-range-structure.md)構造体へのポインター。</span><span class="sxs-lookup"><span data-stu-id="a3f1e-112">[out] A pointer to a [COR_PRF_FUNCTION_ARGUMENT_RANGE](cor-prf-function-argument-range-structure.md) structure that contains the value that is returned from the function.</span></span> <span data-ttu-id="a3f1e-113">戻り値の情報にアクセスするには、 `COR_PRF_ENABLE_FUNCTION_RETVAL` フラグを設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a3f1e-113">To access return value information, the `COR_PRF_ENABLE_FUNCTION_RETVAL` flag must be set.</span></span> <span data-ttu-id="a3f1e-114">プロファイラーは、 [ICorProfilerInfo:: SetEventMask メソッド](icorprofilerinfo-seteventmask-method.md)を使用してイベントフラグを設定できます。</span><span class="sxs-lookup"><span data-stu-id="a3f1e-114">The profiler can use the [ICorProfilerInfo::SetEventMask method](icorprofilerinfo-seteventmask-method.md) to set the event flags.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a3f1e-115">解説</span><span class="sxs-lookup"><span data-stu-id="a3f1e-115">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a3f1e-116">必要条件</span><span class="sxs-lookup"><span data-stu-id="a3f1e-116">Requirements</span></span>  
 <span data-ttu-id="a3f1e-117">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a3f1e-117">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a3f1e-118">**ヘッダー** : CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="a3f1e-118">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="a3f1e-119">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a3f1e-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a3f1e-120">**.NET Framework のバージョン:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a3f1e-120">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a3f1e-121">関連項目</span><span class="sxs-lookup"><span data-stu-id="a3f1e-121">See also</span></span>

- [<span data-ttu-id="a3f1e-122">FunctionEnter3WithInfo</span><span class="sxs-lookup"><span data-stu-id="a3f1e-122">FunctionEnter3WithInfo</span></span>](functionenter3withinfo-function.md)
- [<span data-ttu-id="a3f1e-123">FunctionLeave3WithInfo</span><span class="sxs-lookup"><span data-stu-id="a3f1e-123">FunctionLeave3WithInfo</span></span>](functionleave3withinfo-function.md)
- [<span data-ttu-id="a3f1e-124">FunctionTailcall3WithInfo</span><span class="sxs-lookup"><span data-stu-id="a3f1e-124">FunctionTailcall3WithInfo</span></span>](functiontailcall3withinfo-function.md)
- [<span data-ttu-id="a3f1e-125">ICorProfilerInfo3 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="a3f1e-125">ICorProfilerInfo3 Interface</span></span>](icorprofilerinfo3-interface.md)
- [<span data-ttu-id="a3f1e-126">プロファイリングのインターフェイス</span><span class="sxs-lookup"><span data-stu-id="a3f1e-126">Profiling Interfaces</span></span>](profiling-interfaces.md)
- [<span data-ttu-id="a3f1e-127">プロファイル</span><span class="sxs-lookup"><span data-stu-id="a3f1e-127">Profiling</span></span>](index.md)
