---
title: ICorProfilerCallback::ExceptionCatcherLeave メソッド
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.ExceptionCatcherLeave
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::ExceptionCatcherLeave
helpviewer_keywords:
- ExceptionCatcherLeave method [.NET Framework profiling]
- ICorProfilerCallback::ExceptionCatcherLeave method [.NET Framework profiling]
ms.assetid: 1f3dbdf5-db0c-4b07-bbb7-375de2a63673
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: f7f1b2756dd180cb0a701429978a34ea80447a86
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59107641"
---
# <a name="icorprofilercallbackexceptioncatcherleave-method"></a><span data-ttu-id="7db72-102">ICorProfilerCallback::ExceptionCatcherLeave メソッド</span><span class="sxs-lookup"><span data-stu-id="7db72-102">ICorProfilerCallback::ExceptionCatcherLeave Method</span></span>
<span data-ttu-id="7db72-103">コントロールが、適切なから渡されることをプロファイラーに通知`catch`ブロックします。</span><span class="sxs-lookup"><span data-stu-id="7db72-103">Notifies the profiler that control is being passed out of the appropriate `catch` block.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7db72-104">構文</span><span class="sxs-lookup"><span data-stu-id="7db72-104">Syntax</span></span>  
  
```  
HRESULT ExceptionCatcherLeave();  
```  
  
## <a name="remarks"></a><span data-ttu-id="7db72-105">Remarks</span><span class="sxs-lookup"><span data-stu-id="7db72-105">Remarks</span></span>  
 <span data-ttu-id="7db72-106">プロファイラーでは、スタックはガベージ コレクションを許可する状態にできない可能性がありますので、このメソッドの実装でブロックしないでくださいし、そのため、プリエンプティブなガベージ コレクションを有効にできません。</span><span class="sxs-lookup"><span data-stu-id="7db72-106">The profiler should not block in its implementation of this method because the stack may not be in a state that allows garbage collection, and therefore preemptive garbage collection cannot be enabled.</span></span> <span data-ttu-id="7db72-107">ここで、プロファイラーをブロックする場合とは、ガベージ コレクションが試行されると、ランタイムがこのコールバックが戻るまでブロックされます。</span><span class="sxs-lookup"><span data-stu-id="7db72-107">If the profiler blocks here and garbage collection is attempted, the runtime will block until this callback returns.</span></span>  
  
 <span data-ttu-id="7db72-108">このメソッドのプロファイラーの実装には、任意の方法で管理されているメモリの割り当てが発生またはマネージ コードを呼び出さないでください。</span><span class="sxs-lookup"><span data-stu-id="7db72-108">The profiler's implementation of this method should not call into managed code or in any way cause a managed-memory allocation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7db72-109">必要条件</span><span class="sxs-lookup"><span data-stu-id="7db72-109">Requirements</span></span>  
 <span data-ttu-id="7db72-110">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="7db72-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7db72-111">**ヘッダー:** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="7db72-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="7db72-112">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7db72-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7db72-113">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7db72-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7db72-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="7db72-114">See also</span></span>

- [<span data-ttu-id="7db72-115">ICorProfilerCallback インターフェイス</span><span class="sxs-lookup"><span data-stu-id="7db72-115">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [<span data-ttu-id="7db72-116">ExceptionCatcherEnter メソッド</span><span class="sxs-lookup"><span data-stu-id="7db72-116">ExceptionCatcherEnter Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptioncatcherenter-method.md)
