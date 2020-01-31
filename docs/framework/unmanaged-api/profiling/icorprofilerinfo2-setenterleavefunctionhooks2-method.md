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
ms.openlocfilehash: 7eac42e1d8132ca9e6d6c6b43efd43b88c1e5d3d
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/29/2020
ms.locfileid: "76868578"
---
# <a name="icorprofilerinfo2setenterleavefunctionhooks2-method"></a><span data-ttu-id="7a490-102">ICorProfilerInfo2::SetEnterLeaveFunctionHooks2 メソッド</span><span class="sxs-lookup"><span data-stu-id="7a490-102">ICorProfilerInfo2::SetEnterLeaveFunctionHooks2 Method</span></span>
<span data-ttu-id="7a490-103">マネージ関数の "enter"、"leave"、および "tailcall" の各フックの更新バージョンで呼び出されるプロファイラー実装関数を指定します。</span><span class="sxs-lookup"><span data-stu-id="7a490-103">Specifies profiler-implemented functions to be called on the updated versions of the "enter", "leave", and "tailcall" hooks of managed functions.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7a490-104">構文</span><span class="sxs-lookup"><span data-stu-id="7a490-104">Syntax</span></span>  
  
```cpp  
HRESULT SetEnterLeaveFunctionHooks2(  
    [in] FunctionEnter2    *pFuncEnter,  
    [in] FunctionLeave2    *pFuncLeave,  
    [in] FunctionTailcall2 *pFuncTailcall);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7a490-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="7a490-105">Parameters</span></span>  
 `pFuncEnter`  
 <span data-ttu-id="7a490-106">から[FunctionEnter2](functionenter2-function.md)コールバックとして使用される実装へのポインター。</span><span class="sxs-lookup"><span data-stu-id="7a490-106">[in] A pointer to the implementation to be used as the [FunctionEnter2](functionenter2-function.md) callback.</span></span>  
  
 `pFuncLeave`  
 <span data-ttu-id="7a490-107">から[FunctionLeave2](functionleave2-function.md)コールバックとして使用される実装へのポインター。</span><span class="sxs-lookup"><span data-stu-id="7a490-107">[in] A pointer to the implementation to be used as the [FunctionLeave2](functionleave2-function.md) callback.</span></span>  
  
 `pFuncTailcall`  
 <span data-ttu-id="7a490-108">から[FunctionTailcall2](functiontailcall2-function.md)コールバックとして使用される実装へのポインター。</span><span class="sxs-lookup"><span data-stu-id="7a490-108">[in] A pointer to the implementation to be used as the [FunctionTailcall2](functiontailcall2-function.md) callback.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7a490-109">Remarks</span><span class="sxs-lookup"><span data-stu-id="7a490-109">Remarks</span></span>  
 <span data-ttu-id="7a490-110">`SetEnterLeaveFunctionHooks2` メソッドは、 [ICorProfilerInfo:: SetEnterLeaveFunctionHooks](icorprofilerinfo-setenterleavefunctionhooks-method.md)メソッドに似ています。</span><span class="sxs-lookup"><span data-stu-id="7a490-110">The `SetEnterLeaveFunctionHooks2` method is similar to the [ICorProfilerInfo::SetEnterLeaveFunctionHooks](icorprofilerinfo-setenterleavefunctionhooks-method.md) method.</span></span> <span data-ttu-id="7a490-111">前者を使用して、enter/leave/tailcall コールバックの新しいバージョンとして使用する関数を指定します。後者の場合は、以前のバージョンの enter/leave/tailcall コールバックとして使用する関数を指定します。</span><span class="sxs-lookup"><span data-stu-id="7a490-111">Use the former to specify functions to be used as the newer versions of the enter/leave/tailcall callbacks, and the latter to specify functions to be used as the older versions of the enter/leave/tailcall callbacks.</span></span>  
  
 <span data-ttu-id="7a490-112">コールバックのセットは一度に1つしかアクティブにできません。</span><span class="sxs-lookup"><span data-stu-id="7a490-112">Only one set of callbacks may be active at a time.</span></span> <span data-ttu-id="7a490-113">したがって、プロファイラーが `ICorProfilerInfo::SetEnterLeaveFunctionHooks` と `SetEnterLeaveFunctionHooks2`の両方を呼び出すと、`SetEnterLeaveFunctionHooks2` が使用されます。</span><span class="sxs-lookup"><span data-stu-id="7a490-113">Thus, if a profiler calls both `ICorProfilerInfo::SetEnterLeaveFunctionHooks` and `SetEnterLeaveFunctionHooks2`, `SetEnterLeaveFunctionHooks2` is used.</span></span>  
  
 <span data-ttu-id="7a490-114">`SetEnterLeaveFunctionHooks2` メソッドは、プロファイラーの[ICorProfilerCallback:: Initialize](icorprofilercallback-initialize-method.md)コールバックからのみ呼び出すことができます。</span><span class="sxs-lookup"><span data-stu-id="7a490-114">The `SetEnterLeaveFunctionHooks2` method may be called only from the profiler's [ICorProfilerCallback::Initialize](icorprofilercallback-initialize-method.md) callback.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7a490-115">要件</span><span class="sxs-lookup"><span data-stu-id="7a490-115">Requirements</span></span>  
 <span data-ttu-id="7a490-116">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7a490-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7a490-117">**ヘッダー** : CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="7a490-117">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="7a490-118">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7a490-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7a490-119">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7a490-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7a490-120">関連項目</span><span class="sxs-lookup"><span data-stu-id="7a490-120">See also</span></span>

- [<span data-ttu-id="7a490-121">ICorProfilerInfo インターフェイス</span><span class="sxs-lookup"><span data-stu-id="7a490-121">ICorProfilerInfo Interface</span></span>](icorprofilerinfo-interface.md)
- [<span data-ttu-id="7a490-122">ICorProfilerInfo2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="7a490-122">ICorProfilerInfo2 Interface</span></span>](icorprofilerinfo2-interface.md)
