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
ms.openlocfilehash: 6b7aa7c60b5e861787d7a115d90a00d67cc48db0
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/29/2020
ms.locfileid: "76866534"
---
# <a name="icorprofilercallbackexceptioncatcherleave-method"></a><span data-ttu-id="fbe5b-102">ICorProfilerCallback::ExceptionCatcherLeave メソッド</span><span class="sxs-lookup"><span data-stu-id="fbe5b-102">ICorProfilerCallback::ExceptionCatcherLeave Method</span></span>
<span data-ttu-id="fbe5b-103">適切な `catch` ブロックから制御が渡されていることをプロファイラーに通知します。</span><span class="sxs-lookup"><span data-stu-id="fbe5b-103">Notifies the profiler that control is being passed out of the appropriate `catch` block.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fbe5b-104">構文</span><span class="sxs-lookup"><span data-stu-id="fbe5b-104">Syntax</span></span>  
  
```cpp  
HRESULT ExceptionCatcherLeave();  
```  
  
## <a name="remarks"></a><span data-ttu-id="fbe5b-105">Remarks</span><span class="sxs-lookup"><span data-stu-id="fbe5b-105">Remarks</span></span>  
 <span data-ttu-id="fbe5b-106">プロファイラーは、このメソッドの実装でブロックしないでください。スタックがガベージコレクションを許可する状態にならないため、プリエンプティブガベージコレクションを有効にすることはできません。</span><span class="sxs-lookup"><span data-stu-id="fbe5b-106">The profiler should not block in its implementation of this method because the stack may not be in a state that allows garbage collection, and therefore preemptive garbage collection cannot be enabled.</span></span> <span data-ttu-id="fbe5b-107">プロファイラーがここでブロックし、ガベージコレクションを実行しようとすると、このコールバックが戻るまでランタイムはブロックします。</span><span class="sxs-lookup"><span data-stu-id="fbe5b-107">If the profiler blocks here and garbage collection is attempted, the runtime will block until this callback returns.</span></span>  
  
 <span data-ttu-id="fbe5b-108">プロファイラーによるこのメソッドの実装では、マネージコードを呼び出さないようにするか、マネージメモリ割り当てを発生させることはできません。</span><span class="sxs-lookup"><span data-stu-id="fbe5b-108">The profiler's implementation of this method should not call into managed code or in any way cause a managed-memory allocation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fbe5b-109">要件</span><span class="sxs-lookup"><span data-stu-id="fbe5b-109">Requirements</span></span>  
 <span data-ttu-id="fbe5b-110">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fbe5b-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fbe5b-111">**ヘッダー** : CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="fbe5b-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="fbe5b-112">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="fbe5b-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="fbe5b-113">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fbe5b-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fbe5b-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="fbe5b-114">See also</span></span>

- [<span data-ttu-id="fbe5b-115">ICorProfilerCallback インターフェイス</span><span class="sxs-lookup"><span data-stu-id="fbe5b-115">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
- [<span data-ttu-id="fbe5b-116">ExceptionCatcherEnter メソッド</span><span class="sxs-lookup"><span data-stu-id="fbe5b-116">ExceptionCatcherEnter Method</span></span>](icorprofilercallback-exceptioncatcherenter-method.md)
