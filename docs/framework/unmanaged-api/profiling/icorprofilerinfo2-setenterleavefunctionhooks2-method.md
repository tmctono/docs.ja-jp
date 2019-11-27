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
ms.openlocfilehash: 4068c8fee13a6086bc6b48bcc6d4117357062747
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/23/2019
ms.locfileid: "74449791"
---
# <a name="icorprofilerinfo2setenterleavefunctionhooks2-method"></a><span data-ttu-id="e6bac-102">ICorProfilerInfo2::SetEnterLeaveFunctionHooks2 メソッド</span><span class="sxs-lookup"><span data-stu-id="e6bac-102">ICorProfilerInfo2::SetEnterLeaveFunctionHooks2 Method</span></span>
<span data-ttu-id="e6bac-103">マネージ関数の "enter"、"leave"、および "tailcall" の各フックの更新バージョンで呼び出されるプロファイラー実装関数を指定します。</span><span class="sxs-lookup"><span data-stu-id="e6bac-103">Specifies profiler-implemented functions to be called on the updated versions of the "enter", "leave", and "tailcall" hooks of managed functions.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e6bac-104">構文</span><span class="sxs-lookup"><span data-stu-id="e6bac-104">Syntax</span></span>  
  
```cpp  
HRESULT SetEnterLeaveFunctionHooks2(  
    [in] FunctionEnter2    *pFuncEnter,  
    [in] FunctionLeave2    *pFuncLeave,  
    [in] FunctionTailcall2 *pFuncTailcall);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e6bac-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="e6bac-105">Parameters</span></span>  
 `pFuncEnter`  
 <span data-ttu-id="e6bac-106">から[FunctionEnter2](../../../../docs/framework/unmanaged-api/profiling/functionenter2-function.md)コールバックとして使用される実装へのポインター。</span><span class="sxs-lookup"><span data-stu-id="e6bac-106">[in] A pointer to the implementation to be used as the [FunctionEnter2](../../../../docs/framework/unmanaged-api/profiling/functionenter2-function.md) callback.</span></span>  
  
 `pFuncLeave`  
 <span data-ttu-id="e6bac-107">から[FunctionLeave2](../../../../docs/framework/unmanaged-api/profiling/functionleave2-function.md)コールバックとして使用される実装へのポインター。</span><span class="sxs-lookup"><span data-stu-id="e6bac-107">[in] A pointer to the implementation to be used as the [FunctionLeave2](../../../../docs/framework/unmanaged-api/profiling/functionleave2-function.md) callback.</span></span>  
  
 `pFuncTailcall`  
 <span data-ttu-id="e6bac-108">から[FunctionTailcall2](../../../../docs/framework/unmanaged-api/profiling/functiontailcall2-function.md)コールバックとして使用される実装へのポインター。</span><span class="sxs-lookup"><span data-stu-id="e6bac-108">[in] A pointer to the implementation to be used as the [FunctionTailcall2](../../../../docs/framework/unmanaged-api/profiling/functiontailcall2-function.md) callback.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e6bac-109">コメント</span><span class="sxs-lookup"><span data-stu-id="e6bac-109">Remarks</span></span>  
 <span data-ttu-id="e6bac-110">`SetEnterLeaveFunctionHooks2` メソッドは、 [ICorProfilerInfo:: SetEnterLeaveFunctionHooks](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-setenterleavefunctionhooks-method.md)メソッドに似ています。</span><span class="sxs-lookup"><span data-stu-id="e6bac-110">The `SetEnterLeaveFunctionHooks2` method is similar to the [ICorProfilerInfo::SetEnterLeaveFunctionHooks](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-setenterleavefunctionhooks-method.md) method.</span></span> <span data-ttu-id="e6bac-111">前者を使用して、enter/leave/tailcall コールバックの新しいバージョンとして使用する関数を指定します。後者の場合は、以前のバージョンの enter/leave/tailcall コールバックとして使用する関数を指定します。</span><span class="sxs-lookup"><span data-stu-id="e6bac-111">Use the former to specify functions to be used as the newer versions of the enter/leave/tailcall callbacks, and the latter to specify functions to be used as the older versions of the enter/leave/tailcall callbacks.</span></span>  
  
 <span data-ttu-id="e6bac-112">コールバックのセットは一度に1つしかアクティブにできません。</span><span class="sxs-lookup"><span data-stu-id="e6bac-112">Only one set of callbacks may be active at a time.</span></span> <span data-ttu-id="e6bac-113">したがって、プロファイラーが `ICorProfilerInfo::SetEnterLeaveFunctionHooks` と `SetEnterLeaveFunctionHooks2`の両方を呼び出すと、`SetEnterLeaveFunctionHooks2` が使用されます。</span><span class="sxs-lookup"><span data-stu-id="e6bac-113">Thus, if a profiler calls both `ICorProfilerInfo::SetEnterLeaveFunctionHooks` and `SetEnterLeaveFunctionHooks2`, `SetEnterLeaveFunctionHooks2` is used.</span></span>  
  
 <span data-ttu-id="e6bac-114">`SetEnterLeaveFunctionHooks2` メソッドは、プロファイラーの[ICorProfilerCallback:: Initialize](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-initialize-method.md)コールバックからのみ呼び出すことができます。</span><span class="sxs-lookup"><span data-stu-id="e6bac-114">The `SetEnterLeaveFunctionHooks2` method may be called only from the profiler's [ICorProfilerCallback::Initialize](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-initialize-method.md) callback.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e6bac-115">要件</span><span class="sxs-lookup"><span data-stu-id="e6bac-115">Requirements</span></span>  
 <span data-ttu-id="e6bac-116">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e6bac-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e6bac-117">**ヘッダー** : CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="e6bac-117">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="e6bac-118">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e6bac-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e6bac-119">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e6bac-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e6bac-120">参照</span><span class="sxs-lookup"><span data-stu-id="e6bac-120">See also</span></span>

- [<span data-ttu-id="e6bac-121">ICorProfilerInfo インターフェイス</span><span class="sxs-lookup"><span data-stu-id="e6bac-121">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
- [<span data-ttu-id="e6bac-122">ICorProfilerInfo2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="e6bac-122">ICorProfilerInfo2 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-interface.md)
