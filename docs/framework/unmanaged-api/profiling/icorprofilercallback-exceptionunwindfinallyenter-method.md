---
title: ICorProfilerCallback::ExceptionUnwindFinallyEnter メソッド
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.ExceptionUnwindFinallyEnter
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::ExceptionUnwindFinallyEnter
helpviewer_keywords:
- ICorProfilerCallback::ExceptionUnwindFinallyEnter method [.NET Framework profiling]
- ExceptionUnwindFinallyEnter method [.NET Framework profiling]
ms.assetid: c7fab986-b69f-4ec8-b7b7-91dcfc239cd0
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: aebfc0d763fa1ea14c55a0c61fbf63db65fefe02
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59137866"
---
# <a name="icorprofilercallbackexceptionunwindfinallyenter-method"></a><span data-ttu-id="62544-102">ICorProfilerCallback::ExceptionUnwindFinallyEnter メソッド</span><span class="sxs-lookup"><span data-stu-id="62544-102">ICorProfilerCallback::ExceptionUnwindFinallyEnter Method</span></span>
<span data-ttu-id="62544-103">例外のアンワインド フェーズの処理が入ることをプロファイラーに通知を`finally`句が指定された関数に含まれています。</span><span class="sxs-lookup"><span data-stu-id="62544-103">Notifies the profiler that the unwind phase of exception handling is entering a `finally` clause contained in the specified function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="62544-104">構文</span><span class="sxs-lookup"><span data-stu-id="62544-104">Syntax</span></span>  
  
```  
HRESULT ExceptionUnwindFinallyEnter(  
    [in] FunctionID functionId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="62544-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="62544-105">Parameters</span></span>  
 `functionId`  
 <span data-ttu-id="62544-106">[in]含む関数の ID、`finally`句。</span><span class="sxs-lookup"><span data-stu-id="62544-106">[in] The ID of the function that contains the `finally` clause.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="62544-107">Remarks</span><span class="sxs-lookup"><span data-stu-id="62544-107">Remarks</span></span>  
 <span data-ttu-id="62544-108">プロファイラーでは、スタックはガベージ コレクションを許可する状態にできない可能性がありますので、このメソッドの実装でブロックしないでくださいし、そのため、プリエンプティブなガベージ コレクションを有効にできません。</span><span class="sxs-lookup"><span data-stu-id="62544-108">The profiler should not block in its implementation of this method because the stack may not be in a state that allows garbage collection, and therefore preemptive garbage collection cannot be enabled.</span></span> <span data-ttu-id="62544-109">ここで、プロファイラーをブロックする場合とは、ガベージ コレクションが試行されると、ランタイムがこのコールバックが戻るまでブロックされます。</span><span class="sxs-lookup"><span data-stu-id="62544-109">If the profiler blocks here and garbage collection is attempted, the runtime will block until this callback returns.</span></span>  
  
 <span data-ttu-id="62544-110">このメソッドのプロファイラーの実装には、任意の方法で管理されているメモリの割り当てが発生またはマネージ コードを呼び出さないでください。</span><span class="sxs-lookup"><span data-stu-id="62544-110">The profiler's implementation of this method should not call into managed code or in any way cause a managed-memory allocation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="62544-111">必要条件</span><span class="sxs-lookup"><span data-stu-id="62544-111">Requirements</span></span>  
 <span data-ttu-id="62544-112">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="62544-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="62544-113">**ヘッダー:** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="62544-113">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="62544-114">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="62544-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="62544-115">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="62544-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="62544-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="62544-116">See also</span></span>

- [<span data-ttu-id="62544-117">ICorProfilerCallback インターフェイス</span><span class="sxs-lookup"><span data-stu-id="62544-117">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [<span data-ttu-id="62544-118">GetNotifiedExceptionClauseInfo メソッド</span><span class="sxs-lookup"><span data-stu-id="62544-118">GetNotifiedExceptionClauseInfo Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getnotifiedexceptionclauseinfo-method.md)
- [<span data-ttu-id="62544-119">ExceptionUnwindFinallyLeave メソッド</span><span class="sxs-lookup"><span data-stu-id="62544-119">ExceptionUnwindFinallyLeave Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionunwindfinallyleave-method.md)
