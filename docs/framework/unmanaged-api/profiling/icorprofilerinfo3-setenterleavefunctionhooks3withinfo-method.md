---
title: ICorProfilerInfo3::SetEnterLeaveFunctionHooks3WithInfo メソッド
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo3.SetEnterLeaveFunctionHooks3WithInfo Method
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo3::SetEnterLeaveFunctionHooks3WithInfo
helpviewer_keywords:
- SetEnterLeaveFunctionHooks3WithInfo method [.NET Framework profiling]
- ICorProfilerInfo3::SetEnterLeaveFunctionHooks3WithInfo method [.NET Framework profiling]
ms.assetid: ca8ea534-e441-47b8-be85-466410988c0a
topic_type:
- apiref
ms.openlocfilehash: d40cb424306535cc502d930dd61e6a1e254667da
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/08/2020
ms.locfileid: "84496179"
---
# <a name="icorprofilerinfo3setenterleavefunctionhooks3withinfo-method"></a><span data-ttu-id="a213b-102">ICorProfilerInfo3::SetEnterLeaveFunctionHooks3WithInfo メソッド</span><span class="sxs-lookup"><span data-stu-id="a213b-102">ICorProfilerInfo3::SetEnterLeaveFunctionHooks3WithInfo Method</span></span>
<span data-ttu-id="a213b-103">マネージ関数の[FunctionEnter3WithInfo](functionenter3withinfo-function.md)、 [FunctionLeave3WithInfo](functionleave3withinfo-function.md)、および[FunctionTailcall3WithInfo](functiontailcall3withinfo-function.md)フックで呼び出されるプロファイラー実装関数を指定します。</span><span class="sxs-lookup"><span data-stu-id="a213b-103">Specifies the profiler-implemented functions that will be called on the [FunctionEnter3WithInfo](functionenter3withinfo-function.md), [FunctionLeave3WithInfo](functionleave3withinfo-function.md), and [FunctionTailcall3WithInfo](functiontailcall3withinfo-function.md) hooks of managed functions.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a213b-104">構文</span><span class="sxs-lookup"><span data-stu-id="a213b-104">Syntax</span></span>  
  
