---
title: ICorProfilerInfo2::SetEnterLeaveFunctionHooks2 メソッド
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo2.SetEnterLeaveFunctionHooks2
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo2::SetEnterLeaveFunctionHooks2
helpviewer_keywords:
- ICorProfilerInfo2::SetEnterLeaveFunctionHooks2 method [.NET Framework profiling]
- SetEnterLeaveFunctionHooks2 method [.NET Framework profiling]
ms.assetid: 3c26b3e7-f72b-48a5-bf8c-edc122523a4b
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: b9f95a404ce7124a76ee527cdc70ccccf103838b
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59076797"
---
# <a name="icorprofilerinfo2setenterleavefunctionhooks2-method"></a><span data-ttu-id="f266b-102">ICorProfilerInfo2::SetEnterLeaveFunctionHooks2 メソッド</span><span class="sxs-lookup"><span data-stu-id="f266b-102">ICorProfilerInfo2::SetEnterLeaveFunctionHooks2 Method</span></span>
<span data-ttu-id="f266b-103">更新されたバージョンの「入力」、「のまま」、およびマネージ関数の"tailcall"フックで呼び出されるプロファイラー実装関数を指定します。</span><span class="sxs-lookup"><span data-stu-id="f266b-103">Specifies profiler-implemented functions to be called on the updated versions of the "enter", "leave", and "tailcall" hooks of managed functions.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f266b-104">構文</span><span class="sxs-lookup"><span data-stu-id="f266b-104">Syntax</span></span>  
  
```  
HRESULT SetEnterLeaveFunctionHooks2(  
    [in] FunctionEnter2    *pFuncEnter,  
    [in] FunctionLeave2    *pFuncLeave,  
    [in] FunctionTailcall2 *pFuncTailcall);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f266b-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="f266b-105">Parameters</span></span>  
 `pFuncEnter`  
 <span data-ttu-id="f266b-106">[in]として使用する実装へのポインター、 [FunctionEnter2](../../../../docs/framework/unmanaged-api/profiling/functionenter2-function.md)コールバック。</span><span class="sxs-lookup"><span data-stu-id="f266b-106">[in] A pointer to the implementation to be used as the [FunctionEnter2](../../../../docs/framework/unmanaged-api/profiling/functionenter2-function.md) callback.</span></span>  
  
 `pFuncLeave`  
 <span data-ttu-id="f266b-107">[in]として使用する実装へのポインター、 [FunctionLeave2](../../../../docs/framework/unmanaged-api/profiling/functionleave2-function.md)コールバック。</span><span class="sxs-lookup"><span data-stu-id="f266b-107">[in] A pointer to the implementation to be used as the [FunctionLeave2](../../../../docs/framework/unmanaged-api/profiling/functionleave2-function.md) callback.</span></span>  
  
 `pFuncTailcall`  
 <span data-ttu-id="f266b-108">[in]として使用する実装へのポインター、 [FunctionTailcall2](../../../../docs/framework/unmanaged-api/profiling/functiontailcall2-function.md)コールバック。</span><span class="sxs-lookup"><span data-stu-id="f266b-108">[in] A pointer to the implementation to be used as the [FunctionTailcall2](../../../../docs/framework/unmanaged-api/profiling/functiontailcall2-function.md) callback.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f266b-109">Remarks</span><span class="sxs-lookup"><span data-stu-id="f266b-109">Remarks</span></span>  
 <span data-ttu-id="f266b-110">`SetEnterLeaveFunctionHooks2`メソッドは、 [icorprofilerinfo::setenterleavefunctionhooks](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-setenterleavefunctionhooks-method.md)メソッド。</span><span class="sxs-lookup"><span data-stu-id="f266b-110">The `SetEnterLeaveFunctionHooks2` method is similar to the [ICorProfilerInfo::SetEnterLeaveFunctionHooks](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-setenterleavefunctionhooks-method.md) method.</span></span> <span data-ttu-id="f266b-111">前者を使用して、tailcall/enter/leave のコールバックの以前のバージョンとして使用する関数を指定する tailcall/enter/leave のコールバックになり、後者の新しいバージョンとして使用する関数を指定します。</span><span class="sxs-lookup"><span data-stu-id="f266b-111">Use the former to specify functions to be used as the newer versions of the enter/leave/tailcall callbacks, and the latter to specify functions to be used as the older versions of the enter/leave/tailcall callbacks.</span></span>  
  
 <span data-ttu-id="f266b-112">一度に 1 つだけの一連のコールバックがアクティブな可能性があります。</span><span class="sxs-lookup"><span data-stu-id="f266b-112">Only one set of callbacks may be active at a time.</span></span> <span data-ttu-id="f266b-113">そのため、プロファイラーは、両方を呼び出す場合`ICorProfilerInfo::SetEnterLeaveFunctionHooks`と`SetEnterLeaveFunctionHooks2`、`SetEnterLeaveFunctionHooks2`使用されます。</span><span class="sxs-lookup"><span data-stu-id="f266b-113">Thus, if a profiler calls both `ICorProfilerInfo::SetEnterLeaveFunctionHooks` and `SetEnterLeaveFunctionHooks2`, `SetEnterLeaveFunctionHooks2` is used.</span></span>  
  
 <span data-ttu-id="f266b-114">`SetEnterLeaveFunctionHooks2`メソッドは、プロファイラーからのみ呼び出すことが[icorprofilercallback::initialize](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-initialize-method.md)コールバック。</span><span class="sxs-lookup"><span data-stu-id="f266b-114">The `SetEnterLeaveFunctionHooks2` method may be called only from the profiler's [ICorProfilerCallback::Initialize](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-initialize-method.md) callback.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f266b-115">必要条件</span><span class="sxs-lookup"><span data-stu-id="f266b-115">Requirements</span></span>  
 <span data-ttu-id="f266b-116">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="f266b-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f266b-117">**ヘッダー:** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="f266b-117">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="f266b-118">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f266b-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f266b-119">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f266b-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f266b-120">関連項目</span><span class="sxs-lookup"><span data-stu-id="f266b-120">See also</span></span>

- [<span data-ttu-id="f266b-121">ICorProfilerInfo インターフェイス</span><span class="sxs-lookup"><span data-stu-id="f266b-121">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
- [<span data-ttu-id="f266b-122">ICorProfilerInfo2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="f266b-122">ICorProfilerInfo2 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-interface.md)
