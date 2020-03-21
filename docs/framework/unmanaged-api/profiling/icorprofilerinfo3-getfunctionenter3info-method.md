---
title: ICorProfilerInfo3::GetFunctionEnter3Info メソッド
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo3.GetFunctionEnter3Info Method
api_location:
- Mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo3::GetFunctionEnter3Info
helpviewer_keywords:
- GetFunctionEnter3Info method [.NET Framework profiling]
- ICorProfilerInfo3::GetFunctionEnter3Info method [.NET Framework profiling]
ms.assetid: 542c7c65-dd56-4651-b76f-5db2465e4a15
topic_type:
- apiref
ms.openlocfilehash: 50d16b8036144d6ede349149fa4ae37344064d8b
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177021"
---
# <a name="icorprofilerinfo3getfunctionenter3info-method"></a><span data-ttu-id="aa8e7-102">ICorProfilerInfo3::GetFunctionEnter3Info メソッド</span><span class="sxs-lookup"><span data-stu-id="aa8e7-102">ICorProfilerInfo3::GetFunctionEnter3Info Method</span></span>
<span data-ttu-id="aa8e7-103">関数によってプロファイラーに報告される関数のスタック フレームと引数情報を提供します、 [FunctionEnter3WithInfo](functionenter3withinfo-function.md)関数です。</span><span class="sxs-lookup"><span data-stu-id="aa8e7-103">Provides the stack frame and argument information of the function that is being reported to the profiler by the [FunctionEnter3WithInfo](functionenter3withinfo-function.md) function.</span></span> <span data-ttu-id="aa8e7-104">このメソッドは、`FunctionEnter3WithInfo` コールバック中にのみ呼び出すことができます。</span><span class="sxs-lookup"><span data-stu-id="aa8e7-104">This method can be called only during the `FunctionEnter3WithInfo` callback.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="aa8e7-105">構文</span><span class="sxs-lookup"><span data-stu-id="aa8e7-105">Syntax</span></span>  
  
```cpp  
HRESULT GetFunctionEnter3Info(  
            [in]  FunctionID functionId,
            [in]  COR_PRF_ELT_INFO eltInfo,  
            [out] COR_PRF_FRAME_INFO *pFrameInfo,  
            [in, out] ULONG *pcbArgumentInfo,  
            [out, size_is(*pcbArgumentInfo)]  
                  COR_PRF_FUNCTION_ARGUMENT_INFO *pArgumentInfo);  
```  
  
