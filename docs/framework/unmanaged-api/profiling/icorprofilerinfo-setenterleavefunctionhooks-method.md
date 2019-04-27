---
title: ICorProfilerInfo::SetEnterLeaveFunctionHooks メソッド
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo.SetEnterLeaveFunctionHooks
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo::SetEnterLeaveFunctionHooks
helpviewer_keywords:
- SetEnterLeaveFunctionHooks method [.NET Framework profiling]
- ICorProfilerInfo::SetEnterLeaveFunctionHooks method [.NET Framework profiling]
ms.assetid: 72399636-c219-4ffd-8ac8-39432c9d4641
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: a2d45e98f3e7b71375b14c43c4bff4929bc79494
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61860938"
---
# <a name="icorprofilerinfosetenterleavefunctionhooks-method"></a><span data-ttu-id="038bf-102">ICorProfilerInfo::SetEnterLeaveFunctionHooks メソッド</span><span class="sxs-lookup"><span data-stu-id="038bf-102">ICorProfilerInfo::SetEnterLeaveFunctionHooks Method</span></span>
<span data-ttu-id="038bf-103">「入力」、「のまま」、およびマネージ関数の"tailcall"フックで呼び出されるプロファイラー実装関数を指定します。</span><span class="sxs-lookup"><span data-stu-id="038bf-103">Specifies profiler-implemented functions to be called on "enter", "leave", and "tailcall" hooks of managed functions.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="038bf-104">構文</span><span class="sxs-lookup"><span data-stu-id="038bf-104">Syntax</span></span>  
  
```  
HRESULT SetEnterLeaveFunctionHooks(  
    [in] FunctionEnter    *pFuncEnter,  
    [in] FunctionLeave    *pFuncLeave,  
    [in] FunctionTailcall *pFuncTailcall);  
```  
  
## <a name="parameters"></a><span data-ttu-id="038bf-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="038bf-105">Parameters</span></span>  
 `pFuncEnter`  
 <span data-ttu-id="038bf-106">[in]として使用する実装へのポインター、 [FunctionEnter](../../../../docs/framework/unmanaged-api/profiling/functionenter-function.md)コールバック。</span><span class="sxs-lookup"><span data-stu-id="038bf-106">[in] A pointer to the implementation to be used as the [FunctionEnter](../../../../docs/framework/unmanaged-api/profiling/functionenter-function.md) callback.</span></span>  
  
 `pFuncLeave`  
 <span data-ttu-id="038bf-107">[in]として使用する実装へのポインター、 [FunctionLeave](../../../../docs/framework/unmanaged-api/profiling/functionleave-function.md)コールバック。</span><span class="sxs-lookup"><span data-stu-id="038bf-107">[in] A pointer to the implementation to be used as the [FunctionLeave](../../../../docs/framework/unmanaged-api/profiling/functionleave-function.md) callback.</span></span>  
  
 `pFuncTailcall`  
 <span data-ttu-id="038bf-108">[in]として使用する実装へのポインター、 [FunctionTailcall](../../../../docs/framework/unmanaged-api/profiling/functiontailcall-function.md)コールバック。</span><span class="sxs-lookup"><span data-stu-id="038bf-108">[in] A pointer to the implementation to be used as the [FunctionTailcall](../../../../docs/framework/unmanaged-api/profiling/functiontailcall-function.md) callback.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="038bf-109">Remarks</span><span class="sxs-lookup"><span data-stu-id="038bf-109">Remarks</span></span>  
 <span data-ttu-id="038bf-110">.NET framework version 1.0 では、各関数ポインターをその対応するコールバックを無効にする null にすることができます。</span><span class="sxs-lookup"><span data-stu-id="038bf-110">In the .NET Framework version 1.0, each function pointer can be null to disable that corresponding callback.</span></span>  
  
 <span data-ttu-id="038bf-111">一度にアクティブにできる 1 つだけの一連のコールバック。</span><span class="sxs-lookup"><span data-stu-id="038bf-111">Only one set of callbacks can be active at a time.</span></span> <span data-ttu-id="038bf-112">そのため、プロファイラーは、両方を呼び出す場合`SetEnterLeaveFunctionHooks`と[icorprofilerinfo 2::setenterleavefunctionhooks2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-setenterleavefunctionhooks2-method.md)、し`SetEnterLeaveFunctionHooks2`が優先されます。</span><span class="sxs-lookup"><span data-stu-id="038bf-112">Thus, if a profiler calls both `SetEnterLeaveFunctionHooks` and [ICorProfilerInfo2::SetEnterLeaveFunctionHooks2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-setenterleavefunctionhooks2-method.md), then `SetEnterLeaveFunctionHooks2` takes precedence.</span></span>  
  
 <span data-ttu-id="038bf-113">`SetEnterLeaveFunctionHooks`メソッドは、プロファイラーからのみ呼び出すことが[icorprofilercallback::initialize](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-initialize-method.md)コールバック。</span><span class="sxs-lookup"><span data-stu-id="038bf-113">The `SetEnterLeaveFunctionHooks` method can be called only from the profiler's [ICorProfilerCallback::Initialize](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-initialize-method.md) callback.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="038bf-114">必要条件</span><span class="sxs-lookup"><span data-stu-id="038bf-114">Requirements</span></span>  
 <span data-ttu-id="038bf-115">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="038bf-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="038bf-116">**ヘッダー:** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="038bf-116">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="038bf-117">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="038bf-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="038bf-118">**.NET Framework のバージョン:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="038bf-118">**.NET Framework Versions:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="038bf-119">関連項目</span><span class="sxs-lookup"><span data-stu-id="038bf-119">See also</span></span>

- [<span data-ttu-id="038bf-120">ICorProfilerInfo インターフェイス</span><span class="sxs-lookup"><span data-stu-id="038bf-120">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
