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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 556048be66a7c60dd82a8d51391a86655db6802a
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67755932"
---
# <a name="icorprofilercallbackexceptionunwindfunctionleave-method"></a><span data-ttu-id="f4d89-102">ICorProfilerCallback::ExceptionUnwindFunctionLeave メソッド</span><span class="sxs-lookup"><span data-stu-id="f4d89-102">ICorProfilerCallback::ExceptionUnwindFunctionLeave Method</span></span>
<span data-ttu-id="f4d89-103">例外処理のアンワインド フェーズの関数のアンワインドが完了したことをプロファイラーに通知します。</span><span class="sxs-lookup"><span data-stu-id="f4d89-103">Notifies the profiler that the unwind phase of exception handling has finished unwinding a function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f4d89-104">構文</span><span class="sxs-lookup"><span data-stu-id="f4d89-104">Syntax</span></span>  
  
```cpp  
HRESULT ExceptionUnwindFunctionLeave();  
```  
  
## <a name="remarks"></a><span data-ttu-id="f4d89-105">Remarks</span><span class="sxs-lookup"><span data-stu-id="f4d89-105">Remarks</span></span>  
 <span data-ttu-id="f4d89-106">ときに、`ExceptionUnwindFunctionLeave`メソッドが呼び出されると、関数のインスタンスとその履歴データは、スタックから削除されます。</span><span class="sxs-lookup"><span data-stu-id="f4d89-106">When the `ExceptionUnwindFunctionLeave` method is called, the function instance and its stack data are removed from the stack.</span></span>  
  
 <span data-ttu-id="f4d89-107">プロファイラーでは、スタックはガベージ コレクションを許可する状態にできない可能性がありますので、この呼び出し中にブロックしないでくださいし、そのため、プリエンプティブなガベージ コレクションを有効にできません。</span><span class="sxs-lookup"><span data-stu-id="f4d89-107">The profiler should not block during this call because the stack may not be in a state that allows garbage collection, and therefore preemptive garbage collection cannot be enabled.</span></span> <span data-ttu-id="f4d89-108">ここで、プロファイラー ブロックされ、ガベージ コレクションが試行されると、ランタイムがこのコールバックが戻るまでブロックされます。</span><span class="sxs-lookup"><span data-stu-id="f4d89-108">If the profiler blocks here and a garbage collection is attempted, the runtime will block until this callback returns.</span></span>  
  
 <span data-ttu-id="f4d89-109">また、この呼び出し中にプロファイラー呼び出す必要がありますいないにマネージ コードまたは任意の方法で管理されているメモリの割り当てが発生します。</span><span class="sxs-lookup"><span data-stu-id="f4d89-109">Also, during this call, the profiler must not call into managed code or in any way cause a managed-memory allocation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f4d89-110">必要条件</span><span class="sxs-lookup"><span data-stu-id="f4d89-110">Requirements</span></span>  
 <span data-ttu-id="f4d89-111">**プラットフォーム:** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="f4d89-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f4d89-112">**ヘッダー:** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="f4d89-112">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="f4d89-113">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f4d89-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f4d89-114">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f4d89-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f4d89-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="f4d89-115">See also</span></span>

- [<span data-ttu-id="f4d89-116">ICorProfilerCallback インターフェイス</span><span class="sxs-lookup"><span data-stu-id="f4d89-116">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [<span data-ttu-id="f4d89-117">ExceptionUnwindFunctionEnter メソッド</span><span class="sxs-lookup"><span data-stu-id="f4d89-117">ExceptionUnwindFunctionEnter Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionunwindfunctionenter-method.md)
