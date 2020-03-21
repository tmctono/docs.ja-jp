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
ms.openlocfilehash: 5346792cb2a1309268cb4ba48625aa559777fbaf
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176995"
---
# <a name="icorprofilerinfo3getfunctiontailcall3info-method"></a><span data-ttu-id="fe52a-102">ICorProfilerInfo3::GetFunctionTailcall3Info メソッド</span><span class="sxs-lookup"><span data-stu-id="fe52a-102">ICorProfilerInfo3::GetFunctionTailcall3Info Method</span></span>
<span data-ttu-id="fe52a-103">関数によってプロファイラーに報告される関数のスタック フレーム[を](functiontailcall3withinfo-function.md)提供します。</span><span class="sxs-lookup"><span data-stu-id="fe52a-103">Provides the stack frame of the function that is being reported to the profiler by the [FunctionTailcall3WithInfo](functiontailcall3withinfo-function.md) function.</span></span> <span data-ttu-id="fe52a-104">このメソッドは、`FunctionTailcall3WithInfo` コールバック中にのみ呼び出すことができます。</span><span class="sxs-lookup"><span data-stu-id="fe52a-104">This method can be called only during the `FunctionTailcall3WithInfo` callback.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fe52a-105">構文</span><span class="sxs-lookup"><span data-stu-id="fe52a-105">Syntax</span></span>  
  
```cpp  
HRESULT GetFunctionTailcall3Info(
            [in]  FunctionID functionId,
            [in]  COR_PRF_ELT_INFO eltInfo,  
            [out] COR_PRF_FRAME_INFO *pFrameInfo);  
```  
  
## <a name="parameters"></a><span data-ttu-id="fe52a-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="fe52a-106">Parameters</span></span>  
 `functionId`  
 <span data-ttu-id="fe52a-107">[in]返`FunctionID`される関数の。</span><span class="sxs-lookup"><span data-stu-id="fe52a-107">[in] The `FunctionID` of the function that is returning.</span></span>  
  
 `eltInfo`  
 <span data-ttu-id="fe52a-108">[in] 特定のスタック フレームに関する情報を表す不透明ハンドル。</span><span class="sxs-lookup"><span data-stu-id="fe52a-108">[in] An opaque handle that represents information about a given stack frame.</span></span> <span data-ttu-id="fe52a-109">プロファイラーは、関数によって`eltInfo`プロファイラーに与えられたものと同`FunctionTailcall3WithInfo`じものを提供する必要があります。</span><span class="sxs-lookup"><span data-stu-id="fe52a-109">The profiler should provide the same `eltInfo` that was given to the profiler by the `FunctionTailcall3WithInfo` function.</span></span>  
  
 `pFrameInfo`  
 <span data-ttu-id="fe52a-110">[out] 特定のスタック フレームに関するジェネリック情報を表す不透明ハンドル。</span><span class="sxs-lookup"><span data-stu-id="fe52a-110">[out] An opaque handle that represents generics information about a given stack frame.</span></span> <span data-ttu-id="fe52a-111">このハンドルは、プロファイラーが `FunctionTailcall3WithInfo` メソッドを呼び出した `GetFunctionTailcall3Info` コールバック内でのみ有効です。</span><span class="sxs-lookup"><span data-stu-id="fe52a-111">This handle is valid only during the `FunctionTailcall3WithInfo` callback in which the profiler called the `GetFunctionTailcall3Info` method.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="fe52a-112">解説</span><span class="sxs-lookup"><span data-stu-id="fe52a-112">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fe52a-113">必要条件</span><span class="sxs-lookup"><span data-stu-id="fe52a-113">Requirements</span></span>  
 <span data-ttu-id="fe52a-114">**:**「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fe52a-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fe52a-115">**ヘッダー** : CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="fe52a-115">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="fe52a-116">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="fe52a-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="fe52a-117">**.NET Framework のバージョン:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fe52a-117">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fe52a-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="fe52a-118">See also</span></span>

- [<span data-ttu-id="fe52a-119">関数を入力します3ウィズインフォ</span><span class="sxs-lookup"><span data-stu-id="fe52a-119">FunctionEnter3WithInfo</span></span>](functionenter3withinfo-function.md)
- [<span data-ttu-id="fe52a-120">関数リーブ3ウィズインフォ</span><span class="sxs-lookup"><span data-stu-id="fe52a-120">FunctionLeave3WithInfo</span></span>](functionleave3withinfo-function.md)
- [<span data-ttu-id="fe52a-121">FunctionTailcall3WithInfo</span><span class="sxs-lookup"><span data-stu-id="fe52a-121">FunctionTailcall3WithInfo</span></span>](functiontailcall3withinfo-function.md)
- [<span data-ttu-id="fe52a-122">ICorProfilerInfo3 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="fe52a-122">ICorProfilerInfo3 Interface</span></span>](icorprofilerinfo3-interface.md)
- [<span data-ttu-id="fe52a-123">プロファイリングのインターフェイス</span><span class="sxs-lookup"><span data-stu-id="fe52a-123">Profiling Interfaces</span></span>](profiling-interfaces.md)
- [<span data-ttu-id="fe52a-124">プロファイリング</span><span class="sxs-lookup"><span data-stu-id="fe52a-124">Profiling</span></span>](index.md)
