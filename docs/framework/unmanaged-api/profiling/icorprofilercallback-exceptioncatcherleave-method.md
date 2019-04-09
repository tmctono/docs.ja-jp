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
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2019
ms.locfileid: "59107641"
---
# <a name="icorprofilercallbackexceptioncatcherleave-method"></a><span data-ttu-id="82d6c-102">ICorProfilerCallback::ExceptionCatcherLeave メソッド</span><span class="sxs-lookup"><span data-stu-id="82d6c-102">ICorProfilerCallback::ExceptionCatcherLeave Method</span></span>
<span data-ttu-id="82d6c-103">コントロールが、適切なから渡されることをプロファイラーに通知`catch`ブロックします。</span><span class="sxs-lookup"><span data-stu-id="82d6c-103">Notifies the profiler that control is being passed out of the appropriate `catch` block.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="82d6c-104">構文</span><span class="sxs-lookup"><span data-stu-id="82d6c-104">Syntax</span></span>  
  
```  
HRESULT ExceptionCatcherLeave();  
```  
  
## <a name="remarks"></a><span data-ttu-id="82d6c-105">Remarks</span><span class="sxs-lookup"><span data-stu-id="82d6c-105">Remarks</span></span>  
 <span data-ttu-id="82d6c-106">プロファイラーでは、スタックはガベージ コレクションを許可する状態にできない可能性がありますので、このメソッドの実装でブロックしないでくださいし、そのため、プリエンプティブなガベージ コレクションを有効にできません。</span><span class="sxs-lookup"><span data-stu-id="82d6c-106">The profiler should not block in its implementation of this method because the stack may not be in a state that allows garbage collection, and therefore preemptive garbage collection cannot be enabled.</span></span> <span data-ttu-id="82d6c-107">ここで、プロファイラーをブロックする場合とは、ガベージ コレクションが試行されると、ランタイムがこのコールバックが戻るまでブロックされます。</span><span class="sxs-lookup"><span data-stu-id="82d6c-107">If the profiler blocks here and garbage collection is attempted, the runtime will block until this callback returns.</span></span>  
  
 <span data-ttu-id="82d6c-108">このメソッドのプロファイラーの実装には、任意の方法で管理されているメモリの割り当てが発生またはマネージ コードを呼び出さないでください。</span><span class="sxs-lookup"><span data-stu-id="82d6c-108">The profiler's implementation of this method should not call into managed code or in any way cause a managed-memory allocation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="82d6c-109">必要条件</span><span class="sxs-lookup"><span data-stu-id="82d6c-109">Requirements</span></span>  
 <span data-ttu-id="82d6c-110">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="82d6c-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="82d6c-111">**ヘッダー:** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="82d6c-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="82d6c-112">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="82d6c-112">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="82d6c-113">.NET Framework のバージョン: </span><span class="sxs-lookup"><span data-stu-id="82d6c-113">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="82d6c-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="82d6c-114">See also</span></span>

- [<span data-ttu-id="82d6c-115">ICorProfilerCallback インターフェイス</span><span class="sxs-lookup"><span data-stu-id="82d6c-115">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [<span data-ttu-id="82d6c-116">ExceptionCatcherEnter メソッド</span><span class="sxs-lookup"><span data-stu-id="82d6c-116">ExceptionCatcherEnter Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptioncatcherenter-method.md)