```cpp  
HRESULT SetEnterLeaveFunctionHooks3WithInfo(  
            [in] FunctionEnter3WithInfo    *pFuncEnter3,  
            [in] FunctionLeave3withInfo    *pFuncLeave3,  
            [in] FunctionTailcall3WithInfo *pFuncTailcall3);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a213b-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="a213b-105">Parameters</span></span>  
 `pFuncEnter3`  
 <span data-ttu-id="a213b-106">からコールバックとして使用される実装へのポインター `FunctionEnter3WithInfo` 。</span><span class="sxs-lookup"><span data-stu-id="a213b-106">[in] A pointer to the implementation to be used as the `FunctionEnter3WithInfo` callback.</span></span>  
  
 `pFuncLeave3`  
 <span data-ttu-id="a213b-107">からコールバックとして使用される実装へのポインター `FunctionLeave3WithInfo` 。</span><span class="sxs-lookup"><span data-stu-id="a213b-107">[in] A pointer to the implementation to be used as the `FunctionLeave3WithInfo` callback.</span></span>  
  
 `pFuncTailcall3`  
 <span data-ttu-id="a213b-108">からコールバックとして使用される実装へのポインター `FunctionTailcall3WithInfo` 。</span><span class="sxs-lookup"><span data-stu-id="a213b-108">[in] A pointer to the implementation to be used as the `FunctionTailcall3WithInfo` callback.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a213b-109">解説</span><span class="sxs-lookup"><span data-stu-id="a213b-109">Remarks</span></span>  
 <span data-ttu-id="a213b-110">[FunctionEnter3WithInfo](functionenter3withinfo-function.md)、 [FunctionLeave3WithInfo](functionleave3withinfo-function.md)、および[FunctionTailcall3WithInfo](functiontailcall3withinfo-function.md)の各フックは、スタックフレームと引数の検査を提供します。</span><span class="sxs-lookup"><span data-stu-id="a213b-110">The [FunctionEnter3WithInfo](functionenter3withinfo-function.md), [FunctionLeave3WithInfo](functionleave3withinfo-function.md), and [FunctionTailcall3WithInfo](functiontailcall3withinfo-function.md) hooks provide stack frame and argument inspection.</span></span> <span data-ttu-id="a213b-111">この情報にアクセスするには、 `COR_PRF_ENABLE_FUNCTION_ARGS` 、 `COR_PRF_ENABLE_FUNCTION_RETVAL` 、および/または `COR_PRF_ENABLE_FRAME_INFO` フラグを設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a213b-111">To access that information, the `COR_PRF_ENABLE_FUNCTION_ARGS`, `COR_PRF_ENABLE_FUNCTION_RETVAL`, and/or `COR_PRF_ENABLE_FRAME_INFO` flags have to be set.</span></span> <span data-ttu-id="a213b-112">プロファイラーは、 [ICorProfilerInfo:: SetEventMask](icorprofilerinfo-seteventmask-method.md)メソッドを使用してイベントフラグを設定し、メソッドを使用し `SetEnterLeaveFunctionHooks3WithInfo` てこの関数の実装を登録できます。</span><span class="sxs-lookup"><span data-stu-id="a213b-112">The profiler can use the [ICorProfilerInfo::SetEventMask](icorprofilerinfo-seteventmask-method.md) method to set the event flags, and then use the `SetEnterLeaveFunctionHooks3WithInfo` method to register your implementation of this function.</span></span>  
  
 <span data-ttu-id="a213b-113">コールバックのセットは一度に1つしかアクティブにできません。また、最新バージョンが優先されます。</span><span class="sxs-lookup"><span data-stu-id="a213b-113">Only one set of callbacks may be active at a time, and the newest version takes precedence.</span></span> <span data-ttu-id="a213b-114">したがって、プロファイラーが[SetEnterLeaveFunctionHooks2](icorprofilerinfo2-setenterleavefunctionhooks2-method.md)との両方を呼び出すと `SetEnterLeaveFunctionHooks3WithInfo` 、 `SetEnterLeaveFunctionHooks3WithInfo` が使用されます。</span><span class="sxs-lookup"><span data-stu-id="a213b-114">Therefore, if a profiler calls both [SetEnterLeaveFunctionHooks2](icorprofilerinfo2-setenterleavefunctionhooks2-method.md) and `SetEnterLeaveFunctionHooks3WithInfo`, `SetEnterLeaveFunctionHooks3WithInfo` is used.</span></span>  
  
 <span data-ttu-id="a213b-115">メソッドは、 `SetEnterLeaveFunctionHooks3WithInfo` プロファイラーの[ICorProfilerCallback:: Initialize](icorprofilercallback-initialize-method.md)コールバックからのみ呼び出すことができます。</span><span class="sxs-lookup"><span data-stu-id="a213b-115">The `SetEnterLeaveFunctionHooks3WithInfo` method may be called only from the profiler's [ICorProfilerCallback::Initialize](icorprofilercallback-initialize-method.md) callback.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a213b-116">要件</span><span class="sxs-lookup"><span data-stu-id="a213b-116">Requirements</span></span>  
 <span data-ttu-id="a213b-117">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a213b-117">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a213b-118">**ヘッダー** : CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="a213b-118">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="a213b-119">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a213b-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a213b-120">**.NET Framework のバージョン:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a213b-120">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a213b-121">関連項目</span><span class="sxs-lookup"><span data-stu-id="a213b-121">See also</span></span>

- [<span data-ttu-id="a213b-122">SetEnterLeaveFunctionHooks3</span><span class="sxs-lookup"><span data-stu-id="a213b-122">SetEnterLeaveFunctionHooks3</span></span>](icorprofilerinfo3-setenterleavefunctionhooks3-method.md)
- [<span data-ttu-id="a213b-123">FunctionEnter3</span><span class="sxs-lookup"><span data-stu-id="a213b-123">FunctionEnter3</span></span>](functionenter3-function.md)
- [<span data-ttu-id="a213b-124">FunctionLeave3</span><span class="sxs-lookup"><span data-stu-id="a213b-124">FunctionLeave3</span></span>](functionleave3-function.md)
- [<span data-ttu-id="a213b-125">FunctionTailcall3</span><span class="sxs-lookup"><span data-stu-id="a213b-125">FunctionTailcall3</span></span>](functiontailcall3-function.md)
- [<span data-ttu-id="a213b-126">FunctionEnter3WithInfo</span><span class="sxs-lookup"><span data-stu-id="a213b-126">FunctionEnter3WithInfo</span></span>](functionenter3withinfo-function.md)
- [<span data-ttu-id="a213b-127">FunctionLeave3WithInfo</span><span class="sxs-lookup"><span data-stu-id="a213b-127">FunctionLeave3WithInfo</span></span>](functionleave3withinfo-function.md)
- [<span data-ttu-id="a213b-128">FunctionTailcall3WithInfo</span><span class="sxs-lookup"><span data-stu-id="a213b-128">FunctionTailcall3WithInfo</span></span>](functiontailcall3withinfo-function.md)
- [<span data-ttu-id="a213b-129">グローバル静的関数のプロファイル</span><span class="sxs-lookup"><span data-stu-id="a213b-129">Profiling Global Static Functions</span></span>](profiling-global-static-functions.md)
- [<span data-ttu-id="a213b-130">ICorProfilerInfo3 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="a213b-130">ICorProfilerInfo3 Interface</span></span>](icorprofilerinfo3-interface.md)
- [<span data-ttu-id="a213b-131">プロファイリングのインターフェイス</span><span class="sxs-lookup"><span data-stu-id="a213b-131">Profiling Interfaces</span></span>](profiling-interfaces.md)
- [<span data-ttu-id="a213b-132">プロファイル</span><span class="sxs-lookup"><span data-stu-id="a213b-132">Profiling</span></span>](index.md)
