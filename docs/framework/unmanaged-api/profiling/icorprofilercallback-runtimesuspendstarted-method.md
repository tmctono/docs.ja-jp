---
title: ICorProfilerCallback::RuntimeSuspendStarted メソッド
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.RuntimeSuspendStarted
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::RuntimeSuspendStarted
helpviewer_keywords:
- ICorProfilerCallback::RuntimeSuspendStarted method [.NET Framework profiling]
- RuntimeSuspendStarted method [.NET Framework profiling]
ms.assetid: c8461cac-e31b-4efa-ad2c-26598173eb96
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: a5606a556dd7aeafe6d7a6408d236f2bee8dc773
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61992213"
---
# <a name="icorprofilercallbackruntimesuspendstarted-method"></a><span data-ttu-id="cd604-102">ICorProfilerCallback::RuntimeSuspendStarted メソッド</span><span class="sxs-lookup"><span data-stu-id="cd604-102">ICorProfilerCallback::RuntimeSuspendStarted Method</span></span>
<span data-ttu-id="cd604-103">ランタイムのすべてのスレッドを中断しようとして、ランタイムがプロファイラーに通知します。</span><span class="sxs-lookup"><span data-stu-id="cd604-103">Notifies the profiler that the runtime is about to suspend all runtime threads.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cd604-104">構文</span><span class="sxs-lookup"><span data-stu-id="cd604-104">Syntax</span></span>  
  
```  
HRESULT RuntimeSuspendStarted(  
    [in] COR_PRF_SUSPEND_REASON suspendReason);  
```  
  
## <a name="parameters"></a><span data-ttu-id="cd604-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="cd604-105">Parameters</span></span>  
 `suspendReason`  
 <span data-ttu-id="cd604-106">[in]値、 [COR_PRF_SUSPEND_REASON](../../../../docs/framework/unmanaged-api/profiling/cor-prf-suspend-reason-enumeration.md)中断の理由を示す列挙体。</span><span class="sxs-lookup"><span data-stu-id="cd604-106">[in] A value of the [COR_PRF_SUSPEND_REASON](../../../../docs/framework/unmanaged-api/profiling/cor-prf-suspend-reason-enumeration.md) enumeration that indicates the reason for the suspension.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="cd604-107">Remarks</span><span class="sxs-lookup"><span data-stu-id="cd604-107">Remarks</span></span>  
 <span data-ttu-id="cd604-108">アンマネージ コードに含まれるすべてのランタイム スレッドがランタイムを再入力するまで実行を続行できます。</span><span class="sxs-lookup"><span data-stu-id="cd604-108">All runtime threads that are in unmanaged code are allowed to continue running until they try to re-enter the runtime.</span></span> <span data-ttu-id="cd604-109">その時点で、中断されます、ランタイムが再開されるまでです。</span><span class="sxs-lookup"><span data-stu-id="cd604-109">At that point they will also be suspended until the runtime resumes.</span></span> <span data-ttu-id="cd604-110">これは、ランタイムに入る新しいスレッドにも適用されます。</span><span class="sxs-lookup"><span data-stu-id="cd604-110">This also applies to new threads that enter the runtime.</span></span> <span data-ttu-id="cd604-111">ランタイムのすべてのスレッドは、割り込み可能なコードにある既にまたは割り込み可能なコードに到達するときに中断するように求められる場合はすぐにいずれかの中断です。</span><span class="sxs-lookup"><span data-stu-id="cd604-111">All threads in the runtime are either suspended immediately if they are already in interruptible code, or they are asked to suspend when they reach interruptible code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cd604-112">必要条件</span><span class="sxs-lookup"><span data-stu-id="cd604-112">Requirements</span></span>  
 <span data-ttu-id="cd604-113">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="cd604-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cd604-114">**ヘッダー:** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="cd604-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="cd604-115">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="cd604-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="cd604-116">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cd604-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cd604-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="cd604-117">See also</span></span>

- [<span data-ttu-id="cd604-118">ICorProfilerCallback インターフェイス</span><span class="sxs-lookup"><span data-stu-id="cd604-118">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [<span data-ttu-id="cd604-119">RuntimeSuspendAborted メソッド</span><span class="sxs-lookup"><span data-stu-id="cd604-119">RuntimeSuspendAborted Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimesuspendaborted-method.md)
- [<span data-ttu-id="cd604-120">RuntimeSuspendFinished メソッド</span><span class="sxs-lookup"><span data-stu-id="cd604-120">RuntimeSuspendFinished Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimesuspendfinished-method.md)
