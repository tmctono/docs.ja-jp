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
ms.openlocfilehash: cff2dd9fdb05ea4dd160dfa57df6f047beb57f69
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/08/2020
ms.locfileid: "84500300"
---
# <a name="icorprofilercallbackexceptioncatcherleave-method"></a><span data-ttu-id="76269-102">ICorProfilerCallback::ExceptionCatcherLeave メソッド</span><span class="sxs-lookup"><span data-stu-id="76269-102">ICorProfilerCallback::ExceptionCatcherLeave Method</span></span>
<span data-ttu-id="76269-103">適切なブロックから制御が渡されていることをプロファイラーに通知し `catch` ます。</span><span class="sxs-lookup"><span data-stu-id="76269-103">Notifies the profiler that control is being passed out of the appropriate `catch` block.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="76269-104">構文</span><span class="sxs-lookup"><span data-stu-id="76269-104">Syntax</span></span>  
  
```cpp  
HRESULT ExceptionCatcherLeave();  
```  
  
## <a name="remarks"></a><span data-ttu-id="76269-105">解説</span><span class="sxs-lookup"><span data-stu-id="76269-105">Remarks</span></span>  
 <span data-ttu-id="76269-106">プロファイラーは、このメソッドの実装でブロックしないでください。スタックがガベージコレクションを許可する状態にならないため、プリエンプティブガベージコレクションを有効にすることはできません。</span><span class="sxs-lookup"><span data-stu-id="76269-106">The profiler should not block in its implementation of this method because the stack may not be in a state that allows garbage collection, and therefore preemptive garbage collection cannot be enabled.</span></span> <span data-ttu-id="76269-107">プロファイラーがここでブロックし、ガベージコレクションを実行しようとすると、このコールバックが戻るまでランタイムはブロックします。</span><span class="sxs-lookup"><span data-stu-id="76269-107">If the profiler blocks here and garbage collection is attempted, the runtime will block until this callback returns.</span></span>  
  
 <span data-ttu-id="76269-108">プロファイラーによるこのメソッドの実装では、マネージコードを呼び出さないようにするか、マネージメモリ割り当てを発生させることはできません。</span><span class="sxs-lookup"><span data-stu-id="76269-108">The profiler's implementation of this method should not call into managed code or in any way cause a managed-memory allocation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="76269-109">要件</span><span class="sxs-lookup"><span data-stu-id="76269-109">Requirements</span></span>  
 <span data-ttu-id="76269-110">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="76269-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="76269-111">**ヘッダー** : CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="76269-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="76269-112">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="76269-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="76269-113">**.NET Framework のバージョン:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="76269-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="76269-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="76269-114">See also</span></span>

- [<span data-ttu-id="76269-115">ICorProfilerCallback インターフェイス</span><span class="sxs-lookup"><span data-stu-id="76269-115">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
- [<span data-ttu-id="76269-116">ExceptionCatcherEnter メソッド</span><span class="sxs-lookup"><span data-stu-id="76269-116">ExceptionCatcherEnter Method</span></span>](icorprofilercallback-exceptioncatcherenter-method.md)
