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
ms.openlocfilehash: f5e4939c814239c297fc0aa88644dc0472b0c419
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/08/2020
ms.locfileid: "84500157"
---
# <a name="icorprofilercallbackexceptionunwindfinallyenter-method"></a><span data-ttu-id="9c118-102">ICorProfilerCallback::ExceptionUnwindFinallyEnter メソッド</span><span class="sxs-lookup"><span data-stu-id="9c118-102">ICorProfilerCallback::ExceptionUnwindFinallyEnter Method</span></span>
<span data-ttu-id="9c118-103">例外処理のアンワインドフェーズが、指定された `finally` 関数に含まれる句を入力していることをプロファイラーに通知します。</span><span class="sxs-lookup"><span data-stu-id="9c118-103">Notifies the profiler that the unwind phase of exception handling is entering a `finally` clause contained in the specified function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9c118-104">構文</span><span class="sxs-lookup"><span data-stu-id="9c118-104">Syntax</span></span>  
  
```cpp  
HRESULT ExceptionUnwindFinallyEnter(  
    [in] FunctionID functionId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9c118-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="9c118-105">Parameters</span></span>

- `functionId`

  <span data-ttu-id="9c118-106">\[in] 句を含む関数の ID `finally` 。</span><span class="sxs-lookup"><span data-stu-id="9c118-106">\[in] The ID of the function that contains the `finally` clause.</span></span>

## <a name="remarks"></a><span data-ttu-id="9c118-107">解説</span><span class="sxs-lookup"><span data-stu-id="9c118-107">Remarks</span></span>  
 <span data-ttu-id="9c118-108">プロファイラーは、このメソッドの実装でブロックしないでください。スタックがガベージコレクションを許可する状態にならないため、プリエンプティブガベージコレクションを有効にすることはできません。</span><span class="sxs-lookup"><span data-stu-id="9c118-108">The profiler should not block in its implementation of this method because the stack may not be in a state that allows garbage collection, and therefore preemptive garbage collection cannot be enabled.</span></span> <span data-ttu-id="9c118-109">プロファイラーがここでブロックし、ガベージコレクションを実行しようとすると、このコールバックが戻るまでランタイムはブロックします。</span><span class="sxs-lookup"><span data-stu-id="9c118-109">If the profiler blocks here and garbage collection is attempted, the runtime will block until this callback returns.</span></span>  
  
 <span data-ttu-id="9c118-110">プロファイラーによるこのメソッドの実装では、マネージコードを呼び出さないようにするか、マネージメモリ割り当てを発生させることはできません。</span><span class="sxs-lookup"><span data-stu-id="9c118-110">The profiler's implementation of this method should not call into managed code or in any way cause a managed-memory allocation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9c118-111">要件</span><span class="sxs-lookup"><span data-stu-id="9c118-111">Requirements</span></span>  
 <span data-ttu-id="9c118-112">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9c118-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9c118-113">**ヘッダー** : CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="9c118-113">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="9c118-114">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9c118-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9c118-115">**.NET Framework のバージョン:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9c118-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9c118-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="9c118-116">See also</span></span>

- [<span data-ttu-id="9c118-117">ICorProfilerCallback インターフェイス</span><span class="sxs-lookup"><span data-stu-id="9c118-117">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
- [<span data-ttu-id="9c118-118">GetNotifiedExceptionClauseInfo メソッド</span><span class="sxs-lookup"><span data-stu-id="9c118-118">GetNotifiedExceptionClauseInfo Method</span></span>](icorprofilerinfo2-getnotifiedexceptionclauseinfo-method.md)
- [<span data-ttu-id="9c118-119">ExceptionUnwindFinallyLeave メソッド</span><span class="sxs-lookup"><span data-stu-id="9c118-119">ExceptionUnwindFinallyLeave Method</span></span>](icorprofilercallback-exceptionunwindfinallyleave-method.md)
