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
ms.openlocfilehash: e88f6356c2e29a1d8a9e49527c5921e8155c3ce4
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/29/2020
ms.locfileid: "76865884"
---
# <a name="icorprofilercallbackruntimesuspendstarted-method"></a><span data-ttu-id="0156b-102">ICorProfilerCallback::RuntimeSuspendStarted メソッド</span><span class="sxs-lookup"><span data-stu-id="0156b-102">ICorProfilerCallback::RuntimeSuspendStarted Method</span></span>
<span data-ttu-id="0156b-103">ランタイムがすべてのランタイムスレッドを中断しようとしていることをプロファイラーに通知します。</span><span class="sxs-lookup"><span data-stu-id="0156b-103">Notifies the profiler that the runtime is about to suspend all runtime threads.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0156b-104">構文</span><span class="sxs-lookup"><span data-stu-id="0156b-104">Syntax</span></span>  
  
```cpp  
HRESULT RuntimeSuspendStarted(  
    [in] COR_PRF_SUSPEND_REASON suspendReason);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0156b-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="0156b-105">Parameters</span></span>  
 `suspendReason`  
 <span data-ttu-id="0156b-106">から中断の理由を示す[COR_PRF_SUSPEND_REASON](cor-prf-suspend-reason-enumeration.md)列挙体の値。</span><span class="sxs-lookup"><span data-stu-id="0156b-106">[in] A value of the [COR_PRF_SUSPEND_REASON](cor-prf-suspend-reason-enumeration.md) enumeration that indicates the reason for the suspension.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0156b-107">コメント</span><span class="sxs-lookup"><span data-stu-id="0156b-107">Remarks</span></span>  
 <span data-ttu-id="0156b-108">アンマネージコード内のすべてのランタイムスレッドは、ランタイムを再入力しようとするまで実行を継続できます。</span><span class="sxs-lookup"><span data-stu-id="0156b-108">All runtime threads that are in unmanaged code are allowed to continue running until they try to re-enter the runtime.</span></span> <span data-ttu-id="0156b-109">その時点で、ランタイムが再開されるまで中断されます。</span><span class="sxs-lookup"><span data-stu-id="0156b-109">At that point they will also be suspended until the runtime resumes.</span></span> <span data-ttu-id="0156b-110">これは、ランタイムに入る新しいスレッドにも当てはまります。</span><span class="sxs-lookup"><span data-stu-id="0156b-110">This also applies to new threads that enter the runtime.</span></span> <span data-ttu-id="0156b-111">ランタイム内のすべてのスレッドは、割り込み可能なコードに既に存在する場合は直ちに中断されます。または、割り込み可能なコードになると中断するように求められます。</span><span class="sxs-lookup"><span data-stu-id="0156b-111">All threads in the runtime are either suspended immediately if they are already in interruptible code, or they are asked to suspend when they reach interruptible code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0156b-112">要件</span><span class="sxs-lookup"><span data-stu-id="0156b-112">Requirements</span></span>  
 <span data-ttu-id="0156b-113">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0156b-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0156b-114">**ヘッダー** : CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="0156b-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="0156b-115">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0156b-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0156b-116">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0156b-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0156b-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="0156b-117">See also</span></span>

- [<span data-ttu-id="0156b-118">ICorProfilerCallback インターフェイス</span><span class="sxs-lookup"><span data-stu-id="0156b-118">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
- [<span data-ttu-id="0156b-119">RuntimeSuspendAborted メソッド</span><span class="sxs-lookup"><span data-stu-id="0156b-119">RuntimeSuspendAborted Method</span></span>](icorprofilercallback-runtimesuspendaborted-method.md)
- [<span data-ttu-id="0156b-120">RuntimeSuspendFinished メソッド</span><span class="sxs-lookup"><span data-stu-id="0156b-120">RuntimeSuspendFinished Method</span></span>](icorprofilercallback-runtimesuspendfinished-method.md)
