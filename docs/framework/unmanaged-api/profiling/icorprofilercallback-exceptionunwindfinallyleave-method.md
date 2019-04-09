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
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2019
ms.locfileid: "59117807"
---
# <a name="icorprofilercallbackexceptionunwindfinallyleave-method"></a><span data-ttu-id="bf4dd-102">ICorProfilerCallback::ExceptionUnwindFinallyLeave メソッド</span><span class="sxs-lookup"><span data-stu-id="bf4dd-102">ICorProfilerCallback::ExceptionUnwindFinallyLeave Method</span></span>
<span data-ttu-id="bf4dd-103">例外のアンワインド フェーズの処理が残っているプロファイラーに通知を`finally`句。</span><span class="sxs-lookup"><span data-stu-id="bf4dd-103">Notifies the profiler that the unwind phase of exception handling has left a `finally` clause.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bf4dd-104">構文</span><span class="sxs-lookup"><span data-stu-id="bf4dd-104">Syntax</span></span>  
  
```  
HRESULT ExceptionUnwindFinallyLeave();  
```  
  
## <a name="remarks"></a><span data-ttu-id="bf4dd-105">Remarks</span><span class="sxs-lookup"><span data-stu-id="bf4dd-105">Remarks</span></span>  
 <span data-ttu-id="bf4dd-106">プロファイラーでは、スタックはガベージ コレクションを許可する状態にできない可能性がありますので、この呼び出し中にブロックしないでくださいし、そのため、プリエンプティブなガベージ コレクションを有効にできません。</span><span class="sxs-lookup"><span data-stu-id="bf4dd-106">The profiler should not block during this call because the stack may not be in a state that allows garbage collection, and therefore preemptive garbage collection cannot be enabled.</span></span> <span data-ttu-id="bf4dd-107">ここで、プロファイラー ブロックされ、ガベージ コレクションが試行されると、ランタイムがこのコールバックが戻るまでブロックされます。</span><span class="sxs-lookup"><span data-stu-id="bf4dd-107">If the profiler blocks here and a garbage collection is attempted, the runtime will block until this callback returns.</span></span>  
  
 <span data-ttu-id="bf4dd-108">また、この呼び出し中にプロファイラー呼び出す必要がありますいないにマネージ コードまたは任意の方法で管理されているメモリの割り当てが発生します。</span><span class="sxs-lookup"><span data-stu-id="bf4dd-108">Also, during this call, the profiler must not call into managed code or in any way cause a managed-memory allocation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bf4dd-109">必要条件</span><span class="sxs-lookup"><span data-stu-id="bf4dd-109">Requirements</span></span>  
 <span data-ttu-id="bf4dd-110">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="bf4dd-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bf4dd-111">**ヘッダー:** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="bf4dd-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="bf4dd-112">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="bf4dd-112">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="bf4dd-113">.NET Framework のバージョン: </span><span class="sxs-lookup"><span data-stu-id="bf4dd-113">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="bf4dd-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="bf4dd-114">See also</span></span>

- [<span data-ttu-id="bf4dd-115">ICorProfilerCallback インターフェイス</span><span class="sxs-lookup"><span data-stu-id="bf4dd-115">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [<span data-ttu-id="bf4dd-116">ExceptionUnwindFinallyEnter メソッド</span><span class="sxs-lookup"><span data-stu-id="bf4dd-116">ExceptionUnwindFinallyEnter Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionunwindfinallyenter-method.md)
