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
ms.openlocfilehash: 3b25ae535bfe50d216ca64a2e8163c0e6df58535
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67755963"
---
# <a name="icorprofilercallbackexceptionunwindfinallyenter-method"></a><span data-ttu-id="1ed88-102">ICorProfilerCallback::ExceptionUnwindFinallyEnter メソッド</span><span class="sxs-lookup"><span data-stu-id="1ed88-102">ICorProfilerCallback::ExceptionUnwindFinallyEnter Method</span></span>
<span data-ttu-id="1ed88-103">例外のアンワインド フェーズの処理が入ることをプロファイラーに通知を`finally`句が指定された関数に含まれています。</span><span class="sxs-lookup"><span data-stu-id="1ed88-103">Notifies the profiler that the unwind phase of exception handling is entering a `finally` clause contained in the specified function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1ed88-104">構文</span><span class="sxs-lookup"><span data-stu-id="1ed88-104">Syntax</span></span>  
  
```cpp  
HRESULT ExceptionUnwindFinallyEnter(  
    [in] FunctionID functionId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1ed88-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="1ed88-105">Parameters</span></span>  
 `functionId`  
 <span data-ttu-id="1ed88-106">[in]含む関数の ID、`finally`句。</span><span class="sxs-lookup"><span data-stu-id="1ed88-106">[in] The ID of the function that contains the `finally` clause.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="1ed88-107">Remarks</span><span class="sxs-lookup"><span data-stu-id="1ed88-107">Remarks</span></span>  
 <span data-ttu-id="1ed88-108">プロファイラーでは、スタックはガベージ コレクションを許可する状態にできない可能性がありますので、このメソッドの実装でブロックしないでくださいし、そのため、プリエンプティブなガベージ コレクションを有効にできません。</span><span class="sxs-lookup"><span data-stu-id="1ed88-108">The profiler should not block in its implementation of this method because the stack may not be in a state that allows garbage collection, and therefore preemptive garbage collection cannot be enabled.</span></span> <span data-ttu-id="1ed88-109">ここで、プロファイラーをブロックする場合とは、ガベージ コレクションが試行されると、ランタイムがこのコールバックが戻るまでブロックされます。</span><span class="sxs-lookup"><span data-stu-id="1ed88-109">If the profiler blocks here and garbage collection is attempted, the runtime will block until this callback returns.</span></span>  
  
 <span data-ttu-id="1ed88-110">このメソッドのプロファイラーの実装には、任意の方法で管理されているメモリの割り当てが発生またはマネージ コードを呼び出さないでください。</span><span class="sxs-lookup"><span data-stu-id="1ed88-110">The profiler's implementation of this method should not call into managed code or in any way cause a managed-memory allocation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1ed88-111">必要条件</span><span class="sxs-lookup"><span data-stu-id="1ed88-111">Requirements</span></span>  
 <span data-ttu-id="1ed88-112">**プラットフォーム:** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="1ed88-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1ed88-113">**ヘッダー:** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="1ed88-113">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="1ed88-114">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1ed88-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="1ed88-115">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1ed88-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1ed88-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="1ed88-116">See also</span></span>

- [<span data-ttu-id="1ed88-117">ICorProfilerCallback インターフェイス</span><span class="sxs-lookup"><span data-stu-id="1ed88-117">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [<span data-ttu-id="1ed88-118">GetNotifiedExceptionClauseInfo メソッド</span><span class="sxs-lookup"><span data-stu-id="1ed88-118">GetNotifiedExceptionClauseInfo Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getnotifiedexceptionclauseinfo-method.md)
- [<span data-ttu-id="1ed88-119">ExceptionUnwindFinallyLeave メソッド</span><span class="sxs-lookup"><span data-stu-id="1ed88-119">ExceptionUnwindFinallyLeave Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionunwindfinallyleave-method.md)
