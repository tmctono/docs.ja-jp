---
title: ICorProfilerCallback::ExceptionUnwindFinallyLeave メソッド
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.ExceptionUnwindFinallyLeave
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::ExceptionUnwindFinallyLeave
helpviewer_keywords:
- ICorProfilerCallback::ExceptionUnwindFinallyLeave method [.NET Framework profiling]
- ExceptionUnwindFinallyLeave method [.NET Framework profiling]
ms.assetid: 2350351e-f253-4c0c-a191-f952bc5700e6
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 7ba62ab2c4df73b570fb1c76adaee44a2a2ce8c3
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61597155"
---
# <a name="icorprofilercallbackexceptionunwindfinallyleave-method"></a><span data-ttu-id="282f2-102">ICorProfilerCallback::ExceptionUnwindFinallyLeave メソッド</span><span class="sxs-lookup"><span data-stu-id="282f2-102">ICorProfilerCallback::ExceptionUnwindFinallyLeave Method</span></span>
<span data-ttu-id="282f2-103">例外のアンワインド フェーズの処理が残っているプロファイラーに通知を`finally`句。</span><span class="sxs-lookup"><span data-stu-id="282f2-103">Notifies the profiler that the unwind phase of exception handling has left a `finally` clause.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="282f2-104">構文</span><span class="sxs-lookup"><span data-stu-id="282f2-104">Syntax</span></span>  
  
```  
HRESULT ExceptionUnwindFinallyLeave();  
```  
  
## <a name="remarks"></a><span data-ttu-id="282f2-105">Remarks</span><span class="sxs-lookup"><span data-stu-id="282f2-105">Remarks</span></span>  
 <span data-ttu-id="282f2-106">プロファイラーでは、スタックはガベージ コレクションを許可する状態にできない可能性がありますので、この呼び出し中にブロックしないでくださいし、そのため、プリエンプティブなガベージ コレクションを有効にできません。</span><span class="sxs-lookup"><span data-stu-id="282f2-106">The profiler should not block during this call because the stack may not be in a state that allows garbage collection, and therefore preemptive garbage collection cannot be enabled.</span></span> <span data-ttu-id="282f2-107">ここで、プロファイラー ブロックされ、ガベージ コレクションが試行されると、ランタイムがこのコールバックが戻るまでブロックされます。</span><span class="sxs-lookup"><span data-stu-id="282f2-107">If the profiler blocks here and a garbage collection is attempted, the runtime will block until this callback returns.</span></span>  
  
 <span data-ttu-id="282f2-108">また、この呼び出し中にプロファイラー呼び出す必要がありますいないにマネージ コードまたは任意の方法で管理されているメモリの割り当てが発生します。</span><span class="sxs-lookup"><span data-stu-id="282f2-108">Also, during this call, the profiler must not call into managed code or in any way cause a managed-memory allocation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="282f2-109">必要条件</span><span class="sxs-lookup"><span data-stu-id="282f2-109">Requirements</span></span>  
 <span data-ttu-id="282f2-110">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="282f2-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="282f2-111">**ヘッダー:** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="282f2-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="282f2-112">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="282f2-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="282f2-113">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="282f2-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="282f2-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="282f2-114">See also</span></span>

- [<span data-ttu-id="282f2-115">ICorProfilerCallback インターフェイス</span><span class="sxs-lookup"><span data-stu-id="282f2-115">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [<span data-ttu-id="282f2-116">ExceptionUnwindFinallyEnter メソッド</span><span class="sxs-lookup"><span data-stu-id="282f2-116">ExceptionUnwindFinallyEnter Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionunwindfinallyenter-method.md)
