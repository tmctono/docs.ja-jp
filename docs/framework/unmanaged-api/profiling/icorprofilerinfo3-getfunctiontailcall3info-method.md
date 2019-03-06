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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: b3d5d3808f51f921bd3e0c94942a1fb07a35d876
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/06/2019
ms.locfileid: "57487812"
---
# <a name="icorprofilerinfo3getfunctiontailcall3info-method"></a><span data-ttu-id="6ea9c-102">ICorProfilerInfo3::GetFunctionTailcall3Info メソッド</span><span class="sxs-lookup"><span data-stu-id="6ea9c-102">ICorProfilerInfo3::GetFunctionTailcall3Info Method</span></span>
<span data-ttu-id="6ea9c-103">によってプロファイラーに報告される関数のスタック フレームを提供します、 [FunctionTailcall3WithInfo](../../../../docs/framework/unmanaged-api/profiling/functiontailcall3withinfo-function.md)関数。</span><span class="sxs-lookup"><span data-stu-id="6ea9c-103">Provides the stack frame of the function that is being reported to the profiler by the [FunctionTailcall3WithInfo](../../../../docs/framework/unmanaged-api/profiling/functiontailcall3withinfo-function.md) function.</span></span> <span data-ttu-id="6ea9c-104">このメソッドは、`FunctionTailcall3WithInfo` コールバック中にのみ呼び出すことができます。</span><span class="sxs-lookup"><span data-stu-id="6ea9c-104">This method can be called only during the `FunctionTailcall3WithInfo` callback.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6ea9c-105">構文</span><span class="sxs-lookup"><span data-stu-id="6ea9c-105">Syntax</span></span>  
  
```  
HRESULT GetFunctionTailcall3Info(   
            [in]  FunctionID functionId,   
            [in]  COR_PRF_ELT_INFO eltInfo,  
            [out] COR_PRF_FRAME_INFO *pFrameInfo);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6ea9c-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="6ea9c-106">Parameters</span></span>  
 `functionId`  
 <span data-ttu-id="6ea9c-107">[in]`FunctionID`を返す関数。</span><span class="sxs-lookup"><span data-stu-id="6ea9c-107">[in] The `FunctionID` of the function that is returning.</span></span>  
  
 `eltInfo`  
 <span data-ttu-id="6ea9c-108">[in] 特定のスタック フレームに関する情報を表す不透明ハンドル。</span><span class="sxs-lookup"><span data-stu-id="6ea9c-108">[in] An opaque handle that represents information about a given stack frame.</span></span> <span data-ttu-id="6ea9c-109">プロファイラーを提供する必要があります、同じ`eltInfo`によってプロファイラーに指定されたです、`FunctionTailcall3WithInfo`関数。</span><span class="sxs-lookup"><span data-stu-id="6ea9c-109">The profiler should provide the same `eltInfo` that was given to the profiler by the `FunctionTailcall3WithInfo` function.</span></span>  
  
 `pFrameInfo`  
 <span data-ttu-id="6ea9c-110">[out] 特定のスタック フレームに関するジェネリック情報を表す不透明ハンドル。</span><span class="sxs-lookup"><span data-stu-id="6ea9c-110">[out] An opaque handle that represents generics information about a given stack frame.</span></span> <span data-ttu-id="6ea9c-111">このハンドルは、プロファイラーが `FunctionTailcall3WithInfo` メソッドを呼び出した `GetFunctionTailcall3Info` コールバック内でのみ有効です。</span><span class="sxs-lookup"><span data-stu-id="6ea9c-111">This handle is valid only during the `FunctionTailcall3WithInfo` callback in which the profiler called the `GetFunctionTailcall3Info` method.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6ea9c-112">Remarks</span><span class="sxs-lookup"><span data-stu-id="6ea9c-112">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6ea9c-113">必要条件</span><span class="sxs-lookup"><span data-stu-id="6ea9c-113">Requirements</span></span>  
 <span data-ttu-id="6ea9c-114">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="6ea9c-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6ea9c-115">**ヘッダー:** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="6ea9c-115">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="6ea9c-116">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6ea9c-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6ea9c-117">**.NET Framework のバージョン:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6ea9c-117">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6ea9c-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="6ea9c-118">See also</span></span>
- [<span data-ttu-id="6ea9c-119">FunctionEnter3WithInfo</span><span class="sxs-lookup"><span data-stu-id="6ea9c-119">FunctionEnter3WithInfo</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionenter3withinfo-function.md)
- [<span data-ttu-id="6ea9c-120">FunctionLeave3WithInfo</span><span class="sxs-lookup"><span data-stu-id="6ea9c-120">FunctionLeave3WithInfo</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionleave3withinfo-function.md)
- [<span data-ttu-id="6ea9c-121">FunctionTailcall3WithInfo</span><span class="sxs-lookup"><span data-stu-id="6ea9c-121">FunctionTailcall3WithInfo</span></span>](../../../../docs/framework/unmanaged-api/profiling/functiontailcall3withinfo-function.md)
- [<span data-ttu-id="6ea9c-122">ICorProfilerInfo3 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="6ea9c-122">ICorProfilerInfo3 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-interface.md)
- [<span data-ttu-id="6ea9c-123">プロファイリングのインターフェイス</span><span class="sxs-lookup"><span data-stu-id="6ea9c-123">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
- [<span data-ttu-id="6ea9c-124">プロファイル</span><span class="sxs-lookup"><span data-stu-id="6ea9c-124">Profiling</span></span>](../../../../docs/framework/unmanaged-api/profiling/index.md)
