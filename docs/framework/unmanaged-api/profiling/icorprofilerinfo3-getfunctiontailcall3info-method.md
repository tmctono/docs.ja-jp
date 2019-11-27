---
title: ICorProfilerInfo3::GetFunctionTailcall3Info メソッド
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo3.GetFunctionTailcall3Info Method
api_location:
- Mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo3::GetFunctionTailcall3Info
helpviewer_keywords:
- ICorProfilerInfo3::GetFunctionTailcall3Info method [.NET Framework profiling]
- GetFunctionTailcall3Info method [.NET Framework profiling]
ms.assetid: afdb5ac9-5bf5-4b91-b7cb-f81db23d7da3
topic_type:
- apiref
ms.openlocfilehash: e7a25fce945504cff0d07f499ae4bb79378e9f3a
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/23/2019
ms.locfileid: "74449693"
---
# <a name="icorprofilerinfo3getfunctiontailcall3info-method"></a><span data-ttu-id="fd5d8-102">ICorProfilerInfo3::GetFunctionTailcall3Info メソッド</span><span class="sxs-lookup"><span data-stu-id="fd5d8-102">ICorProfilerInfo3::GetFunctionTailcall3Info Method</span></span>
<span data-ttu-id="fd5d8-103">[FunctionTailcall3WithInfo](../../../../docs/framework/unmanaged-api/profiling/functiontailcall3withinfo-function.md)関数によってプロファイラーに報告される関数のスタックフレームを提供します。</span><span class="sxs-lookup"><span data-stu-id="fd5d8-103">Provides the stack frame of the function that is being reported to the profiler by the [FunctionTailcall3WithInfo](../../../../docs/framework/unmanaged-api/profiling/functiontailcall3withinfo-function.md) function.</span></span> <span data-ttu-id="fd5d8-104">このメソッドは、`FunctionTailcall3WithInfo` コールバック中にのみ呼び出すことができます。</span><span class="sxs-lookup"><span data-stu-id="fd5d8-104">This method can be called only during the `FunctionTailcall3WithInfo` callback.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fd5d8-105">構文</span><span class="sxs-lookup"><span data-stu-id="fd5d8-105">Syntax</span></span>  
  
```cpp  
HRESULT GetFunctionTailcall3Info(   
            [in]  FunctionID functionId,   
            [in]  COR_PRF_ELT_INFO eltInfo,  
            [out] COR_PRF_FRAME_INFO *pFrameInfo);  
```  
  
## <a name="parameters"></a><span data-ttu-id="fd5d8-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="fd5d8-106">Parameters</span></span>  
 `functionId`  
 <span data-ttu-id="fd5d8-107">からを返す関数の `FunctionID`。</span><span class="sxs-lookup"><span data-stu-id="fd5d8-107">[in] The `FunctionID` of the function that is returning.</span></span>  
  
 `eltInfo`  
 <span data-ttu-id="fd5d8-108">[in] 特定のスタック フレームに関する情報を表す不透明ハンドル。</span><span class="sxs-lookup"><span data-stu-id="fd5d8-108">[in] An opaque handle that represents information about a given stack frame.</span></span> <span data-ttu-id="fd5d8-109">プロファイラーは、`FunctionTailcall3WithInfo` 関数によってプロファイラーに与えられたのと同じ `eltInfo` を提供する必要があります。</span><span class="sxs-lookup"><span data-stu-id="fd5d8-109">The profiler should provide the same `eltInfo` that was given to the profiler by the `FunctionTailcall3WithInfo` function.</span></span>  
  
 `pFrameInfo`  
 <span data-ttu-id="fd5d8-110">[out] 特定のスタック フレームに関するジェネリック情報を表す不透明ハンドル。</span><span class="sxs-lookup"><span data-stu-id="fd5d8-110">[out] An opaque handle that represents generics information about a given stack frame.</span></span> <span data-ttu-id="fd5d8-111">このハンドルは、プロファイラーが `FunctionTailcall3WithInfo` メソッドを呼び出した `GetFunctionTailcall3Info` コールバック内でのみ有効です。</span><span class="sxs-lookup"><span data-stu-id="fd5d8-111">This handle is valid only during the `FunctionTailcall3WithInfo` callback in which the profiler called the `GetFunctionTailcall3Info` method.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="fd5d8-112">コメント</span><span class="sxs-lookup"><span data-stu-id="fd5d8-112">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fd5d8-113">要件</span><span class="sxs-lookup"><span data-stu-id="fd5d8-113">Requirements</span></span>  
 <span data-ttu-id="fd5d8-114">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fd5d8-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fd5d8-115">**ヘッダー** : CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="fd5d8-115">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="fd5d8-116">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="fd5d8-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="fd5d8-117">**.NET Framework のバージョン:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fd5d8-117">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fd5d8-118">参照</span><span class="sxs-lookup"><span data-stu-id="fd5d8-118">See also</span></span>

- [<span data-ttu-id="fd5d8-119">FunctionEnter3WithInfo</span><span class="sxs-lookup"><span data-stu-id="fd5d8-119">FunctionEnter3WithInfo</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionenter3withinfo-function.md)
- [<span data-ttu-id="fd5d8-120">FunctionLeave3WithInfo</span><span class="sxs-lookup"><span data-stu-id="fd5d8-120">FunctionLeave3WithInfo</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionleave3withinfo-function.md)
- [<span data-ttu-id="fd5d8-121">FunctionTailcall3WithInfo</span><span class="sxs-lookup"><span data-stu-id="fd5d8-121">FunctionTailcall3WithInfo</span></span>](../../../../docs/framework/unmanaged-api/profiling/functiontailcall3withinfo-function.md)
- [<span data-ttu-id="fd5d8-122">ICorProfilerInfo3 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="fd5d8-122">ICorProfilerInfo3 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-interface.md)
- [<span data-ttu-id="fd5d8-123">プロファイリングのインターフェイス</span><span class="sxs-lookup"><span data-stu-id="fd5d8-123">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
- [<span data-ttu-id="fd5d8-124">プロファイル</span><span class="sxs-lookup"><span data-stu-id="fd5d8-124">Profiling</span></span>](../../../../docs/framework/unmanaged-api/profiling/index.md)
