---
title: ICorProfilerCallback::RuntimeSuspendFinished メソッド
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.RuntimeSuspendFinished
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::RuntimeSuspendFinished
helpviewer_keywords:
- ICorProfilerCallback::RuntimeSuspendFinished method [.NET Framework profiling]
- RuntimeSuspendFinished method [.NET Framework profiling]
ms.assetid: b7723f58-c55c-4399-9972-1bbf3b866694
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 6412f31417ead963e987e0c50ad46c78a77d367f
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67750855"
---
# <a name="icorprofilercallbackruntimesuspendfinished-method"></a><span data-ttu-id="9e1b3-102">ICorProfilerCallback::RuntimeSuspendFinished メソッド</span><span class="sxs-lookup"><span data-stu-id="9e1b3-102">ICorProfilerCallback::RuntimeSuspendFinished Method</span></span>
<span data-ttu-id="9e1b3-103">ランタイムでランタイムのすべてのスレッドの中断が完了したことをプロファイラーに通知します。</span><span class="sxs-lookup"><span data-stu-id="9e1b3-103">Notifies the profiler that the runtime has completed suspension of all runtime threads.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9e1b3-104">構文</span><span class="sxs-lookup"><span data-stu-id="9e1b3-104">Syntax</span></span>  
  
```cpp  
HRESULT RuntimeSuspendFinished();  
```  
  
## <a name="remarks"></a><span data-ttu-id="9e1b3-105">Remarks</span><span class="sxs-lookup"><span data-stu-id="9e1b3-105">Remarks</span></span>  
 <span data-ttu-id="9e1b3-106">アンマネージ コードに含まれるすべてのランタイム スレッドがランタイムを再入力するまで実行を続行できます。</span><span class="sxs-lookup"><span data-stu-id="9e1b3-106">All runtime threads that are in unmanaged code are allowed to continue running until they try to re-enter the runtime.</span></span> <span data-ttu-id="9e1b3-107">その時点で、中断されます、ランタイムが再開されるまでです。</span><span class="sxs-lookup"><span data-stu-id="9e1b3-107">At that point they will also be suspended until the runtime resumes.</span></span> <span data-ttu-id="9e1b3-108">これは、ランタイムに入る新しいスレッドにも適用されます。</span><span class="sxs-lookup"><span data-stu-id="9e1b3-108">This also applies to new threads that enter the runtime.</span></span> <span data-ttu-id="9e1b3-109">ランタイムのすべてのスレッドは、割り込み可能なコードにある既にまたは割り込み可能なコードに到達するときに中断するように求められる場合はすぐにいずれかの中断です。</span><span class="sxs-lookup"><span data-stu-id="9e1b3-109">All threads in the runtime are either suspended immediately if they are already in interruptible code, or they are asked to suspend when they reach interruptible code.</span></span>  
  
 <span data-ttu-id="9e1b3-110">`RuntimeSuspendFinished`コールバックと同じスレッドで発生することが保証されます、 [icorprofilercallback::runtimesuspendstarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimesuspendstarted-method.md)コールバック。</span><span class="sxs-lookup"><span data-stu-id="9e1b3-110">The `RuntimeSuspendFinished` callback is guaranteed to occur on the same thread as the [ICorProfilerCallback::RuntimeSuspendStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimesuspendstarted-method.md) callback.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9e1b3-111">必要条件</span><span class="sxs-lookup"><span data-stu-id="9e1b3-111">Requirements</span></span>  
 <span data-ttu-id="9e1b3-112">**プラットフォーム:** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="9e1b3-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9e1b3-113">**ヘッダー:** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="9e1b3-113">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="9e1b3-114">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9e1b3-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9e1b3-115">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9e1b3-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9e1b3-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="9e1b3-116">See also</span></span>

- [<span data-ttu-id="9e1b3-117">ICorProfilerCallback インターフェイス</span><span class="sxs-lookup"><span data-stu-id="9e1b3-117">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [<span data-ttu-id="9e1b3-118">RuntimeSuspendAborted メソッド</span><span class="sxs-lookup"><span data-stu-id="9e1b3-118">RuntimeSuspendAborted Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimesuspendaborted-method.md)