## <a name="parameters"></a><span data-ttu-id="aa8e7-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="aa8e7-106">Parameters</span></span>  
 `functionId`  
 <span data-ttu-id="aa8e7-107">[in] 入力される関数の `FunctionID`。</span><span class="sxs-lookup"><span data-stu-id="aa8e7-107">[in] The `FunctionID` of the function that is being entered.</span></span>  
  
 `eltInfo`  
 <span data-ttu-id="aa8e7-108">[in] 特定のスタック フレームに関する情報を表す不透明ハンドル。</span><span class="sxs-lookup"><span data-stu-id="aa8e7-108">[in] An opaque handle that represents information about a given stack frame.</span></span> <span data-ttu-id="aa8e7-109">プロファイラーは`eltInfo`[、関数によって](functionenter3withinfo-function.md)与えられたものと同じを提供する必要があります。</span><span class="sxs-lookup"><span data-stu-id="aa8e7-109">The profiler should provide the same `eltInfo` that it was given by the [FunctionEnter3WithInfo](functionenter3withinfo-function.md) function.</span></span>  
  
 `pFrameInfo`  
 <span data-ttu-id="aa8e7-110">[out] 特定のスタック フレームに関するジェネリック情報を表す不透明ハンドル。</span><span class="sxs-lookup"><span data-stu-id="aa8e7-110">[out] An opaque handle that represents generics information about a given stack frame.</span></span> <span data-ttu-id="aa8e7-111">このハンドルは、プロファイラーが `FunctionEnter3WithInfo` メソッドを呼び出した `GetFunctionEnter3Info` コールバック内でのみ有効です。</span><span class="sxs-lookup"><span data-stu-id="aa8e7-111">This handle is valid only during the `FunctionEnter3WithInfo` callback in which the profiler called the `GetFunctionEnter3Info` method.</span></span>  
  
 `pcbArgumentInfo`  
 <span data-ttu-id="aa8e7-112">[イン、アウト][COR_PRF_FUNCTION_ARGUMENT_INFO](cor-prf-function-argument-info-structure.md)構造体の合計サイズ (バイト単位) へのポインター ( および、 が`pArgumentInfo`指す引数範囲の追加[のCOR_PRF_FUNCTION_ARGUMENT_RANGE](cor-prf-function-argument-range-structure.md)構造体を含む )。</span><span class="sxs-lookup"><span data-stu-id="aa8e7-112">[in, out] A pointer to the total size, in bytes, of the [COR_PRF_FUNCTION_ARGUMENT_INFO](cor-prf-function-argument-info-structure.md) structure (plus any additional [COR_PRF_FUNCTION_ARGUMENT_RANGE](cor-prf-function-argument-range-structure.md) structures for the argument ranges pointed to by `pArgumentInfo`).</span></span> <span data-ttu-id="aa8e7-113">指定されたサイズの大きさが十分でない場合、ERROR_INSUFFICIENT_BUFFER が戻り、必要なサイズが `pcbArgumentInfo` に格納されます。</span><span class="sxs-lookup"><span data-stu-id="aa8e7-113">If the specified size is not enough, ERROR_INSUFFICIENT_BUFFER is returned and the expected size is stored in `pcbArgumentInfo`.</span></span> <span data-ttu-id="aa8e7-114">`GetFunctionEnter3Info` を呼び出して `*pcbArgumentInfo` の必要な値を取得するには、`*pcbArgumentInfo` を 0 に、`pArgumentInfo` を NULL にそれぞれ設定します。</span><span class="sxs-lookup"><span data-stu-id="aa8e7-114">To call `GetFunctionEnter3Info` just to retrieve the expected value for `*pcbArgumentInfo`, set `*pcbArgumentInfo`=0 and `pArgumentInfo`=NULL.</span></span>  
  
 `pArgumentInfo`  
 <span data-ttu-id="aa8e7-115">[アウト]メモリ内の関数の引数の位置を左から右の順序で記述する[COR_PRF_FUNCTION_ARGUMENT_INFO](cor-prf-function-argument-info-structure.md)構造体へのポインター。</span><span class="sxs-lookup"><span data-stu-id="aa8e7-115">[out] A pointer to a [COR_PRF_FUNCTION_ARGUMENT_INFO](cor-prf-function-argument-info-structure.md) structure that describes the locations of the function's arguments in memory, in left-to-right order.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="aa8e7-116">解説</span><span class="sxs-lookup"><span data-stu-id="aa8e7-116">Remarks</span></span>  
 <span data-ttu-id="aa8e7-117">プロファイラーは、調べている関数の `COR_PRF_FUNCTION_ARGUMENT_INFO` 構造体に十分な領域を割り当て、`pcbArgumentInfo` パラメーターでサイズを示す必要があります。</span><span class="sxs-lookup"><span data-stu-id="aa8e7-117">The profiler must allocate sufficient space for the `COR_PRF_FUNCTION_ARGUMENT_INFO` structure of the function that is being inspected, and must indicate the size in the `pcbArgumentInfo` parameter.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="aa8e7-118">必要条件</span><span class="sxs-lookup"><span data-stu-id="aa8e7-118">Requirements</span></span>  
 <span data-ttu-id="aa8e7-119">**:**「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="aa8e7-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="aa8e7-120">**ヘッダー** : CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="aa8e7-120">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="aa8e7-121">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="aa8e7-121">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="aa8e7-122">**.NET Framework のバージョン:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="aa8e7-122">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="aa8e7-123">関連項目</span><span class="sxs-lookup"><span data-stu-id="aa8e7-123">See also</span></span>

- [<span data-ttu-id="aa8e7-124">関数を入力します3ウィズインフォ</span><span class="sxs-lookup"><span data-stu-id="aa8e7-124">FunctionEnter3WithInfo</span></span>](functionenter3withinfo-function.md)
- [<span data-ttu-id="aa8e7-125">関数リーブ3ウィズインフォ</span><span class="sxs-lookup"><span data-stu-id="aa8e7-125">FunctionLeave3WithInfo</span></span>](functionleave3withinfo-function.md)
- [<span data-ttu-id="aa8e7-126">FunctionTailcall3WithInfo</span><span class="sxs-lookup"><span data-stu-id="aa8e7-126">FunctionTailcall3WithInfo</span></span>](functiontailcall3withinfo-function.md)
- [<span data-ttu-id="aa8e7-127">ICorProfilerInfo3 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="aa8e7-127">ICorProfilerInfo3 Interface</span></span>](icorprofilerinfo3-interface.md)
- [<span data-ttu-id="aa8e7-128">プロファイリングのインターフェイス</span><span class="sxs-lookup"><span data-stu-id="aa8e7-128">Profiling Interfaces</span></span>](profiling-interfaces.md)
- [<span data-ttu-id="aa8e7-129">プロファイリング</span><span class="sxs-lookup"><span data-stu-id="aa8e7-129">Profiling</span></span>](index.md)
