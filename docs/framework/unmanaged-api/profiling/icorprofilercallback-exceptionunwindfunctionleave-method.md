---
title: ICorProfilerCallback::ExceptionUnwindFunctionLeave メソッド
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.ExceptionUnwindFunctionLeave
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::ExceptionUnwindFunctionLeave
helpviewer_keywords:
- ICorProfilerCallback::ExceptionUnwindFunctionLeave method [.NET Framework profiling]
- ExceptionUnwindFunctionLeave method [.NET Framework profiling]
ms.assetid: ebaad1d5-ee0a-4cb0-96bc-8ba5d371b747
topic_type:
- apiref
ms.openlocfilehash: 8694a2d19c3b98487b86da4273eb0c68fb9d9ace
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/08/2020
ms.locfileid: "84500118"
---
# <a name="icorprofilercallbackexceptionunwindfunctionleave-method"></a><span data-ttu-id="d8f33-102">ICorProfilerCallback::ExceptionUnwindFunctionLeave メソッド</span><span class="sxs-lookup"><span data-stu-id="d8f33-102">ICorProfilerCallback::ExceptionUnwindFunctionLeave Method</span></span>
<span data-ttu-id="d8f33-103">例外処理のアンワインドフェーズが関数のアンワインドを完了したことをプロファイラーに通知します。</span><span class="sxs-lookup"><span data-stu-id="d8f33-103">Notifies the profiler that the unwind phase of exception handling has finished unwinding a function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d8f33-104">構文</span><span class="sxs-lookup"><span data-stu-id="d8f33-104">Syntax</span></span>  
  
```cpp  
HRESULT ExceptionUnwindFunctionLeave();  
```  
  
## <a name="remarks"></a><span data-ttu-id="d8f33-105">解説</span><span class="sxs-lookup"><span data-stu-id="d8f33-105">Remarks</span></span>  
 <span data-ttu-id="d8f33-106">`ExceptionUnwindFunctionLeave`メソッドが呼び出されると、関数インスタンスとそのスタックデータがスタックから削除されます。</span><span class="sxs-lookup"><span data-stu-id="d8f33-106">When the `ExceptionUnwindFunctionLeave` method is called, the function instance and its stack data are removed from the stack.</span></span>  
  
 <span data-ttu-id="d8f33-107">スタックがガベージコレクションを許可する状態ではなく、したがって、プリエンプティブガベージコレクションを有効にできないため、この呼び出し中にプロファイラーはブロックしないでください。</span><span class="sxs-lookup"><span data-stu-id="d8f33-107">The profiler should not block during this call because the stack may not be in a state that allows garbage collection, and therefore preemptive garbage collection cannot be enabled.</span></span> <span data-ttu-id="d8f33-108">プロファイラーがここでブロックし、ガベージコレクションを実行しようとすると、このコールバックが戻るまでランタイムはブロックします。</span><span class="sxs-lookup"><span data-stu-id="d8f33-108">If the profiler blocks here and a garbage collection is attempted, the runtime will block until this callback returns.</span></span>  
  
 <span data-ttu-id="d8f33-109">また、この呼び出しでは、プロファイラーはマネージコードを呼び出さないようにするか、マネージメモリ割り当てを発生させることはできません。</span><span class="sxs-lookup"><span data-stu-id="d8f33-109">Also, during this call, the profiler must not call into managed code or in any way cause a managed-memory allocation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d8f33-110">要件</span><span class="sxs-lookup"><span data-stu-id="d8f33-110">Requirements</span></span>  
 <span data-ttu-id="d8f33-111">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d8f33-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d8f33-112">**ヘッダー** : CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="d8f33-112">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="d8f33-113">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d8f33-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d8f33-114">**.NET Framework のバージョン:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d8f33-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d8f33-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="d8f33-115">See also</span></span>

- [<span data-ttu-id="d8f33-116">ICorProfilerCallback インターフェイス</span><span class="sxs-lookup"><span data-stu-id="d8f33-116">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
- [<span data-ttu-id="d8f33-117">ExceptionUnwindFunctionEnter メソッド</span><span class="sxs-lookup"><span data-stu-id="d8f33-117">ExceptionUnwindFunctionEnter Method</span></span>](icorprofilercallback-exceptionunwindfunctionenter-method.md)
